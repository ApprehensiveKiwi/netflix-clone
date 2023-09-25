<script>
	import Fa from 'svelte-fa';
	import { faPlusCircle } from '@fortawesome/free-solid-svg-icons';
</script>

<a
    href="/add">
	<div
		class="container"
	>
		<Fa icon={faPlusCircle} class="" />
	</div>
    <p class="text text-center font-main pt-6 text-[1.25vw] ">
        Add Profile
    </p>
</a>

<style>
    .container {
        display: grid;
        place-content: center;
        color: gray;
        font-size: 7vw;

        width: 10vw;
        height: 10vw;
        border-radius: 0.375rem/* 6px */;
        transition: all .2s ease-out;
    }
    .container:hover {
        background-color: white;
    }
    .text {
        color: gray;
    }
    .container:hover ~ .text { color: whitesmoke; }

</style>
