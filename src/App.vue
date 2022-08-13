<template>
  <header class="header">
    <div class="header-name-container">
      <router-link to="/">
        <img src='./assets/headerLogo.png' width="200" height="40" alt="logo">
      </router-link>
      <nav>
        <router-link to="/">Hem</router-link>
        <router-link to="/about">Om mig</router-link>
        <router-link to="/projects">Projekt</router-link>
        <router-link to="/contact">Kontakt</router-link>
      </nav>
    </div>
  </header>
  <router-view />
  <footer class="footer-container">
    <div class="footer-content">
      <div class="about">
        <h2>Om mig</h2>
        <p>Hej mitt namn är william 29 årig utvecklare från sverige</p>
      </div>
      <div class="links">
        <h2>Snabb länkar</h2>
        <router-link to="/">Hem</router-link>
        <router-link to="/about">Om mig</router-link>
        <router-link to="/projects">Projekt</router-link>
        <router-link to="/contact">Kontakt</router-link>
      </div>
      <div class="contact-details">
        <h2>Kontakta mig</h2>
        <p>William ali</p>
        <p>telefonnummer: 072-90 22 198</p>
        <p>Email: william.ali@hotmail.se</p>
      </div>
    </div>
  </footer>
</template>

<style>
html
{
  overflow-y: scroll;
}

#app
{
  font-family: monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: white;
  margin: 20px 350px;
}

body
{
  background: white;
}

nav
{
  display: flex;
  align-items: center;
  text-align: right;
  font-size: 18px;
}

nav a
{
  padding-left: 50px;
  color: black;
}

nav a.router-link-exact-active
{
  color: rgb(155, 106, 106)
}

.header
{
  box-shadow: 1px 1px 6px 1px black;
  padding: 5px;
}

.header-name-container
{
  display: flex;
  gap:250px;
}

.header-name-text
{
  margin: 0;
  font-weight: normal;
  font-family: monospace;
  font-size: x-large;
}

a
{
  text-decoration: none;
}

a:hover
{
  color: rgba(135, 206, 250, 0.7)
}

h1,
h2,
h3,
h4,
h5,
h6
{
  color: black;
}

.footer-container
{
  bottom: 0;
  width: 100%;
  margin-top: 10px;
  background: #f2f2f2;
  height: fit-content;
  color: black;
  border-radius: 5px;
  text-align: left;
  box-shadow: 1px 1px 4px 2px;
}

.footer-content
{
  display: flex;
  height: 100%;
  gap: 0.3em;
}

.about
{
  width: 40%;
  margin-left: 5px;
}

.about p
{
  font-size: 14px;
}

.links
{
  display: flex;
  flex-direction: column;
  row-gap: 10px;
  margin-bottom: 20px;
  width: 30%;
  padding-left: 20px;
}

.links a
{
  font-size: 16px;
}

.contact-details
{
  display: flex;
  flex-direction: column;
  padding-right: 5px;
}

.contact-details p
{
  font-size: 14px;
}

p
{
  margin: 5px;
}

</style>
