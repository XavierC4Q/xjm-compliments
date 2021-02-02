<template>
  <div>
    <Nuxt />
  </div>
</template>

<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.primary-btn {
  background-color: #118ab2;
  border-radius: 1rem;
  padding: 0.6rem;
  color: #fff;
  font-size: 1rem;
  text-transform: uppercase;
  font-weight: bold;
  width: 12rem;
  cursor: pointer;
  border: 1px solid #f2f2f2;
}

.primary-btn:disabled {
  background-color: lightgray;
  cursor: not-allowed;
  color: grey;
}
</style>
