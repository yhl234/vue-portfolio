<template>
	<div class="works bottom" v-cloak>
		<div class="card" v-for="(i, index) in works" :key="index">
			<div class="imgContainer">
				<img :src="i.img" loading="lazy" />
			</div>
			<div>
				<span>
					<a>{{ i.name }}</a> |
					<a>{{ i.category }}</a>
				</span>
			</div>
			<p>{{ i.description }}</p>
			<div class="card-btns">
				<a :href="i.code" class="code">Code</a>
				<a :href="i.url" class="live">Live</a>
			</div>
		</div>
	</div>
</template>
<script>
const works = [
	{
		img: "https://picsum.photos/300/200?random=1.jpg",
		name: "test",
		category: "test",
		description:
			"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
		code: "www.github.com",
		url: "www.google.com"
	},
	{
		img: "https://picsum.photos/300/200?random=2.jpg",
		name: "test2",
		category: "test2",
		description:
			"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
		url: "www.google.com",
		code: "www.github.com"
	},
	{
		img: "https://picsum.photos/300/200?random=3.jpg",
		name: "test3",
		category: "test",
		description:
			"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
		url: "www.google.com",
		code: "www.github.com"
	},
	{
		img: "https://picsum.photos/300/200?random=4.jpg",
		name: "test4",
		category: "test4",
		description:
			"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
		url: "www.google.com",
		code: "www.github.com"
	}
];
export default {
	name: "Works",
	data: function() {
		return {
			works
		};
	},
	methods: {}
};
</script>
<style lang="scss" scoped>
.works {
	display: flex;
	overflow-x: scroll;
}
.card {
	overflow: hidden;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	border: 1px solid rgba(255, 255, 255, 0.664);
	margin: 2rem;
	min-width: 300px;
	height: 400px;
	p {
		margin-top: 0;
	}
	.card-btns {
		display: flex;
		a {
			flex: 1 0;
			padding: 0.5rem;
			border: 0.5px solid #fff;
			border-collapse: collapse;
		}
	}
}
.imgContainer {
	width: 300px;
	height: 200px;
	overflow: hidden;
	img {
		transition: all 3s ease-in-out;
		&:hover {
			scale: 1.2;
		}
	}
}
</style>
