<template>
	<video src="./assets/video/freelance-front-end-developer.mp4"
		preload="metadata"
		width="1920"
		height="1080"
		muted autoplay loop playsinline webkit-playsinline
	></video>

	<div>
		<figure class="my-photo">
			<a href="https://www.ferditarakci.com" :aria-label="title">
				<img :alt="title" src="./assets/images/my.jpg" width="531" height="531" />
			</a>
		</figure>

		<h1><a href="https://www.ferditarakci.com" :aria-label="title">Ferdi Tarakcı</a></h1>

		<h2>Web Developer | Doğasever | Hayvansever</h2>

		<p>10 yılı aşkındır front-end ve back-end alanında web tabanlı yazılımlar geliştiriyorum.</p>

		<p>Şimdilerde Digidea Agency'de Front End Developer pozisyonunda tam zamanlı olarak çalışıyorum.</p>

		<Socials :myTitle="title" />
	</div>
</template>

<script>
import Socials from "./components/Socials";

export default {
	name: "App",

	components: {
		Socials,
	},

	data() {
		return {
			title: 'Web Developer Ferdi Tarakcı'
		}
	}
};
</script>

<style lang="scss">
	@import "./assets/scss/style.scss";
</style>