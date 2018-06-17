<template>
  <div id="app">
    <nav class="navbar">
      <div class="logo col-md-3">Travel</div>
      <div class="search-container col-md-9">
        <i class="fas fa-search"></i>
        <input type="text" name="" placeholder="Explore your own activities" class="search-bar">
      </div>
    </nav>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
:root {
  --main-color: #7828B4;
  --sec-color: #9013FE;
  --lighter-grey: #f2f2f2;
  --light-grey: #EBEBEB;
  --dark-grey: #D7D7D7;
  --darker-grey: #9B9B9B;
}
* {
  font-family: Roboto;
}
img {
  max-width: 100%;
}
#app {

}
.navbar {
  background: var(--main-color);
}
.logo {
  color: #fff;
  font-family: Optima-ExtraBlack;
  font-size: 36px;
}
.search-container {
  position: relative;
}
.search-bar {
  width: 388px;
  font-size: 20px;
  font-style: italic;
  background: var(--main-color);
  border: none;
  border-bottom: 2px solid #fff;
  padding-left: 42px;
}
::placeholder {
  color: rgba(255,255,255,0.50);
  font-weight: 200;
}
.fa-search {
  color: #fff;
  position: absolute;
  font-size: 20px;
  top: 8px;
  left: 20px;
}
</style>
