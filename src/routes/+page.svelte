<script>
    import "../app.css";

	import ProfileButton from './comp/profileButton.svelte';
	import AddProfile from './comp/addProfile.svelte';

	import Apollo from '$lib/assets/apollo.jpg';
	import Athena from '$lib/assets/athena.jpg';
	import Adonis from '$lib/assets/adonis.jpg';
	import Phoebe from '$lib/assets/phoebe.jpg';

	const data = [
		{ Name: 'Apollo', Icon: Apollo },
		{ Name: 'Athena', Icon: Athena },
		{ Name: 'Adonis', Icon: Adonis },
		{ Name: 'Phoebe', Icon: Phoebe }
	];
</script>

<div class="background w-screen h-screen font-main">
	<div class="flex flex-col gap-10 yCentre">
		<h1 class="text-white text-center text-[3.5vw]">Who's watching?</h1>
		<div class=" flex w-full justify-center gap-10">
			{#each data as profile}
				<ProfileButton data={profile} />
			{/each}
			<AddProfile />
		</div>
		<form action="/profilemanagement" class=" justify-center m-auto pt-10">
			<input type="submit" value="Manage Profiles" class="manageButton px-8 py-2" />
		</form>
	</div>
</div>

<style>
	
	.manageButton {
		cursor: pointer;
		font-size: 1.25vw;
		color: gray;
		border: 1px solid gray;
	}
	.manageButton:hover {
		color: white;
		border: 1px solid white;
		
	}
	
	
</style>
