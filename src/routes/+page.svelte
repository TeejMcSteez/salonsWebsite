<script>
    let showMenu = false;
    
    function toggleNavBar() {
      showMenu = !showMenu;
    }
  </script>
  
  <div class="min-h-screen dark:bg-slate-900 bg-local">
    <!-- Header and Navigation -->
    <header class="bg-gradient-to-r from-neutral-800 to-pink-600 dark:from-pink-600 dark:to-neutral-800 text-white">
      <div class="container mx-auto px-6 py-4 flex items-center justify-between">
        <h1 class="text-3xl md:text-4xl font-extrabold tracking-tight">Heathers Website</h1>
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
        <nav class="hidden lg:flex space-x-4">
          <a href="#policies" class="px-4 py-2 rounded hover:bg-pink-400 transition">Policies</a>
          <a href="#location/contact" class="px-4 py-2 rounded hover:bg-pink-400 transition">Contact</a>
        </nav>
      </div>
      <!-- Mobile Navigation -->
      {#if showMenu}
        <nav class="lg:hidden bg-gradient-to-r from-neutral-800 to-pink-600">
          <div class="container mx-auto px-6 py-2 flex flex-col space-y-2">
            <a href="#policies" class="block px-4 py-2 rounded hover:bg-pink-400 transition">Policies</a>
            <a href="#location/contact" class="block px-4 py-2 rounded hover:bg-pink-400 transition">Contact</a>
          </div>
        </nav>
      {/if}
    </header>
  
    <!-- Main Content -->
    <main class="container mx-auto px-6 py-8">
      <section id="services" class="my-8 p-6 bg-white dark:bg-slate-800 dark:text-gray-100 rounded-lg shadow">
        <h2 class="text-2xl font-bold mb-4">Services</h2>
        <!-- Extensions -->
        <div id="extensions" class="mb-6">
          <h3 class="text-xl font-semibold underline">Extensions</h3>
          <p class="text-gray-600 dark:text-gray-300">Consultation Required (Prices provided at consultation)</p>
          <ul class="list-disc pl-5 mt-2">
            <li class="text-gray-700 dark:text-gray-200">$150+</li>
          </ul>
        </div>
        <!-- Haircuts -->
        <div id="haircuts" class="mb-6">
          <h3 class="text-xl font-semibold underline">Haircuts</h3>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mt-2">
            <div>
              <h4 class="font-semibold italic">Men</h4>
              <ul class="list-disc pl-5">
                <li>Hair Cut - $20</li>
                <li>Beard Trim - $10</li>
              </ul>
            </div>
            <div>
              <h4 class="font-semibold italic">Women</h4>
              <ul class="list-disc pl-5">
                <li>Dry Cut - $30</li>
                <li>Shampoo/Cut/Style - $35</li>
                <li>Shampoo Style - $35</li>
                <li>Conditioning Treatment - $35</li>
              </ul>
            </div>
          </div>
        </div>
        <!-- Color & Foils -->
        <div id="color" class="mb-6">
          <h3 class="text-xl font-semibold underline">Color & Foils</h3>
          <p class="text-gray-600 dark:text-gray-300">Single color included (4oz) & additional usage at extra cost</p>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mt-2">
            <div>
              <h4 class="font-medium">Color</h4>
              <ul class="list-disc pl-5">
                <li>Short Hair - $55</li>
                <li>Medium Hair - $65</li>
                <li>Long Hair - $85</li>
                <li>Conditioning Treatments - $35</li>
              </ul>
            </div>
            <div>
              <h4 class="font-medium">Foils</h4>
              <ul class="list-disc pl-5">
                <li>Partial: Short $65, Medium $75, Long $85</li>
                <li>Full: Short $75, Medium $85, Long $95</li>
              </ul>
            </div>
          </div>
          <div class="mt-4">
            <h4 class="font-medium">Toning</h4>
            <ul class="list-disc pl-5">
              <li>Short Hair - $25</li>
              <li>Medium Hair - $35</li>
              <li>Long Hair - $45</li>
            </ul>
          </div>
        </div>
        <!-- Waxing -->
        <div id="waxing">
          <h3 class="text-xl font-semibold underline">Waxing</h3>
          <ul class="list-disc pl-5">
            <li>Eyebrows - $10</li>
            <li>Lips - $10</li>
            <li>Chin - $10</li>
            <li>Face - $30</li>
          </ul>
        </div>
      </section>
      
      <section id="policies" class="my-8 p-6 bg-white dark:bg-slate-800 dark:text-gray-100 rounded-lg shadow">
        <h2 class="text-2xl font-bold mb-4">Policies</h2>
        <ul class="list-disc pl-5 mb-6 text-lg">
          <li>Please no box dye soon before appointment unless consulted with me beforehand</li>
          <li>Please inform me of any prior damage or issues so I can address them before your appointment.</li>
          <li>Prices are final and non-negotiable.</li>
        </ul>
        <p class="text-gray-700 dark:text-gray-200 text-lg mb-4">
          Please sign the release form below to confirm you are aware of my policies before booking your first appointment.
        </p>
        <a href="https://forms.gle/HpeYNZTKBB5XhjH56" 
           class="text-xl underline italic hover:animate-pulse">Sign the Release Form</a>
      </section>

      <section id="pictureParralax">
        
      </section>
      
      <section id="location/contact" class="my-8 p-6 bg-white dark:bg-slate-800 dark:text-gray-100 rounded-lg shadow">
        <h2 class="text-2xl font-bold mb-4">Location & Contact</h2>
        <p class="mb-4 text-gray-700 dark:text-gray-200">South City Street, Kings Mountain, North Carolina 28086</p>
        <p class="mb-4 text-lg">maryheathermeltonwork@gmail.com</p>
        <p class="mb-4 text-lg">Phone: 704-692-1792</p>
        <footer class="text-sm">
          Please be respectful of my time; contact after 7pm may not receive a timely response.
        </footer>
      </section>
    </main>
  
    <!-- Footer -->
    <footer class="text-center bg-black text-white py-4">
      <p>
        Made by <a href="https://teejmcsteez.tech/" target="_blank" class="underline italic">Tommy Hall</a>. 
        See <a href="https://github.com/TeejMcSteez/salonsWebsite" target="_blank" class="italic underline">GitHub</a>
      </p>
    </footer>
  </div>
  