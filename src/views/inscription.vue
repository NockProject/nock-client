<template>
  <div>
    <menu-connect route="/connect" />

    <h2>Création du compte</h2>

    <form id="connect" @submit.prevent="sendForm" method="post">
      <div class="field-wrap">
        <label for="firstname"
          ><img src="../assets/icons/connectPeople.svg" alt="icon people"
        /></label>
        <input
          class="name"
          type="text"
          name="firstName"
          id="firstName"
          v-model="user.firstName"
          placeholder="John"
        />
      </div>
      <div class="field-wrap">
        <label for="lastname"
          ><img src="../assets/icons/connectPeople.svg" alt="icon people"
        /></label>
        <input
          class="name"
          type="text"
          name="lastName"
          id="lastName"
          v-model="user.lastName"
          placeholder="Doe"
        />
      </div>
      <div class="field-wrap">
        <label for="email"
          ><img src="../assets/icons/mailIcon.svg" alt="icon mail"
        /></label>
        <input
          class="email"
          type="email"
          name="email"
          id="email"
          v-model="user.email"
          min="0"
          placeholder="john.doe@email.com"
        />
      </div>
      <div class="field-wrap">
        <label for="password"
          ><img src="../assets/icons/lock-icon.svg" alt="icon mail"
        /></label>
        <input
          class="password"
          type="password"
          name="password"
          id="password"
          v-model="user.password"
          min="0"
          placeholder="*********"
        />
      </div>
      <div class="field-wrap">
        <label for="confirmPassword"
          ><img src="../assets/icons/lock-icon.svg" alt="icon mail"
        /></label>
        <input
          class="password"
          type="password"
          name="verifPassword"
          id="verifPassword"
          v-model="user.verifPassword"
          min="0"
          placeholder="*********"
        />
      </div>
      <div class="button-container">
        <button type="submit" class="buttonClick buttonBefore">
          Confirmation
        </button>
      </div>
    </form>
  </div>
</template>

<script>
import menuConnect from "../components/menu-connect";
import axios from "axios";

export default {
  components: {
    menuConnect
  },
  data() {
    return {
      user: {
        firstName: "",
        lastName: "",
        email: "",
        password: "",
        verifPassword: ""
      }
    };
  },
  methods: {
    sendForm() {
      if (this.password === this.verifPassword) {
        if (this.firstName !== "" || this.lastName !== "") {
          if (this.email !== "") {
            axios
              .post("https://nock-nock.herokuapp.com/api/auth/signup", {
                firstName: this.user.firstName,
                lastName: this.user.lastName,
                email: this.user.email,
                password: this.user.password
              })
              .then(
                this.$router.push("/connect"),
                this.$toasted.show("Compte créé", {
                  theme: "toasted-primary",
                  position: "top-right",
                  duration: 5000
                })
              );
          }
        }
      }
    }
  }
};
</script>

<style lang="scss" scoped>
h2 {
  margin-top: 70px;
  font-size: 14px;
  text-transform: uppercase;
  color: #ffba00;
  margin-left: 20px;
}
.button-container {
  font-weight: bold;
  text-align: center;
  margin-top: 70px;
  font-size: 10px;

  .buttonClick {
    width: 95%;
    display: block;
    margin: 20px 10px 10px 10px;
    padding: 18px 40px;
    border-radius: 5px;
    text-transform: uppercase;
    text-decoration: none;

    -webkit-box-shadow: 0 3px 6px -2px rgba(0, 0, 0, 0.5);
    -moz-box-shadow: 0 3px 6px -2px rgba(0, 0, 0, 0.5);
    box-shadow: 0 3px 6px -2px rgba(0, 0, 0, 0.5);
  }

  .buttonBefore {
    background-color: #2e3460;
    color: white;
  }
}

form {
  margin-top: 30px;
  display: block;
  position: relative;

  .mdp {
    position: absolute;
    bottom: -30px;
    right: 20px;
    font-size: 10px;
    text-decoration: none;
    color: #ffba00;
    font-family: Montserrat B, sans-serif;
  }

  .field-wrap {
    position: relative;
    margin-bottom: 40px;
    text-align: center;

    input {
      margin: 0 auto;
      border: none;
      border-bottom: #2e3460 1px solid;
      width: 90%;
      padding: 0 0 15px 45px;
      font-size: 14px;
      font-family: Montserrat B, sans-serif;
      color: #2e3460;
    }

    label {
      position: absolute;
      transform: translateY(6px);
      left: 20px;
      top: -10px;
      color: rgba($white, 0.5);
      transition: all 0.25s ease;
      backface-visibility: hidden;
      pointer-events: none;
      font-size: 22px;
    }
  }
}
.errors {
  font-size: 12px;
  color: crimson;
}
</style>
