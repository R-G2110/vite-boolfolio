<script>
	export default {
		name: 'Header',
	}
</script>

<template>
	<header>
		<div class="container">
			<nav>
				<ul>
					<li>
						<router-link :to="{name: 'home'}">Home</router-link>
					</li>
					<li>
						<router-link :to="{name: 'about'}">About</router-link>
					</li>
					<li>
						<router-link :to="{name: 'projects'}">Projects</router-link>
					</li>
					<li>
						<router-link :to="{name: 'contacts'}">Contacts</router-link>
					</li>
				</ul>
			</nav>
		</div>
	</header>
</template>


<style lang="scss" scoped>
	header {
		height: 80px;
		width: 100%;
		background-color: brown;
		color: white;
	}

</style>