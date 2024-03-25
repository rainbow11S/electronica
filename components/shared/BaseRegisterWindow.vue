<template>
  <form class="register-form" @submit.prevent>
    <h4 class="main-headline">Regiser</h4>
    <div>
      <div class="name-input">
        <span class="caption-text">Name</span>
        <input
          v-model="name"
          placeholder="Your name"
          minlength="1"
          maxlength="15" />
      </div>
      <div class="email-input">
        <span class="caption-text">Email</span>
        <input
          v-model="email"
          placeholder="Your email"
          minlength="1"
          maxlength="32" />
      </div>
      <div class="password-input">
        <span class="caption-text">Password</span>
        <input
          v-model="password"
          placeholder="Your password"
          minlength="1"
          maxlength="32" />
      </div>
      <div class="password-repeat-input">
        <span class="caption-text">Password repeat</span>
        <input
          v-model="password"
          placeholder="Your password"
          minlength="1"
          maxlength="32" />
      </div>
    </div>
  </form>
</template>

<style lang="scss">
.register-form {
  position: relative;
  width: 600px;
  min-height: 800px;
  background-color: #ffffff;
  text-align: center;

  .main-headline {
    @include orbitron;
    font-size: 30px;
    color: #1a1a1d;
  }
}
</style>
