<template>
  <footer class="footer-main">
    <img class="logo-site" src="/icons/musor.svg" alt="" />
    <div class="logos-block">
      <img src="/icons/vk.svg" alt="" />
      <img src="/icons/telegram.svg" alt="" />
      <img src="/icons/instagram.svg" alt="" />
    </div>
  </footer>
</template>

<style lang="scss">
.footer-main {
  min-height: 500px;
  padding: 40px 100px;
  background-color: #000000;

  .logo-site {
    width: 70px;
    height: 70px;
  }
  .logos-block {
    display: flex;
    padding-top: 25px;
    gap: 10px;

    img {
      width: 40px;
      height: 40px;
      padding: 10px;
      background-color: #292828;
      border-radius: 100%;
    }
  }
}
</style>
