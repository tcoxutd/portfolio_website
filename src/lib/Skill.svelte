<script>
  export let skills = [];
</script>

<div class="skill-container">
  {#each skills as skill}
    <div class="skill">{skill}</div>
  {/each}
</div>

<style>
  .skill-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    color: var(--background-dark);
  }

  .skill {
    background-color: var(--foreground-light2);
    border-radius: 12px;
    margin: 0.2em;
    padding: 0.2em;
  }
</style>
