<script lang="ts">
  import Header from "$lib/components/Header.svelte";
  
  // Icons
  const ArrowRight = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>`;
  const PlayCircle = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><polygon points="10 8 16 12 10 16 10 8"/></svg>`;
  const ChevronLeft = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m15 18-6-6 6-6"/></svg>`;
  const ChevronRight = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m9 18 6-6-6-6"/></svg>`;
  const Check = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>`;
  const Plus = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="M12 5v14"/></svg>`;
  const Instagram = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>`;
  const LinkedIn = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect width="4" height="12" x="2" y="9"/><circle cx="4" cy="4" r="2"/></svg>`;
  const XIcon = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 6 6 18"/><path d="m6 6 18 12"/></svg>`;

  // Data
  const heroImages = [
    "/generated/image-parent-checking-on-sleeping-baby-in-dark-1765494975489-0.webp",
    "/generated/image-person-using-phone-with-red-light-in-dar-1765494978301-1.webp",
    "/generated/image-close-up-of-hands-holding-iphone-with-su-1765494980530-2.webp",
    "/generated/image-peaceful-bedroom-at-night-with-person-re-1765494982782-3.webp",
    "/generated/image-young-parent-looking-tired-but-content-h-1765494985034-4.webp",
    "/generated/image-person-in-athletic-wear-checking-phone-a-1765494987477-5.webp"
  ];

  const benefitCards = [
    {
      title: "Protect your melatonin.",
      desc: "Red light doesn't suppress melatonin production like white or blue light. Move through the night without resetting your circadian rhythm.",
      image: "/generated/image-peaceful-bedroom-at-night-with-person-re-1765494982782-3.webp"
    },
    {
      title: "Check on baby without waking up.",
      desc: "Perfect for nighttime parenting. See what you need without the harsh white flash that fully wakes your brain—or your baby.",
      image: "/generated/image-young-parent-looking-tired-but-content-h-1765494985034-4.webp"
    },
    {
      title: "Don't disturb your partner.",
      desc: "Late-night bathroom trip? Looking for something? Use your phone's light without flooding the room with sleep-disrupting brightness.",
      image: "/generated/image-person-in-athletic-wear-checking-phone-a-1765494987477-5.webp"
    }
  ];

  const steps = [
    {
      step: 1,
      title: "Attach to your iPhone case.",
      desc: "Switch To Red fits the latest 3-5 iPhone models. The discreet design integrates seamlessly with your phone's aesthetic—barely noticeable during the day.",
      image: "attach"
    },
    {
      step: 2,
      title: "Slide the red lens over your flash.",
      desc: "Simple manual mechanism. When you need light at night, just slide the translucent red lens into position over your phone's flashlight.",
      image: "slide"
    },
    {
      step: 3,
      title: "Move through the night safely.",
      desc: "Check on your baby, navigate to the bathroom, find what you need—all without the harsh white light that disrupts melatonin and wakes your brain.",
      image: "use"
    }
  ];

  const faqs = [
    "How does red light protect my sleep?",
    "Will this work with my iPhone model?",
    "Does the red light provide enough visibility?",
    "Will it overheat my phone?",
    "How is this different from red light glasses or apps?"
  ];
</script>

<Header />

<main class="w-full overflow-x-hidden">
  <!-- Hero Section -->
  <section class="pt-32 pb-16 md:pt-40 md:pb-24 px-6 text-center max-w-7xl mx-auto">
    <h1 class="text-4xl md:text-6xl lg:text-7xl font-medium tracking-tight text-[#1A1A1A] mb-6 leading-[1.1]">
      Move through the night<br />without waking your brain.
    </h1>
    <p class="text-gray-600 text-lg md:text-xl max-w-3xl mx-auto mb-10 leading-relaxed font-light">
      A simple red-light filter for your iPhone flash. Check on baby, navigate in darkness, find what you need—all without disrupting your melatonin or waking your partner.
    </p>
    <button class="bg-[#1A1A1A] text-white px-8 py-3.5 rounded-sm font-medium hover:bg-black transition-colors">
      Get yours now
    </button>
  </section>

  <!-- Hero Images Scroll -->
  <div class="w-full overflow-x-auto pb-12 hide-scrollbar">
    <div class="flex gap-4 px-6 min-w-max">
      {#each heroImages as img, i}
        <div class="relative w-48 h-64 md:w-64 md:h-80 rounded-3xl overflow-hidden flex-shrink-0">
          <img src={img} alt="Lifestyle" class="w-full h-full object-cover" />
        </div>
      {/each}
    </div>
  </div>

  <!-- Product Feature Section -->
  <section class="py-20 px-6 max-w-7xl mx-auto">
    <div class="bg-white rounded-[40px] p-8 md:p-16 flex flex-col md:flex-row items-center gap-12 shadow-sm">
      <!-- Product Image -->
      <div class="w-full md:w-1/2 flex justify-center">
        <div class="relative w-full max-w-md">
          <img src="/generated/image-close-up-of-hands-holding-iphone-with-su-1765494980530-2.webp" alt="iPhone with red light filter" class="w-full h-auto rounded-2xl shadow-xl" />
        </div>
      </div>
      
      <!-- Content -->
      <div class="w-full md:w-1/2 space-y-6">
        <h2 class="text-3xl md:text-4xl font-medium leading-tight text-[#1A1A1A]">
          Science-backed sleep protection in your pocket.
        </h2>
        <p class="text-gray-600 leading-relaxed">
          White and blue light suppress melatonin—even brief exposure can reset your circadian rhythm. Red light doesn't. That's why NASA, military personnel, and sailors use red light for night operations.
        </p>
        <p class="text-gray-600 leading-relaxed">
          Switch To Red brings this proven science to your everyday life. No apps, no settings, no complexity. Just slide and go.
        </p>
      </div>
    </div>
  </section>

  <!-- Value Proposition -->
  <section class="py-16 px-6 max-w-7xl mx-auto" id="science">
    <div class="grid md:grid-cols-2 gap-12 items-start">
      <h2 class="text-3xl md:text-5xl font-medium tracking-tight text-[#1A1A1A] leading-tight">
        Your sleep matters more than you think.
      </h2>
      <p class="text-gray-600 text-lg font-light leading-relaxed">
        A single flash of white light at night can fully reset your circadian rhythm. For parents checking on babies, for anyone navigating their home after dark, this adds up to chronic sleep disruption. Switch To Red solves a problem you didn't know had such a simple solution.
      </p>
    </div>
  </section>

  <!-- Benefit Cards -->
  <section class="py-8 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-3 gap-6">
      {#each benefitCards as card}
        <div class="relative h-[480px] rounded-3xl overflow-hidden group">
          <img src={card.image} alt={card.title} class="absolute inset-0 w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
          <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-black/20 to-transparent"></div>
          <div class="absolute bottom-0 left-0 right-0 p-8 text-white">
            <h3 class="text-2xl font-medium mb-3">{card.title}</h3>
            <p class="text-white/80 text-sm leading-relaxed font-light">{card.desc}</p>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <!-- Testimonial -->
  <section class="py-24 px-6 max-w-4xl mx-auto text-center">
    <blockquote class="text-2xl md:text-3xl font-medium leading-relaxed text-[#1A1A1A] mb-8">
      "Red light is the gold standard for nighttime visibility without circadian disruption. This is exactly the kind of simple, science-backed tool that makes healthy habits effortless."
    </blockquote>
    <div class="flex flex-col items-center gap-3">
      <img src="/generated/image-sleep-researcher-or-scientist-in-casual--1765494992366-7.webp" alt="Sleep Researcher" class="w-12 h-12 rounded-full object-cover" />
      <div class="text-center">
        <div class="font-medium text-sm">Dr. Sarah Chen</div>
        <div class="text-gray-500 text-xs">Sleep Researcher</div>
      </div>
    </div>
  </section>

  <!-- Stats Grid -->
  <section class="py-12 px-6 max-w-7xl mx-auto border-t border-gray-200">
    <div class="grid md:grid-cols-3 gap-8 text-center md:text-left">
      <div>
        <h3 class="text-xl font-medium mb-2">Zero overheating.</h3>
        <p class="text-gray-500 text-sm font-light">Tested for 30+ minutes of continuous use. Safe, reliable, and designed for repeated daily use.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">Fits latest iPhones.</h3>
        <p class="text-gray-500 text-sm font-light">Compatible with the last 3-5 iPhone models. Discreet design that integrates seamlessly.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">Patented in France.</h3>
        <p class="text-gray-500 text-sm font-light">Protected red flash cover mechanism. First of its kind in the sleep-tech accessory space.</p>
      </div>
    </div>
  </section>

  <!-- How it works -->
  <section class="py-20 px-6 max-w-7xl mx-auto">
    <div class="mb-16 max-w-md">
      <h2 class="text-4xl font-medium mb-6">How it works.</h2>
      <p class="text-gray-600 font-light">Three simple steps to sleep-safe nighttime visibility. No apps, no settings, no complexity.</p>
    </div>

    <div class="space-y-6">
      {#each steps as step}
        <div class="bg-white rounded-[40px] p-8 md:p-12 flex flex-col md:flex-row items-center gap-8 max-w-4xl mx-auto shadow-sm">
          <div class="w-full md:w-2/3">
            <span class="inline-block w-8 h-8 rounded-full border border-gray-200 text-center leading-8 text-sm font-medium mb-4">{step.step}</span>
            <h3 class="text-2xl font-medium mb-3">{step.title}</h3>
            <p class="text-gray-500 font-light leading-relaxed">{step.desc}</p>
          </div>
          
          <!-- Visual Representation -->
          <div class="w-full md:w-1/3 flex justify-center">
            <div class="relative w-32 h-32 rounded-2xl bg-gradient-to-br from-primary-100 to-primary-200 flex items-center justify-center">
              {#if step.image === 'attach'}
                <svg class="w-16 h-16 text-primary-700" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <rect x="5" y="2" width="14" height="20" rx="2" />
                  <path d="M12 18h.01" />
                </svg>
              {:else if step.image === 'slide'}
                <svg class="w-16 h-16 text-primary-700" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M5 12h14" />
                  <path d="m12 5 7 7-7 7" />
                </svg>
              {:else}
                <svg class="w-16 h-16 text-primary-700" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <circle cx="12" cy="12" r="10" />
                  <path d="M12 16v-4" />
                  <path d="M12 8h.01" />
                </svg>
              {/if}
            </div>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <!-- Dark Cards Section -->
  <section class="py-8 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-2 gap-6">
      <!-- Science Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">Backed by research.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">NASA, military, and circadian scientists trust red light.</h2>
        </div>
        <!-- Abstract wavelength visual -->
        <div class="absolute inset-0 flex items-center justify-center opacity-20 mt-20">
           <svg viewBox="0 0 400 200" class="w-full h-full text-primary-500 stroke-current fill-none">
              <path d="M 0 100 Q 50 50, 100 100 T 200 100 T 300 100 T 400 100" stroke-width="3" />
              <path d="M 0 120 Q 50 70, 100 120 T 200 120 T 300 120 T 400 120" stroke-width="3" opacity="0.6" />
           </svg>
        </div>
      </div>

      <!-- Design Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">Minimalist design.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">Discreet, reliable, and built to last.</h2>
        </div>
        <!-- Abstract product visual -->
        <div class="absolute inset-0 flex items-center justify-center opacity-10 mt-20">
           <div class="w-48 h-80 border-4 border-gray-600 rounded-[40px]"></div>
        </div>
      </div>
    </div>
  </section>

  <!-- Pricing Section -->
  <section class="py-24 px-6 max-w-7xl mx-auto" id="buy">
    <div class="text-center mb-16">
      <h2 class="text-3xl md:text-4xl font-medium mb-4">Better sleep starts tonight.</h2>
      <p class="text-gray-500 font-light max-w-2xl mx-auto">One simple accessory. Lifetime of better nighttime habits. No subscription, no recurring fees—just a smarter way to use your phone at night.</p>
    </div>

    <div class="max-w-md mx-auto">
      <!-- Single Product -->
      <div class="bg-white rounded-[32px] p-8 flex flex-col shadow-sm">
        <div class="w-12 h-12 bg-primary-100 rounded-full mb-6 flex items-center justify-center">
          <svg class="w-6 h-6 text-primary-700" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path
              d="M12 2L13.2 9.92154L20.6603 7L14.4 12L20.6603 17L13.2 14.0785L12 22L10.8 14.0785L3.33975 17L9.6 12L3.33975 7L10.8 9.92154L12 2Z"
              fill="currentColor"
            />
          </svg>
        </div>
        <h3 class="text-2xl font-medium mb-1">Switch To Red</h3>
        <p class="text-sm text-gray-500 mb-6">Red-light filter for iPhone flash</p>
        <div class="mb-8">
          <span class="text-4xl font-medium">€24</span>
          <div class="text-xs text-gray-500 mt-2">Free shipping in EU • 30-day returns</div>
        </div>
        <ul class="space-y-4 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Patented red-light filtering technology
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Fits latest 3-5 iPhone models
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Tested for zero overheating (30+ min continuous use)
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Discreet design that integrates with your phone
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Simple slide mechanism—no apps or settings
          </li>
        </ul>
        <button class="w-full bg-[#1A1A1A] text-white py-3.5 rounded-sm font-medium hover:bg-black transition-colors text-base">
          Pre-order now
        </button>
        <p class="text-xs text-center text-gray-400 mt-4">Launching Q2 2025 • Limited first batch</p>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section class="py-20 px-6 max-w-3xl mx-auto" id="faq">
    <h2 class="text-3xl font-medium text-center mb-12">Your questions answered.</h2>
    <div class="space-y-4">
      {#each faqs as question}
        <div class="border-b border-gray-200 py-4 flex justify-between items-center cursor-pointer group hover:bg-gray-50/50 transition-colors px-2">
          <span class="text-sm md:text-base font-medium text-gray-800">{question}</span>
          <span class="text-gray-400 group-hover:text-black transition-colors">{@html Plus}</span>
        </div>
      {/each}
    </div>
    <div class="mt-12 text-center">
      <button class="border border-gray-300 px-6 py-3 rounded-sm text-xs font-medium hover:bg-gray-50 transition-colors">
        View all Frequently Asked Questions
      </button>
    </div>
  </section>

  <!-- Footer -->
  <footer class="py-16 px-6 border-t border-gray-200 bg-[#F9F8F6]">
    <div class="max-w-7xl mx-auto">
      <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-8 mb-16">
        <div class="flex items-center gap-2">
          <div class="w-6 h-6 text-[#1A1A1A]">
            <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M12 2L13.2 9.92154L20.6603 7L14.4 12L20.6603 17L13.2 14.0785L12 22L10.8 14.0785L3.33975 17L9.6 12L3.33975 7L10.8 9.92154L12 2Z"
                fill="currentColor"
              />
            </svg>
          </div>
          <span class="font-semibold text-lg">Switch To Red</span>
        </div>
        
        <nav class="flex flex-wrap gap-6 md:gap-8 text-xs font-medium text-gray-600">
          <a href="#science" class="hover:text-black">The Science</a>
          <a href="#faq" class="hover:text-black">FAQ</a>
          <a href="#" class="hover:text-black">Contact</a>
          <a href="#" class="hover:text-black">Terms & Conditions</a>
          <a href="#" class="hover:text-black">Privacy Policy</a>
        </nav>

        <div class="flex gap-4 text-gray-800">
          <a href="#" class="hover:text-black" aria-label="X (Twitter)">{@html XIcon}</a>
          <a href="#" class="hover:text-black" aria-label="Instagram">{@html Instagram}</a>
          <a href="#" class="hover:text-black" aria-label="LinkedIn">{@html LinkedIn}</a>
        </div>
      </div>

      <div class="text-[10px] text-gray-400 leading-relaxed max-w-5xl">
        <p class="mb-2">Switch To Red is a consumer product designed to filter light wavelengths. This product is not a medical device and does not diagnose, treat, cure, or prevent any disease or medical condition. All information provided about circadian rhythm, melatonin, and sleep is for educational purposes only and should not be considered medical advice. Consult with a healthcare provider for personalized medical guidance.</p>
        <p class="mb-2">Patent pending in France. International patent applications in progress. Product specifications and compatibility may vary. Compatible with select iPhone models—please verify compatibility before purchase.</p>
        <p class="mt-2">© 2025 Switch To Red. All rights reserved.</p>
      </div>
    </div>
  </footer>
</main>

<style>
  :global(body) {
    background-color: #F9F8F6;
    font-family: 'Inter', sans-serif;
  }
  
  .hide-scrollbar::-webkit-scrollbar {
    display: none;
  }
  .hide-scrollbar {
    -ms-overflow-style: none;
    scrollbar-width: none;
  }
</style>

