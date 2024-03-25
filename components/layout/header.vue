<template>
  <header class="site-header">
    <img class="logo-icon" src="/icons/musor.svg" alt="" />
    <div class="category-products">
      <p class="category-name">iPhone</p>
      <p class="category-name">MacBook</p>
      <p class="category-name">AirPods</p>
      <p class="category-name">Apple TV</p>
      <p class="category-name">Watch</p>
      <p class="category-name">Dyson</p>
    </div>
    <div>
      <img class="login-icon" src="/icons/login.svg" alt="" />
      <img class="ellipsis-icon" src="/icons/ellipsis.svg" alt="" />
    </div>
  </header>
</template>

<style lang="scss">
.site-header {
  display: flex;
  justify-content: space-between;
  height: 70px;
  padding: 0 50px;
  background-color: #333333;

  .logo-icon {
    width: 55px;
    height: 55px;
    margin: 7.5px 0;
  }
  .category-products {
    display: flex;
    gap: 30px;

    .category-name {
      @include orbitron;
      color: #ffffff;
      font-size: 25px;
      margin: auto 0;
    }
  }
  .login-icon,
  .ellipsis-icon {
    width: 30px;
    height: 30px;
    margin: 20px 0;
  }
}
</style>
