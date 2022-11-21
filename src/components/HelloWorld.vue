<template>
	<div class="maincontainer"></div>
</template>

<script>
	export default {
		name: "HelloWorld",
		props: {
			msg: String,
		},
	};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
	.maincontainer {
		background-color: #f5f5f5;
		height: 100vh;
		width: 100vw;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
</style>
