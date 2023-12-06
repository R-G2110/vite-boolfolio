<script>

import { store } from '../data/store';
import ProjectCard from './partials/ProjectCard.vue';

	export default {
		name: 'Main',
		components: {
      ProjectCard
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
		<div class="container">
			<div class="cards-wrapper">
				<ProjectCard 
					v-for="(project, index) in store.projects" 
					:key="index"
					:project="project" 
				/>
			</div>
		</div>
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