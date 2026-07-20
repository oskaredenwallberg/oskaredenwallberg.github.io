<script lang="ts">
    import ItemRecent from "$lib/components/ItemRecent.svelte";
    import ItemPublication from "$lib/components/ItemPublication.svelte";

    const publications = [
        {
            title: "Power-Domain CSI Prediction for Downlink Power Allocation in MIMO-OFDM Systems",
            names: "Oskar Edén Wallberg, Bo Qian, and Yusheng Ji",
            venue: "IEEE Transactions on Vehicular Technology (2026) Under major revision",
            image: "images/publications/pdct.svg",
            href1: "https://github.com/oskaredenwallberg/wireless-6g",
            href2: "",
            href3: "",
            href4: "./assets/PDCT.pdf",
        },
        {
            title: "Power Allocation for FD-RAN Systems with Heuristic-Guided Reinforcement Learning",
            names: "Oskar Edén Wallberg, et al.",
            venue: "Manuscript in preparation (2027)",
            image: "images/publications/overview.svg",
            href1: "https://github.com/oskaredenwallberg/wireless-6g",
            href2: "",
            href3: "",
            href4: "",
        },
    ]

    const latest = [
        {
            date: "Sep 2026",
            href: "",
            text: "Visiting Student Researcher at the University of Tokyo.",
        },
        {
            date: "Feb 2026",
            href: "",
            text: "Master's thesis as Visiting Student Researcher at Stanford University.",
        },
        {
            date: "Sep 2025",
            href: "",
            text: "Visiting Student Researcher at the National Institute of Informatics.",
        },
    ]
</script>


<section class="section">
    <h2>Research overview</h2>
    <p class="overview">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum
        tincidunt, augue ut ultrices posuere, nisl erat aliquet risus, vitae
        tincidunt nibh mauris eget odio. Integer non ipsum vel velit facilisis
        volutpat. Curabitur dapibus, lacus vitae pretium aliquam, purus lectus
        posuere erat, non tempus ligula mauris eget lacus. Sed id sem sed mauris
        interdum pretium ut sed nunc.
    </p>
</section>

<section class="section">
    <h2>Publications</h2>
    
    {#each publications as item}
        <ItemPublication
            title={ item.title }
            names={ item.names }
            venue={ item.venue }
            image={ item.image }
            href1={ item.href1 }
            href2={ item.href2 }
            href3={ item.href3 }
            href4={ item.href4 }
        />
    {/each}
</section> 

<section class="section">
    <h2>Research Experience</h2>
    {#each latest as item}
        <ItemRecent
            date={ item.date }
            href={ item.href }
            text={ item.text }
        />
    {/each}
</section>

<style>
    .overview {
        color: var(--text-muted);
    }
</style>

