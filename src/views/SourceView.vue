<template>
	<div id="status" :class="{ animate: animateView }" :style="{ 'animation-delay': animationDelay }"
		class="content-container">
		<section id="source" class="section-container" :style="{ 'animation-delay': animationDelay }">
			<div class="section-header clipped-medium-backward">
				<img src="/icons/campaign.svg" />
				<h1>Source</h1>
			</div>
			<div class="section-content-container">
				<p>
                    test
                </p>
			</div>
		</section>
	</div>
</template>