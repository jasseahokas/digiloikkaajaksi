<template>
	<div class="reason" :class="{ open: open }" @click="toggle">
		<div class="overlay">
			<h1>?</h1>
			<img class="gif" src="../assets/giphy.gif" alt="" />
		</div>
		<div class="content" :class="color">
			<h3>{{ title }}</h3>
			<p>{{ text }}</p>
		</div>
	</div>
</template>
<script>
	export default {
		name: "ReasonComp",
		props: {
			color: {
				type: String,
			},
			title: {
				type: String,
			},
			text: {
				type: String,
			},
		},
		data() {
			return {
				open: false,
			};
		},
		methods: {
			toggle() {
				this.$emit("toggle");
				this.open = !this.open;
			},
		},
	};
</script>
<style lang="scss" scoped>
	.reason {
		width: 300px;
		aspect-ratio: 1 / 1;
        @media screen and (max-width: 1000px) {
			width: 200px;
		}
		@media screen and (max-width: 700px) {
            max-width: 300px;
			width: 100%;
			aspect-ratio: 5 / 3;
		}
		overflow: hidden;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		position: relative;

		.overlay {
			position: absolute;
			width: 100%;
			height: 100%;
			transition: 1s cubic-bezier(0.075, 0.82, 0.165, 1);
			transform: scale(100%);
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: center;
			gap: 16px;
			z-index: 50;
			cursor: pointer;
			h1 {
				color: #f5f5f5;
				font-size: 100px;
				z-index: 50;
				position: relative;
				mix-blend-mode: difference;
				transition: 1s cubic-bezier(0.075, 0.82, 0.165, 1);
				pointer-events: none;
			}
			.gif {
				position: absolute;

				width: 100%;
				height: 100%;
			}
		}

		.content {
			position: absolute;
			width: 100%;
			height: 100%;
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: flex-start;
			gap: 16px;
			z-index: 5;
			padding: 16px;
			box-sizing: border-box;
			cursor: pointer;
			@media screen and (max-width: 1000px) {
                gap: 12px;
				padding: 12px;
			}
			h3 {
				color: #f5f5f5;
				font-size: 24px;
				z-index: 50;
				position: relative;
				mix-blend-mode: difference;
				transition: 1s cubic-bezier(0.075, 0.82, 0.165, 1);
				pointer-events: none;
				margin: 0;
				@media screen and (max-width: 600px) {
					font-size: 20px;
				}
			}
			p {
				color: #f5f5f5;
				font-size: 16px;
				z-index: 50;
				position: relative;
				mix-blend-mode: difference;
				transition: 1s cubic-bezier(0.075, 0.82, 0.165, 1);
				pointer-events: none;
				text-align: start;
				margin: 0;
				@media screen and (max-width: 600px) {
					font-size: 14px;
				}
			}
		}
		.light {
			background-color: #000000;
		}
		.dark {
			background-color: rgb(255, 255, 255);
		}

		&:hover {
			.overlay {
				h1 {
					transform: scale(350%);
				}
			}
		}
	}

	.open {
		.overlay {
			transform: scale(400%);
			opacity: 0;
			h1 {
				transform: scale(50%);
			}
		}
	}
</style>