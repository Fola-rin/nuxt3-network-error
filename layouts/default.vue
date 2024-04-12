<template>
    <div class="main-app">
      <nav class="main-app__header"><NuxtLink to="/">Home</NuxtLink></nav>
      <div class="main-app__content">
        <slot />
      </div>
      <nav class="main-app__footer"><NuxtLink to="/">Home</NuxtLink></nav>
    </div>
</template>

<style>
* {
    padding: 0;
    margin: 0;
    outline: 0;
    box-sizing: border-box;
}
  body {
    font-family: Arial, Helvetica, sans-serif;
  }
  .main-app {
    width: 100%;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    background-color:azure;
  }
  .main-app__header, .main-app__footer  {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 30px;
    background-color: antiquewhite;
  }
  .main-app__header a, .main-app__footer a {
    color: black;
    text-decoration: solid;
    font-weight: 600;
  }
  .main-app__content {
    width: 100%;
    max-width: 1000px;
    margin: auto;
    flex: 1;
    padding: 40px 0;
  }
  .main-app__title {
    margin-bottom: 30px;
    text-align: center;
  }
  .main-app__image {
    width: 400px;
    height: 400px;
    border-radius: 10px;
    object-fit: cover;
    display: block;
    margin: 0 auto 20px;
  }

  .main-app__text {
    margin-bottom: 10px;
  }
</style>