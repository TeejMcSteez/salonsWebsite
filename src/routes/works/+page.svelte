<script>
    import work1 from "$lib/assets/works/work1.jpg";
    import work2 from "$lib/assets/works/work2.jpg";
    import work4 from "$lib/assets/works/work4.jpg";
    import work6 from "$lib/assets/works/work6.jpg";
    import work7 from "$lib/assets/works/work7.jpg";
    import work8 from "$lib/assets/works/work8.jpg";
    
    // Add functionality for filtering hairstyle categories
    let currentCategory = "all";
    let works = [
        { img: work1, category: "coloring", title: "Flowing Curls", description: "Flowing curls with light blonde hair" },
        { img: work2, category: "coloring", title: "Light Blonde", description: "Natural-looking sun-kissed highlights" },
        { img: work4, category: "styling", title: "Formal Updo", description: "Elegant updo perfect for special occasions" },
        { img: work6, category: "haircuts", title: "Simple Cut", description: "Layered cut with even ends" },
        { img: work7, category: "coloring", title: "Vibrant Red", description: "Bold and vibrant red color transformation" },
        { img: work8, category: "styling", title: "Simple Cut with Highlights", description: "Elegant cut with highlights" }
    ];
    
    // Filter works based on selected category
    $: filteredWorks = currentCategory === "all" 
        ? works 
        : works.filter(work => work.category === currentCategory);
    
    function scrollTop() {
        window.scroll({top: 0, behavior: "smooth"});
    }
    
    let selectedImage = null;
    
    function openImage(work) {
        selectedImage = work;
    }
    
    function closeImage() {
        selectedImage = null;
    }
</script>

<div id="container" class="min-w-screen min-h-screen overflow-hidden bg-rose-50 text-gray-800">
    <!-- Header with salon info -->
    <header class="bg-white shadow-md">
        <div class="container mx-auto px-4 py-4 flex flex-col md:flex-row justify-between items-center">
            <h1 class="text-3xl font-bold text-rose-600 mb-2 md:mb-0">Beautiful Hair by Heather Melton</h1>
            <div class="flex items-center gap-6">
                <a href="/" class="font-medium text-white bg-rose-600 rounded-xl hover:bg-rose-500 hover:text-rose-600 transition duration-300 py-2 px-4">Home</a>
            </div>
        </div>
    </header>
    
    <!-- Hero banner -->
    <div class="bg-gradient-to-r from-rose-300 to-purple-300 text-gray-900 py-10 md:py-16">
        <div class="container mx-auto px-4 text-center">
            <h2 class="text-3xl md:text-4xl font-bold mb-4">Transforming Hair, Transforming Lives</h2>
            <p class="text-lg md:text-xl max-w-2xl mx-auto opacity-90 mb-6">Browse through my portfolio of real clients and amazing transformations.</p>
        </div>
    </div>
    
    <!-- Style category filter -->
    <div class="container mx-auto px-4 py-8">
        <h3 class="text-2xl font-semibold text-center mb-6">My Latest Work</h3>
        <div class="flex flex-wrap justify-center gap-3 mb-10">
            <button 
                class={`px-4 py-2 rounded-full transition duration-300 ${currentCategory === 'all' ? 'bg-rose-600 text-white' : 'bg-white hover:bg-rose-100'}`}
                on:click={() => currentCategory = 'all'}>
                All Styles
            </button>
            <button 
                class={`px-4 py-2 rounded-full transition duration-300 ${currentCategory === 'haircuts' ? 'bg-rose-600 text-white' : 'bg-white hover:bg-rose-100'}`}
                on:click={() => currentCategory = 'haircuts'}>
                Haircuts
            </button>
            <button 
                class={`px-4 py-2 rounded-full transition duration-300 ${currentCategory === 'coloring' ? 'bg-rose-600 text-white' : 'bg-white hover:bg-rose-100'}`}
                on:click={() => currentCategory = 'coloring'}>
                Coloring
            </button>
            <button 
                class={`px-4 py-2 rounded-full transition duration-300 ${currentCategory === 'styling' ? 'bg-rose-600 text-white' : 'bg-white hover:bg-rose-100'}`}
                on:click={() => currentCategory = 'styling'}>
                Styling
            </button>
        </div>
        
        <!-- Gallery grid with larger images -->
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-6 md:gap-8">
            {#each filteredWorks as work, i}
                <div 
                    class="bg-white rounded-lg overflow-hidden shadow-lg cursor-pointer transform transition duration-300 hover:shadow-xl"
                    on:click={() => openImage(work)}
                    on:keydown={(e) => e.key === 'Enter' && openImage(work)}
                    role="button"
                    tabindex="0">
                    <div class="relative">
                        <img src={work.img} alt={work.title} class="w-full h-96 object-cover" />
                        <div class="absolute top-0 right-0 bg-rose-600 text-white text-xs uppercase tracking-wider font-bold px-3 py-1 m-3 rounded-full">
                            {work.category}
                        </div>
                    </div>
                    <div class="p-4 text-center">
                        <h3 class="text-xl font-bold">{work.title}</h3>
                        <p class="text-gray-600">{work.description}</p>
                    </div>
                </div>
            {/each}
        </div>
    </div>
    
    <!-- Testimonials section -->
    <!-- <div class="bg-white py-12 mt-12">
        <div class="container mx-auto px-4">
            <h3 class="text-2xl font-semibold text-center mb-10">What My Clients Say</h3>
            </div>
        </div> -->
    </div>
    
    <!-- Fullscreen image viewer -->
    {#if selectedImage}
        <div class="fixed inset-0 bg-black bg-opacity-90 flex items-center justify-center z-20 p-4" on:click={closeImage}>
            <div class="relative max-w-5xl w-full h-full flex items-center justify-center" on:click|stopPropagation>
                <img src={selectedImage.img} alt={selectedImage.title} class="max-w-full max-h-full object-contain" />
                <div class="absolute bottom-0 left-0 right-0 bg-black bg-opacity-70 text-white p-4 text-center">
                    <h3 class="text-xl font-bold">{selectedImage.title}</h3>
                    <p>{selectedImage.description}</p>
                </div>
                <button class="absolute top-4 right-4 bg-white text-black w-10 h-10 rounded-full flex items-center justify-center hover:bg-gray-200" on:click={closeImage}>
                    ✕
                </button>
            </div>
        </div>
    {/if}
    
    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-10">
        <div class="container mx-auto px-4">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div>
                    <h4 class="text-xl font-bold text-rose-400 mb-4">Beautiful Hair by Heather Melton</h4>
                    <p class="mb-2">South City Street</p>
                    <p class="mb-2">Kings Mountain, NC 28086</p>
                    <p class="mb-2">(704) 692-1792</p>
                    <p>maryheathermeltonwork@gmail.com</p>
                </div>
                <div>
                    <h4 class="text-xl font-bold text-rose-400 mb-4">Booking Policy</h4>
                    <p class="mb-2">Booking is appointment only with walk-ins welcome if there is availibility.</p>
                    <p class="mb-2">Please contact me to book and appointment!</p>
                </div>
                <div>
                    <!-- Add links for her pages -->
                    <h4 class="text-xl font-bold text-rose-400 mb-4">Follow Me</h4>
                    <div class="flex gap-4">
                        <a href="https://www.instagram.com/maryheathermelton?igsh=OTNiZm1qcDI0dzd3" class="bg-white bg-opacity-20 w-10 h-10 rounded-full flex items-center justify-center hover:bg-rose-600 transition duration-300">
                            <span class="sr-only">Instagram</span>
                            <svg class="h-5 w-5" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
                            </svg>
                        </a>
                        <!-- Add facebook link when I get it -->
                        <!-- <a href="#" class="bg-white bg-opacity-20 w-10 h-10 rounded-full flex items-center justify-center hover:bg-rose-600 transition duration-300">
                            <span class="sr-only">Facebook</span>
                            <svg class="h-5 w-5" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M22.675 0h-21.35c-.732 0-1.325.593-1.325 1.325v21.351c0 .731.593 1.324 1.325 1.324h11.495v-9.294h-3.128v-3.622h3.128v-2.671c0-3.1 1.893-4.788 4.659-4.788 1.325 0 2.463.099 2.795.143v3.24l-1.918.001c-1.504 0-1.795.715-1.795 1.763v2.313h3.587l-.467 3.622h-3.12v9.293h6.116c.73 0 1.323-.593 1.323-1.325v-21.35c0-.732-.593-1.325-1.325-1.325z"/>
                            </svg>
                        </a> -->
                    </div>
                </div>
            </div>
            <div class="mt-10 text-center border-t border-gray-800 pt-8">
                <button 
                    type="button" 
                    class="mt-4 inline-flex items-center px-4 py-2 bg-rose-600 hover:bg-rose-700 text-white rounded-full transition duration-300" 
                    on:click={scrollTop} 
                    on:keydown={(e) => e.key === 'Enter' && scrollTop()} 
                    aria-roledescription="button">
                    <svg class="w-4 h-4 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 10l7-7m0 0l7 7m-7-7v18"></path>
                    </svg>
                    Back to Top
                </button>
            </div>
        </div>
    </footer>