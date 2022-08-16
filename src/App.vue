<template>
  <header class="header">
    <div class="header-name-container">
      <router-link to="/">
        <img class="header-logo" src='./assets/headerLogo.png' alt="logo">
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
  color: black;
  margin: 20px 300px;
}

body
{
  background: white;
}

header
{
  width: 100%;
}

nav
{
  display: flex;
  margin-right: 20px;
  justify-content: center;
  align-items: center;
  font-size: 18px;
  width: 100%;
}

nav a
{
  margin:0px 20px;
  color: black;
}

nav a.router-link-exact-active
{
  color: rgb(155, 106, 106)
}

.header
{
  box-shadow: 1px 1px 6px 1px black;
  width: 100%;
}

.header-name-container
{
  display: flex;
}

.header-name-text
{
  margin: 0;
  font-weight: normal;
  font-family: monospace;
  font-size: x-large;
  width: 100%;
}

.header-logo
{
  margin-top:10px;
  padding-bottom:10px;
  margin-left:5px;
  width: 200px;
  height: 40px;
}

a
{
  text-decoration: none;
}

a:hover
{
  color: rgba(135, 206, 250, 0.7)
}


.footer-container
{
  bottom: 0;
  width: 100%;
  margin-top: 10px;
  background: #f2f2f2;
  height: fit-content;

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

@media screen and (max-width:4000px) and (min-width: 2880px)
{
  .footer-content p {
    font-size: 30px;
  }
  .footer-content h2 {
    font-size: 35px;
  }
  .links a {
    font-size: 30px;
  }

  nav
  {
    display: flex;
    align-items: center;
    text-align: center;
    width: 100%;
    font-size: 30px;
  }

  .header
  {
    box-shadow: 1px 1px 6px 1px black;
    padding: 5px;
    width: 100%;
    height: 65px;
  }

  .header-name-container
  {
    width: 100%;
    display: flex;
    gap: 1000px;

  }

  .header-logo
  {
    width: 200px;
    height: 70px;
  }
}

@media screen and (max-width:768px) and (min-width: 500px)
{
  #app
  {
    font-family: monospace;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: black;
    margin: auto;
  }

  nav
  {
    display: flex;
    align-items: center;
    text-align: center;
    font-size: 18px;
  }


  .header
  {
    box-shadow: 1px 1px 6px 1px black;
    padding: 5px;
  }

  .header-name-container
  {
    display: flex;
    gap: 40px;
  }

  .header-name-text
  {
    margin: 0;
    font-weight: normal;
    font-family: monospace;
    font-size: x-large;
  }

}

@media (max-width: 480px)
{

  #app
  {
    font-family: monospace;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: black;
    margin: auto;
  }

  nav
  {
    display: none;
  }

  header
  {
    margin: 0;
    padding: 0;
    width: 100;
  }

  .header-name-container
  {
    width: 100%;
    margin: 0;
    padding: 0;
  }
}
</style>
