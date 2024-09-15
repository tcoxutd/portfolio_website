<script>
  import Project from "$lib/Project.svelte";
  import project_list from "$lib/projects.json";
</script>

<div class="main-content">
  <h1 class="tight-header">Tristan Cox</h1>
  <summary>
    I am a developer with a passion for real-time systems. I have been
    programming since middle school and have recently acquired my Bachelors in
    Computer Science from the University of Texas at Dallas. I love software engineering
    because of the satisfaction intuitive, snappy software gives to those who
    use it and those who build it.
  </summary>

  <h2 class="underlined">Projects</h2>
  <div class="hline"></div>
  <div class="hlayout-spread">
    {#each project_list.projects as proj}
      <a href={proj.superpage} class="hlayout-column">
        <Project
          imageUrl={proj.image}
          title={proj.title}
          description={proj.description}
          skills={proj.skills}
        ></Project>
      </a>
    {/each}
  </div>
  <!-- 
    --background-dark: #0a102b;
    --background-light: #182547;
    --foreground-light: #748db3; 
    --foreground-extralight: #9abbec;
    -->
</div>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");
  :root {
    --background-dark: #0a0a0a;
    --background-light: #0f0f0f;
    --foreground-light: rgb(255, 255, 255);
    --foreground-light2: rgb(117, 177, 255);
    --foreground-extralight: #0066ff;
    --default-font: "Poppins";
  }

  :global(body) {
    background-color: var(--background-dark);
    color: var(--foreground-light);
    font-family: var(--default-font);
    margin: 0 0 0 0;
    padding: 0 0 0 0;
  }

  a.hlayout-column {
    text-decoration: none;
  }

  .hline {
    width: 100%;
    height: 3px;
    margin-bottom: 4px;
    background-color: var(--background-light);
  }

  :global(.main-content) {
    padding-left: 1em;
    padding-right: 1em;
  }

  :global(.underlined) {
    padding-bottom: 0;
    margin-bottom: 0;
  }

  :global(.tight-header){
    padding-bottom: 0;
    margin-bottom: 0.1em;
  }

  :global(.hlayout-spread) {
    display: flex;
    justify-content: space-between; /* Evenly spaces the columns */
    align-items: flex-start; /* Makes sure the columns stretch to the same height */
    flex-wrap: wrap;
  }

  :global(.hlayout-column) {
    flex: 1; /* Ensures all columns take up equal space */
    padding: 8px;
    text-align: center;
    border-radius: 8px;
    min-width: 300px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  /* For smaller screens (up to 768px), switch to 2 columns */
  @media (max-width: 768px) {
    .hlayout-column {
      flex: 1 1 calc(50% - 20px); /* 2 columns with space between them */
      margin-bottom: 20px;
    }
  }

  /* For extra small screens (up to 480px), switch to a single column */
  @media (max-width: 480px) {
    .hlayout-column {
      flex: 1 1 100%; /* 1 column filling the full width */
      margin-bottom: 20px;
    }
  }
</style>
