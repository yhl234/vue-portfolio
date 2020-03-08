/* eslint-disable no-console */
<template>
  <div class="bottom" v-cloak>
    <form id="contact" class="contact-form" @submit.prevent="validateForm">
      <div class="required" v-for=" (i,index) in this.validate" :key="index">{{i}}</div>
      <label>Name</label>
      <input type="text" name="user_name" v-model="name" />
      <label>Email</label>
      <input type="email" name="user_email" v-model="email" />
      <label>Message</label>
      <textarea name="message" v-model="message"></textarea>
      <vue-recaptcha sitekey="6LePUM4UAAAAAHb4c65hKC0yK9N3moIyerHsWNjn"></vue-recaptcha>
      <button type="submit" value="Send">Submit</button>
      <div>{{this.status}}</div>
    </form>
  </div>
</template>

<script>
import emailjs from "emailjs-com";
import VueRecaptcha from "vue-recaptcha";
export default {
  name: "Contact",
  components: { VueRecaptcha },
  data: function() {
    return {
      name: "",
      email: "",
      message: "",
      status: "",
      validate: []
    };
  },
  methods: {
    validateForm() {
      this.validate = [];
      this.status = "";
      if (this.name === "") {
        this.validate.push("Name is required");
      }
      if (this.email === "") {
        this.validate.push("Email is required");
      }
      if (this.message === "") {
        this.validate.push("Message is required");
      }
      if (this.validate.length === 0) {
        this.sendEmail();
      }
    },
    sendEmail() {
      emailjs
        .send(
          "gmail",
          "template_wBaZWgJK",
          { name: this.name, email: this.email, message: this.message },
          "user_nA6P8cuhfuXYF41H0AfBJ"
        )
        .then(
          response => {
            this.status = "Send! Thank you for your time";
            this.name = "";
            this.email = "";
            this.message = "";
            console.log("SUCCESS!", response.status, response.text);
          },
          error => {
            this.status = "FAILED... Please try again later";
            console.log("FAILED...", error);
          }
        );
    }
  }
};
</script>
<style lang="less" scoped>
.required {
  color: var(--color-intrative);
  margin-bottom: 0.5rem;
}
.bottom {
  display: flex;
  justify-content: center;
  text-align: left;
}
#contact {
  width: 50%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}
input:not(#google),
textarea {
  margin-bottom: 3rem;
  border: 0;
  padding: 0.5rem;
  border-radius: 0.2rem;
  background: var(--color-text);
}
label {
  margin-bottom: 1rem;
}
button {
  padding: 0.5rem;
  width: 30%;
  border: 0.5px solid #fff;
  border-collapse: collapse;
  background: transparent;
}
</style>
