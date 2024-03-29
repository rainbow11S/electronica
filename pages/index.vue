<template>
  <div>
    <div class="preview">
      <SharedBaseImagesSlider :images="images" />
    </div>
    <div class="categories-main">
      <h4 class="block-headline">CATEGORIES</h4>
      <div class="categories">
        <div class="category-block">
          <img class="photo-category" src="/images/airpods-vector.svg" alt="" />
          <p class="name-category">AirPods</p>
        </div>
        <div class="category-block">
          <img
            class="photo-category vis-pr"
            src="/images/ap-vis-pro.jpeg"
            alt="" />
          <p class="name-category">Vision Pro</p>
        </div>
        <div class="category-block">
          <img
            class="photo-category ap-tv"
            src="/images/apple-tv.jpeg"
            alt="" />
          <p class="name-category">Apple TV</p>
        </div>
        <div class="category-block">
          <img
            class="photo-category homepod"
            src="/images/homepod-vector.jpeg"
            alt="" />
          <p class="name-category">Homepod</p>
        </div>
        <div class="category-block">
          <img
            class="photo-category ipad"
            src="/images/ipad-vector.jpeg"
            alt="" />
          <p class="name-category">iPad</p>
        </div>
        <div class="category-block">
          <img
            class="photo-category phone"
            src="/images/iphone-vector.svg"
            alt="" />
          <p class="name-category">iPhone</p>
        </div>
        <div class="category-block">
          <img
            class="photo-category mac"
            src="/images/mac-vector.webp"
            alt="" />
          <p class="name-category">MacBook</p>
        </div>
      </div>
    </div>
    <div class="blocks-category">
      <div class="block-category">
        <p class="text-block">iPhone <br /><span>от 40000 p.</span></p>
        <img class="telephones" src="/images/iphones-fullhd.png" alt="" />
      </div>
      <div class="block-category">
        <p class="text-block">iPad <br /><span>от 29000 p.</span></p>
        <img class="tablets" src="/images/ipad-fullhd.png" alt="" />
      </div>
      <div class="block-category">
        <p class="text-block">AirPods <br /><span>от 12000 p.</span></p>
        <img class="headphones" src="/images/airpods-fullhd.png" alt="" />
      </div>
      <div class="block-category">
        <p class="text-block">Watches <br /><span>от 25000 p.</span></p>
        <img class="watches" src="/images/watches-fullhd.png" alt="" />
      </div>
    </div>
    <h4 class="block-headline">POPULAR PRODUCTS</h4>
    <div class="row main-block-card">
      <SharedBaseProductCard v-for="res in data?.products" :product="res" />
    </div>
  </div>
</template>

<script setup>
const images = [
  "/images/preview-iphone.png",
  "/images/preview-iphone2.webp",
  "/images/preview-iphone3.jpeg",
  "/images/preview-iphone4.jpeg",
];
const { data } = await useFetch("https://dummyjson.com/products");
console.log(data.value);
</script>

<style lang="scss">
body {
  margin: 0;
}
.preview {
  img {
    width: 100%;
    height: auto;
  }
}
.block-headline {
  @include orbitron;
  font-size: 50px;
  padding: 30px;
  margin: 0;
  text-align: center;
  border-bottom: 1px solid #000000;
}
.categories-main {
  padding: 40px 0;

  .categories {
    display: flex;
    align-items: baseline;
    height: 150px;
    padding-top: 20px;

    .category-block {
      display: flex;
      flex-direction: column;
      margin: 0 auto;
      gap: 15px;
      .photo-category {
        width: 120px;
      }
      .vis-pr {
        width: 160px;
      }
      .ap-tv,
      .ipad {
        width: 130px;
      }
      .phone {
        width: 100px;
      }
      .mac {
        width: 200px;
      }
      .name-category {
        @include orbitron;
        font-size: 20px;
        margin: 0;
        text-align: center;
      }
    }
  }
}
.blocks-category {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 30px;
  padding: 100px 0;
  margin: 100px 30px;
  border-radius: 30px;
  background-color: #7b7b7b;

  .block-category {
    position: relative;
    width: 450px;
    min-height: 350px;
    border-radius: 30px;
    overflow: hidden;
    background-color: #1a1a1d;

    .text-block {
      @include orbitron;
      color: #ffffff;
      font-size: 20px;
      margin: 0;
      padding-top: 25px;
      text-align: center;
    }
    img {
      width: 300px;
      position: absolute;
    }
    .telephones {
      bottom: -70px;
      left: 75px;
    }
    .tablets {
      bottom: -85px;
      right: -40px;
    }
    .headphones {
      bottom: -20px;
      right: 75px;
    }
    .watches {
      bottom: -40px;
      left: -20px;
    }
  }
}
.main-block-card {
  justify-content: center;
  gap: 40px 0;
  padding-top: 100px;
}
</style>
