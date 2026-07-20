<script lang="ts">
    import ItemText from "$lib/components/ItemRecent.svelte";

    const data = [
        { date:"Sep 2026", href:"https://tlab.hongo.wide.ad.jp/",        text:"Visiting Student Researcher at the University of Tokyo, Tsukada lab." },
        { date:"Jul 2026", href:"https://stanford.edu/~boyd/index.html", text:"Master's thesis at Stanford University, Stephen P. Boyd's lab." },
        { date:"May 2026", href:"/research",                             text:"IEEE TVT manuscript under major revision." },
        { date:"Dec 2025", href:"https://klab-nii.github.io/",           text:"Research internship at National Institute of Informatics, Yusheng Ji lab." },
    ];
</script>


<section class="section">
    <div class="intro">
        <div>
            <h2>Oskar Edén Wallberg</h2>
            <p>Machine Learning • Optimization • Algorithms</p>
            <p class="bio">
                I am a master's student in Computer Science and Engineering specializing in Machine Learning at KTH Royal Institute of Technology, Sweden. I hold a B.Sc in Industrial Engineering and Management also at KTH. Currently, I am expanding my research experience for an upcoming PhD application.
            </p>
        </div>
        <img class="profile-pic" src="images/profilepic.jpeg" alt="Oskar Edén Wallberg">
    </div>
</section>

<section class="section">
    <h2>Latest</h2>
    {#each data as item}
        <ItemText
            date={item.date}
            href={item.href}
            text={item.text}
        />
    {/each}
</section>


<style>
    .profile-pic {
        width: 200px;
        height: 200px;
        border-radius: 50%;
        object-fit: cover;
    }

    .intro {
        display: flex;
        align-items: center;
        /* gap: 2rem; */
    }

    .bio {
        color: var(--text-muted);
    }

    @media (max-width: 700px) {
        .intro {
            flex-direction: column;
            align-items: stretch;
            gap: 1rem;
        }

        .profile-pic {
            width: 100%;
            height: auto;
            aspect-ratio: 1 / 1;
            border-radius: 50%;
            object-fit: cover;
        }
    }
</style>