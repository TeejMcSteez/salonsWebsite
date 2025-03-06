<script>
    import work1 from "$lib/assets/works/work1.jpg";
    import work2 from "$lib/assets/works/work2.jpg";
    import work4 from "$lib/assets/works/work4.jpg";
    import work6 from "$lib/assets/works/work6.jpg";
    import work7 from "$lib/assets/works/work7.jpg";
    import work8 from "$lib/assets/works/work8.jpg";

    function scrollTop() {
        window.scroll({top: 0, behavior: "smooth"});
    }
</script>

<div id="container" class="container dark:bg-neutral-500 min-w-screen min-h-screen overflow-auto">

    <div class="flex flex-row justify-between bg-indigo-300">
        <h1 class="m-4 bold text-2xl">My Work</h1>
        <a href="/" class="m-4 hover:animate-pulse hover:bg-neutral-300 rounded-xl p-2">Home</a>
    </div>
    
    <div class="grid flex flex-col place-content-center m-3">
        <div class="min-h-screen mb-3">
            <img src={work1} alt="">
        </div>
        <div class="min-h-screen mb-3">
            <img src={work2} alt="">
        </div>
        <div class="min-h-screen mb-3">
            <img src={work4} alt="">
        </div>
        <div class="min-h-screen mb-3">
            <img src={work6} alt="">
        </div>
        <div class="min-h-screen mb-3">
            <img src={work7} alt="">
        </div>
        <div class="min-h-screen mb-3">
            <img src={work8} alt="">
        </div>
    </div>

    <footer class="flex flex-col items-center m-2 p-2">
        <button type="button" class="p-2 bg-neutral-600 rounded-xl hover:animate-pulse hover:bg-neutral-300" on:click={scrollTop} on:keydown={(e) => e.key === 'Enter' && scrollTop()} aria-roledescription="button">Scroll to Top</button>
    </footer>
</div>