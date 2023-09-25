<script>
	import Page from '../+page.svelte';
	import Phoebe from '$lib/assets/phoebe.jpg';
</script>

<div class=" w-screen h-screen background flex justify-center font-main">
	<form class="mainContainer yCentre" action="/">
		<div class="headContainer">
			<h1>Add profile</h1>
			<p class="subtitle">Add a profile for another person watching Netflix.</p>
		</div>

		<div class="entryContainer flex">
			<img src={Phoebe} alt="profile" class=" object-cover w-[9vw] h-[9vw] overflow rounded-md" />
			<div class="nameSelect">
				<input type="text" placeholder="Name" class="yCentre" />
			</div>
			<div class="yCentre h-[2vw] checkContainer relative">
				<span class="toolTip"
					>If selected, this profile will only see TV shows and movies rated for ages 12 and under.</span
				>

				<span class="checkmark" />
				<input id="kidCheck" type="checkbox" checked="checked" />
				<label for="kidCheck" class=" text-[1.25vw] align-middle">Kid?</label>
			</div>
		</div>

		<div class="flex gap-[1vw]">
			<input type="button" value="Continue" class="submitButton continueButton" />
			<input type="submit" value="Cancel" class="submitButton cancelButton" />
		</div>
	</form>
</div>

<style>
	.checkContainer .toolTip {
		transition: opacity 300ms;
		position: absolute;
		z-index: 1;
		opacity: 0;

		background-color: white;
		color: black;
		text-align: center;
		padding: 1vw;
		width: 15vw;
		transform: translate(-30%, -120%);
	}
	.checkContainer:hover .toolTip {
		transition: all 1000ms;
		opacity: 1;
	}
	.submitButton {
		font-size: 1.25vw;
		padding: 2vw;
		padding-top: 0.5vw;
		padding-bottom: 0.5vw;
		color: white;
		cursor: pointer;
	}
	.continueButton {
		font-weight: bold;
		background-color: white;
		color: black;
	}
	.continueButton:hover {
		background-color: red;
		color: white;
	}
	.cancelButton {
		border: 1px solid #7f7f7f;
		color: #7f7f7f;
	}
	.cancelButton:hover {
		border: 1px solid white;
		color: white;
	}

	.mainContainer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		color: white;
		width: 40%;
		gap: 10px;
	}
	.headContainer {
	}
	.headContainer h1 {
		font-size: 4vw;
	}
	.headContainer p {
		color: gray;
		font-size: 1.25vw;
	}
	.entryContainer {
		border-top: 1px solid #333333;
		border-bottom: 1px solid #333333;
		display: flex;
		margin-top: 0.5vw;
		padding-top: 1.5vw;
		padding-bottom: 1.5vw;

		gap: 1vw;
	}
	.nameSelect {
		flex: 1;
	}
	.nameSelect input {
		background-color: #656565;
		width: 100%;
		height: 2.5vw;
		padding: 1vw;
		outline: none;
		font-size: 1.1vw;
	}

	.nameSelect input::placeholder {
		color: #cacaca;
	}
	.yCentre {
		position: relative;
		top: 50%;
		-webkit-transform: translateY(-50%);
		-ms-transform: translateY(-50%);
		transform: translateY(-50%);
	}

	[type='checkbox'] {
		width: 2vw;
		height: 2vw;
		color: dodgerblue;
		vertical-align: middle;
		-webkit-appearance: none;
		background: none;
		border: 0;
		outline: 0;
		flex-grow: 0;
		transition: background 300ms;
		cursor: pointer;
	}

	/* Pseudo element for check styling */

	[type='checkbox']::before {
		content: '';
		color: transparent;
		display: block;
		width: inherit;
		height: inherit;
		border-radius: inherit;
		border: 0;
		background-color: transparent;
		background-size: contain;
		border: 1px solid #333333;
	}

	[type='checkbox']:checked::before {
		box-shadow: none;
		background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E %3Cpath d='M15.88 8.29L10 14.17l-1.88-1.88a.996.996 0 1 0-1.41 1.41l2.59 2.59c.39.39 1.02.39 1.41 0L17.3 9.7a.996.996 0 0 0 0-1.41c-.39-.39-1.03-.39-1.42 0z' fill='%23fff'/%3E %3C/svg%3E");
	}

	/* IE */

	[type='checkbox']::-ms-check {
		content: '';
		color: transparent;
		display: block;
		width: inherit;
		height: inherit;
		border-radius: inherit;
		border: 0;
		background-color: transparent;
		background-size: contain;
	}

	[type='checkbox']:checked::-ms-check {
		box-shadow: none;
		background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E %3Cpath d='M15.88 8.29L10 14.17l-1.88-1.88a.996.996 0 1 0-1.41 1.41l2.59 2.59c.39.39 1.02.39 1.41 0L17.3 9.7a.996.996 0 0 0 0-1.41c-.39-.39-1.03-.39-1.42 0z' fill='%23fff'/%3E %3C/svg%3E");
	}
</style>
