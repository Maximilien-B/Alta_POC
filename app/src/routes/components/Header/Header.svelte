<script>
    import header_data from './data/header_data.json'

    let active = 0 // to set
    let data = header_data
    let heights = new Array(data.links.length).fill(0)

</script>

<header>
    <div class="header_container">
        <div class="header_logo">

            <p><span>ELTA</span><br>MUSIC</p>
            <svg viewBox="0 0 2 3" aria-hidden="true">
                <path d="M0,0 L1,2 C1.5,3 1.5,3 2,3 L2,0 Z" />
            </svg>
        </div>
        <div class="header_menu">
            <div class="header_links">
                {#each data.links as content, i}
                    <!-- svelte-ignore a11y-no-static-element-interactions -->
                    <div class="dropdown_component" aria-label="dropdown"  on:mouseenter={()=>{
                        const size = 3 * content.links.length
                        heights[i] = size + "em"
                    }} on:mouseleave={()=>{
                        heights[i] = 0
                    }}>
                        {#if active == i}
                            <p class="active_page">{content.name}</p>
                        {:else}
                            <p>{content.name}</p>
                        {/if}

                        <div class="dropdown_content" style="height: {heights[i]}">
                            {#each content.links as link, j}
                                <a href={link.link}><p>{link.name}</p></a>
                            {/each}
                        </div>
                    </div>
                {/each}
            </div>
            <div class="header_right">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-cart3" viewBox="0 0 16 16">
                    <path d="M0 1.5A.5.5 0 0 1 .5 1H2a.5.5 0 0 1 .485.379L2.89 3H14.5a.5.5 0 0 1 .49.598l-1 5a.5.5 0 0 1-.465.401l-9.397.472L4.415 11H13a.5.5 0 0 1 0 1H4a.5.5 0 0 1-.491-.408L2.01 3.607 1.61 2H.5a.5.5 0 0 1-.5-.5M3.102 4l.84 4.479 9.144-.459L13.89 4zM5 12a2 2 0 1 0 0 4 2 2 0 0 0 0-4m7 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4m-7 1a1 1 0 1 1 0 2 1 1 0 0 1 0-2m7 0a1 1 0 1 1 0 2 1 1 0 0 1 0-2"/>
                </svg>
            </div>
        </div>
    </div>
</header>

