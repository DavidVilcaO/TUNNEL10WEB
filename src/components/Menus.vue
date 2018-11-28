<template>
      <div class="menu">
        <a href="index.html">
        <div class="logo">
          <img src="../assets/logo-tunnel10.png" alt="">
        </div>
        </a>
        <div class="items-menu"><!-- 
          <a href="privacy.html">Privacy</a>
          <a href="security.html">Securrity</a>
          <a href="availability.html">Availability</a>
          <a href="compliance.html">Compliance</a> -->
          <a href="/#">Privacy</a>
          <a href="/#">Securrity</a>
          <a href="/#">Availability</a>
          <a href="/#">Compliance</a>
        </div>
      </div>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="stylus">
.menu 
  width 100%
  height 150px
  display flex
  justify-content space-between
  align-content center
  align-items center
@media screen and (max-width: 600px) {
  .menu {
    justify-content center
  }
}

.logo
  margin 10px

.items-menu
    margin 10px 30px 10px 10px
    display: flex
    a 
      margin 30px
      cursor pointer
      color white
      list-style none
      font-family Avenir
      // font-family: 'Roboto', sans-serif;
      text-decoration none
      font-weight: 300;
@media screen and (max-width: 600px) {
  .items-menu {
    display: none;
  }
}
  

</style>