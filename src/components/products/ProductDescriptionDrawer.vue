<template>
  <div class="drawer-background" :class="{show: active}" @click="$emit('close-product-drawer')">
  </div>
  <div class="drawer" :class="{show: active}">
    <div class="drawer-close" @click="$emit('close-product-drawer')">
      X
    </div>
    <div v-if="product2" class="product-details">
      <h3 class="text-center">{{ product2.name }}</h3>
      <p class="description">{{ product2.description }}</p>
      <b class="text-center">${{ product2.price.toFixed(2) }}</b>

      <div class="cart-total" v-if="product_total">
        <p class="drawer__cart" >В корзине: <b>{{ product_total }}</b></p>
      </div>

      <div class="drawer__buttons">
        <button class="drawer__button" @click="addToCart()">Добавить</button>
        <button class="drawer__button" @click="removeFromCart">Удалить</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductDescriptionDrawer",
  props: ['product2', 'active'],
  methods: {
    addToCart() {
      this.$store.commit('addToCart', this.product2)
    },
    removeFromCart() {
      this.$store.commit('removeFromCart', this.product2)
    }
  },
  computed: {
    product_total() {
      return this.$store.getters.productQuantity(this.product2)
    }
  }
}
</script>

<style lang="scss">
.drawer-background {
  width: 100%;
  height: 100vh;
  position: fixed;
  left: 0;
  top: 0;
  background-color: rgba(124, 124, 123, 0.55);
  z-index: 100;
  display: none;
  transition: display .5s;

  &.show {
    display: block;
  }
}

.drawer {
  width: 95vw;
  height: 100vh;
  background-color: white;
  position: fixed;
  top: 0;
  left: -105vw;
  padding: 15px;
  transition: left .5s;
  z-index: 101;
  overflow-y: scroll;

  &.show {
    left: 34%;
  }
}

.drawer-close {
  font-size: 1.5rem;
  padding: 5px;
  border-radius: 5px;
  right: 10px;
  border: 2px solid gray;
  color: gray;
  width: 15px;
  float: right;
  cursor: pointer;

  &:hover {
    background-color: lightgray;
  }
}

.product-details {
  display: flex;
  justify-content: center;
  flex-direction: column;

  p.description {
    padding: 20px;
    line-height: 1.5rem;
  }

  .btn-container {
    button {
      width: 150px;
      border: none;
      padding: 10px;
      border-radius: 5px;
      margin: 0 5px 50px;
      cursor: pointer;
    }
  }
}

@media (min-width: 500px) {
  .drawer {
    width: 450px;
  }
}
</style>
