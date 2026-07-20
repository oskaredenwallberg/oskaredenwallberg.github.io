<script lang="ts">
    type Props = {
        title: string,
        names: string,
        venue: string,
        image: string, 
        href1: string,
        href2: string,
        href3: string,
        href4: string,
    }

    let expanded = $state(false);
    let { title, names, venue, image, href1, href2, href3, href4 }: Props = $props();
</script>


<div class="publication-card">
    <div class="publication-content">
        
        <div class="publication-header">
            <p class="publication-title">{ title }</p>
        </div>

        <p class="publication-meta">{ names }</p>
        <p class="publication-meta"><em>{ venue }</em></p>

    </div>

    <div class="publication-side">
        
        <button class="publication-figure" onclick={ () => expanded = true }>
            <img class="publication-figure-img" src={ image } alt="Overview" />
        </button>

        {#if expanded}
            <button class="figure-modal" type="button" onclick={() => expanded = false}>
                <img class="figure-modal-img" src={image} alt="Expanded figure" />
            </button>
        {/if}

        <div class="publication-icons">
            <a href={ href1 } target="_blank" rel="noopener"><img src="/images/icons/github-icon-white.svg" alt="GitHub"></a>
            <a href={ href2 } target="_blank" rel="noopener"><img src="/images/icons/arxiv-icon-white.svg" alt="arXiv"></a>
            <a href={ href3 } target="_blank" rel="noopener"><img src="/images/icons/ieee-icon-white.svg" alt="IEEE"></a>
            <a href={ href4 } target="_blank" rel="noopener"><img src="/images/icons/pdf-icon-white.svg" alt="PDF"></a>
        </div>

    </div>
</div>


<style>
    .publication-card {
        display: grid;
        grid-template-columns: 1fr 100px;
        gap: 2rem;

        padding: 1.25rem 0;
        border-bottom: 1px solid var(--border);

        align-items: center;
    }

    .publication-side {
        justify-self: end;
        display: flex;
        flex-direction: row;
        justify-content: center;
        gap: 0.5rem;
        height: 100%;
    }

    .publication-header {
        display: flex;
        justify-content: space-between;
        gap: 1rem;
    }

    .publication-title {
        font-size: 0.95rem;
        margin: 0;
        color: var(--text);
        font-weight: 500;
    }

    .publication-meta {
        font-size: 0.95rem;
        margin: 0rem 0;
        color: var(--text-muted);
    }

    .publication-figure {
        width: 120px;
        height: 75px;

        display: block;
        padding: 0;
        border: 1px solid var(--border);
        border-radius: 6px;
        overflow: hidden;

        background: var(--figure-bg);
        cursor: zoom-in;
    }

    .publication-figure-img {
        display: block;
        width: 100%;
        height: 100%;

        object-fit: cover;
        border: 0;
        border-radius: 0;
    }

    .publication-icons {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        height: 100%;
    }

    .publication-icons a {
        width: 14px;
        height: 14px;

        display: flex;
        align-items: center;
        justify-content: center;
    }

    .publication-icons img {
        max-width: 100%;
        max-height: 100%;
        object-fit: contain;
    }


    .figure-modal {
        position: fixed;
        inset: 0;

        display: flex;
        justify-content: center;
        align-items: center;

        margin: 0;
        padding: 0;
        border: none;
        outline: none;

        background: rgba(0, 0, 0, 0.85);
        cursor: zoom-out;
        z-index: 1000;
    }

    .figure-modal-img {
        width: auto;
        height: 90vh;

        background: white;
        border-radius: 8px;
        cursor: zoom-out;
    }

    @media (max-width: 700px) {
        .publication-card {
            grid-template-columns: 1fr;
            gap: 1rem;
        }

        .publication-side {
            width: 100%;
            justify-self: stretch;

            display: flex;
            flex-direction: column;
            gap: 0.75rem;
        }

        .publication-figure {
            width: 100%;
            height: 100%;
            max-height: none;
            object-fit: contain;
            pointer-events: none;
            cursor: default;
        }

        .publication-icons {
            width: 100%;
            height: auto;
            flex-direction: row;
            justify-content: space-evenly;
            align-items: center;
        }

        .publication-icons a {
            width: 18px;
            height: 18px;
        }
    }
</style>

