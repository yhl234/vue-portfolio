<template>
	<nav>
		<Ul>
			<li><a href="#">Home</a></li>
			<li><a href="#">Works</a></li>
			<li><a href="#">Resume</a></li>
			<li><a href="#">Contact</a></li>
		</Ul>
	</nav>
</template>
<script>
export default {
	name: "Home"
};
</script>
<style scoped>
nav {
	background: rgb(47, 46, 53);
}
ul {
	display: flex;
	list-style: none;
	justify-content: flex-end;
}
li {
	padding: 1rem;
}
a {
	color: #ffffff;
}
</style>
