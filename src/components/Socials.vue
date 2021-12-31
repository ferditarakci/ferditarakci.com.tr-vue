<template>
	<div class="socials">
		<div>
			<a
				href="https://www.linkedin.com/in/ferditarakci/"
				class="li"
				rel="external noopener"
				aria-label="Web Developer - Ferdi Tarakcı, Linkedin"
				target="_blank"
			><i class="fab fa-linkedin"></i></a>
			<a
				href="https://www.instagram.com/webdeveloper_ferditarakci/"
				class="in"
				rel="external noopener"
				aria-label="Web Developer - Ferdi Tarakcı, Instagram"
				target="_blank"
			><i class="fab fa-instagram"></i></a>
			<a
				href="https://twitter.com/ferditarakci"
				class="tw"
				rel="external noopener"
				aria-label="Web Developer - Ferdi Tarakcı, Twitter"
				target="_blank"
			><i class="fab fa-twitter"></i></a>
			<a
				href="https://www.facebook.com/WebDeveloperFerdiTarakci/"
				class="fb"
				rel="external noopener"
				aria-label="Web Developer - Ferdi Tarakcı, Facebook"
				target="_blank"
			><i class="fab fa-facebook-f"></i></a>
			<a
				href="https://github.com/ferditarakci"
				class="gh"
				rel="external noopener"
				aria-label="Web Developer - Ferdi Tarakcı, Github"
				target="_blank"
			><i class="fab fa-github"></i></a>
		</div>
		<div>
			<a
				href="https://api.whatsapp.com/send/?phone=905468312073&text=Merhaba!"
				class="wh"
				rel="external noopener"
				aria-label="Web Developer - Ferdi Tarakcı, Whatsapp"
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
	setup() {
		const whatsapp = ref(null);

		onMounted(() => {
			// Mobile cihazlarda whatsapp bağlantı scheme'sını değiştirerek direkt uygulamayı açtırmayı sağlıyoruz.
			// https://api.whatsapp.com/send/?phone=905468312073?text=Merhaba! to whatsapp://send/?phone=905468312073&text=Merhaba!
			if (/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini|Mobile/.exec(navigator.userAgent)) {
				whatsapp.value.href = whatsapp.value.href.replace(/(https:\/\/(web|api).whatsapp.com\/)/i, 'whatsapp://')
				whatsapp.value.removeAttribute('target')
			}
		});

		return {
			whatsapp
		}
	},
};
</script>