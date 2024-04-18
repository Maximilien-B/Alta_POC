<script>

</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<div class="page" on:scroll={(e) => {
		console.log("scrolled uwu")
		console.log(e)
	}}>
		<section class="header_pvk">
			<h1><span class="colored_header_pvk">PF1</span>. Polyvoks</h1>
			<p>A double-stereo filter.</p>
		</section>
		<section class="presentation_video">
			<div class="dark-filter"></div>
			<div class="sci-fi-bg"></div>
			<div class="top_left_deco">
				<div></div>
				<svg viewBox="0 0 2 3" aria-hidden="true" fill="currentColor">
					<path d="M0,0 L0,3 C0.5,3 0.5,3 1,2 L2,0 Z" />
				</svg>
			</div>
			<div class="bottom_right_deco">
				<svg viewBox="0 0 2 3" aria-hidden="true" fill="currentColor">
					<path d="M0,0 L1,2 C1.5,3 1.5,3 2,3 L2,0 Z" />
				</svg>
				<div></div>
			</div>
		</section>
		<section class="paragraph_container">
			<h1><span class="colored_header_pvk">the classic Soviet filter</span></h1>
			<p>POLIVOKS PF3 double-stereo filter utilizes the classic Soviet filter chip for a unique and iconic filter tone.  Two independent 12dB multi-mode filters that can be controlled by a single cutoff knob. Turning the filter into a 24dB filter, when connected in series. When connected in stereo, you can achieve interesting effects by using different modes to each channel. A noise generator is on board pre-filter and can be used separately as a source of white and pink noise. Volume as well as clean and processed signal balance per channel. Can be used as two independent filters or stereo mode.</p>
		</section>
		<section class="double_paragraph">
			<div class="left_prgph_container">
				<p>
					From ethereal drones to pulsating rhythms, the PF3 invites you on a journey of sonic exploration like no other. Its intuitive interface beckons you to dive deep into a world of modulation and harmonics, where every twist of a knob unveils a new sonic landscape. Whether you're a seasoned musician or an aspiring producer, the Polyvox PF3 promises to ignite your imagination and elevate your sound to unprecedented heights. Brace yourself for an auditory adventure that will astonish and inspire.
				</p>
			</div>
			<div class="right_prgph_container"></div>
		</section>
		<section>

		</section>
	</div>

</section>

