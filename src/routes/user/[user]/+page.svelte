<script>
	import { page } from '$app/stores';
	let user = $page.params.user;
	import Fa from 'svelte-fa';
	import {
		faSearch,
		faBell,
		faArrowLeft,
		faCaretDown,
		faPencil,
		faPersonArrowUpFromLine,
		faRotateForward,
		faArrowsRotate,
		faQuestionCircle,
		faUser
	} from '@fortawesome/free-solid-svg-icons';
	import icon from '../../../lib/assets/adonis.jpg';
	import logo from '../../../lib/assets/logo.png';

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

<head>
	<title>Home</title>
</head>
<div class="background h-screen w-screen">
	<nav class="navbar font-main">
		<ul class="navList lg:text-[0.8vw] md:text-[1vw]">
			<li>
				<a href="?q=home">
					<img src={logo} alt="netflix logo" class="w-[100px] object-cover" />
				</a>
			</li>
			<li><a href="?q=home">Home</a></li>
			<li><a href="?q=shows">TV Shows</a></li>
			<li><a href="?q=movies">Movies</a></li>
			<li><a href="?q=new">New & Popular</a></li>
			<li><a href="?q=mylist">My List</a></li>
			<li><a href="?q=langs">Browse By Languages</a></li>
		</ul>
		<ul class="navList">
			<li><a href="../"><Fa icon={faSearch} /></a></li>
			<li><a href="../"><Fa icon={faBell} /></a></li>
			<li>
				<div class="profileButtonContainer cursor-pointer">
					<img
						src={data.find((item) => item.Name === user).Icon}
						alt="Profile"
						class="w-[35px] h-[35px] object-cover rounded-md"
					/>
					<div>
						<Fa icon={faCaretDown} />
					</div>
					<span class="toolTip text-[14px] flex flex-col">
							<ul class="flex flex-col gap-2 py-3 text-white">
								{#each data as profile}
									<li class="flex px-2 gap-2">
										<a href="../user/{profile.Name}">
											<img
												src={profile.Icon}
												alt={profile.Name}
												class="object-cover w-[35px] h-[35px] rounded-md"
											/>
											<p class=" self-center">{profile.Name}</p>
										</a>
									</li>
								{/each}
								<ul class="manageContainer px-2">
									<il>
										<a href="../../profilemanagement">
											<Fa icon={faPencil} size="1.5x" />
											<p>Manage Profiles</p>
										</a>
									</il>
									<il class="inactive">
										<a href="">
											<Fa icon={faArrowsRotate} size="1.5x" />
											<p>Transfer Profile</p>
										</a>
									</il>
									<il class="inactive">
										<a href="">
											<Fa icon={faUser} size="1.5x" />
											<p>Account</p>
										</a>
									</il>
									<il class="inactive">
										<a href="">
											<Fa icon={faQuestionCircle} size="1.5x" />
											<p>Help Centre</p>
										</a>
									</il>
								</ul>
								<a href="../../" class="hover:underline">Sign out of Netflix</a>
							</ul>
					</span>
				</div>
			</li>
		</ul>
	</nav>
	<div />
</div>

<style>
	.manageContainer {
		border-top: 1px solid #5a5a5a;
		border-bottom: 1px solid #5a5a5a;
		padding-top: 20px;
		padding-bottom: 20px;
		display: flex;
		flex-direction: column;
		justify-content: center;
	}
	.toolTip::before {
	content: '';
	position: absolute;
	display: block;    
	width: 0px;        
	left: 50%;
	top: 0;
	border: 15px solid transparent;
	border-top: 0;
	border-bottom: 15px solid black;
	transform: translate(250%, calc(-100%));

	}

	.navList li a:hover {
		color: gray;
	}
	.inactive {
		color: gray;
		pointer-events: none;
	}
	.manageContainer il a {
		display: flex;
		padding-left: 10px;
		gap: 20px;
	}
	.manageContainer il a:hover {
		text-decoration: underline;
	}
	.manageContainer il:not(:last-child) {
		padding-bottom: 15px;
	}

	.navbar {
		color: #e0e0e0;
		display: flex;
		justify-content: space-between;
		background-color: rgba(0, 0, 0, 0.472);
		height: 64px;
		padding: 60px;
		padding-top: 0px;
		padding-bottom: 0px;
	}
	.profileButtonContainer {
		position: relative;
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 13px;
	}
	.profileButtonContainer div {
		transition: all 200ms;
	}
	.profileButtonContainer:hover div {
		transform: rotate(180deg);
	}

	.navList {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 20px;
	}
	.profileButtonContainer span {
		visibility: hidden;
		opacity: 0;
		transition: opacity 1000ms;
	}
	.toolTip ul li a {
		display: flex;
		gap: 10px;
	}
	.toolTip ul li:hover {
		text-decoration: underline;
	}
	.profileButtonContainer .toolTip {
		width: 225px;
		transform: translate(-45%, 107.5%);
		gap: 20px;
		position: absolute;
		z-index: 1;
		opacity: 0;
		bottom: 0;
		background-color: rgba(0, 0, 0, 0.802);
		color: black;
		text-align: center;
	}
	.profileButtonContainer:hover span {
		visibility: visible;
		opacity: 1;
	}

</style>
