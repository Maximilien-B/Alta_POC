<script>
	function fadeOnScrollDown(node) {
		const observer = new IntersectionObserver(entries => {
			for (var entry of entries) {
				if (entry.isIntersecting && entry.intersectionRatio > 0) {
					if (entry.boundingClientRect.top > entry.rootBounds.top) {
						node.style.opacity = '1';
						node.style.transform = 'translateY(-10px)';
						observer.unobserve(node);
					}
				}
			}
		}, { threshold: 0.5 });
		observer.observe(node);

		return {
			destroy() {
				observer.disconnect();
			}
		};
	}
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section >
	<div class="page" >
		<section class="header_pvk">
			<h1><span class="colored_header_pvk">PF1</span>. Polyvoks</h1>
			<p>A double-stereo filter.</p>
		</section>
		<section class="presentation_video" use:fadeOnScrollDown>
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
		<div id="bg"></div>
		<section class="paragraph_container" use:fadeOnScrollDown>
			<h1><span class="colored_header_pvk">the classic Soviet filter</span></h1>
			<p>POLIVOKS PF3 double-stereo filter utilizes the classic Soviet filter chip for a unique and iconic filter tone.  Two independent 12dB multi-mode filters that can be controlled by a single cutoff knob. Turning the filter into a 24dB filter, when connected in series. When connected in stereo, you can achieve interesting effects by using different modes to each channel. A noise generator is on board pre-filter and can be used separately as a source of white and pink noise. Volume as well as clean and processed signal balance per channel. Can be used as two independent filters or stereo mode.</p>
		</section>
		<section class="double_paragraph" use:fadeOnScrollDown>
			<div class="text_prgph_container">
				<p use:fadeOnScrollDown>
					From ethereal drones to pulsating rhythms, the <span class="colored_header_pvk">PF3</span> invites you on a journey of sonic exploration like no other. Its intuitive interface beckons you to dive deep into a world of modulation and harmonics, where every twist of a knob unveils a new sonic landscape. Whether you're a seasoned musician or an aspiring producer, the <span class="colored_header_pvk">Polyvox PF3</span> promises to ignite your imagination and elevate your sound to unprecedented heights. Brace yourself for an auditory adventure that will <span class="colored_header_pvk">astonish</span> and <span class="colored_header_pvk">inspire</span>.
				</p>
			</div>
			<div id="pf-img1" class="section_img_bg"></div>
		</section>
		<section class="paragraph_container" use:fadeOnScrollDown>
			<h1><span class="colored_header_pvk">Warning!</span></h1>
			<p>Before using the device, turn it on for 5-7 minutes and let it stand. The control transistor should warm up. So that in SOFT mode there is no feedback when the FREQ knobs are in zero position. If you overdo it. The UD1208 chips used in the filter are very sensitive and are never the same. Therefore you will not mathematically get two identical filters. Which is an advantage when using the unit in stereo. </p>
		</section>
		<section class="double_paragraph" use:fadeOnScrollDown>
			<div class="text_prgph_container">
				<p>
					available in <span class="colored_header_pvk">three</span> stylish <span class="colored_header_pvk">colors</span>, this sleek synth offers musicians and producers a versatile tool for sonic exploration. Choose from classic <span class="colored_header_pvk">black</span>, <span class="colored_header_pvk">maize yellow</span>, <span class="colored_header_pvk">dark grey</span> or minimalist <span class="colored_header_pvk">white</span> to suit your aesthetic preferences. With its compact design and captivating hues, the Polyvox PF3 adds a touch of sophistication to any studio setup or live performance.
				</p>
			</div>
			<div id="pf-img2" class="section_img_bg"></div>
		</section>
		<section use:fadeOnScrollDown
				class="spec_header">
			<h1><span class="colored_header_pvk">Specifications</span></h1>
		</section>
		<section class="specs_container" use:fadeOnScrollDown>
			<div class="pf3_options">
				<ul>
					<li><p><span class="colored_header_pvk">ER modes</span> - Lowpass, Bandpass, Hi-pass, Notch.</p></li>
					<li><p><span class="colored_header_pvk">E generator</span>  - pink, white and channel balancing.</p></li>
					<li><p><span class="colored_header_pvk">ER 1 and FILTER 2</span> - CV  controls.</p></li>
					<li><p>switches to control two filters and CV at the same time with one slice knob.</p></li>
					<li><p>/HARD cutoff control</p></li>
				</ul>
			</div>
			<div class="pf3_specs">
				<ul>
					<li><p><span class="colored_header_pvk">Input audio signal level</span>:  Max 1.5 V</p></li>
					<li><p><span class="colored_header_pvk">Modulation CV input</span>:  - 5 to +5 V or 0 to + 10V</p></li>
					<li><p><span class="colored_header_pvk">Power supply</span>: universal mains adapter 100-220V / 12V 1A out</p></li>
					<li><p><span class="colored_header_pvk">Filter weight</span>: 0,7kg</p></li>
					<li><p><span class="colored_header_pvk">Packed weight</span>: 1 kg</p></li>
					<li><p><span class="colored_header_pvk">Dimensions</span>: 175x135x50mm</p></li>
				</ul>
			</div>
		</section>
	</div>

</section>

