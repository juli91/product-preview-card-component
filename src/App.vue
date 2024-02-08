<template id="app">
  <div class="main">
    <div class="container">
      <div class="content">
        <div v-if="isMobile()" class="image">
          <img
            src="./assets/image-product-mobile.jpg"
            class="main-img"
            alt="Perfume"
          />
        </div>
        <div v-else class="image">
          <img
            src="./assets/image-product-desktop.jpg"
            class="main-img"
            alt="Perfume"
          />
        </div>
        <div class="text">
          <p class="category">PERFUME</p>
          <h1>Gabrielle Essence Eau de Parfum</h1>
          <p>
            A floral, solar and voluptuous interpretation composed by Olivier
            Polge, Perfumer-Creator for the House of CHANEL.
          </p>
          <div class="price">
            <p class="new-price">$149.99</p>
            <p class="old-price">$169.99</p>
          </div>
          <button>
            <img src="./assets/icon-cart.svg" alt="Cart Icon" />
            <p>Add to Cart</p>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    isMobile() {
      if (screen.width <= 768) {
        return true;
      } else {
        return false;
      }
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@500;700&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,700&family=League+Spartan:wght@500;700&display=swap");

html {
  background-color: #f2ebe2;
}

body {
  margin: 0;
  font-family: "Montserrat";
  $headings-font-family: "Fraunces";
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100vh;
  font-size: 14px;
  text-align: left;
  $white: white;
  $dark-grey: #1c232b;
  $dark-green: #368168;
  color: #6c7289;
  $border-radius: 10px;

  .main {
    display: flex;
    align-items: center;
    justify-content: center;
    margin: auto;
    width: 100%;
    height: 100%;
  }

  button,
  .content {
    border-radius: $border-radius;
  }

  h1,
  .new-price {
    font-family: $headings-font-family;
    font-size: 2rem;
  }

  .text,
  .image {
    @media (min-width: 1024px) {
      width: 100%;
    }
  }

  .container {
    @media (min-width: 1024px) {
      width: 50%;
      height: 50%;
    }
  }

  .content {
    background: $white;

    @media (max-width: 1024px) {
      margin-left: 1rem;
      margin-right: 1rem;
    }

    @media (min-width: 1024px) {
      display: flex;
    }
  }

  .text {
    max-width: 100%;
    line-height: 1.75;
    padding: 1.5rem;
  }

  h1 {
    color: $dark-grey;
    line-height: 1;
  }

  .category {
    letter-spacing: 0.25rem;
    margin: 0;
    font-size: 12px;
  }

  .price {
    display: flex;
    align-items: center;
    gap: 1.5rem;

    .old-price,
    .new-price {
      margin: 0;
    }

    .new-price {
      color: $dark-green;
    }

    .old-price {
      text-decoration: line-through;
    }
  }

  .main-img {
    width: 100%;
    height: 100%;
    border-top-left-radius: 10px;
    object-fit: cover;

    @media (max-width: 1024px) {
      border-top-right-radius: 10px;
    }

    @media (min-width: 1024px) {
      border-bottom-left-radius: 10px;
    }
  }

  button {
    font-family: "Montserrat";
    display: flex;
    gap: 1rem;
    align-items: center;
    justify-content: center;
    width: 100%;
    background: $dark-green;
    color: $white;
    font-weight: 800;
    border: none;
    padding: 1rem;
    margin-top: 1.5rem;

    &:hover {
      background: darken($dark-green, 15%);
      cursor: pointer;
    }

    p {
      margin: 0;
    }
  }
}
</style>
