<script>
  import before from '$lib/assets/before.jpg'
  import after from '$lib/assets/after.jpg'

  let showMenu = false;
  
  function toggleNavBar() {
    showMenu = !showMenu;
  }
</script>

<div class="min-h-screen dark:bg-slate-900 bg-gray-50">
<!-- Header and Navigation -->
<header class="bg-gradient-to-r from-pink-600 to-purple-700 text-white shadow-lg">
  <div class="container mx-auto px-6 py-4 flex items-center justify-between">
    <div class="flex items-center">
      <h1 class="text-3xl md:text-4xl font-extrabold tracking-tight">Heather's Salon</h1>
    </div>
    <!-- Mobile Hamburger Icon -->
    <button class="lg:hidden focus:outline-none" on:click={toggleNavBar} aria-label="Toggle navigation menu">
      <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        {#if showMenu === false}
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" 
        d="M4 6h16M4 12h16M4 18h16"></path>
        {/if}
        {#if showMenu === true}
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
        {/if}
      </svg>
    </button>
    <!-- Desktop Navigation -->
    <nav class="hidden lg:flex space-x-6">
      <a href="#services" class="px-4 py-2 rounded-full hover:bg-white hover:text-pink-600 transition-all font-medium">Services</a>
      <a href="#gallery" class="px-4 py-2 rounded-full hover:bg-white hover:text-pink-600 transition-all font-medium">Gallery</a>
      <a href="#policies" class="px-4 py-2 rounded-full hover:bg-white hover:text-pink-600 transition-all font-medium">Policies</a>
      <a href="#location" class="px-4 py-2 rounded-full hover:bg-white hover:text-pink-600 transition-all font-medium">Contact</a>
      <a href="/works" class="px-4 py-2 rounded-full bg-white text-pink-600 hover:bg-pink-100 transition-all font-medium">Portfolio</a>
    </nav>
  </div>
  <!-- Mobile Navigation -->
  {#if showMenu}
    <nav class="lg:hidden bg-pink-700 animate-fadeIn">
      <div class="container mx-auto px-6 py-2 flex flex-col space-y-2">
        <a href="#services" class="block px-4 py-3 rounded hover:bg-pink-600 transition-all border-b border-pink-500">Services</a>
        <a href="#gallery" class="block px-4 py-3 rounded hover:bg-pink-600 transition-all border-b border-pink-500">Gallery</a>
        <a href="#policies" class="block px-4 py-3 rounded hover:bg-pink-600 transition-all border-b border-pink-500">Policies</a>
        <a href="#location" class="block px-4 py-3 rounded hover:bg-pink-600 transition-all border-b border-pink-500">Contact</a>
        <a href="/works" class="block px-4 py-3 rounded bg-white text-pink-600 hover:bg-pink-100 transition-all">Portfolio</a>
      </div>
    </nav>
  {/if}
</header>

<!-- Hero Section -->
<section class="bg-gradient-to-b from-pink-100 to-white dark:from-slate-800 dark:to-slate-900 py-16">
  <div class="container mx-auto px-6 text-center">
    <h2 class="text-4xl md:text-5xl font-bold mb-4 text-gray-800 dark:text-white">Transform Your Look</h2>
    <p class="text-xl mb-8 text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">Expert hair styling, coloring, and extensions in Kings Mountain, North Carolina.</p>
    <a href="#location" class="bg-pink-600 text-white px-8 py-3 rounded-full text-lg font-semibold hover:bg-pink-700 transition-all shadow-md">Book Your Appointment</a>
  </div>
</section>

<!-- Main Content -->
<main class="container mx-auto px-6 py-12">
  <!-- Services Section -->
  <section id="services" class="my-12">
    <div class="text-center mb-12">
      <h2 class="text-3xl font-bold mb-4 text-pink-600 dark:text-pink-400">Our Services</h2>
      <p class="text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">Professional hair services tailored to your unique style and needs.</p>
    </div>
    
    <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
      <!-- Extensions -->
      <div class="bg-white dark:bg-slate-800 rounded-lg shadow-md overflow-hidden transition-all hover:shadow-lg">
        <div class="bg-pink-600 py-3 px-6">
          <h3 class="text-xl font-bold text-white">Extensions</h3>
        </div>
        <div class="p-6">
          <p class="text-gray-600 dark:text-gray-300 mb-4">Consultation Required (Prices provided at consultation)</p>
          <div class="flex justify-between items-center p-3 bg-pink-50 dark:bg-slate-700 rounded">
            <span class="font-medium">Starting at</span>
            <span class="text-xl font-bold text-pink-600 dark:text-pink-400">$150+</span>
          </div>
        </div>
      </div>
      
      <!-- Haircuts -->
      <div class="bg-white dark:bg-slate-800 rounded-lg shadow-md overflow-hidden transition-all hover:shadow-lg">
        <div class="bg-pink-600 py-3 px-6">
          <h3 class="text-xl font-bold text-white">Haircuts</h3>
        </div>
        <div class="p-6">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <div>
              <h4 class="font-semibold text-lg mb-3 text-pink-500 dark:text-pink-400">Men</h4>
              <ul class="space-y-2">
                <li class="flex justify-between"><span>Hair Cut</span> <span class="font-bold">$20</span></li>
                <li class="flex justify-between"><span>Beard Trim</span> <span class="font-bold">$10</span></li>
              </ul>
            </div>
            <div>
              <h4 class="font-semibold text-lg mb-3 text-pink-500 dark:text-pink-400">Women</h4>
              <ul class="space-y-2">
                <li class="flex justify-between"><span>Dry Cut</span> <span class="font-bold">$30</span></li>
                <li class="flex justify-between"><span>Shampoo/Cut/Style</span> <span class="font-bold">$35</span></li>
                <li class="flex justify-between"><span>Shampoo Style</span> <span class="font-bold">$35</span></li>
                <li class="flex justify-between"><span>Conditioning Treatment</span> <span class="font-bold">$35</span></li>
              </ul>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Color & Foils -->
      <div class="bg-white dark:bg-slate-800 rounded-lg shadow-md overflow-hidden transition-all hover:shadow-lg">
        <div class="bg-pink-600 py-3 px-6">
          <h3 class="text-xl font-bold text-white">Color & Foils</h3>
        </div>
        <div class="p-6">
          <p class="text-gray-600 dark:text-gray-300 mb-4">Single color included (4oz) & additional usage at extra cost</p>
          
          <div class="mb-4">
            <h4 class="font-semibold text-lg mb-3 text-pink-500 dark:text-pink-400">Color</h4>
            <ul class="space-y-2">
              <li class="flex justify-between"><span>Short Hair</span> <span class="font-bold">$55</span></li>
              <li class="flex justify-between"><span>Medium Hair</span> <span class="font-bold">$65</span></li>
              <li class="flex justify-between"><span>Long Hair</span> <span class="font-bold">$85</span></li>
              <li class="flex justify-between"><span>Conditioning Treatments</span> <span class="font-bold">$35</span></li>
            </ul>
          </div>
          
          <div class="mb-4">
            <h4 class="font-semibold text-lg mb-3 text-pink-500 dark:text-pink-400">Foils</h4>
            <ul class="space-y-2">
              <li class="flex justify-between"><span>Partial: Short</span> <span class="font-bold">$65</span></li>
              <li class="flex justify-between"><span>Partial: Medium</span> <span class="font-bold">$75</span></li>
              <li class="flex justify-between"><span>Partial: Long</span> <span class="font-bold">$85</span></li>
              <li class="flex justify-between"><span>Full: Short</span> <span class="font-bold">$75</span></li>
              <li class="flex justify-between"><span>Full: Medium</span> <span class="font-bold">$85</span></li>
              <li class="flex justify-between"><span>Full: Long</span> <span class="font-bold">$95</span></li>
            </ul>
          </div>
          
          <div>
            <h4 class="font-semibold text-lg mb-3 text-pink-500 dark:text-pink-400">Toning</h4>
            <ul class="space-y-2">
              <li class="flex justify-between"><span>Short Hair</span> <span class="font-bold">$25</span></li>
              <li class="flex justify-between"><span>Medium Hair</span> <span class="font-bold">$35</span></li>
              <li class="flex justify-between"><span>Long Hair</span> <span class="font-bold">$45</span></li>
            </ul>
          </div>
        </div>
      </div>
      
      <!-- Waxing -->
      <div class="bg-white dark:bg-slate-800 rounded-lg shadow-md overflow-hidden transition-all hover:shadow-lg">
        <div class="bg-pink-600 py-3 px-6">
          <h3 class="text-xl font-bold text-white">Waxing</h3>
        </div>
        <div class="p-6">
          <ul class="space-y-2">
            <li class="flex justify-between"><span>Eyebrows</span> <span class="font-bold">$10</span></li>
            <li class="flex justify-between"><span>Lips</span> <span class="font-bold">$10</span></li>
            <li class="flex justify-between"><span>Chin</span> <span class="font-bold">$10</span></li>
            <li class="flex justify-between"><span>Face</span> <span class="font-bold">$30</span></li>
          </ul>
        </div>
      </div>
    </div>
  </section>
  
  <!-- Gallery Section -->
  <section id="gallery" class="my-16">
    <div class="text-center mb-12">
      <h2 class="text-3xl font-bold mb-4 text-pink-600 dark:text-pink-400">Transformation Gallery</h2>
      <p class="text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">See the stunning before and after transformations from our salon.</p>
    </div>
    
    <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
      <div class="relative rounded-lg overflow-hidden shadow-lg group">
        <img src={before} alt="Before transformation" class="w-full h-auto transition-transform duration-500 group-hover:scale-105" />
        <div class="absolute bottom-0 left-0 right-0 bg-gradient-to-t from-black to-transparent p-4">
          <span class="text-white font-semibold text-xl">Before</span>
        </div>
      </div>
      
      <div class="relative rounded-lg overflow-hidden shadow-lg group">
        <img src={after} alt="After transformation" class="w-full h-auto transition-transform duration-500 group-hover:scale-105" />
        <div class="absolute bottom-0 left-0 right-0 bg-gradient-to-t from-black to-transparent p-4">
          <span class="text-white font-semibold text-xl">After</span>
        </div>
      </div>
    </div>
    
    <div class="mt-10 text-center">
      <a href="https://www.instagram.com/maryheathermelton?igsh=OTNiZm1qcDI0dzd3" target="_blank" 
         class="inline-flex items-center bg-gradient-to-r from-pink-500 to-purple-600 text-white font-bold py-3 px-6 rounded-full hover:from-pink-600 hover:to-purple-700 transition-all shadow-md">
        <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
          <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
        </svg>
        See More on Instagram
      </a>
    </div>
  </section>
  
  <!-- Policies Section -->
  <section id="policies" class="my-16">
    <div class="text-center mb-12">
      <h2 class="text-3xl font-bold mb-4 text-pink-600 dark:text-pink-400">Salon Policies</h2>
      <p class="text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">Please review our policies before booking your appointment.</p>
    </div>
    
    <div class="bg-white dark:bg-slate-800 rounded-lg shadow-lg p-8">
      <ul class="space-y-4 mb-8">
        <li class="flex items-start">
          <svg class="w-6 h-6 text-pink-500 mr-2 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
          </svg>
          <span class="text-gray-700 dark:text-gray-200">Please no box dye soon before appointment unless consulted with me beforehand</span>
        </li>
        <li class="flex items-start">
          <svg class="w-6 h-6 text-pink-500 mr-2 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
          </svg>
          <span class="text-gray-700 dark:text-gray-200">Please inform me of any prior damage or issues so I can address them before your appointment.</span>
        </li>
        <li class="flex items-start">
          <svg class="w-6 h-6 text-pink-500 mr-2 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
          </svg>
          <span class="text-gray-700 dark:text-gray-200">Prices are final and non-negotiable.</span>
        </li>
      </ul>
      
      <div class="bg-pink-50 dark:bg-slate-700 p-6 rounded-lg border-l-4 border-pink-500">
        <p class="text-gray-700 dark:text-gray-200 mb-4">
          Please sign the release form below to confirm you are aware of my policies before booking your first appointment.
        </p>
        <a href="https://forms.gle/HpeYNZTKBB5XhjH56" 
           class="inline-block bg-pink-600 hover:bg-pink-700 text-white font-bold py-2 px-6 rounded-lg transition-all">
          Sign the Release Form
        </a>
      </div>
    </div>
  </section>
  
  <!-- Location & Contact Section -->
  <section id="location" class="my-16">
    <div class="text-center mb-12">
      <h2 class="text-3xl font-bold mb-4 text-pink-600 dark:text-pink-400">Location & Contact</h2>
      <p class="text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">Ready to book your appointment? Get in touch today.</p>
    </div>
    
    <div class="bg-white dark:bg-slate-800 rounded-lg shadow-lg overflow-hidden">
      <div class="grid grid-cols-1 md:grid-cols-2">
        <div class="p-8">
          <h3 class="text-2xl font-semibold mb-6 text-gray-800 dark:text-white">Contact Information</h3>
          <p class="font-semibold mb-4 text-gray-800 dark:text-white">Contact by phone or email is preferred</p>
          <div class="space-y-4">
            <div class="flex items-start">
              <svg class="w-6 h-6 text-pink-500 mr-3 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path>
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path>
              </svg>
              <div>
                <h4 class="font-medium text-gray-700 dark:text-gray-200">Address</h4>
                <p class="text-gray-600 dark:text-gray-300">South City Street, Kings Mountain, North Carolina 28086</p>
              </div>
            </div>
            
            <div class="flex items-start">
              <svg class="w-6 h-6 text-pink-500 mr-3 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path>
              </svg>
              <div>
                <h4 class="font-medium text-gray-700 dark:text-gray-200">Email</h4>
                <p class="text-gray-600 dark:text-gray-300">maryheathermeltonwork@gmail.com</p>
              </div>
            </div>
            
            <div class="flex items-start">
              <svg class="w-6 h-6 text-pink-500 mr-3 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path>
              </svg>
              <div>
                <h4 class="font-medium text-gray-700 dark:text-gray-200">Phone</h4>
                <p class="text-gray-600 dark:text-gray-300">704-692-1792</p>
              </div>
            </div>
            
            <div class="flex items-start">
              <svg class="w-6 h-6 text-pink-500 mr-3 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
              </svg>
              <div>
                <h4 class="font-medium text-gray-700 dark:text-gray-200">Instagram</h4>
                <a href="https://www.instagram.com/maryheathermelton?igsh=OTNiZm1qcDI0dzd3" target="_blank" class="text-pink-500 hover:text-pink-600 transition-colors">@maryheathermelton</a>
              </div>
            </div>
          </div>
        </div>
        
        <div class="bg-pink-50 dark:bg-slate-700 p-8">
          <h3 class="text-2xl font-semibold mb-6 text-gray-800 dark:text-white">Hours of Operation</h3>
          
          <div class="space-y-4">
            <div class="flex justify-between pb-2 border-b border-pink-100 dark:border-slate-600">
              <span class="font-medium">Monday - Friday</span>
              <span>By appointment</span>
            </div>
            <div class="flex justify-between pb-2 border-b border-pink-100 dark:border-slate-600">
              <span class="font-medium">Saturday</span>
              <span>By appointment</span>
            </div>
            <div class="flex justify-between pb-2 border-b border-pink-100 dark:border-slate-600">
              <span class="font-medium">Sunday</span>
              <span>Closed</span>
            </div>
          </div>
          
          <div class="mt-6 p-4 bg-white dark:bg-slate-800 rounded-lg">
            <p class="text-gray-600 dark:text-gray-300 text-sm">
              Please be respectful of my time; contact after 7pm may not receive a timely response.
            </p>
          </div>
          
          <div class="mt-6">
            <!-- <a href="https://heathermelton.as.me/" class="block w-full text-center bg-pink-600 hover:bg-pink-700 text-white font-bold py-3 px-6 rounded-lg transition-all">
              Book Your Appointment
            </a> -->
            <a href="https://app.acuityscheduling.com/schedule.php?owner=35091671&ref=booking_button" target="_blank" class="acuity-embed-button" style="background: #000000; color: #fff; padding: 8px 12px; border: 0px; -webkit-box-shadow: 0 -2px 0 rgba(0,0,0,0.15) inset;-moz-box-shadow: 0 -2px 0 rgba(0,0,0,0.15) inset;box-shadow: 0 -2px 0 rgba(0,0,0,0.15) inset;border-radius: 4px; text-decoration: none; display: inline-block;">Schedule Appointment</a><link rel="stylesheet" href="https://embed.acuityscheduling.com/embed/button/35091671.css" id="acuity-button-styles" /><script src="https://embed.acuityscheduling.com/embed/button/35091671.js" async></script>
          </div>
        </div>
      </div>
    </div>
    <div class="flex flex-row items-center justify-center">
      <a href="#location/" on:click={() => window.scrollTo({top: 0, behavior: "smooth"})} class="p-2 m-4 items-center justify-center text-center bg-pink-600 hover:bg-pink700 rounded-lg text-white font-bold">Back to Top</a>
    </div>
  </section>
</main>

<!-- Footer -->
<footer class="bg-gradient-to-r from-neutral-800 to-pink-800 text-white py-8">
  <div class="container mx-auto px-6">
    <div class="flex flex-col md:flex-row justify-between items-center">
      <div class="mb-6 md:mb-0">
        <h1 class="text-2xl font-bold text-center">Heather's Salon</h1>
        <p class="text-gray-300 mt-2">Kings Mountain, North Carolina</p>
      </div>
      
      <div class="text-center md:text-right">
        <p class="mb-2">
          Made by <a href="https://teejmcsteez.tech/" target="_blank" class="underline hover:text-pink-300 transition-colors">Tommy Hall</a>
        </p>
        <p>
          <a href="https://github.com/TeejMcSteez/salonsWebsite" target="_blank" class="text-gray-300 hover:text-white transition-colors">View on GitHub</a>
        </p>
      </div>
    </div>
  </div>
</footer>
</div>