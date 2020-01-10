<template>
	<div class="home">
		<!-- Photo by Patrick Tomasso on Unsplash -->
		<div class="top center-center">
			<h1>Louis Lee</h1>
		</div>
		<template v-if="this.menu === 'home'">
			<Works />
		</template>
		<template v-if="this.menu === 'contact'">
			<Contact />
		</template>
	</div>
</template>
<script>
import Works from "./Works";
import Contact from "./Contact";
export default {
	name: "Home",
	props: ["menu"],
	components: {
		Works,
		Contact
	}
};
</script>
<style lang="scss" scoped>
h1 {
	font-family: "Fredericka the Great", cursive;
}
.home {
	display: grid;
	position: relative;
	grid-template-areas: "top" "bottom";
	grid-template-rows: 300px auto;
}
.home::after {
	content: "";
	background-image: url("../assets/img/bg.jpg");
	// Photo by Patrick Tomasso on Unsplash
	background-size: cover;
	background-position: center;
	background-repeat: no-repeat;
	opacity: 0.1;
	top: 0;
	left: 0;
	bottom: 0;
	right: 0;
	position: absolute;
	z-index: -1;
}
.top {
	grid-area: top;
}
.bottom {
	grid-area: bottom;
	padding: 0 3rem;
}
</style>
