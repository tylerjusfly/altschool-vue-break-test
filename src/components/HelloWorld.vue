<template>
  <div class="hello">
    <div class="main--div" :class="modalOpen">
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

        <button class="button" @Click="modalPopup">
          <img
            class="btn-icon"
            src="https://www.svgrepo.com/show/423687/shopping-cart-ecommerce.svg"
            alt="cart"
          />
          <span>Add To Cart </span>
        </button>
      </div>
    </div>
    <!-- Popup -->
    <div v-show="showPopup" class="popup">
      <h3
        v-if="setError"
        style="color: red; text-align: center"
        class="sign-in-title"
      >
        {{ setError }}
      </h3>
      <h3 v-else class="sign-in-title">Sign In with username TylerJusfly</h3>
      <a class="close" href="#" @Click="closeModal">&times;</a>
      <label>
        Username
        <input
          type="text"
          placeholder="Enter A Username"
          v-model="Inputusername"
        />
      </label>
      <button class="button" @Click="signInUser">
        <img
          class="btn-icon"
          src="https://www.svgrepo.com/show/281591/send.svg"
          alt="Arrow Svg"
          style="width: 30px !important"
        />
        <span>SignIn</span>
      </button>
    </div>
    <!-- SignIn completed Modal -->
    <div class="popup hello" v-show="success">
      <h3>Hello world</h3>
      <a class="close" href="#" @Click="closeModal">&times;</a>
      <img
        src="https://www.svgrepo.com/show/295329/connect-transfer.svg"
        alt="image"
        width="100"
      />
      <p style="text-align: center !important">
        I did'nt plan on letting you add anything to cart, let's just say i
        pranked you. sorry.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  data() {
    return {
      modalOpen: '',
      showPopup: false,
      Inputusername: '',
      username: 'tylerjusfly',
      success: false,
      setError: null,
    };
  },
  methods: {
    modalPopup() {
      this.modalOpen = 'modal-open';
      this.showPopup = true;
    },
    closeModal() {
      this.showPopup = false;
      this.modalOpen = '';
      this.success = false;
    },
    signInUser() {
      console.log(this.Inputusername.toLowerCase());
      if (this.Inputusername.toLowerCase() === this.username) {
        this.showPopup = false;
        this.success = true;
        this.setError = null;
        this.Inputusername = '';
      } else {
        this.setError = 'Invalid Username';
        setTimeout(() => {
          this.setError = null;
        }, 1000);
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  display: flex;
  flex-direction: column;
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
  cursor: pointer;
  padding: 15px;
  width: 100%;
  border-radius: 8px;
  border: none;
  color: #fff;
  background-color: #213b68;
}
.btn-icon {
  vertical-align: middle;
  width: 40px;
  padding-right: 8px;
}
span {
  vertical-align: middle;
  align-self: center;
  font-weight: 700;
}
.modal-open {
  transition: opacity 500ms;
  opacity: 0.5;
  z-index: -1;
}
.popup {
  margin-top: 30px;
  padding: 20px;
  background: #fff;
  border-radius: 5px;
  width: 300px;
  position: relative;
  bottom: 500px;
  left: 10px;
  z-index: 1;
  transition: all 10s ease-in-out;
}
.popup .close {
  position: absolute;
  top: 20px;
  right: 30px;
  transition: all 200ms;
  font-size: 30px;
  font-weight: bold;
  text-decoration: none;
  color: #333;
}
.popup .close:hover {
  color: red;
}
.popup .content {
  max-height: 30%;
  overflow: auto;
}
.sign-in-title {
  margin-top: 40px;
  text-align: center;
  font-family: monospace;
}
input {
  font: 30px;
  padding: 0.6em 0.9em;
  border-radius: 0.4em;
  border: 1px solid #213b68;
  padding-inline: 2em 0.9em;
  width: 12em;
  margin-bottom: 2em;
}
label {
  font-weight: 700;
  font-family: monospace;
}
</style>
