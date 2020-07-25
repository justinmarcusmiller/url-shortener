<template v-if="document.documentElement.clientWidth < 600px">
  <header id="header-mobile">
    <button id="header-toggle" @click="toggleMobileNav">
      <svg
        width="100%"
        height="100%"
        viewBox="0 0 16 16"
        class="bi bi-justify"
        fill="currentColor"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          fill-rule="evenodd"
          d="M2 12.5a.5.5 0 0 1 .5-.5h11a.5.5 0 0 1 0 1h-11a.5.5 0 0 1-.5-.5zm0-3a.5.5 0 0 1 .5-.5h11a.5.5 0 0 1 0 1h-11a.5.5 0 0 1-.5-.5zm0-3a.5.5 0 0 1 .5-.5h11a.5.5 0 0 1 0 1h-11a.5.5 0 0 1-.5-.5zm0-3a.5.5 0 0 1 .5-.5h11a.5.5 0 0 1 0 1h-11a.5.5 0 0 1-.5-.5z"
        />
      </svg>
    </button>
    <nav id="mobile-nav">
      <h2>Shortly</h2>
      <nav id="mobile-account-nav">
        <a href="#" class="mobile-links">Login</a>
        <a href="#" class="mobile-links">Sign Up</a>
      </nav>
      <hr />
      <nav id="mobile-link-nav">
        <ul>
          <li>
            <a class="mobile-links" href="#">Features</a>
          </li>
          <li>
            <a class="mobile-links" href="#">Pricing</a>
          </li>
          <li>
            <a class="mobile-links" href="#">Resources</a>
          </li>
        </ul>
      </nav>
      <hr />
    </nav>
  </header>
</template>

<script>
export default {
  methods: {
    toggleMobileNav() {
      console.log("test");
      var nav = document.getElementById("mobile-nav");
      nav.classList.toggle("flex");
      //nav.style.display = "flex";
      console.log(nav);
    },
  },
};
</script>

<style>
#header-mobile {
  display: none;
}

.flex {
  display: flex !important;
}

#mobile-nav {
  display: none;
  flex-direction: column;
  background-color: white;
  position: fixed;
  top: 0;
  z-index: 2;
  left: 0;
  width: 100%;
  height: 100vh;
  align-items: center;
}

#mobile-nav h2 {
  margin-top: 75px;
}

#header-toggle {
  z-index: 3;
  border: none;
  background: none;
  position: fixed;
  left: 0;
  top: 0;
  width: 50px;
  height: 50px;
  margin: 5px;
}

hr {
  border: 1px solid gray;
  width: 90%;
  height: 1px;
}

#mobile-account-nav {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;
  width: 100%;
  height: 150px;
}

#mobile-link-nav {
  width: 100%;
}

#mobile-link-nav ul {
  list-style-type: none;
  text-align: center;
  width: 100%;
  height: 300px;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}

.mobile-links {
  text-decoration: none;
  font-size: 24px;
  font-weight: 700;
  color: hsl(257, 7%, 63%);
}

.mobile-links:hover {
  color: hsl(260, 8%, 14%);
}

#login-btn-mobile {
  border: 1px solid hsl(180, 66%, 49%);
  font-size: 16px;
  border-radius: 10px;
  padding: 10px 25px;
  font-weight: 700;
  color: hsl(257, 7%, 63%);
}

#login-btn-mobile:hover {
  color: hsl(260, 8%, 14%);
  color: white;
  background-color: hsl(180, 66%, 49%);
}

#signUp-btn-mobile {
  background-color: hsl(180, 66%, 49%);
  border: none;
  color: white;
  font-weight: 700;
  border-radius: 10px;
  font-size: 16px;
  padding: 10px 20px;
}

@media only screen and (max-width: 600px) {
  #header-mobile {
    display: unset;
  }
}
</style>
