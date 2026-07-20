<script lang="ts">
    type Props = {
        date: string,
        href: string,
        text: string,
    }

    let { date, href, text }: Props = $props();
</script>


<div class="latest-row">

    <span class="date">{ date }</span>

    <a class="latest-item" href={ href }>
        <p>{ text }</p>
    </a>
    
</div>


<style>
    .latest-row {
        display: grid;
        grid-template-columns: 120px 1fr;
        align-items: center;
        gap: 1.5rem;
    }

    .date {
        color: var(--text);
        font-weight: 600;
    }

    .latest-item {
        display: block;
        padding: 0.6rem 1.25rem;
        border-bottom: 1px solid var(--border);

        color: var(--text-muted);
        text-decoration: none;

        transition: 0.2s ease;
    }

    .latest-item:hover {
        color: var(--text);
        border-color: var(--text-muted);
    }

    .latest-item:hover,
    .latest-item:hover p {
        text-decoration: none;
    }

    @media (max-width: 700px) {
        .latest-row {
            grid-template-columns: 1fr;
            gap: 0.25rem;
        }

        .latest-item {
            padding: 0.6rem 0rem;
        }

        .date {
            display: block;
        }
    }
</style>