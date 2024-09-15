<nav class="topnav">
  <a href="/">Tristan Cox's Portfolio</a>
  <div>
    <a href="/" class="nav-link">Home</a>
    <a href="/contact" class="nav-link">Contact</a>
  </div>
</nav>
<slot></slot>

<style>
  div {
    display: flex;
  }
  .topnav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-left: 1em;
    padding-right: 1em;
    background-color: var(--background-light);
  }
  .nav-link {
    color: var(--foreground-light);
    text-decoration: none;
    padding: 8px 16px;
    border-radius: 4px;
    transition: color 0.3s ease;
  }

  .nav-link:hover {
    color: white;
  }
  
  a {
    text-decoration: none;
    color: var(--foreground-extralight);
  }
</style>
