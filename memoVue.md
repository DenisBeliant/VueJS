# Capturer un texte entré dans un champ de saisie : 

**VueJS**

new Vue({
  el: '#app',
  data: {
    nameValue: ''
  }
})

**HTML**

<div id="app">
  <h2>What's your Name ? </h2>
  <label for="name">Name:</label>
  <input id="name" type="text" v-model="nameValue" />
  <div class="colorful">
    Hey
    <div class="greeting"> {{ nameValue }}</div>
    do you ❤️ tacos ?    
  </div>

</div>

**CSS**

body {
  display: flex;
  justify-content: center;
  background: #1d1d43;
  color: #e6e6e6;
  text-align: center;
}

#app{
  margin: 10vh auto;
}

.colorful {
  font-weight: bold;
  font-size: 1.4em;
  padding-top: 40px;
  width: 300px;  
  color: #00bcd4;
}

# Ajouter / Enlever une classe sur un élément :

**VueJS**

new Vue({
  el: '#app',
  data: {
    active: false
  }
})

**HTML**

<div id="app">
  <button @click="active = !active">Toggle me</button>
  <p :class="{ chartreuse: active }">Sometimes I need to be styled differently</p>
</div>

**CSS**

#app {
  margin: 50px;
}

.chartreuse {
  color : chartreuse;
}

# Afficher / Cacher un élément au clic sur un bouton :

**VueJS**

new Vue({
  el: '#app',
  data: {
    showTacos: false,
  }
})

**HTML**

<div id="app">
  <button v-on:click="showTacos = !showTacos">
    Toggle Tacos
  </button>
  <p v-if="showTacos"> 🌮 🌮 🌮</p>
</div>

**CSS**

body {
  display: flex;
  justify-content : center;
}

#app {
  margin: 50px;
}

p {
  padding: 10px 12px;
  border: 1px solid brown;
  background : #eee;
}