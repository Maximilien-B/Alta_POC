<script>
	import { page } from '$app/stores';
	import logo from '$lib/images/logo.png';
	import github from '$lib/images/github.svg';
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
                <div class="dropdown_component">
                    <p class="active_page">products</p>
                    <div class="dropdown_content">
                        <a href="/">Text 1</a>
                        <a href="/">Text 2</a>
                    </div>
                </div>
                <div class="dropdown_component">
                    <p>shop</p>
                </div>
                <div class="dropdown_component">
                    <p>retailers</p>
                </div>
                <div class="dropdown_component">
                    <p>discontinued</p>
                </div>
                <div class="dropdown_component">
                    <p>About</p>
                </div>

            </div>
            <div class="header_right">
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-cart3" viewBox="0 0 16 16">
                    <path d="M0 1.5A.5.5 0 0 1 .5 1H2a.5.5 0 0 1 .485.379L2.89 3H14.5a.5.5 0 0 1 .49.598l-1 5a.5.5 0 0 1-.465.401l-9.397.472L4.415 11H13a.5.5 0 0 1 0 1H4a.5.5 0 0 1-.491-.408L2.01 3.607 1.61 2H.5a.5.5 0 0 1-.5-.5M3.102 4l.84 4.479 9.144-.459L13.89 4zM5 12a2 2 0 1 0 0 4 2 2 0 0 0 0-4m7 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4m-7 1a1 1 0 1 1 0 2 1 1 0 0 1 0-2m7 0a1 1 0 1 1 0 2 1 1 0 0 1 0-2"/>
                </svg>
            </div>
        </div>
    </div>
</header>

