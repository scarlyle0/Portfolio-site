<script>
	import projects from '$lib/Projects';
</script>

	<h1>Projects</h1>
    <main>
        <div class="projects">
            {#each projects as project}
                <div class="project">
                    <div class="header">
                        <h2>
                            {project.title}
                        </h2>
                        <div class="techsContainer">
                            Technologies:
                            <div class="techs">
                                {#each project.technologies as tech}
                                    <div>{tech}</div>
                                {/each}
                            </div>
                        </div>
                    </div>
                    <div class="descandimg">
						<p>{project.description}</p>
						{#if project.video}
							<video width="256" height="256" controls autoplay loop muted>
								<source src={project.video} type="video/mp4">
								Your browser does not support the video tag.
							</video>
						{/if}
                    </div>
                    <div style="display: flex; gap: 10px;">
                        {#if project.url != ''}
                            <a href={project.url} target="_blank" rel="noreferrer">
                                <div class="button">see more</div>
                            </a>
                        {/if }
                        {#if project.code != ''}
                        <a href={project.code} target="_blank" rel="noreferrer">
                            <div class="button">code</div>
                        </a>
                        {/if }
                    </div>
                </div>
            {/each}
        </div>
    </main>

<style>

	a {
		text-decoration: none;
	}

    main {
		max-width: 100%;
		min-height: 500px;
		text-align: left;
		margin: 0 auto;
		box-sizing: border-box;
		margin-bottom: 100px;
    }

	.projects {
		width: 100%;
		margin: 20px auto;
		display: flex;
		gap: 20px;
		flex-direction: column;
		align-items: center;
		margin-bottom: 10px;
	}

	.project {
		text-align: start;
		display: flex;
		flex-direction: column;
		color: white;
		background: #111;
		padding: 1.5rem;
		width: 90%;
		gap: 20px;
		transition: transform 0.2s ease-in-out;
		border-radius: 25px;
	}

	h1 {
		font-size: 60px;
		font-weight: 700;
		text-align: center;
		margin-top: 10px;
		margin-bottom: 5px;
	}

	.descandimg {
		display:flex; 
		gap: 30px; 
		justify-content: space-between; 
		align-items: center;
	}

	h2 {
		display: flex;
		margin: 0;
	}

	.project p {
		font-weight: 100;
		color: #708090;
		text-align: left;
	}

	video {
		width: 256px;
		height: 256px;
		border-radius: 10px;
	}

	.techsContainer {
		display: flex;
		flex-wrap: wrap;
		gap: 10px;
	}

	.techs {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.techs > div {
		margin: 0 0 0 10px;
	}

	.button {
		display: flex;
		justify-content: center;
		align-items: center;
		color: white;
		border: 2px solid white;
		padding: 10px;
	}

	@media (max-width: 600px) {
		.descandimg {
			flex-direction: column; /* Switch to column for mobile */
		}
		
		video {
			width:256px;
			height: 256px;
			border-radius: 10px;
		}

		.project {
			align-items: center;
		}

	}

</style>