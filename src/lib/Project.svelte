<script>
  import { onMount } from "svelte";
  import Skill from "$lib/Skill.svelte";
  export let imageUrl = "";
  export let title = "Project Title";
  export let description = "This is a brief description of the project.";
  export let skills = [];

  let observer;

  // Check if the viewport is mobile-size (up to 480px width)

  onMount(() => {
    const columns = document.querySelectorAll(".portfolio-entry");

    observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          // If the column is in view, add the 'active' class, otherwise remove it
          if (entry.isIntersecting) {
            entry.target.classList.add("mobile-scroll-active");
          } else {
            entry.target.classList.remove("mobile-scroll-active");
          }
        });
      },
      {
        threshold: 0.6, // Trigger when at least 50% of the element is visible
      }
    );

    // Observe each column
    columns.forEach((column) => observer.observe(column));
  });
</script>

<div class="portfolio-entry">
  <div class="mobile-scroll-active"></div>
  <img src={imageUrl} alt={title} />
  <h2>{title}</h2>
  <Skill {skills}></Skill>
  <p>{description}</p>
</div>

<style>
  .portfolio-entry {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 4px 8px var(--background-light);
    width: 80%;
    transition: box-shadow 0.3s ease;
  }

  .portfolio-entry:hover {
    box-shadow: 0 8px 18px var(--foreground-extralight);
  }

  @media (max-width: 480px) {
    .mobile-scroll-active {
      box-shadow: 0 8px 18px var(--foreground-extralight);
    }
  }

  img {
    width: 100%;
    height: auto;
    max-width: 400px;
    border-radius: 8px;
  }

  h2 {
    margin: 15px 0 10px;
    font-size: 1.5em;
    color: var(--foreground-extralight);
  }

  p {
    font-size: 1em;
    color: var(--foreground-light);
    text-align: center;
  }
</style>
