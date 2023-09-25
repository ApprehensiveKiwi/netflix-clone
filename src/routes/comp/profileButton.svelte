<script>
    export let data
</script>
<a
    href="/user/{data.Name}?q=home">
    <div class="container w-[10vw] h-[10vw] overflow-clip rounded-md">
        <img src={data.Icon} alt={data.Name} class="w-full h-full object-cover">
    </div>
    <p class="text-center font-main pt-6 text-[1.25vw] ">
        {data.Name}
    </p>
</a>
<style>
    p {
        color: gray;
    }
    a:hover p { color: whitesmoke; }

    a:hover .container {
        outline: 4px solid white;
    }
    img {
        transition: all .1s ease-out;
    }
    a:hover img {
        transform: scale(1.05);
    }
</style>
