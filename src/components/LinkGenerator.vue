<template>
  <div id="link-generator">
    <form id="link-form" @submit.prevent="submitURL()">
      <input v-model="urlInput" type="url" placeholder="Shorten a link here..."/>
      <button id="url-submit-btn" >Shorten It!</button>
    </form>
    <div id="link-list">
      <div class="saved-link" v-for="link in links" :key="link.url">
        <p>{{ link.url }}</p>
        <p :id=link.url>https://rel.ink/{{ link.hashid }}</p>
        <button class="copy-btn" @click="copyLink(`https://rel.ink/` + link.hashid)">Copy Link</button>
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
    }
  },
  mounted(){
    if(localStorage.getItem('links')) {
      try {
        this.links = JSON.parse(localStorage.getItem('links'));
        console.log("Loaded Links");
      } catch(e) {
        console.log("ERROR");
        console.log(e);
        localStorage.removeItem('links');
      }
    }
  },
  methods: {
    submitURL: function() {
      const postURL = 'https://rel.ink/api/links/';

      const link = {
        url: this.urlInput
      }

      const request = new Request(postURL, {
        method: 'POST',
        body: JSON.stringify(link),
        headers: new Headers({
          'Content-Type': 'application/JSON'
        })
      });
      console.log(request)
      console.log(link)
      //console.log({"hashid": this.hashid,"url": this.url})
      //this.links.push({"url":"google.com","hashid":"RgeNko"})
      fetch(request)
        .then(res => res.json())
        //.then(res => console.log(res))
        .then(res =>
          this.links.push({"hashid": res.hashid,"url": res.url}),
          this.saveLinks()
        );
    },
    removeLink(x) {
      this.links.splice(x, 1);
      this.saveLinks();
    },
    saveLinks() {
      const parsed = JSON.stringify(this.links);
      localStorage.setItem('links', parsed)
      console.log("saved Links");
      console.log(localStorage.links)
    },
    copyLink(){
    }
  }
}
</script>

<style>
  #link-form {
    background-image: url('../assets/bg-shorten-desktop.svg');
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
    flex-grow: .5;
    margin: 25px;
  }
  #link-form input {
    flex-grow: 3;
    margin: 45px;
    padding: 15px 0;
    border-radius: 5px;
    outline: none;
    border: none;
    padding-left: 15px;
  }
  input::placeholder, input[type=url i] {
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
</style>