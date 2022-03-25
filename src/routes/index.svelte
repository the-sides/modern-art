<script>
	import ad from '$static/ad.gif';
	import database from '$lib/db';

	const getTime = time => {
		const date = new Date(time)
		return `${date.getHours()}:${date.getMinutes()}:${date.getSeconds()}`
	}

	async function getData() {
		const { data, error } = await database.from('Messages').select();
		if (error) throw new Error(error.message);
		return data.map(msg => ({
			...msg, 
			created_at: getTime(msg.created_at)
		}));
	}
	async function sendMessage(content) {
		const { data, error } = await database.from('Messages').insert({ content });
		if (error) throw new Error(error.message);
		else window.location.reload()
		return data;
	}
	const onSubmit = (ev) => {
		console.log(ev.target.composer.value);
		sendMessage(ev.target.composer.value);
	};
</script>

<!-- A <main> is the same as <div>, but more clear -->
<main
	class="max-w-[1138px] mx-auto px-4 xl:px-0 py-8 relative min-h-screen max-w-screen overflow-hidden"
>
	<div class="relative z-10">
		<div>
			<img src="banner.jpg" alt="Logo Banner" class="w-full object-cover" />
		</div>

		<div class="mt-3 grid grid-cols-2 md:grid-cols-3 gap-3 items-start">
			<div class="flex-1 h-[400px] bg-[#90F7DE] p-4 text-[22px]  flex flex-col">
				<div class="overflow-auto mb-3">
					{#await getData()}
						<p>Fetching data...</p>
					{:then data}
						{#each data as messageObj}
							<div class="flex justify-between py-2 border-b border-lime-400">
								<p class="text-sm">{messageObj.content}</p>
								<span class="text-xs">{messageObj.created_at}</span>
							</div>
						{/each}
					{:catch error}
						<p>Something went wrong while fetching the data:</p>
						<pre>{error}</pre>
					{/await}
				</div>
				<form class="mt-auto flex" on:submit|preventDefault={onSubmit}>
					<input type="text" name="composer" id="composer" class="px-2 flex-1 placeholder:text-opacity-50" placeholder="enter message here" />
					<button type="submit">
						<svg
							width="36"
							height="36"
							viewBox="0 0 24 24"
							fill="none"
							xmlns="http://www.w3.org/2000/svg"
						>
							<path
								d="M12 22C6.47967 21.9939 2.00606 17.5203 2 12V11.8C2.10993 6.30453 6.63459 1.92796 12.1307 2.00088C17.6268 2.07381 22.0337 6.56889 21.9978 12.0653C21.9619 17.5618 17.4966 21.9989 12 22ZM12 4C7.58172 4 4 7.58172 4 12C4 16.4183 7.58172 20 12 20C16.4183 20 20 16.4183 20 12C19.995 7.58378 16.4162 4.00496 12 4ZM12 17L10.59 15.59L13.17 13H7V11H13.17L10.59 8.41L12 7L17 12L12 17Z"
								fill="#2E3A59"
							/>
						</svg>
					</button>
				</form>
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
			<div class="whitespace-nowrap">
				the internet is not free or happy anymore there is only capitalism and sorrow
			</div>
		</div>

		<figure class="mt-4 w-full h-[292px]">
			<!-- This is an alt way to import images/gifs, but with performance boost -->
			<img src={ad} alt="Advertisment" class="w-full h-full object-cover" />
		</figure>

		<div class="border-t-2 border-black mt-8 pt-4 text-[48px] leading-[52px]">
			<span>i ran out of ideas</span>
			<br />
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
