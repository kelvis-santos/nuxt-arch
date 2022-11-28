<template>
  <div class="container">
    <div class="card-image"><img :src="image" alt="Prod"></div>
    <div class="card-info text-back-color">
      <div class="card-name">{{ name }}</div>
      <div class="card-description">{{ description }}</div>
      <div class="card-value">{{ value }}</div>
      <div class="card-quantity">{{ quantity }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'block',
  props: {
    image: {
      default: 'https://www.dtalemodern.com/pub/media/catalog/product/t/e/test-product.jpg'
    },
    name: {
      type: String,
      required: false,
      default: null
    },
    description: {
      type: String,
      required: false,
      default: null
    },
    value: {
      type: Number,
      required: false,
      default: null
    },
    quantity: {
      type: Number,
      required: false,
      default: null
    }
  }
}
</script>

<style>
  .container {
    margin: 5px;
    border: 0.5;
    border-radius: 1rem;
    width: auto;
    height: 8rem;
    background-color: #393E46;
    display: flex;
    text-align: center;
    justify-content: center;
    align-items: center;

    box-shadow: 11px 9px 10px 0px rgba(0,0,0,0.1);
  }
  .card-image {
    display: flex;
    width: 40%;
    align-content: flex-start;
  }
  .card-image, img {
    height: auto;
    width: 100px;
  }
  .text-back-color {
    background-color: #6D9886;
    color: #F2E7D5;
  }
  .card-info {
    margin: 3px;
    width: 60%;
  }
  .card-description {
    white-space: nowrap; 
    width: 200px; 
    overflow: hidden;
    text-overflow: ellipsis; 
    border: 1px solid #000000;
  }
</style>