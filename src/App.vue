<template>
	<video :src="video"
		preload="metadata"
		width="1920"
		height="1080"
		muted
		autoplay
		loop
		playsinline
		webkit-playsinline
	></video>

	<div>
		<figure class="my-photo">
			<a :href="domain" :aria-label="title">
				<img :alt="title" :src="image" width="531" height="531">
			</a>
			<a
				href="https://cv.ferditarakci.com.tr"
				title="Ferdi Tarakçı Özgeçmiş"
				aria-label="Ferdi Tarakçı Özgeçmiş"
				class="cv" target="_blank"
			>
				<i class="fas fa-id-card"></i>
			</a>
		</figure>

		<h1><a :href="domain" :title="title" :aria-label="title">Ferdi Tarakcı</a></h1>

		<h2>Web Developer | Doğasever | Hayvansever</h2>

		<p>10 yılı aşkındır front-end ve back-end alanında web tabanlı yazılımlar geliştiriyorum.</p>

		<p>Şimdilerde Digidea Agency'de Front End Developer pozisyonunda tam zamanlı olarak çalışıyorum.</p>

		<Socials :myTitle="title" />
	</div>
</template>

<script>
import Socials from "./components/Socials"

export default {
	name: "App",

	components: {
		Socials
	},

	data() {
		const title = process.env.VUE_APP_TITLE
		const domain = process.env.VUE_APP_DOMAIN

		return {
			title,
			domain,
			video: domain + '/assets/video/freelance-front-end-developer.mp4',
			image: domain + '/assets/images/my.jpg'
		}
	}
}
</script>

<style lang="scss">
	@import "./assets/scss/style.scss";
</style>