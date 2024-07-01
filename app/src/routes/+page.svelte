<script>
    import { base } from '$app/paths'
	import ThreeDViewer from "./components/3DViewer/ThreeDViewer.svelte";

	let show_teapot = false
	let yb_links = ["https://www.youtube.com/embed/MifoWuu6a98", "https://www.youtube.com/embed/T4MhAel0PoM"]
	function switchModel() {
		show_teapot = !show_teapot;
	}
	function fadeOnScrollDown(node) {
		const observer = new IntersectionObserver(entries => {
			for (var entry of entries) {
				if (entry.isIntersecting && entry.intersectionRatio > 0) {
					if (entry.boundingClientRect.top > entry.rootBounds.top || entry.boundingClientRect.bottom < entry.rootBounds.bottom) {
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

	let clicked_vid_1, clicked_vid_2 = false
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section >
	<div class="page" >
		<section class="header_pvk">
			<div>
				<h1><span class="colored_header_pvk">PF1</span>. Polyvoks</h1>
				<p>A double-stereo filter.</p>
			</div>
			<div class="dl_content">
				<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-file-earmark-pdf-fill" viewBox="0 0 16 16">
					<path d="M5.523 12.424q.21-.124.459-.238a8 8 0 0 1-.45.606c-.28.337-.498.516-.635.572l-.035.012a.3.3 0 0 1-.026-.044c-.056-.11-.054-.216.04-.36.106-.165.319-.354.647-.548m2.455-1.647q-.178.037-.356.078a21 21 0 0 0 .5-1.05 12 12 0 0 0 .51.858q-.326.048-.654.114m2.525.939a4 4 0 0 1-.435-.41q.344.007.612.054c.317.057.466.147.518.209a.1.1 0 0 1 .026.064.44.44 0 0 1-.06.2.3.3 0 0 1-.094.124.1.1 0 0 1-.069.015c-.09-.003-.258-.066-.498-.256M8.278 6.97c-.04.244-.108.524-.2.829a5 5 0 0 1-.089-.346c-.076-.353-.087-.63-.046-.822.038-.177.11-.248.196-.283a.5.5 0 0 1 .145-.04c.013.03.028.092.032.198q.008.183-.038.465z"/>
					<path fill-rule="evenodd" d="M4 0h5.293A1 1 0 0 1 10 .293L13.707 4a1 1 0 0 1 .293.707V14a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V2a2 2 0 0 1 2-2m5.5 1.5v2a1 1 0 0 0 1 1h2zM4.165 13.668c.09.18.23.343.438.419.207.075.412.04.58-.03.318-.13.635-.436.926-.786.333-.401.683-.927 1.021-1.51a11.7 11.7 0 0 1 1.997-.406c.3.383.61.713.91.95.28.22.603.403.934.417a.86.86 0 0 0 .51-.138c.155-.101.27-.247.354-.416.09-.181.145-.37.138-.563a.84.84 0 0 0-.2-.518c-.226-.27-.596-.4-.96-.465a5.8 5.8 0 0 0-1.335-.05 11 11 0 0 1-.98-1.686c.25-.66.437-1.284.52-1.794.036-.218.055-.426.048-.614a1.24 1.24 0 0 0-.127-.538.7.7 0 0 0-.477-.365c-.202-.043-.41 0-.601.077-.377.15-.576.47-.651.823-.073.34-.04.736.046 1.136.088.406.238.848.43 1.295a20 20 0 0 1-1.062 2.227 7.7 7.7 0 0 0-1.482.645c-.37.22-.699.48-.897.787-.21.326-.275.714-.08 1.103"/>
				</svg>
				<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-paperclip" viewBox="0 0 16 16">
					<path d="M4.5 3a2.5 2.5 0 0 1 5 0v9a1.5 1.5 0 0 1-3 0V5a.5.5 0 0 1 1 0v7a.5.5 0 0 0 1 0V3a1.5 1.5 0 1 0-3 0v9a2.5 2.5 0 0 0 5 0V5a.5.5 0 0 1 1 0v7a3.5 3.5 0 1 1-7 0z"/>
				</svg>
			</div>
		</section>
		<section class="presentation_video" use:fadeOnScrollDown>
			<div class="dark-filter"></div>
			<div class="synth_images">
				<div class="synth_1_pf s_img"></div>
				<div class="synth_2_pf s_img"></div>
				<div class="synth_3_pf s_img"></div>
			</div>
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
		<section class="double_paragraph" id="cp-2" use:fadeOnScrollDown>
			<div class="text_prgph_container">
				<p use:fadeOnScrollDown>
					From ethereal drones to pulsating rhythms, the <span class="colored_header_pvk">PF3</span> invites you on a journey of sonic exploration like no other. Its intuitive interface beckons you to dive deep into a world of modulation and harmonics. Whether you're a seasoned musician or an aspiring producer, the <span class="colored_header_pvk">Polyvox PF3</span> promises to ignite your imagination and elevate your sound to unprecedented heights. Brace yourself for an auditory adventure that will <span class="colored_header_pvk">astonish</span> and <span class="colored_header_pvk">inspire</span>.
				</p>
			</div>
			<div id="pf-img1" class="section_img_bg"></div>
		</section>
		<section class="paragraph_container" use:fadeOnScrollDown>
			<h1><span class="colored_header_pvk">Warning!</span></h1>
			<p>Before using the device, turn it on for 5-7 minutes and let it stand. The control transistor should warm up. So that in SOFT mode there is no feedback when the FREQ knobs are in zero position. If you overdo it. The UD1208 chips used in the filter are very sensitive and are never the same. Therefore you will not mathematically get two identical filters. Which is an advantage when using the unit in stereo. </p>
		</section>
		<section class="double_paragraph" id="cp-1" use:fadeOnScrollDown>
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
		<section class="viewer" use:fadeOnScrollDown>
			<div class="top_left_deco" id="deco_2">
				<div><p>Polyvoks | PF3</p></div>
				<svg viewBox="0 0 2 3" aria-hidden="true" fill="currentColor">
					<path d="M0,0 L0,3 C0.5,3 0.5,3 1,2 L2,0 Z" />
				</svg>
			</div>
			<div class="bottom_right_deco" id="deco_3">
				<svg viewBox="0 0 2 3" aria-hidden="true" fill="currentColor">
					<path d="M0,0 L1,2 C1.5,3 1.5,3 2,3 L2,0 Z" />
				</svg>
				<div>
					<label class="cb_container">
						<input type="radio" checked="checked" name="radio" class="first_cb">
						<span class="checkmark" id="cb_1"></span>
					</label>
					<label class="cb_container">
						<input type="radio" name="radio" class="second_cb">
						<span class="checkmark" id="cb_2"></span>
					</label>
					<label class="cb_container">
						<input type="radio" name="radio" class="third_cb">
						<span class="checkmark" id="cb_3"></span>
					</label>
				</div>
			</div>
			{#if show_teapot}
				<ThreeDViewer ModelPath="{base}/models/the_utah_teapot.glb" objectVector={[0.1,0.1,0.1,-4]}/>
			{:else}
				<ThreeDViewer ModelPath="{base}/models/scene.glb" objectVector={[0.04,0.04,0.04,0]}/>
			{/if}

		</section>
		<section class="buy_section">
			<h1>Get yours <span class="colored_header_pvk">Today</span>.</h1>
			<div class="buy_btns">
				<div class="left_btn">
					<div>

						<p>Add to Cart</p>
					</div>
					<svg viewBox="0 0 2 3" aria-hidden="true" fill="currentColor">
						<path d="M0,0 L0,3 C0.5,3 0.5,3 1,2 L2,0 Z" />
					</svg>
				</div>
				<div class="right_btn">
					<svg viewBox="0 0 2 3" aria-hidden="true" fill="currentColor">
						<path d="M0,0 L1,2 C1.5,3 1.5,3 2,3 L2,0 Z" />
					</svg>
					<div>
						<p>Order now</p>
					</div>

				</div>
			</div>
		</section>
		<section class="reviewSection" use:fadeOnScrollDown>
			<div class="YTvids" id="mini_carousel">
				<div class="vid" id="vid_1">
					{#if clicked_vid_1}
						<iframe
								src={yb_links[0]}
								title="YouTube video player"
								allow="accelerometer; autoplay; encrypted-media; gyroscope; gyroscope; picture-in-picture; web-share"
								allowfullscreen
						></iframe>
					{:else}
						<img src="https://img.youtube.com/vi/MifoWuu6a98/maxresdefault.jpg" alt="YouTube Thumbnail" class="thumbnail" on:click={()=>{ clicked_vid_1 = true}}>
						<div class="floating_loader_text" on:click={()=>{ clicked_vid_1 = true}}>
							<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-play" viewBox="0 0 16 16">
								<path d="M10.804 8 5 4.633v6.734zm.792-.696a.802.802 0 0 1 0 1.392l-6.363 3.692C4.713 12.69 4 12.345 4 11.692V4.308c0-.653.713-.998 1.233-.696z"/>
							</svg>
						</div>
					{/if}
				</div>
				<div class="vid" id="vid_2">
					{#if clicked_vid_2}
						<iframe
								src={yb_links[1]}
								title="YouTube video player"
								allow="accelerometer; autoplay; encrypted-media; gyroscope; gyroscope; picture-in-picture; web-share"
								allowfullscreen
						></iframe>
					{:else}
						<img src="https://img.youtube.com/vi/T4MhAel0PoM/maxresdefault.jpg" alt="YouTube Thumbnail" class="thumbnail" on:click={()=>{ clicked_vid_2 = true}}>
						<div class="floating_loader_text" on:click={()=>{ clicked_vid_2 = true}}>
							<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-play" viewBox="0 0 16 16">
								<path d="M10.804 8 5 4.633v6.734zm.792-.696a.802.802 0 0 1 0 1.392l-6.363 3.692C4.713 12.69 4 12.345 4 11.692V4.308c0-.653.713-.998 1.233-.696z"/>
							</svg>
						</div>
					{/if}


				</div>
			</div>
			<div>
				<p>Check out those Awesome Videos for more Details !</p>
			</div>
		</section>
	</div>

</section>

