<script lang="ts">

</script>


<nav class="navbar">
    <a href="/">
        Home
    </a>
    <a href="/research">
        Research
    </a>
    <a href="/projects">
        Projects
    </a>
    <!-- <a href="/blog">
        Blog
    </a> -->
    <a href="./assets/CV2026.pdf" target="_blank" rel="noopener">
        CV
    </a>
</nav>


<style>
    .navbar {
        display: flex;
        justify-content: flex-end;
        gap: 2.5rem;
        padding: 1rem 0;
        border-bottom: 1px solid var(--border);
        margin-bottom: 1rem;
    }

    .navbar a {
        color: var(--text-muted);
        text-decoration: none;
        transition: color 0.2s ease;
    }

    .navbar a:hover {
        color: var(--text);
    }

    @media (max-width: 700px) {
        .navbar {
            width: 100%;
            justify-content: space-between;
            gap: 0;
        }
    }
</style>