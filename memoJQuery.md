# Capturer un texte entré dans un champ de saisie : 

**JQuery**

` // this is an alias to $(document).ready(function() {
$(function() {
  // keypress wouldn't include delete key, keyup does. We also query the div id app and find the other elements so that we can reduce lookups
  $('#app').keyup(function(e) {
    // get data from input with #name
    var nameInput = $(this).find('#name').val();
    // get data from input with .name
    var greeting = $(this).find('.greeting');

    greeting.empty();
    if (nameInput.length > 0 ) {
      greeting.append(nameInput);  
    }
    
  });
});`

**HTML**

<div id="app">
  <h2>What's your Name ? </h2>
  <label for="name">Name:</label>
  <input id="name" type="text" />
  <div class="colorful">
    Hey
    <div class="greeting"></div>
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

**JQuery**

$(function() {
  $('button').click(function(e) {
    $('.toggle').toggleClass('red');
    $(this).attr('aria-pressed', ($(this).attr('aria-pressed') == "false" ? true : false));
  });
});

**HTML**

<div id="app">
  <button aria-pressed="false">Toggle me</button>
  <p class="toggle">Sometimes I need to be styled differently</p>
</div>

**CSS**

#app {
  margin: 50px;
}

.red { 
  color: red; 
}

# Afficher / Cacher un élément au clic sur un bouton :

**JQuery**

$(function() {
  $('#toggleTacos').on('click', function() {
    $('.tacos-box').toggle();
  });
});

**HTML**

<div id="app">
  <button type="button" id="toggleTacos">
    Toggle Tacos
  </button>
  <p  class="tacos-box" >🌮 🌮🌮</p>
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
