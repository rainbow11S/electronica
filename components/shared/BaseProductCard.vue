<template>
  <div>
    <div class="product-card">
      <img :src="product?.images[0]" alt="" />
      <h5 class="title-card">{{ product?.title }}</h5>
      <div class="block-prices">
        <p class="decoration-price">{{ product?.price + "$" }}</p>
        <p class="price">
          {{
            Math.round(
              product?.price -
                (product?.price / 100) * product?.discountPercentage
            ) + "$"
          }}
        </p>
      </div>
      <div class="block-buttons">
        <button class="buy-button">Купить</button>
        <button class="about-button">Подробнее</button>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["product"]);
</script>

<style lang="scss">
.product-card {
  width: 260px;
  height: 700px;
  box-shadow: 0 0 8px #5e5e5e;
  margin: 0 30px;
  padding: 20px;
  border-radius: 30px;
  position: relative;

  img {
    width: 260px;
    height: 260px;
    object-fit: contain;
  }
  .title-card {
    @include michroma;
    margin: 0;
    padding-top: 30px;
    font-size: 19px;
  }
  .decoration-price,
  .price {
    @include orbitron;
    margin: 0;
    font-size: 25px;
    letter-spacing: 1.5px;
  }
  .block-prices {
    display: flex;
    padding-top: 10px;
    gap: 15px;
    .decoration-price {
      text-decoration: line-through;
    }
  }
  .block-buttons {
    position: absolute;
    display: flex;
    flex-direction: column;
    width: 100%;
    max-width: 260px;
    bottom: 20px;
    gap: 10px 0;

    .buy-button,
    .about-button {
      min-height: 40px;
      border-radius: 30px;
      border: none;
      transition: 0.3s;

      &:hover {
        background-color: #950740;
        color: #d9d9d9;
      }
    }
    .buy-button {
      background-color: #6f2232;
      color: #d9d9d9;
    }
  }
}
</style>
