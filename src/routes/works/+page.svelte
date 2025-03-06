<script>
    import work1 from "$lib/assets/works/work1.jpg";
    import work2 from "$lib/assets/works/work2.jpg";
    import work4 from "$lib/assets/works/work4.jpg";
    import work6 from "$lib/assets/works/work6.jpg";
    import work7 from "$lib/assets/works/work7.jpg";
    import work8 from "$lib/assets/works/work8.jpg";
</script>

<div id="container" class="container min-w-screen min-h-screen overflow-auto snap-y snap-mandatory">

    <div class="flex flex-row justify-between m-5 p-2">
        <h1 class="m-4 bold text-2xl">My Work</h1>
        <a href="/" class="m-4 hover:animate-pulse">Home</a>
    </div>
    
    <div class="grid flex flex-col place-content-center m-3">
        <div class="min-h-screen snap-start">
            <img src={work1} alt="">
        </div>
        <div class="min-h-screen snap-start">
            <img src={work2} alt="">
        </div>
        <div class="min-h-screen snap-start">
            <img src={work4} alt="">
        </div>
        <div class="min-h-screen snap-start">
            <img src={work6} alt="">
        </div>
        <div class="min-h-screen snap-start">
            <img src={work7} alt="">
        </div>
        <div class="min-h-screen snap-start">
            <img src={work8} alt="">
        </div>
    </div>

</div>