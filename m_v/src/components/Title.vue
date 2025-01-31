<template>
    <div class="title-container">
      <h3>{{ text }}</h3>
    </div>
  </template>
  
  <script>
  export default {
    name: "Title",
    props: {
      text: {
        type: String,
        required: true,
      },
    },
  };
  </script>
  
  <style scoped>


  .title-container {
    --b: 5px;   /* Espessura da borda */
    --a: 35deg; /* Inclinação do lado direito */
    --c: #ffffff; /* Cor */
  
    position: absolute;
    top: 40px;
    left: 5em;
    
    line-height: 1.2; /* Controla a altura */
    padding-inline: calc(.5lh*tan(var(--a)) + var(--b)/cos(var(--a)));
    text-indent: .1em;
    padding: 0 40px;
    color: white;
  }
  
  .title-container::before {
    content: "";
    position: absolute;
    inset: 0;
    background: var(--c);
    clip-path: polygon(
      0 0, calc(100% - .5lh*tan(var(--a))) 0, 100% 50%, calc(100% - .5lh*tan(var(--a))) 100%, 0 100%, calc(.5lh*tan(var(--a))) 50%,
      0 0, calc(var(--b)*(tan(var(--a)) + 1/cos(var(--a)))) var(--b), 
      calc(.5lh*tan(var(--a)) + var(--b)/cos(var(--a))) 50%, calc(var(--b)*(tan(var(--a)) + 1/cos(var(--a)))) calc(100% - var(--b)), 
      calc(100% - .5lh*tan(var(--a)) - var(--b)*(1/cos(var(--a)) - tan(var(--a)))) calc(100% - var(--b)), 
      calc(100% - var(--b)/cos(var(--a))) 50%, calc(100% - .5lh*tan(var(--a)) - var(--b)*(1/cos(var(--a)) - tan(var(--a)))) var(--b), 
      calc(var(--b)*(tan(var(--a)) + cos(var(--a)))) var(--b)
    );
  }
  </style>
  
  