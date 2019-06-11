<template>
  <div id="app">
    <header>
      <banner></banner>
    </header>
    <main>
      <form-page></form-page>
    </main>
  </div>
</template>

<script>
import Banner from "./components/Banner";
import FormPage from "./components/FormPage";

export default {
  name: "app",
  components: {
    Banner,
    FormPage
  }
};
</script>
<style>
html {
  box-sizing: border-box;
}
*,
*:before,
*:after {
  box-sizing: inherit;
}

#app {
  font-family: "Cabin", Arial, Geneva, sans-serif;
  margin: 0px;
  padding: 0px;
}
</style>
