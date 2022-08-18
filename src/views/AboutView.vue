<template>
  <div class="main">
    <div class="head-container">
      <h3 class="head-text">
        Blivande front-end utvecklare med stort intresse för back-end utveckling
        <p>
          Hej och välkommen till min portfolio! <br />
          Mitt namn är william ali, 29 årig utvecklare från sverige
          Här kommer ni hitta information om mig och projekten jag har jobbat
          med och även projekt jag aktuellt jobbar på!
        </p>
        <router-link to="/projects">Klicka här för att direkt se mina projekt!</router-link>
      </h3>
    </div>
  </div>
</template>


<style scoped>
h3 {
  font-size: 30px;
}
p{
  font-size: 14px;
}
a {
  font-size: 14px;
}
.main {
  margin: 20px 0px;
  display: flex;
  text-align: center;
  justify-content: center;
  width: 100%;
  border: 1px solid black;
  border-radius: 10px;
}

.head-container {
  width: 50%;
  line-height: 25px;
}  


@media (max-width: 425px) {
  .head-container {
  width: 100%;
  line-height: 25px;
}  
}

</style>