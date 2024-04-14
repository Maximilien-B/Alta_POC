<script>
	import { page } from '$app/stores';
	import logo from '$lib/images/logo.png';
	import github from '$lib/images/github.svg';
</script>

<header>
    <div class="header_container">
        <div class="header_logo">
            <a href="/">
                <img src={logo} alt="logo" />
            </a>
        </div>
        <div class="header_links">
            <a href="/">Home</a>
            <a href="/about">About</a>
        </div>
        <div class="header_github">
            <a href="https://github.com/michal-josef-spacek">
                <img src={github} alt="github" />
            </a>
        </div>
</header>

