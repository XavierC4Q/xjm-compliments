<template>
  <div>
    <Nuxt />
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Londrina+Solid:wght@300;400&display=swap');
html {
  font-family: 'Londrina Solid', cursive;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  background-color: #f8edeb;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

button,
input {
  font-family: 'Londrina Solid', cursive;
}

.primary-btn {
  background-color: #118ab2;
  border-radius: 1rem;
  padding: 0.6rem;
  color: #fff;
  font-size: 1.6rem;
  text-transform: uppercase;
  font-weight: bold;
  cursor: pointer;
  border: transparent;
  letter-spacing: 0.15rem;
}

.primary-btn:disabled {
  background-color: lightgray;
  cursor: not-allowed;
  color: grey;
}
</style>
