<template>
	<div id="status" :class="{ animate: animateView }" :style="{ 'animation-delay': animationDelay }"
		class="content-container">
		<section id="missions" class="section-container" :style="{ 'animation-delay': animationDelay }">
			<div class="section-header clipped-medium-backward">
				<img src="/icons/protocol.svg" />
				<h1>Credits</h1>
			</div>
			<div class="source-container">
				<div class="links">
					This project is NOT (originally) mine! Please, check out the original creator, Kuenaimaku: 
				</div>
				<div class="links">
					<a href="https://github.com/Kuenaimaku/lancer-briefings">
						Kuenaimaku's Repo 
						<img src="/icons/github.svg" class="github"/>
					</a>
					<a href="https://github.com/Arch-Noize/sotw-briefing-1">
						My Repo 
						<img src="/icons/github.svg" class="github"/>
					</a>
				</div>
			</div>
		</section>
	</div>
</template>

<script>

export default {
	props: {
		animate: {
			type: Boolean,
			required: true,
		},
		initialSlug: {
			type: String,
			required: true,
		},
	},
	data() {
		return {
			animateView: this.animate,
			animationDelay: "1.75s",
			clockAnimationDelay: "2500",
			missionMarkdown: "",
		};
	},
	computed: {},
	created() {
		this.setAnimate();
		this.setClockAnimateDelay();
	},
	methods: {
		setAnimate() {
			if (this.animate) {
				this.animateView = true;
			}
			let statusAnimated = window.sessionStorage.getItem("statusAnimated");
			if (statusAnimated) {
				this.animationDelay = "0s";
			}
			if (statusAnimated === null) {
				window.sessionStorage.setItem("statusAnimated", true);
			}
		},
		setClockAnimateDelay() {
			let delayToFloat = parseFloat(this.animationDelay.replace("s", ""));
			let finalClockDelay = delayToFloat * 600 + 600;
			this.clockAnimationDelay = finalClockDelay.toString();
		},
	},
};
</script>
