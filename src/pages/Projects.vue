<script>

import { store } from '../data/store';
import ProjectCard from '../components/partials/ProjectCard.vue';
import Navigator from '../components/partials/Navigator.vue';

	export default {
		components: {
      ProjectCard,
			Navigator
    },
		data() {
      return {
        store
      }
    },
		
	}
</script>

<template>
	<main>	
		<div class="cards-wrapper">
			<ProjectCard 
				v-for="(project, index) in store.projects" 
				:key="index"
				:project="project" 
			/>
		</div>
		<Navigator />
	</main>
</template>


<style lang="scss" scoped>
	main {
		.container{
			.cards-wrapper{
				width: 100%;
				display: flex;
				flex-wrap: wrap;
			}
		}
	}
</style>