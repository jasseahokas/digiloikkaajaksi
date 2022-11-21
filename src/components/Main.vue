<template>
	<div class="maincontainer" :class="theme">
		<h1 id="header">
			Jasse <span class="rainbow">Kukan</span> Digiloikkaajaksi 2023
		</h1>
		<div class="reasons">
			<h2>Kolme (3) syytä miksi</h2>
			<div class="reasonsContainer">
				<Reason
					@toggle="toggleTheme"
					:color="theme"
					title="Osaan koodaa"
					text="Tämänkin sivun hutasin muutamassa tunnissa. Osaan käytetäviä (eng. usability) ja ei niin käytettäviä CSS tekniikoita joilla voimme räätälöidä kunkin lukijan lukukokemuksen juuri sopivan epämiellyttäväksi. On tullu tehtyy jne. voitte esim käydä tsekkaa nacun refei"
				/>
				<Reason
					@toggle="toggleTheme"
					:color="theme"
					title="Ihan ok tyyppi"
					text="Nätti feissi ja äässi. Teen kaiken aina asenteella seksikkäästi. Huudi mut poppaan, pormestari. Jasse bitch täs kaupingis johtaa."
				/>
				<Reason
					@toggle="toggleTheme"
					:color="theme"
					title="*Porinaa*"
					text="Tunnetusti loistava leipuri ja Avara Luonto -nautiskelija. Ps. ostin perjantaina uuden bogon."
				/>
			</div>
		</div>
	</div>
	<div class="border" />
</template>

<script>
	import Reason from "./Reason.vue";
	export default {
		name: "MainComp",
		components: {
			Reason,
		},
		data() {
			return {
				theme: "light",
			};
		},
		methods: {
			toggleTheme() {
				this.theme = this.theme === "light" ? "dark" : "light";
			},
		},
	};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
	.maincontainer {
		height: 100vh;
		width: 100vw;
		min-height: 700px;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		h1,
		h2 {
			color: white;
			mix-blend-mode: difference;
			margin: 10px;
		}
		#header {
			width: calc(100vw - 120px);
			@media screen and (max-width: 700px) {
				margin-top: 25px;
				font-size: 24px;
			}
		}
		.reasons {
			@media screen and (max-width: 700px) {
				h2 {
					font-size: 20px;
					margin: 8px;
				}
			}
			.reasonsContainer {
				display: flex;
				flex-direction: row;
				align-items: center;
				justify-content: center;
				gap: 16px;

				@media screen and (max-width: 700px) {
					flex-direction: column;
					width: 75vw;
				}
			}
		}
	}

	.light {
		background-color: #f5f5f5;
	}

	.dark {
		background-color: #000;
	}

	.border {
		position: absolute;
		//center
		left: 50%;
		top: 50%;
		transform: translate(-50%, -50%);
		//border
		width: calc(100% - 50px);
		height: calc(100% - 50px);
		border: 8px solid #323232;
		animation: rainbow-border 1s linear;
		animation-iteration-count: infinite;
	}

	@keyframes rainbow-border {
		100%,
		0% {
			border-color: rgb(255, 0, 0);
		}
		8% {
			border-color: rgb(255, 127, 0);
		}
		16% {
			border-color: rgb(255, 255, 0);
		}
		25% {
			border-color: rgb(127, 255, 0);
		}
		33% {
			border-color: rgb(0, 255, 0);
		}
		41% {
			border-color: rgb(0, 255, 127);
		}
		50% {
			border-color: rgb(0, 255, 255);
		}
		58% {
			border-color: rgb(0, 127, 255);
		}
		66% {
			border-color: rgb(0, 0, 255);
		}
		75% {
			border-color: rgb(127, 0, 255);
		}
		83% {
			border-color: rgb(255, 0, 255);
		}
		91% {
			border-color: rgb(255, 0, 127);
		}
	}
</style>
