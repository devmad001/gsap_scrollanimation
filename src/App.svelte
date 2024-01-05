<script>
	import Hero from "./components/Hero.svelte"
	import FeatureDescription from "./components/FeatureDescription.svelte"
	import Footer from "./components/Footer.svelte"

	import { gsap } from "gsap"
	import { ScrollTrigger } from "gsap/ScrollTrigger"
	import { onMount } from "svelte"

	gsap.registerPlugin(ScrollTrigger)

	let windowW = window.innerWidth

	window.addEventListener("resize", () => windowW = window.innerWidth )

	onMount(() => {
		
		if (windowW < 1360) return false

		const heroTimeline = gsap.timeline()
		const featuresTimeline = gsap.timeline()
		const footerTimeline = gsap.timeline()

		heroTimeline.from(".hero__logo", {
			opacity: 0,
			duration: 1.2
		})
		.from(".header__headline", {
			opacity: 0,
			y: -50,
			duration: 1.2
		})
		.from(".header__subheadline", {
			opacity: 0,
			y: -50,
			duration: 1.2
		})
		.from(".header__ctas button:first-of-type", {
			opacity: 0,
			y: 50,
			duration: 1.2
		})
		.from(".header__ctas button:last-of-type", {
			opacity: 0,
			y: 50,
			duration: 1.2
		})
		.from(".counter--1 .counter__line", {
			opacity: 0,
			height: 0,
			duration: 1.2
		})
		.from(".counter--1 .counter__value", {
			opacity: 0,
			scale: 0,
			duration: 1.2
		})

		featuresTimeline
			.to(".gallery__img--1", {
				opacity: 1,
				"clip-path": "polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%)",
				duration: 1.2
		})
		.to(".gallery__img--2", {
				opacity: 1,
				"clip-path": "polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%)",
				duration: 1.2
		})
		.to(".gallery__img--3", {
				opacity: 1,
				"clip-path": "polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%)",
				duration: 1.2
		})
		.to(".gallery__img--4", {
				opacity: 1,
				"clip-path": "polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%)",
				duration: 1.2
		})
		.from(".feature-description__subheadline", {
			opacity: 0,
			duration: 1.2
		})
		.from(".feature-description__headline", {
			opacity: 0,
			duration: 1.2
		})
		.from(".feature-description__description", {
			opacity: 0,
			y: 50,
			duration: 1.2
		})

		footerTimeline
			.from(".counter--2 .counter__line", {
					opacity: 0,
					height: 0,
					duration: 1.2
				})
			.from(".counter--2 .counter__value", {
				opacity: 0,
				scale: 0,
				duration: 1.2
			})
			.from(".footer__headline", {
				opacity: 0,
				duration: 1
			})
			.from(".footer__description", {
				opacity: 0,
				duration: 1
			})
			.from(".footer button", {
				opacity: 0,
				duration: 1
			})

		ScrollTrigger.create({
			animation: heroTimeline,
			trigger: ".hero",
			start: "-50px top",
			end: "bottom -40%",
			ease: "power3",
			scrub: 5,
			pin: true
		})

		ScrollTrigger.create({
			animation: featuresTimeline,
			trigger: ".feature-description",
			start: "top top",
			ease: "power3",
			scrub: 3,
			pin: true
		})

		ScrollTrigger.create({
			animation: footerTimeline,
			trigger: ".footer",
			start: "-200px center",
			end: "-100px bottom",
			ease: "power3.inOut",
			toggleActions: "play none reverse none"
		})

	})

</script>

<main class="lp">
	<Hero />
	<FeatureDescription />
	<Footer />
</main>

<style>
	.lp {
		overflow: hidden;
		height: 100%;
	}
</style>