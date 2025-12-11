<script>
  import { onMount } from 'svelte';

  let isScrolled = false;

  onMount(() => {
    const handleScroll = () => {
      isScrolled = window.scrollY > 10;
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });
</script>

<header class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 px-6 py-5 flex items-center justify-between {isScrolled ? 'bg-[#F9F8F6]/90 backdrop-blur-md shadow-sm' : 'bg-transparent'}">
  <div class="flex items-center">
    <!-- Logo -->
    <a href="/" class="flex items-center gap-2 group">
      <div class="w-6 h-6 text-[#1A1A1A]">
        <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path
            d="M12 2L13.2 9.92154L20.6603 7L14.4 12L20.6603 17L13.2 14.0785L12 22L10.8 14.0785L3.33975 17L9.6 12L3.33975 7L10.8 9.92154L12 2Z"
            fill="currentColor"
          />
        </svg>
      </div>
      <span class="font-semibold text-lg text-[#1A1A1A]">Switch To Red</span>
    </a>
  </div>

  <div class="flex items-center gap-8">
    <nav class="hidden md:flex items-center gap-8 text-[13px] font-medium text-gray-600">
      <a href="#science" class="hover:text-black transition-colors">The Science</a>
      <a href="#faq" class="hover:text-black transition-colors">FAQ</a>
    </nav>
    <a href="#buy" class="bg-[#1A1A1A] text-white text-[13px] font-medium px-5 py-2.5 rounded-sm hover:bg-black transition-colors">
      Buy now
    </a>
  </div>
</header>