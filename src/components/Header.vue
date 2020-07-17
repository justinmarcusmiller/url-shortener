<template>
  <header id="header">
    <div id="header-left">
      <h2>Shortly</h2>
      <ul>
        <li>
          <a href="#">Features</a>
        </li>
        <li>
          <a href="#">Pricing</a>
        </li>
        <li>
          <a href="#">Resources</a>
        </li>
      </ul>
    </div>
    <div id="header-right">
      <button id="login-btn">Login</button>
      <button id="signUp-btn">Sign Up</button>
    </div>
  </header>
</template>

<style>
#header {
  display: flex;
  justify-content: space-between;
  margin: 25px;
}
#header-left {
  display: flex;
  align-items: center;
}

#header-left ul {
  display: flex;
  list-style: none;
  justify-content: space-evenly;
  width: 400px;
}

#header-left ul a {
  text-decoration: none;
  font-weight: 700;
  color: hsl(257, 7%, 63%);
}

#header-left ul a:hover {
  color: hsl(260, 8%, 14%);
}

#login-btn {
  border: none;
  font-size: 16px;
  font-weight: 700;
  margin-right: 15px;
  color: hsl(257, 7%, 63%);
}

#login-btn:hover {
  color: hsl(260, 8%, 14%);
}

#signUp-btn {
  background-color: hsl(180, 66%, 49%);
  border: none;
  color: white;
  font-weight: 700;
  border-radius: 10px;
  font-size: 16px;
  padding: 10px 20px;
}
</style>
