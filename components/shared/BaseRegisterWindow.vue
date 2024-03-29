<template>
  <form id="form" class="register-form" @submit.prevent>
    <img
      @click="closeForm"
      class="cancel-button"
      src="/icons/cancel.svg"
      alt="" />
    <h4 class="main-headline">Regiser</h4>
    <div class="input-forms">
      <input
        v-model="user.username"
        placeholder="Your name"
        minlength="1"
        maxlength="15" />
      <input
        v-model="user.email"
        placeholder="Your email"
        minlength="1"
        maxlength="32" />
      <input
        v-model="user.password"
        placeholder="Your password"
        minlength="1"
        maxlength="32" />
    </div>
    <button @click="register" class="reg-button">Register</button>
    <p class="text-privacy-policy">
      By clicking on the button you agree to the <span>"Privacy Policy"</span>
    </p>
  </form>
</template>

<script setup>
const user = ref({
  email: "",
  username: "",
  password: "",
});
const closeForm = () => {
  form.style.display = "none";
};
const register = async () => {
  const { data } = await useFetch("https://dummyjson.com/users/add", {
    method: "post",
    body: {
      email: user.value.email,
      username: user.value.username,
      password: user.value.password,
    },
  });
};
</script>

<style lang="scss">
.register-form {
  display: none;
  position: absolute;
  left: calc(50% - 300px);
  top: 10%;
  z-index: 1;
  width: 600px;
  min-height: 600px;
  border-radius: 30px;
  padding: 30px;
  background-color: #c2c2c2;
  text-align: center;

  .cancel-button {
    position: absolute;
    left: 10px;
    top: 10px;
    width: 40px;
    height: 40px;
  }

  .main-headline {
    @include orbitron;
    font-size: 30px;
    color: #1a1a1d;
  }
  input,
  .reg-button {
    @include orbitron;

    color: #1a1a1a;
    border-radius: 15px;
    border: none;
  }
  .input-forms {
    display: flex;
    flex-direction: column;
    gap: 20px;

    input {
      font-size: 17px;
      max-width: 100%;
      outline: none;
      min-height: 50px;
      padding: 10px 20px;
    }
  }
  .reg-button {
    width: 100%;
    font-size: 20px;
    padding: 20px;
    margin-top: 100px;
    background-color: #00a522;
    transition: 0.3s;

    &:hover {
      background-color: #439654;
    }
  }
  .text-privacy-policy {
    @include orbitron;
    font-size: 17px;
    padding-top: 25px;
    margin: 0;

    span {
      font-size: 18px;
      color: #00a522;
    }
  }
}
</style>
