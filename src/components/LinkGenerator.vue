<template>
  <div id="link-generator">
    <form id="link-form" @submit.prevent="submitURL()">
      <input
        v-model="urlInput"
        type="url"
        placeholder="Shorten a link here..."
      />
      <button id="url-submit-btn">Shorten It!</button>
    </form>
    <div id="link-list">
      <div class="saved-link" v-for="link in links" :key="link.hashid">
        <p>{{ link.url }}</p>
        <p>https://rel.ink/{{ link.hashid }}</p>
        <textarea
          :id="link.url"
          :value="'https://rel.ink/' + link.hashid"
        ></textarea>
        <button class="copy-btn" readonly @click="copyLink(link.url)">Copy Link</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      urlInput: null,
      links: [],
    };
  },
  mounted() {
    if (localStorage.getItem("links")) {
      try {
        this.links = JSON.parse(localStorage.getItem("links"));
        console.log("Loaded Links");
      } catch (e) {
        console.log("ERROR");
        console.log(e);
        localStorage.removeItem("links");
      }
    }
  },
  methods: {
    submitURL: function() {
      const postURL = "https://rel.ink/api/links/";

      const link = {
        url: this.urlInput,
      };

      const request = new Request(postURL, {
        method: "POST",
        body: JSON.stringify(link),
        headers: new Headers({
          "Content-Type": "application/JSON",
        }),
      });
      //console.log(request)
      //console.log(link)
      //console.log({"hashid": this.hashid,"url": this.url})
      fetch(request)
        .then((res) => res.json())
        //.then(res => console.log(res))
        .then(
          (res) => this.links.push({ hashid: res.hashid, url: res.url }),
          this.saveLinks()
        );
    },
    removeLink(x) {
      this.links.splice(x, 1);
      this.saveLinks();
    },
    saveLinks() {
      const parsed = JSON.stringify(this.links);
      localStorage.setItem("links", parsed);
      console.log("saved Links");
      console.log(localStorage.links);
    },
    copyLink(id) {
      let el = document.getElementById(id);
      //console.log(el.textContent);
      el.select();
      el.setSelectionRange(0, 99999);
      document.execCommand("copy");
      alert("Copied the text: " + el.value);
      //console.log(el);
    },
  },
};
</script>

<style>
#link-form {
  background-image: url("../assets/bg-shorten-desktop.svg");
  background-size: cover;
  background-repeat: no-repeat;
  background-color: hsl(257, 27%, 26%);
  height: 125px;
  display: flex;
  align-items: center;
  justify-content: space-around;
  border-radius: 10px;
}
.saved-link {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 100px;
}
#url-submit-btn {
  background-color: hsl(180, 66%, 49%);
  border: none;
  color: white;
  font-weight: 700;
  border-radius: 10px;
  font-size: 18px;
  padding: 15px 30px;
  flex-grow: 0.5;
  margin: 25px;
}
#link-form input {
  flex-grow: 3;
  margin: 45px;
  padding: 15px 0;
  border-radius: 10px;
  outline: none;
  border: none;
  padding-left: 15px;
}
input::placeholder,
input[type="url" i] {
  font-size: 16px;
}

.copy-btn {
  background-color: hsl(180, 66%, 49%);
  border: none;
  color: white;
  font-weight: 700;
  border-radius: 10px;
  font-size: 16px;
  padding: 10px 20px;
  margin: 25px;
}

.saved-link textarea {
  width: 1px;
  height: 1px;
  position: fixed;
  top: 0;
  left: 0;
  opacity: 0;
  border: none;
}

.saved-link p:last-of-type{
  color: hsl(180, 66%, 49%);
}

@media only screen and (max-width: 600px) {
  #link-form {
    flex-direction: column;
    height: 200px;
    justify-content: space-evenly;
    margin-bottom: 50px;
  }
  #link-form input {
    margin: 0;
    flex-grow: unset;
    width: 90%;
  }
  #link-form button {
    flex-grow: unset;
    margin: 0;
    width: 90%;
  }
  .saved-link {
    flex-direction: column;
    height: 150px;
    margin: 50px;
  }
  .copy-btn {
    margin: 0;
  }
}
</style>
