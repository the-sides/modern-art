<script>
	import ad from '$static/ad.gif'
</script>

<!-- A <main> is the same as <div>, but more clear -->
<main class="max-w-[1138px] mx-auto px-4 xl:px-0 py-8 relative min-h-screen max-w-screen overflow-hidden">
	<div class="relative z-10">
		<div>
			<img src="banner.jpg" alt="Logo Banner" class="w-full object-cover" />
		</div>

		<div class="mt-3 grid grid-cols-2 md:grid-cols-3 gap-3 items-start">
			<div class="flex-1 min-h-[400px] bg-[#90F7DE] p-4 text-[22px]">
				i want to put a chatbox here i put one on one of my really old websites and everyone was
				just mean as hell to each other all the time like they would fight through the chatbox on
				this random fucking website i owned it was great
			</div>
			<div class="flex-1">
				<div class="max-h-[260px] overflow-auto bg-[#C4C4C4] p-4 text-[22px]">
					a little scrollbox with like our names and what we like to do or something. memorialize
					our legacy of being lazy and not working on the website. a little scrollbox with like our
					names and what we like to do or something. memorialize our legacy of being lazy and not
					working on the website.
				</div>
				<img src="tohru-tongue.gif" alt="Blue water" class="mt-3 object-cover w-full h-full" />
			</div>
			<div>
				<img src="blue.jpg" alt="Blue water" class="object-cover w-full h-full" />
				<div class="mt-5 text-[24px]">
					we can put something dumb here like joker beatbox or an image of shinji in a chair. go
					crazy go stupid go crazy go s
				</div>
			</div>
			<div>
				<img src="dominos.gif" alt="Blue water" class="object-cover w-full h-full" />

			</div>
			<div class="whitespace-nowrap">the internet is not free or happy anymore there is only capitalism and sorrow</div>
		</div>

		<figure class="mt-4 w-full h-[292px]">
			<!-- This is an alt way to import images/gifs, but with performance boost -->
			<img src={ad} alt="Advertisment" class="w-full h-full object-cover">
		</figure>

		<div class="border-t-2 border-black mt-8 pt-4 text-[48px] leading-[52px]">
			<span>i ran out of ideas</span>
			<br>
			<span class="text-red-600">just use more memes or something</span>
		</div>

	</div>

	<!-- Background image -->
	<!-- Using position:absolute to span the back -->
</main>
<img
	src="bg.jpg"
	alt="Background"
	class="absolute inset-0 w-full h-full object-cover opacity-[0.15]"
/>
