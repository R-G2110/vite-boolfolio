<script>
export default {
	name: 'ProjectCard',
	props: {
		project: Object
	}

}
</script>

<template>
		<div class="card">
				<div class="left">
						<div class="card-image">
							<img src="/src/img/No-Image-Placeholder.png" alt="">
							<!-- <img src="{{ $movie->image }}" alt=""> -->
						</div>
						<div class="card-title">
							<h3>{{ project.name }}</h3>
						</div>
				</div>

				<div class="card-info">
						<div class="details">
							<h4>Type:</h4>
							<p v-if="project.type">{{ project.type.name }}</p>
							<p v-else>no type</p>

							<h4>Technologies:</h4>
							<p
								v-if="project.technologies == 0"
							>no technologies</p>
							<p
								v-else
								v-for="(technology, index) in project.technologies" 
								:key="index"
							>- {{ technology.name }}</p>
							<h4>Status:</h4>
							<p>{{  project.status }}</p>
							<a href="#">
								<button class="btn"><strong>More Info</strong></button>
							</a>
							
						</div>
				</div>

		</div>
</template>

<style lang="scss" scoped>
  a {
    color: #C4C4C4;
    text-decoration: none;
  }
	h4 {
		margin-top: 10px;
	}
	.card {
		display: flex;
		position: relative;
		overflow: hidden;
		margin: 30px auto;
		width: 24.45%;
		height: 300px;
		border: 1px solid black;
		cursor: pointer;
		&:hover img{
			scale: 1.2;
			transition: all 2s;
		}
		&:hover .card-info {
			background-color: #C4C4C4;
			color: black;
		}
		&:hover a {
			color: black;
		}
		.left {
			.card-image {
				width: 200px;
			}
			.card-title {
				width: 200px;
				height: 70px;
				padding: 10px 20px;
				position: absolute;
				bottom: 0;
				left: 0;
				background-color: black;
				color: white;
			}
		}
		.card-info{
			width: calc(100% - 200px);
			padding: 10px;
			overflow: auto;
			position: relative;
		
			&:hover .btn{
				display: block;
			}
			.btn {
				display: none;
				cursor: pointer;
				margin-top: 20px;
				&:hover {
					background-color: red;
					color: white;
				}
			}
		}
	}
</style>