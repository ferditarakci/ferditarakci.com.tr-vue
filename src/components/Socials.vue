<template>
	<div class="socials">
		<div>
			<a
				v-for="(social, index) in socials"
				:key="index"
				:href="social.link"
				:class="social.class"
				:aria-label="title(social.title)"
				target="_blank"
				rel="external noopener"
			><i :class="`fab ${social.icon}`"></i></a>
		</div>
		<div>
			<a
				href="https://api.whatsapp.com/send/?phone=905468312073&text=Merhaba!"
				class="wh"
				rel="external noopener"
				:aria-label="title('Whatsapp')"
				target="_blank"
				ref="whatsapp"
			><i class="fab fa-whatsapp"></i><span>Bana Whatsapp'tan ulaşabilirsiniz!</span></a>
		</div>
	</div>
</template>

<script>
import {ref, onMounted} from 'vue';

export default {
	name: "Socials",

	props: ['myTitle'],

	setup() {
		const whatsapp = ref(null);

		onMounted(() => {
			// Mobile cihazlarda whatsapp bağlantı scheme'sını değiştirerek direkt uygulamayı açtırmayı sağlıyoruz.
			// https://api.whatsapp.com/send/?phone=905468312073?text=Merhaba! to whatsapp://send/?phone=905468312073&text=Merhaba!
			if (/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini|Mobile/.exec(navigator.userAgent)) {
				let wp = whatsapp.value
				wp.href = wp.href.replace(/(https:\/\/(web|api).whatsapp.com\/)/i, 'whatsapp://')
				wp.removeAttribute('target')
			}
		});

		return {
			whatsapp
		}
	},

	data() {
		return {
			socials: [
				{
					title: 'Github',
					class: 'gh',
					icon: 'fa-github',
					link: 'https://github.com/ferditarakci'
				},
				{
					title: 'Linkedin',
					class: 'li',
					icon: 'fa-linkedin',
					link: 'https://www.linkedin.com/in/ferditarakci/'
				},
				{
					title: 'Instagram',
					class: 'in',
					icon: 'fa-instagram',
					link: 'https://www.instagram.com/webdeveloper_ferditarakci/'
				},
				{
					title: 'Twitter',
					class: 'tw',
					icon: 'fa-twitter',
					link: 'https://twitter.com/ferditarakci'
				},
				{
					title: 'Facebook',
					class: 'fb',
					icon: 'fa-facebook-f',
					link: 'https://www.facebook.com/WebDeveloperFerdiTarakci/'
				}
			]
		}
	},

	methods: {
		title(a) {
			return `${this.myTitle}, ${a}`
		}
	}
};
</script>