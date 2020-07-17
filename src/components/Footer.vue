<template>
  <footer id="footer">
    <h2>Shortly</h2>
    <ul>
      <li><b>Features</b></li>
      <li>
        <a href="#">Link Shortening</a>
      </li>
      <li>
        <a href="#">Branded Links</a>
      </li>
      <li>
        <a href="#">Analytics</a>
      </li>
    </ul>
    <ul>
      <li><b>Resources</b></li>
      <li>
        <a href="#">Blog</a>
      </li>
      <li>
        <a href="#">Developers</a>
      </li>
      <li>
        <a href="#">Support</a>
      </li>
    </ul>
    <ul>
      <li><b>Company</b></li>
      <li>
        <a href="#">About</a>
      </li>
      <li>
        <a href="#">Our Team</a>
      </li>
      <li>
        <a href="#">Careers</a>
      </li>
      <li>
        <a href="#">Contact</a>
      </li>
    </ul>
    <div id="social-links">
      <a id="facebook-btn" href="#"></a>
      <a id="twitter-btn" href="#"></a>
      <a id="pinterest-btn" href="#"></a>
      <a id="instagram-btn" href="#"></a>
    </div>
  </footer>
</template>

<style>
#boost-cta {
  background-image: url("../assets/bg-boost-desktop.svg");
  background-size: cover;
  background-repeat: no-repeat;
  background-color: hsl(257, 27%, 26%);
  height: 125px;
  color: white;
}
#footer {
  background-color: hsl(260, 8%, 14%);
  display: flex;
  justify-content: space-evenly;
  align-items: flex-start;
  padding-top: 25px;
  height: 200px;
  color: hsl(0, 0%, 100%);
}
#footer li:first-of-type {
  margin-bottom: 15px;
}
#footer li {
  list-style: none;
}
#footer a {
  color: hsl(0, 0%, 75%);
  text-decoration: none;
}
#footer a:hover {
  color: white;
}
#social-links {
  display: flex;
}
#facebook-btn,
#twitter-btn,
#pinterest-btn,
#instagram-btn {
  height: 25px;
  width: 25px;
  background-color: white;
  background-repeat: no-repeat;
  mask-repeat: no-repeat;
  mask-position: center;
  margin: 0 15px;
  transition: background-color .1s ease-in-out;
}
#facebook-btn {
  -webkit-mask-image: url("../assets/icon-facebook.svg");
  mask-image: url("../assets/icon-facebook.svg");
}
#twitter-btn {
  -webkit-mask-image: url("../assets/icon-twitter.svg");
  mask-image: url("../assets/icon-twitter.svg");
}
#facebook-btn:hover, #twitter-btn:hover, #pinterest-btn:hover, #instagram-btn:hover {
  background-color: hsl(180, 66%, 49%);
}
#pinterest-btn {
  -webkit-mask-image: url("../assets/icon-pinterest.svg");
  mask-image: url("../assets/icon-pinterest.svg");
}
#instagram-btn {
  -webkit-mask-image: url("../assets/icon-instagram.svg");
  mask-image: url("../assets/icon-instagram.svg");
}
</style>
