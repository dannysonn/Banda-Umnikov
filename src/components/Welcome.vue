<template>
  <div class="welcome">
    <div class="welcome__text">
      <h1>Hello</h1>
      <p>Want to choose your beer? Or find something new? You can do it all here.</p>
    </div>
    <div class="welcome__iphone">
      <img src="https://imagens.trocafone.com/images/phones/iphone-xs-max-cinzaespacial-frete.png" alt="">
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
  h1 {
    position: relative;
  }

  h1:after {
    content: '!';

    position: absolute;
    z-index: 10;

    animation: jump .5s linear infinite;
  }

  @keyframes jump {
    0%, 100% {
      transform: translate(0, 0);
    }
    50% {
      transform: translate(0px, -5px);
    }
  }

  .welcome {
    display: flex;
    padding: 2rem 2rem 0;

    background-image: linear-gradient(180deg, #121e3d 0, #000);
  }

  .welcome__iphone img {
    width: 100%;
    max-width: 500px;
    height: 100%;
    max-height: 500px;
  }

  .welcome__text {
    width: 60%;
    margin: auto;
  }

  .welcome__iphone {
    width: 40%;
  }
</style>