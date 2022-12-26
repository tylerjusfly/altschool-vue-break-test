<template>
  <div class="hello">
    <div class="main--div">
      <img
        class="image"
        src="https://lilyscent.com.ng/wp-content/uploads/2022/05/IMG_3634-1.jpg"
        alt="main image"
      />
      <div class="text--div">
        <div class="text-text">
          A floral, solar and voluptuous interpretation composed by Olivier
          Polge, Perfumer-Creator for the House of CHANEL.
        </div>

        <button class="button">
          <img
            class="btn-icon"
            src="https://www.svgrepo.com/show/423687/shopping-cart-ecommerce.svg"
            alt="cart"
          />
          <span>Add To Cart </span>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
// import image from "./shopping-cart.svg";
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  data() {
    return {};
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  display: flex;
  justify-content: center;
  align-items: center;
}
.main--div {
  width: 300px;
}
.image {
  width: 100%;
  border-radius: 10px 10px 0 0;
}
.text--div {
  display: flex;
  flex-direction: column;
  gap: 30px;
  border-radius: 0 0 10px 10px;
  justify-content: center;
  align-items: center;
  background-color: white;
  width: 87%;
  padding: 30px 20px;
}
.text-text {
  font-weight: 600;
  font-family: monospace;
}
.button {
  display: flex;
  justify-content: center;
  align-items: center;
  /* align-content: center; */
  padding: 15px;
  width: 100%;
  border-radius: 8px;
  border: none;
  color: #fff;
  background-color: #213b68;
}
.btn-icon {
  width: 40px;
}
span {
  font-weight: 700;
}
</style>
