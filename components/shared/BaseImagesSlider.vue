<template>
  <div class="images-slider">
    <button @click="slideImage" class="button-l">
      <img class="left-icon" src="/icons/left.svg" alt="" />
    </button>
    <img :src="images[currentImage]" alt="" />
    <button @click="slideImage" class="button-r">
      <img class="right-icon" src="/icons/right.svg" alt="" />
    </button>
  </div>
</template>

<script setup>
const props = defineProps(["images"]);
const currentImage = ref(0);

console.log(props.images.length);
const slideImage = () => {
  currentImage.value += 1;
  if (currentImage.value >= props?.images.length) {
    currentImage.value = 0;
  }
};
console.log(props.images);
</script>

<style lang="scss">
.images-slider {
  display: flex;
  position: relative;
  .button-l,
  .button-r {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 25px;
    height: 25px;
    border: none;
    padding: 0;
    background-color: transparent;
    .left-icon,
    .right-icon {
      width: 25px;
      height: 25px;
    }
  }
  .button-l {
    left: 10px;
  }
  .button-r {
    right: 10px;
  }
}
</style>
