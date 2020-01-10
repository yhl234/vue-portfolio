<template>
	<div class="bottom">
		<form @submit.prevent="sendEmail">
			<label>Name</label>
			<input type="text" name="user_name" />
			<label>Email</label>
			<input type="email" name="user_email" />
			<label>Message</label>
			<textarea name="message"></textarea>
			<button type="submit" value="Send">Submit</button>
		</form>
	</div>
</template>

<script>
import emailjs from "emailjs-com";

export default {
	name: "Contact",
	methods: {
		sendEmail: e => {
			emailjs.sendForm(
				"YOUR_SERVICE_ID",
				"YOUR_TEMPLATE_ID",
				e.target,
				"YOUR_USER_ID"
			);
			// .then(
			//   result => {
			//     console.log("SUCCESS!", response.status, response.text);
			//   },
			//   error => {
			//     console.log("FAILED...", error);
			//   }
			// );
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
	// height: 60%;
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
