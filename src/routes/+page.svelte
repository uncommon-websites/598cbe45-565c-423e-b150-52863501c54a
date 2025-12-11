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
    "/generated/image-modern-dental-office-interior-with-comfo-1765495439276-0.webp",
    "/generated/image-friendly-female-dentist-smiling-warmly-i-1765495443175-1.webp",
    "/generated/image-young-professional-woman-smiling-confide-1765495446192-2.webp",
    "/generated/image-sleek-dental-chair-in-contemporary-studi-1765495449227-3.webp",
    "/generated/image-dental-team-collaborating-in-bright-welc-1765495452244-4.webp",
    "/generated/image-patient-relaxing-comfortably-in-dental-c-1765495455308-5.webp"
  ];

  const benefitCards = [
    {
      title: "Modern studios designed for comfort.",
      desc: "Our studios feature home-like amenities and inviting atmospheres that make you actually look forward to your dental visit.",
      image: "/generated/image-bright-modern-dental-studio-reception-ar-1765495458613-6.webp"
    },
    {
      title: "Compassionate, judgment-free care.",
      desc: "Our team creates a welcoming environment where you feel heard, respected, and comfortable—no matter how long it's been since your last visit.",
      image: "/generated/image-compassionate-dentist-having-a-caring-co-1765495461832-7.webp"
    },
    {
      title: "Latest technology and innovations.",
      desc: "We invest in cutting-edge dental technology and continued education to provide you with the most advanced, comfortable care available.",
      image: "/generated/image-advanced-dental-technology-equipment-in--1765495464975-8.webp"
    }
  ];

  const steps = [
    {
      step: 1,
      title: "Choose your service.",
      desc: "From routine cleanings to Invisalign, teeth whitening, or full mouth reconstruction—we offer comprehensive dental care tailored to your needs.",
      image: "plan"
    },
    {
      step: 2,
      title: "Book your appointment.",
      desc: "Select from 23 convenient locations across Austin, Houston, and San Antonio. Easy online scheduling or same-day emergency appointments available.",
      image: "schedule"
    },
    {
      step: 3,
      title: "Visit our modern studio.",
      desc: "Arrive at a welcoming space designed for comfort. Our friendly team greets you in an environment that feels nothing like a traditional dental office.",
      image: "results"
    },
    {
      step: 4,
      title: "Experience comfortable care.",
      desc: "Receive expert treatment from our compassionate dentists using the latest technology, all in a relaxed, judgment-free atmosphere.",
      image: "notes"
    },
    {
      step: 5,
      title: "Maintain your smile.",
      desc: "Leave with a personalized care plan and easy scheduling for follow-ups. We're here to support your ongoing dental health journey.",
      image: "improve"
    }
  ];

  const faqs = [
    "Do you accept dental insurance?",
    "What is the Swish Smile Membership?",
    "Do you offer same-day emergency appointments?",
    "How much does Invisalign cost at Swish?",
    "What financing options are available?",
    "How do I choose a location near me?"
  ];
</script>

<Header />

<main class="w-full overflow-x-hidden">
  <!-- Hero Section -->
  <section class="pt-32 pb-16 md:pt-40 md:pb-24 px-6 text-center max-w-7xl mx-auto">
    <h1 class="text-4xl md:text-6xl lg:text-7xl font-medium tracking-tight text-[#1A1A1A] mb-6 leading-[1.1]">
      Dental care you'll<br />actually look forward to.
    </h1>
    <p class="text-gray-600 text-lg md:text-xl max-w-3xl mx-auto mb-10 leading-relaxed font-light">
      Modern studios, compassionate care, and the latest technology. Swish Dental transforms dental visits into comfortable experiences across 23 Texas locations.
    </p>
    <button class="bg-[#1A1A1A] text-white px-8 py-3.5 rounded-sm font-medium hover:bg-black transition-colors">
      Book your visit
    </button>
  </section>

  <!-- Hero Images Scroll -->
  <div class="w-full overflow-x-auto pb-12 hide-scrollbar">
    <div class="flex gap-4 px-6 min-w-max">
      {#each heroImages as img, i}
        <div class="relative w-48 h-64 md:w-64 md:h-80 rounded-3xl overflow-hidden flex-shrink-0">
          <img src={img} alt="Swish Dental Studio" class="w-full h-full object-cover" />
        </div>
      {/each}
    </div>
  </div>

  <!-- Locations Section -->
  <section class="py-20 px-6 max-w-7xl mx-auto" id="locations">
    <div class="bg-white rounded-[40px] p-8 md:p-16 flex flex-col md:flex-row items-center gap-12 shadow-sm">
      <!-- Location Map Visual -->
      <div class="w-full md:w-1/2 flex justify-center">
        <div class="relative w-full h-[400px] bg-gray-50 rounded-3xl overflow-hidden flex items-center justify-center">
          <div class="text-center space-y-6 p-8">
            <div class="text-6xl font-bold text-[#1A1A1A]">23</div>
            <div class="text-xl font-medium text-gray-700">Locations Across Texas</div>
            <div class="grid grid-cols-3 gap-4 text-sm text-gray-600 max-w-md mx-auto">
              <div class="text-center">
                <div class="font-medium text-[#1A1A1A]">16</div>
                <div class="text-xs">Austin Area</div>
              </div>
              <div class="text-center">
                <div class="font-medium text-[#1A1A1A]">5</div>
                <div class="text-xs">Houston Area</div>
              </div>
              <div class="text-center">
                <div class="font-medium text-[#1A1A1A]">2</div>
                <div class="text-xs">San Antonio</div>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Content -->
      <div class="w-full md:w-1/2 space-y-6">
        <h2 class="text-3xl md:text-4xl font-medium leading-tight text-[#1A1A1A]">
          Find a studio near you.
        </h2>
        <p class="text-gray-600 text-lg font-light leading-relaxed">
          With locations throughout Austin, Houston, and San Antonio, there's a Swish studio conveniently located near your home or office. Each studio features the same modern design, advanced technology, and compassionate care you deserve.
        </p>
        <button class="flex items-center gap-2 text-[#1A1A1A] font-medium hover:opacity-70 transition-opacity">
          {@html ArrowRight}
          View all locations
        </button>
      </div>
    </div>
  </section>

  <!-- Value Proposition -->
  <section class="py-16 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-2 gap-12 items-start">
      <h2 class="text-3xl md:text-5xl font-medium tracking-tight text-[#1A1A1A] leading-tight">
        Dental anxiety doesn't have to hold you back.
      </h2>
      <p class="text-gray-600 text-lg font-light leading-relaxed">
        We understand that dental visits can be stressful. That's why we've reimagined every aspect of the experience—from our modern studios to our compassionate team. At Swish, you're not just a patient; you're part of a community that believes dental care should be comfortable, accessible, and something you actually look forward to.
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
      "I used to dread going to the dentist, but Swish completely changed that. The studio feels more like a spa than a dental office, and the team made me feel so comfortable. I actually look forward to my appointments now!"
    </blockquote>
    <div class="flex flex-col items-center gap-3">
      <img src="/generated/image-happy-millennial-woman-with-natural-smil-1765495468009-9.webp" alt="Patient" class="w-12 h-12 rounded-full object-cover" />
      <div class="text-center">
        <div class="font-medium text-sm">Sarah M.</div>
        <div class="text-gray-500 text-xs">Swish Patient, Austin</div>
      </div>
    </div>
  </section>

  <!-- Stats Grid -->
  <section class="py-12 px-6 max-w-7xl mx-auto border-t border-gray-200">
    <div class="grid md:grid-cols-3 gap-8 text-center md:text-left">
      <div>
        <h3 class="text-xl font-medium mb-2">10,000+ five-star reviews.</h3>
        <p class="text-gray-500 text-sm font-light">Our patients love us. Join thousands of happy smiles who've discovered comfortable dental care.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">Same-day emergency care.</h3>
        <p class="text-gray-500 text-sm font-light">Dental emergencies happen. We're here when you need us with same-day appointments available.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">23 convenient locations.</h3>
        <p class="text-gray-500 text-sm font-light">Find a Swish studio near you across Austin, Houston, and San Antonio.</p>
      </div>
    </div>
  </section>

  <!-- How it works -->
  <section class="py-20 px-6 max-w-7xl mx-auto" id="services">
    <div class="mb-16 max-w-md">
      <h2 class="text-4xl font-medium mb-6">How it works.</h2>
      <p class="text-gray-600 font-light">From booking to follow-up care, we've designed every step of your dental experience to be simple, comfortable, and stress-free. Here's what to expect when you visit Swish.</p>
    </div>

    <div class="space-y-6">
      {#each steps as step}
        <div class="bg-white rounded-[40px] p-8 md:p-12 flex flex-col items-center text-center max-w-2xl mx-auto shadow-sm">
          <div class="w-full text-left mb-8">
            <span class="inline-block w-8 h-8 rounded-full border border-gray-200 text-center leading-8 text-sm font-medium mb-4">{step.step}</span>
            <h3 class="text-2xl font-medium mb-3">{step.title}</h3>
            <p class="text-gray-500 font-light text-sm max-w-lg">{step.desc}</p>
          </div>
          
          <!-- Phone Mockup for Step -->
          <div class="relative w-[240px] h-[480px] bg-black rounded-[35px] border-[6px] border-black shadow-xl overflow-hidden mt-4">
             <div class="absolute top-0 left-0 right-0 h-5 bg-black z-20 flex justify-center">
                <div class="w-16 h-3 bg-black rounded-b-lg"></div>
             </div>
             <div class="w-full h-full bg-white pt-8 px-3 overflow-hidden">
                <!-- Dynamic Content based on step -->
                {#if step.image === 'plan'}
                  <div class="space-y-3 mt-4">
                    <div class="p-3 border rounded-xl border-black bg-gray-50">
                      <div class="font-bold text-xs mb-1">Optimal ID</div>
                      <div class="h-1 w-full bg-gray-200 rounded"></div>
                    </div>
                    <div class="p-3 border rounded-xl border-gray-200">
                       <div class="font-bold text-xs mb-1 text-gray-400">Essential</div>
                       <div class="h-1 w-full bg-gray-100 rounded"></div>
                    </div>
                  </div>
                {:else if step.image === 'schedule'}
                   <div class="mt-4">
                     <div class="text-center font-bold mb-4">Appointment</div>
                     <div class="bg-gray-100 h-32 rounded-xl mb-3 flex items-center justify-center text-xs text-gray-400">Map View</div>
                     <button class="w-full bg-black text-white text-xs py-2 rounded-lg">Confirm</button>
                   </div>
                {:else if step.image === 'results'}
                   <div class="bg-black h-full -mx-3 -mt-8 pt-10 px-3 text-white">
                      <div class="text-center mb-6">
                        <div class="w-12 h-12 bg-gray-700 rounded-full mx-auto mb-2"></div>
                        <div class="text-sm font-bold">Grace Parker</div>
                      </div>
                      <div class="space-y-2">
                         <div class="bg-gray-800 p-2 rounded-lg h-10"></div>
                         <div class="bg-gray-800 p-2 rounded-lg h-10"></div>
                      </div>
                   </div>
                {:else if step.image === 'notes'}
                   <div class="mt-4 space-y-3">
                      <div class="font-bold text-sm">Health Status</div>
                      <div class="text-[10px] text-gray-500 leading-relaxed">
                        You usually make smart choices for your health through regular exercise...
                      </div>
                      <div class="bg-gray-50 p-2 rounded text-[10px] text-gray-600">
                        Since your diet lacks enough fruits and vegetables...
                      </div>
                   </div>
                {:else}
                   <div class="mt-4 flex flex-col h-full">
                      <div class="flex-1">
                        <div class="bg-gray-100 p-2 rounded-lg rounded-tl-none text-[10px] mb-2 max-w-[80%]">
                          What benefits can I get by bringing ApoB closer to the optimal range?
                        </div>
                        <div class="bg-blue-50 p-2 rounded-lg rounded-tr-none text-[10px] ml-auto max-w-[80%]">
                          By lowering ApoB, you reduce the number of cholesterol-carrying particles...
                        </div>
                      </div>
                      <div class="h-10 border-t mt-2"></div>
                   </div>
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
      <!-- Insurance Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">We work with your insurance.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">Most major insurance plans accepted.</h2>
          <p class="text-gray-400 text-sm mt-4 max-w-sm">We'll verify your coverage and help you maximize your benefits. Plus, flexible financing options through Cherry, CareCredit, and HFD.</p>
        </div>
        <!-- Abstract Visual -->
        <div class="absolute inset-0 flex items-center justify-center opacity-10 mt-20">
           <svg viewBox="0 0 200 100" class="w-full h-full text-gray-500 fill-current">
              <circle cx="50" cy="50" r="30" />
              <circle cx="150" cy="50" r="30" />
              <circle cx="100" cy="30" r="25" />
           </svg>
        </div>
      </div>

      <!-- Membership Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">No insurance? No problem.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">Join the Swish Smile Membership.</h2>
          <p class="text-gray-400 text-sm mt-4 max-w-sm">Get exclusive perks and discounts on all services with our proprietary membership program designed for patients without insurance.</p>
        </div>
        <!-- Abstract Visual -->
        <div class="absolute inset-0 flex items-center justify-center mt-20 overflow-hidden">
           <div class="text-8xl font-bold text-gray-600 opacity-10 select-none">
             SWISH
           </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Services Section -->
  <section class="py-24 px-6 max-w-7xl mx-auto" id="book">
    <div class="text-center mb-16">
      <h2 class="text-3xl md:text-4xl font-medium mb-4">Comprehensive dental care for everyone.</h2>
      <p class="text-gray-500 font-light max-w-2xl mx-auto">From preventative care to cosmetic dentistry, we offer a full range of services to keep your smile healthy and beautiful.</p>
    </div>

    <div class="grid md:grid-cols-2 gap-6 max-w-4xl mx-auto">
      <!-- Invisalign -->
      <div class="bg-white rounded-[32px] p-8 flex flex-col">
        <div class="w-12 h-12 bg-gray-100 rounded-full mb-6 flex items-center justify-center text-2xl">✨</div>
        <h3 class="text-2xl font-medium mb-1">Invisalign</h3>
        <p class="text-sm text-gray-500 mb-6">Straighten your smile discreetly.</p>
        <div class="mb-8">
          <div class="text-lg font-medium text-[#1A1A1A]">$2,025 OFF</div>
          <div class="text-[10px] text-gray-500 mt-1 font-medium">Limited time offer. Half the average cost of braces.</div>
        </div>
        <ul class="space-y-4 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Clear aligners that fit your lifestyle
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Comfortable and virtually invisible
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Flexible financing options available
          </li>
        </ul>
        <button class="w-full bg-[#1A1A1A] text-white py-3 rounded-sm font-medium hover:bg-black transition-colors">Book consultation</button>
      </div>

      <!-- Preventative Care -->
      <div class="bg-white rounded-[32px] p-8 flex flex-col relative overflow-hidden">
        <div class="absolute top-0 right-0 bg-[#FFF8E1] px-4 py-1 rounded-bl-xl text-xs font-medium text-orange-800">New Patients</div>
        <div class="w-12 h-12 bg-orange-100 rounded-full mb-6 flex items-center justify-center text-2xl">🦷</div>
        <h3 class="text-2xl font-medium mb-1">Preventative Care</h3>
        <p class="text-sm text-gray-500 mb-6">Keep your smile healthy and bright.</p>
        <div class="mb-8">
          <div class="text-lg font-medium text-[#1A1A1A]">FREE Whitening</div>
          <div class="text-[10px] text-gray-500 mt-1 font-medium">For new patients. Includes comprehensive exam and cleaning.</div>
        </div>
        <ul class="space-y-4 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Comprehensive dental exams
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Professional cleanings and hygiene
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Digital X-rays and imaging
          </li>
        </ul>
        <button class="w-full bg-[#1A1A1A] text-white py-3 rounded-sm font-medium hover:bg-black transition-colors">Book appointment</button>
      </div>
    </div>

    <div class="text-center mt-12">
      <p class="text-sm text-gray-500 mb-4">We also offer cosmetic dentistry, dental implants, veneers, crowns, emergency care, and more.</p>
      <button class="border border-gray-300 px-6 py-3 rounded-sm text-xs font-medium hover:bg-gray-50 transition-colors">
        View all services
      </button>
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
        View all FAQs
      </button>
    </div>
  </section>

  <!-- Footer -->
  <footer class="py-16 px-6 border-t border-gray-200 bg-[#F9F8F6]">
    <div class="max-w-7xl mx-auto">
      <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-8 mb-16">
        <div class="flex items-center gap-2">
           <span class="font-bold text-lg tracking-wide">SWISH DENTAL</span>
        </div>
        
        <nav class="flex flex-wrap gap-6 md:gap-8 text-xs font-medium text-gray-600">
          <a href="#services" class="hover:text-black">Services</a>
          <a href="#locations" class="hover:text-black">Locations</a>
          <a href="#faq" class="hover:text-black">FAQ</a>
          <a href="#" class="hover:text-black">Careers</a>
          <a href="#" class="hover:text-black">Blog</a>
          <a href="#" class="hover:text-black">Privacy Policy</a>
        </nav>

        <div class="flex gap-4 text-gray-800">
          <a href="https://www.instagram.com/swishdental" target="_blank" rel="noopener noreferrer" class="hover:text-black">{@html Instagram}</a>
          <a href="https://www.facebook.com/swishdental" target="_blank" rel="noopener noreferrer" class="hover:text-black">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"/></svg>
          </a>
        </div>
      </div>

      <div class="text-[10px] text-gray-400 leading-relaxed max-w-5xl">
        <p class="mb-2">© 2024 Swish Dental. All rights reserved. Swish Dental operates modern dental studios across Texas, providing comprehensive dental care including preventative dentistry, cosmetic dentistry, Invisalign, dental implants, and emergency dental services. Each location is staffed by licensed dental professionals committed to patient comfort and quality care.</p>
        <p>All dental services are provided by independent licensed dentists. Treatment plans and pricing may vary by location and individual patient needs. Insurance coverage and financing options available. For specific pricing and service details, please contact your nearest Swish Dental location.</p>
        <p class="mt-2">By providing your contact information, you agree to receive communications from Swish Dental about appointments, promotions, and dental health information. Message and data rates may apply.</p>
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

