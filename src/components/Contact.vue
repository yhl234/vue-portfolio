<template>
  <div class="bottom" v-cloak>
    <form class="contact-form" @submit.prevent="sendEmail">
      <label>Name</label>
      <input type="text" name="user_name" v-model="name" />
      <label>Email</label>
      <input type="email" name="user_email" v-model="email" />
      <label>Message</label>
      <textarea name="message" v-model="message"></textarea>
      <button type="submit" value="Send">Submit</button>
    </form>
  </div>
</template>

<script>
import emailjs from "emailjs-com";

export default {
  name: "Contact",
  data: function() {
    return {
      name: "",
      email: "",
      message: ""
    };
  },
  methods: {
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
            console.log("SUCCESS!", response.status, response.text);
          },
          error => {
            console.log("FAILED...", error);
          }
        );
    }
  }
};
</script>
<style lang="scss" scoped>
.bottom {
  display: flex;
  justify-content: center;
  text-align: left;
}
form {
  width: 50%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}
input,
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
