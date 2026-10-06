<html lang="it" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Laura Macchi | Visual Artist & Graphic Designer</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    
    <!-- Google Fonts: Cormorant Garamond & Plus Jakarta Sans -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;0,700;1,400;1,600&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        gallery: {
                            bg: '#FBF9F5',        // Warm Alabaster / Cream
                            card: '#F4F1EA',      // Soft Warm Beige Accent
                            dark: '#141414',      // Deep Onyx / Charcoal
                            muted: '#66635D',     // Editorial Slate Grey
                            border: '#E2DEC3',    // Delicate Border Neutral
                            accent: '#8C3B2B',    // Muted Terracotta / Rust
                            gold: '#C5A059'       // Soft Editorial Gold Accent
                        }
                    },
                    fontFamily: {
                        sans: ['"Plus Jakarta Sans"', 'sans-serif'],
                        serif: ['"Cormorant Garamond"', 'serif'],
                    }
                }
            }
        }
    </script>

    <style>
        body {
            background-color: #FBF9F5;
            color: #141414;
            font-family: 'Plus Jakarta Sans', sans-serif;
            -webkit-font-smoothing: antialiased;
        }

        /* Editorial Line Decor */
        .editorial-border-b {
            border-bottom: 1px solid rgba(20, 20, 20, 0.12);
        }
        .editorial-border-t {
            border-top: 1px solid rgba(20, 20, 20, 0.12);
        }

        /* Subtle Hover Blur for Gallery */
        .gallery-card:hover .gallery-image {
            transform: scale(1.03);
        }
        
        .gallery-card .gallery-overlay {
            opacity: 0;
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .gallery-card:hover .gallery-overlay {
            opacity: 1;
        }

        /* Filter Tab Active Pill */
        .filter-tab.active {
            color: #141414;
            border-bottom: 2px solid #141414;
        }

        /* Custom Scrollbar for Lightbox */
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #FBF9F5;
        }
        ::-webkit-scrollbar-thumb {
            background: #D1CFC7;
            border-radius: 3px;
        }
    </style>
</head>
<body class="selection:bg-gallery-dark selection:text-gallery-bg flex flex-col justify-between min-h-screen">

    <!-- NAVIGATION HEADER -->
    <header class="fixed top-0 left-0 w-full z-40 bg-[#FBF9F5]/90 backdrop-blur-md editorial-border-b transition-all duration-300">
        <div class="max-w-7xl mx-auto px-6 sm:px-10 h-20 flex items-center justify-between">
            
            <!-- Brand Mark -->
            <a href="#" class="group flex flex-col">
                <span class="font-serif font-semibold text-2xl tracking-widest text-gallery-dark uppercase leading-none">
                    Laura Macchi
                </span>
                <span class="text-[10px] font-sans font-medium tracking-[0.25em] text-gallery-muted uppercase mt-1 group-hover:text-gallery-accent transition-colors">
                Visual Artist &amp; Graphic Design</span>
            </a>

            <!-- Desktop Links -->
            <nav class="hidden md:flex items-center gap-10 text-xs tracking-[0.18em] uppercase font-medium text-gallery-muted">
                <a href="#progetti" class="hover:text-gallery-dark transition-colors">Progetti</a>
                <a href="#visione" class="hover:text-gallery-dark transition-colors">Visione</a>
                <a href="#studio" class="hover:text-gallery-dark transition-colors">Lo Studio</a>
                <a href="#contatti" class="hover:text-gallery-dark transition-colors">Contatti</a>
            </nav>

            <!-- Behance External Link -->
            <div class="hidden sm:flex items-center gap-4">
                <a href="https://www.behance.net/lauramacchi4" target="_blank" rel="noopener noreferrer"
                   class="inline-flex items-center gap-2 text-xs uppercase tracking-widest font-semibold px-4 py-2 border border-gallery-dark/20 hover:border-gallery-dark text-gallery-dark transition-all rounded-full">
                    <span class="www behance">Behance</span>
                    <i data-lucide="arrow-up-right" class="w-3.5 h-3.5"></i>
                </a>
            </div>

            <!-- Mobile Toggle -->
            <button id="mobile-toggle" aria-label="Menu Mobile" class="md:hidden text-gallery-dark p-2">
                <i data-lucide="menu" class="w-6 h-6"></i>
            </button>
        </div>

        <!-- Mobile Drawer -->
        <div id="mobile-menu" class="hidden md:hidden bg-gallery-bg border-b border-gallery-dark/10 px-8 py-6 space-y-4">
            <a href="#progetti" class="block text-sm uppercase tracking-widest font-medium py-2 text-gallery-dark mobile-link">Progetti</a>
            <a href="#visione" class="block text-sm uppercase tracking-widest font-medium py-2 text-gallery-dark mobile-link">Visione</a>
            <a href="#studio" class="block text-sm uppercase tracking-widest font-medium py-2 text-gallery-dark mobile-link">Lo Studio</a>
            <a href="#contatti" class="block text-sm uppercase tracking-widest font-medium py-2 text-gallery-dark mobile-link">Contatti</a>
            <div class="pt-4 editorial-border-t">
                <a href="https://www.behance.net/lauramacchi4" target="_blank" class="inline-flex items-center gap-2 text-xs uppercase tracking-widest font-bold text-gallery-accent">
                    <span>Vedi Portfolio su Behance</span>
                    <i data-lucide="external-link" class="w-4 h-4"></i>
                </a>
            </div>
        </div>
    </header>
	
    <!-- HERO SECTION -->
    <section class="pt-36 sm:pt-44 pb-20 px-6 sm:px-10 max-w-7xl mx-auto">
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 lg:gap-16 items-center">
            
            <!-- Hero Left Typography -->
            <div class="lg:col-span-7 space-y-8">
                
                <div class="inline-flex items-center gap-3">
                    <span class="w-2 h-2 rounded-full bg-gallery-accent"></span>
                    <span class="text-xs uppercase tracking-[0.25em] font-medium text-gallery-muted">Studio d'Arte & Graphic Design</span>
                </div>

                <h1 class="text-4xl sm:text-6xl xl:text-7xl font-serif font-light text-gallery-dark leading-[1.08] tracking-tight">
                    Equilibrio visivo, <br/>
                    <span class="italic font-normal text-gallery-accent">pittura d'autore</span> <br/>
                    e marca contemporanea.
                </h1>

                <p class="text-base sm:text-lg text-gallery-muted font-light leading-relaxed max-w-xl">
                    Mi presento!
					Sono una grafica pubblicitaria e visual designer con la passione per l'arte.
					Ho intrapreso lo studio dell'arte fin da bambina, continuando con la laurea in Conservazione dei beni culturali, in ambito storico artistico medievale e bizzantino.
					Negli anni successivi mi sono impegnata in un corso di arte del Maestro Enrico Massa, storico disegnatore per la Sergio Bonelli Editore, che mi ha insegnato la cura del dettaglio e l'arte del racconto visivo.
					Attraverso questo spazio condivido alcuni dei miei progetti e delle collaborazioni.
                </p>

                <!-- Action Links -->
                <div class="pt-4 flex flex-wrap items-center gap-6">
                    <a href="#progetti" class="inline-flex items-center gap-3 px-7 py-4 bg-gallery-dark text-gallery-bg text-xs uppercase tracking-widest font-semibold hover:bg-gallery-accent transition-colors rounded-full">
                        <span>Esplora il Portfolio</span>
                        <i data-lucide="arrow-down" class="w-4 h-4"></i>
                    </a>

                    <a href="#contatti" class="inline-flex items-center gap-2 text-xs uppercase tracking-widest font-semibold text-gallery-dark hover:text-gallery-accent transition-colors group">
                        <span>Inizia un Progetto</span>
                        <i data-lucide="arrow-right" class="w-4 h-4 group-hover:translate-x-1 transition-transform"></i>
                    </a>
                </div>

                <!-- Studio Meta Grid -->
                <div class="pt-10 editorial-border-t grid grid-cols-3 gap-6 max-w-lg">
                    <div>
                        <span class="block text-2xl font-serif text-gallery-dark">01</span>
                        <span class="text-[11px] uppercase tracking-wider text-gallery-muted">Branding & Gin</span>
                    </div>
                    <div>
                        <span class="block text-2xl font-serif text-gallery-dark">02</span>
                        <span class="text-[11px] uppercase tracking-wider text-gallery-muted">Fine Art & Natura</span>
                    </div>
                    <div>
                        <span class="block text-2xl font-serif text-gallery-dark">03</span>
                        <span class="text-[11px] uppercase tracking-wider text-gallery-muted">Editorial Design</span>
                    </div>
                </div>

            </div>

            <!-- Hero Right Editorial Showcase -->
            <div class="lg:col-span-5">
                <div class="relative">
                    
                    <!-- Decorative Vignette Card -->
                    <div class="bg-gallery-card p-4 sm:p-6 rounded-2xl border border-gallery-border/80 space-y-4">
                        
                        <!-- Hero Highlight Image (Studio Photo) -->
                       <div class="relative aspect-[3/4] overflow-hidden rounded-xl bg-gallery-bg">
  <a href="Foto1.png">
    <img 
      src="Foto1.png" 
      alt="Laura Macchi Studio" 
      class="w-full h-full object-cover object-top filter grayscale contrast-105 hover:grayscale-0 transition-all duration-700" 
      onerror="this.src='https://placehold.co/600x800/E2DEC3/141414?text=Laura+Macchi'"
    >
  </a> 
</div>

                        <!-- Fine Caption -->
                        <div class="flex items-center justify-between text-xs text-gallery-muted font-light pt-1">
                            <span class="italic font-serif text-sm text-gallery-dark">Laura Macchi nel suo Atelier</span>
                            <span class="uppercase tracking-widest text-[10px]">2026 Edition</span>
                        </div>

                    </div>

                </div>
            </div>

        </div>
    </section>
</div>

    <!-- PORTFOLIO SECTION -->
    <section id="progetti" class="py-24 editorial-border-t bg-gallery-bg">
        <div class="max-w-7xl mx-auto px-6 sm:px-10">
            
            <!-- Section Header & Filter Tabs -->
            <div class="flex flex-col md:flex-row md:items-end justify-between mb-16 gap-8">
                <div>
                    <span class="text-xs uppercase tracking-[0.25em] font-medium text-gallery-muted">Selezione Lavori</span>
                    <h2 class="text-3xl sm:text-5xl font-serif font-light text-gallery-dark mt-2">Galleria delle Opere</h2>
                </div>

                <!-- Minimalist Filter Bar -->
                <div class="flex flex-wrap gap-8 text-xs font-semibold uppercase tracking-widest text-gallery-muted editorial-border-b pb-2">
                    <button class="filter-tab active py-1 transition-colors" data-filter="all">
                        Tutti i Lavori
                    </button>
                    <button class="filter-tab py-1 transition-colors hover:text-gallery-dark" data-filter="branding">
                    Branding &amp;Logo</button>
                    <button class="filter-tab py-1 transition-colors hover:text-gallery-dark" data-filter="illustrazione">
                        Illustrazione
                    </button>
                    <button class="filter-tab py-1 transition-colors hover:text-gallery-dark" data-filter="pittura">
                        Pittura Realistica
                    </button>
                </div>
            </div>

            <!-- Gallery Grid -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-12" id="gallery-grid">
                
                <!-- PROJECT 1: Sapore di Mare Gin -->
                <div class="gallery-card group cursor-pointer space-y-4" data-category="branding" onclick="openLightbox('modal-1')">
                    
                    <div class="relative overflow-hidden rounded-xl bg-gallery-card aspect-[4/3] border border-gallery-border/60">
                        <img src="gintonicend1.png" 
                             alt="Sapore di Mare - Spirito Gin" 
                             class="gallery-image w-full h-full object-cover transition-transform duration-700 ease-out"
                             onerror="this.src='https://placehold.co/800x600/141414/FBF9F5?text=Sapore+di+Mare'">

                      <div class="gallery-overlay absolute inset-0 bg-gallery-dark/40 backdrop-blur-[2px] flex items-end p-8 text-gallery-bg">
                            <div class="space-y-1">
                                <span class="text-[10px] font-mono tracking-widest uppercase text-gallery-gold">Palette &amp; Studio Visivo</span>
<p class="text-lg font-serif italic">Esplora il Progetto Completo ↗</p>
                            </div>
                        </div>
                    </div>

                    <div class="flex items-start justify-between">
                        <div>
                            <span class="text-[11px] uppercase tracking-widest text-gallery-muted block">ARREDO &amp; RISTORAZIONE&nbsp;</span>
                            <h3 class="text-2xl font-serif text-gallery-dark group-hover:text-gallery-accent transition-colors mt-0.5">
                                Sapore di Mare — Spirito "Gin"
                            </h3>
                      </div>

                        <!-- Color Palette Indicators -->
                        <div class="flex items-center gap-1.5 pt-2">
                            <span class="w-3.5 h-3.5 rounded-full bg-[#2D3E50] border border-gallery-border" title="Blu Notte"></span>
                            <span class="w-3.5 h-3.5 rounded-full bg-[#D97706] border border-gallery-border" title="Arancio Warm"></span>
                            <span class="w-3.5 h-3.5 rounded-full bg-[#EAB308] border border-gallery-border" title="Oro Ocra"></span>
                        </div>
                    </div>

                </div>

                <!-- PROJECT 2: Rana dagli occhi rossi -->
                <div class="gallery-card group cursor-pointer space-y-4" data-category="pittura" onclick="openLightbox('modal-2')">
                    
                    <div class="relative overflow-hidden rounded-xl bg-gallery-card aspect-[4/3] border border-gallery-border/60">
                        <img src="occhio.jpg" 
                             alt="Rana Naturalistica" 
                             class="gallery-image w-full h-full object-cover transition-transform duration-700 ease-out"
                             onerror="this.src='https://placehold.co/800x600/8C3B2B/FBF9F5?text=Fine+Art+Frog'">

                        <div class="gallery-overlay absolute inset-0 bg-gallery-dark/40 backdrop-blur-[2px] flex items-end p-8 text-gallery-bg">
                            <div class="space-y-1">
                                <span class="text-[10px] font-mono tracking-widest uppercase text-gallery-gold">Studio di Precisione</span>
                                <p class="text-lg font-serif italic">Visualizza Dettagli Tecnici ↗</p>
                            </div>
                        </div>
                    </div>

                    <div class="flex items-start justify-between">
                        <div>
                            <span class="text-[11px] uppercase tracking-widest text-gallery-muted block">Naturalismo & Pittura</span>
                            <h3 class="text-2xl font-serif text-gallery-dark group-hover:text-gallery-accent transition-colors mt-0.5">
                                Espressione Naturale — Tree Frog
                            </h3>
                        </div>

                        <div class="flex items-center gap-1.5 pt-2">
                            <span class="w-3.5 h-3.5 rounded-full bg-[#16A34A] border border-gallery-border"></span>
                            <span class="w-3.5 h-3.5 rounded-full bg-[#DC2626] border border-gallery-border"></span>
                            <span class="w-3.5 h-3.5 rounded-full bg-[#0284C7] border border-gallery-border"></span>
                        </div>
                    </div>

                </div>
				<!-- PROJECT 3: Zahar Bothanics -->
                <div class="gallery-card group cursor-pointer space-y-4" data-category="branding" onclick="openLightbox('modal-3')">
                    
                    <div class="relative overflow-hidden rounded-xl bg-gallery-card aspect-[4/3] border border-gallery-border/60">
                        <img src="crema viso.png" 
                             alt="Zahar Bothanics - Essenze di Argan" 
                             class="gallery-image w-full h-full object-cover transition-transform duration-700 ease-out"
                             onerror="this.src='https://placehold.co/800x600/141414/FBF9F5?text=Sapore+di+Mare'">

                      <div class="gallery-overlay absolute inset-0 bg-gallery-dark/40 backdrop-blur-[2px] flex items-end p-8 text-gallery-bg">
                            <div class="space-y-1">
                                <span class="text-[10px] font-mono tracking-widest uppercase text-gallery-gold">Palette &amp; Studio Visivo</span>
<p class="text-lg font-serif italic">Esplora il Progetto Completo ↗</p>
                            </div>
                        </div>
                    </div>

                    <div class="flex items-start justify-between">
                        <div>
                            <span class="text-[11px] uppercase tracking-widest text-gallery-muted block">Brand identity &amp; Packaging&nbsp;</span>
                            <h3 class="text-2xl font-serif text-gallery-dark group-hover:text-gallery-accent transition-colors mt-0.5">
                            Zahar Bothanics — Essenze di Argan&nbsp;&nbsp; </h3>
                      </div>

                        <!-- Color Palette Indicators -->
                        <div class="flex items-center gap-1.5 pt-2">
                            <span class="w-3.5 h-3.5 rounded-full bg-[#C2A646] border border-gallery-border" title="Oro"></span>
                            <span class="w-3.5 h-3.5 rounded-full bg-[#4A2B18] border border-gallery-border" title="Marrone"></span>
                            <span class="w-3.5 h-3.5 rounded-full bg-[#282828] border border-gallery-border" title="Nero scuro"></span>
                        </div>
                    </div>

                </div>

                <!-- PROJECT 4: Aethel -->
                <div class="gallery-card group cursor-pointer space-y-4" data-category="pittura" onclick="openLightbox('modal-4')">
                    
                    <div class="relative overflow-hidden rounded-xl bg-gallery-card aspect-[4/3] border border-gallery-border/60">
                        <img src="Aethel.png" 
                             alt="Aethel" 
                             class="gallery-image w-full h-full object-cover transition-transform duration-700 ease-out"
                             onerror="this.src='https://placehold.co/800x600/8C3B2B/FBF9F5?text=Fine+Art+Frog'">

                        <div class="gallery-overlay absolute inset-0 bg-gallery-dark/40 backdrop-blur-[2px] flex items-end p-8 text-gallery-bg">
                            <div class="space-y-1">
                                <span class="text-[10px] font-mono tracking-widest uppercase text-gallery-gold">Studio di Precisione</span>
                                <p class="text-lg font-serif italic">Visualizza Dettagli Tecnici ↗</p>
                            </div>
                        </div>
                    </div>

                    <div class="flex items-start justify-between">
                        <div>
                            <span class="text-[11px] uppercase tracking-widest text-gallery-muted block">brand identity &amp; recycle brand</span>
                            <h3 class="text-2xl font-serif text-gallery-dark group-hover:text-gallery-accent transition-colors mt-0.5">
                          Aethel — Conscious Tailoring&nbsp; </h3>
                        </div>

                        <div class="flex items-center gap-1.5 pt-2">
                            <span class="w-3.5 h-3.5 rounded-full bg-[#B84A39] border border-gallery-border"></span>
                            <span class="w-3.5 h-3.5 rounded-full bg-[#6E755E] border border-gallery-border"></span>
                            <span class="w-3.5 h-3.5 rounded-full bg-[#D4C3A3] border border-gallery-border"></span>
                        </div>
                    </div>

                </div>
							
                <!-- PROJECT 3: Atelier Brand Identity -->
                <div class="gallery-card group cursor-pointer space-y-4 md:col-span-2" data-category="branding" onclick="openLightbox('modal-5')">
                    
                    <div class="relative overflow-hidden rounded-xl bg-gallery-card p-12 sm:p-20 border border-gallery-border/60 flex flex-col md:flex-row items-center justify-between gap-8">
                        <div class="space-y-4 max-w-xl">
                            <span class="text-xs uppercase tracking-[0.25em] font-medium text-gallery-accent">Editoriale &amp; marketing</span>
                            <h3 class="text-3xl sm:text-5xl font-serif text-gallery-dark leading-tight">
                            Campagne Pubblicitarie &amp; Comunicazione&nbsp;</h3>
                            <p class="text-sm text-gallery-muted font-light leading-relaxed">
                          Sistemi di comunicazione integrata per marchi,&nbsp; &nbsp; enogastronomia, arte ed eventi d'élite.</p>
                        </div>

                        <div class="w-20 h-20 rounded-full border border-gallery-dark/30 flex items-center justify-center shrink-0 group-hover:bg-gallery-dark group-hover:text-gallery-bg transition-all duration-500">
                            <i data-lucide="arrow-up-right" class="w-8 h-8"></i>
                        </div>
                    </div>

                </div>

            </div>

            <!-- External Behance Banner -->
            <div class="mt-20 p-10 sm:p-14 rounded-2xl bg-gallery-card border border-gallery-border flex flex-col sm:flex-row items-center justify-between gap-8">
                <div class="space-y-2 text-center sm:text-left">
                    <span class="text-xs uppercase tracking-widest text-gallery-accent font-semibold">Archivio Completo</span>
                    <h3 class="text-2xl sm:text-3xl font-serif text-gallery-dark">Esplora tutti i progetti su Behance</h3>
                </div>

                <a href="https://www.behance.net/lauramacchi4" target="_blank" rel="noopener noreferrer" 
                   class="px-8 py-4 bg-gallery-dark text-gallery-bg text-xs uppercase tracking-widest font-semibold hover:bg-gallery-accent transition-colors rounded-full whitespace-nowrap">
                    <span>Visita behance.net/lauramacchi4</span>
                </a>
            </div>

        </div>
    </section>

    <!-- PHILOSOPHY & STUDIO SECTION -->
    <section id="visione" class="py-24 editorial-border-t bg-gallery-bg">
        <div class="max-w-7xl mx-auto px-6 sm:px-10">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-16 items-center">
                
                <div class="lg:col-span-6 space-y-8">
                    <span class="text-xs uppercase tracking-[0.25em] font-medium text-gallery-muted">Filosofia Creativa</span>
                    
                    <h2 class="text-3xl sm:text-5xl font-serif font-light text-gallery-dark leading-snug">
                        "Un'immagine eccellente non comunica solo un messaggio; ne crea la memoria."
                    </h2>

                    <div class="space-y-4 text-sm text-gallery-muted font-light leading-relaxed">
                        <p>
                            Nel mio studio la grafica ed il disegno figurativo non sono entità separate, ma elementi complementari. Ogni bozzetto parte da uno studio attento della luce, dei pigmenti e della geometria compositiva.
                        </p>
                        <p>
                      Che si tratti di un’illustrazione per un’etichetta di pregio come una crema all'Argan,&nbsp; di un opera d'arredo&nbsp; enogastronomica o di un’opera naturalistica, il processo è sempre incentrato sulla ricerca dell'eleganza senza tempo.</p>
                    </div>

                    <div class="pt-4 grid grid-cols-2 gap-8">
                        <div class="editorial-border-t pt-4">
                            <span class="block text-xs uppercase tracking-widest font-semibold text-gallery-dark">Precisione Cromatica</span>
                            <span class="text-xs text-gallery-muted font-light mt-1 block">Studio meticoloso di palette e riflessi.</span>
                        </div>
                        <div class="editorial-border-t pt-4">
                            <span class="block text-xs uppercase tracking-widest font-semibold text-gallery-dark">Approccio Sartoriale</span>
                            <span class="text-xs text-gallery-muted font-light mt-1 block">Ogni progetto è unico e non replicabile.</span>
                        </div>
                    </div>
                </div>

                <div class="lg:col-span-6" id="studio">
                    <div class="bg-gallery-card p-8 rounded-2xl border border-gallery-border space-y-6">
                        <h3 class="text-2xl font-serif text-gallery-dark">Aree di Competenza</h3>
                        
                        <ul class="space-y-4 text-xs tracking-widest uppercase font-medium text-gallery-dark">
                            <li class="flex items-center justify-between pb-3 editorial-border-b">
                                <span>01. Visual Branding & Strategy</span>
                                <span class="text-gallery-muted">Identità Visiva</span>
                            </li>
                            <li class="flex items-center justify-between pb-3 editorial-border-b">
                                <span>02. Fine Art & Illustrazione</span>
                                <span class="text-gallery-muted">Pittura &amp; Natura</span>
                            </li>
                            <li class="flex items-center justify-between pb-3 editorial-border-b">
                                <span>03. Packaging & Etichette Premium</span>
                                <span class="text-gallery-muted">Food &amp; beauty&nbsp;</span>
                            </li>
                            <li class="flex items-center justify-between pb-3 editorial-border-b">
                                <span>04. Direzione Artistica & Layout</span>
                                <span class="text-gallery-muted">Editoria</span>
                            </li>
                        </ul>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- CONTACT SECTION -->
    <section id="contatti" class="py-24 editorial-border-t bg-gallery-bg">
        <div class="max-w-7xl mx-auto px-6 sm:px-10">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-16">
                
                <!-- Left Info -->
                <div class="lg:col-span-5 space-y-8">
                    <div>
                        <span class="text-xs uppercase tracking-[0.25em] font-medium text-gallery-muted">Contatti</span>
                        <h2 class="text-4xl sm:text-6xl font-serif font-light text-gallery-dark mt-2">Iniziamo un Progetto</h2>
                    </div>

                    <p class="text-sm text-gallery-muted font-light leading-relaxed">
                        Se sei interessato a sviluppare un’identità visiva d'impatto, commissionare un’illustrazione o collaborare ad un nuovo marchio, invia un messaggio.
                    </p>

                    <div class="space-y-4 pt-4">
                        <div class="editorial-border-t pt-4">
                            <span class="text-[10px] uppercase tracking-widest text-gallery-muted block">Email Studio</span>
                            <div class="flex items-center gap-3 mt-1">
                                <span class="font-serif text-lg text-gallery-dark" id="email-address">laura.macchi.grafica@gmail.com</span>
                                <button onclick="copyEmail()" class="text-xs uppercase tracking-wider text-gallery-accent hover:underline font-semibold">
                                    Copia
                                </button>
                            </div>
                        </div>

                        <div class="editorial-border-t pt-4">
                            <span class="text-[10px] uppercase tracking-widest text-gallery-muted block">Portfolio Esterno</span>
                            <a href="https://www.behance.net/lauramacchi4" target="_blank" class="font-serif text-lg text-gallery-dark hover:text-gallery-accent transition-colors block mt-1">
                                behance.net/lauramacchi4 ↗
                            </a>
                        </div>
                    </div>
                </div>

                <!-- Form Right -->
                <div class="lg:col-span-7">
                    <form onsubmit="handleContact(event)" class="space-y-8 bg-gallery-card p-8 sm:p-12 rounded-2xl border border-gallery-border">
                        
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-8">
                            <div class="space-y-2 editorial-border-b pb-2">
                                <label for="form-name" class="text-[10px] uppercase tracking-widest font-semibold text-gallery-muted block">Nome & Cognome</label>
                                <input type="text" id="form-name" required placeholder="Es. Mario Rossi" 
                                       class="w-full bg-transparent text-gallery-dark focus:outline-none text-sm font-medium placeholder-gallery-muted/50">
                            </div>

                            <div class="space-y-2 editorial-border-b pb-2">
                                <label for="form-email" class="text-[10px] uppercase tracking-widest font-semibold text-gallery-muted block">Indirizzo Email</label>
                                <input type="email" id="form-email" required placeholder="mario@esempio.it" 
                                       class="w-full bg-transparent text-gallery-dark focus:outline-none text-sm font-medium placeholder-gallery-muted/50">
                            </div>
                        </div>

                        <div class="space-y-2 editorial-border-b pb-2">
                            <label for="form-type" class="text-[10px] uppercase tracking-widest font-semibold text-gallery-muted block">Tipologia di Incarico</label>
                            <select id="form-type" class="w-full bg-transparent text-gallery-dark focus:outline-none text-sm font-medium">
                                <option value="branding">Identità di Marca / Packaging Food & Wine</option>
                                <option value="pittura">Pittura Realistica & Illustrazione</option>
                                <option value="editorial">Editorial & Direzione Artistica</option>
                                <option value="altro">Altro / Richiesta Informazioni</option>
                            </select>
                        </div>

                        <div class="space-y-2 editorial-border-b pb-2">
                            <label for="form-msg" class="text-[10px] uppercase tracking-widest font-semibold text-gallery-muted block">Dettagli sul Progetto</label>
                            <textarea id="form-msg" rows="4" required placeholder="Racconta la tua visione o i dettagli della collaborazione..." 
                                      class="w-full bg-transparent text-gallery-dark focus:outline-none text-sm font-medium resize-none placeholder-gallery-muted/50"></textarea>
                        </div>

                        <button type="submit" class="w-full py-4 bg-gallery-dark text-gallery-bg text-xs uppercase tracking-widest font-semibold hover:bg-gallery-accent transition-colors rounded-full">
                            Invia Richiesta
                        </button>

                        <div id="status-msg" class="hidden text-xs text-center font-medium text-emerald-800 pt-2">
                            ✓ Richiesta inviata con successo. Riceverai risposta entro 24 ore.
                        </div>

                    </form>
                </div>

            </div>
        </div>
    </section>

    <!-- LIGHTBOX MODALS -->
    
    <!-- Modal 1 -->
    <div id="modal-1" class="fixed inset-0 z-50 hidden flex items-center justify-center p-4 bg-gallery-dark/70 backdrop-blur-md">
        <div class="bg-gallery-bg max-w-4xl w-full rounded-2xl p-6 sm:p-10 border border-gallery-border max-h-[90vh] overflow-y-auto relative">
            
            <button onclick="closeLightbox('modal-1')" aria-label="Chiudi Modal" class="absolute top-6 right-6 p-2 rounded-full border border-gallery-dark/20 text-gallery-dark hover:bg-gallery-dark hover:text-gallery-bg transition-colors">
                <i data-lucide="x" class="w-5 h-5"></i>
            </button>

            <span class="text-xs uppercase tracking-widest text-gallery-muted">Studio di Arredo & Ristorazione</span>
            <h3 class="text-3xl sm:text-4xl font-serif text-gallery-dark mt-1">Sapore di Mare — Spirito "Gin"</h3>

            <div class="my-8 rounded-xl overflow-hidden border border-gallery-border">
                <img src="gintonicend.jpg" alt="Sapore di Mare Full" class="w-full h-auto object-cover" onerror="this.src='https://placehold.co/800x600/141414/FBF9F5?text=Sapore+di+Mare'">
            </div>

            <div class="space-y-4 text-sm text-gallery-muted font-light leading-relaxed">
                <p>
                    Progetto di composizione pittorica e grafica orientato al mondo degli <em>Spirits premium</em>. Il lavoro ritrae una bottiglia di <strong>Dry Tonic Three Cents</strong> con un bicchiere di <strong>Gin Roku</strong> affiancati da frutta fresca (arancia ed uva scura).
                </p>
                <p>
                    I toni dominanti spaziano dal blu notte profondo alle sfumature calde dell'arancio e dell'ocra. Progetto realizzato su commissione per un locale nella riviera ligure, a pochi passi da Portofino.
                </p>
            </div>

        </div>
    </div>

    <!-- Modal 2 -->
    <div id="modal-2" class="fixed inset-0 z-50 hidden flex items-center justify-center p-4 bg-gallery-dark/70 backdrop-blur-md">
        <div class="bg-gallery-bg max-w-4xl w-full rounded-2xl p-6 sm:p-10 border border-gallery-border max-h-[90vh] overflow-y-auto relative">
            
            <button onclick="closeLightbox('modal-2')" aria-label="Chiudi Modal" class="absolute top-6 right-6 p-2 rounded-full border border-gallery-dark/20 text-gallery-dark hover:bg-gallery-dark hover:text-gallery-bg transition-colors">
                <i data-lucide="x" class="w-5 h-5"></i>
            </button>

            <span class="text-xs uppercase tracking-widest text-gallery-muted">Naturalismo & Pittura</span>
            <h3 class="text-3xl sm:text-4xl font-serif text-gallery-dark mt-1">Espressione Naturale — Rana dagli occhi rossi</h3>

            <div class="my-8 rounded-xl overflow-hidden border border-gallery-border">
                <img src="Rana1.jpg" alt="Frog Full" class="w-full h-auto object-cover" onerror="this.src='https://placehold.co/800x600/8C3B2B/FBF9F5?text=Tree+Frog'">
            </div>

            <div class="space-y-4 text-sm text-gallery-muted font-light leading-relaxed">
                <p>
                    Opera in acrilico iperrealistica focalizzata sullo studio del contrasto cromatico tra la pelle verde e blu dell'anfibio, fino all'occhio rosso rubino con riflessi dettagliati.
              </p>
            </div>

        </div>
    </div>
			
			  <!-- Modal 3 -->
    <div id="modal-3" class="fixed inset-0 z-50 hidden flex items-center justify-center p-4 bg-gallery-dark/70 backdrop-blur-md">
        <div class="bg-gallery-bg max-w-4xl w-full rounded-2xl p-6 sm:p-10 border border-gallery-border max-h-[90vh] overflow-y-auto relative">
            
            <button onclick="closeLightbox('modal-3')" aria-label="Chiudi Modal" class="absolute top-6 right-6 p-2 rounded-full border border-gallery-dark/20 text-gallery-dark hover:bg-gallery-dark hover:text-gallery-bg transition-colors">
                <i data-lucide="x" class="w-5 h-5"></i>
            </button>

            <span class="text-xs uppercase tracking-widest text-gallery-muted">Brand Identity & Packaging</span>
            <h3 class="text-3xl sm:text-4xl font-serif text-gallery-dark mt-1">Zahar Bothanics — Essenze di Argan </h3>

            <div class="my-8 rounded-xl overflow-hidden border border-gallery-border">
                <img src="pexels-44740874-12998410.png" alt="Essenza pura del deserto Full" class="w-full h-auto object-cover" onerror="this.src='https://placehold.co/800x600/141414/FBF9F5?text=Sapore+di+Mare'">
            </div>

            <div class="space-y-4 text-sm text-gallery-muted font-light leading-relaxed">
                <p>
                    L'obbiettivo della progettazione per il logo della <em>Zahar Bothanics</em> è stato quello di valorizzare la <strong>purezza</strong> e l'<strong>artigianalità</strong> dell'olio di Argan al 100%.
                </p>
                <p>
                    L'incontro tra la tradizione cosmetica naturale ed un design moderno, pulito ed elegante. La narrazione visiva ruota attorno ai concetti di trasparenza, essenzialità e lusso naturale.
                </p>
            </div>

        </div>
    </div>

    <!-- Modal 4 -->
    <div id="modal-4" class="fixed inset-0 z-50 hidden flex items-center justify-center p-4 bg-gallery-dark/70 backdrop-blur-md">
        <div class="bg-gallery-bg max-w-4xl w-full rounded-2xl p-6 sm:p-10 border border-gallery-border max-h-[90vh] overflow-y-auto relative">
            
            <button onclick="closeLightbox('modal-4')" aria-label="Chiudi Modal" class="absolute top-6 right-6 p-2 rounded-full border border-gallery-dark/20 text-gallery-dark hover:bg-gallery-dark hover:text-gallery-bg transition-colors">
                <i data-lucide="x" class="w-5 h-5"></i>
            </button>

            <span class="text-xs uppercase tracking-widest text-gallery-muted">Brand Identity & Packaging</span>
            <h3 class="text-3xl sm:text-4xl font-serif text-gallery-dark mt-1">Aethel - Conscious Tailoring</h3>

            <div class="my-8 rounded-xl overflow-hidden border border-gallery-border">
                <img src="Aethel2.png" alt="Frog Full" class="w-full h-auto object-cover" onerror="this.src='https://placehold.co/800x600/8C3B2B/FBF9F5?text=Tree+Frog'">
            </div>

            <div class="space-y-4 text-sm text-gallery-muted font-light leading-relaxed">
                <p>
                    Progetto di branding circolare per <em>Aethel — Conscious Tailoring</em>, incentrato sul connubio tra <strong>sartorialità di alta gamma</strong> e <strong>riuso consapevole dei tessuti</strong>. L'identità visiva riflette l'anima sostenibile del brand attraverso un design essenziale, raffinato e fortemente legato all'etica del riciclo.
              </p>
            </div>

        </div>
	</div>

    <!-- Modal 5 -->
    <div id="modal-5" class="fixed inset-0 z-50 hidden flex items-center justify-center p-4 bg-gallery-dark/70 backdrop-blur-md">
        <div class="bg-gallery-bg max-w-4xl w-full rounded-2xl p-6 sm:p-10 border border-gallery-border max-h-[90vh] overflow-y-auto relative">
            
            <button onclick="closeLightbox('modal-5')" aria-label="Chiudi Modal" class="absolute top-6 right-6 p-2 rounded-full border border-gallery-dark/20 text-gallery-dark hover:bg-gallery-dark hover:text-gallery-bg transition-colors">
                <i data-lucide="x" class="w-5 h-5"></i>
            </button>

            <span class="text-xs uppercase tracking-widest text-gallery-muted">Comunicazione multicanale</span>
            <h3 class="text-3xl sm:text-4xl font-serif text-gallery-dark mt-1">Editoria & Social</h3>

            <div class="my-8 p-12 bg-gallery-card border border-gallery-border text-center space-y-4 rounded-xl">
                <i data-lucide="palette" class="w-12 h-12 text-gallery-dark mx-auto"></i>
                <h4 class="font-serif text-2xl text-gallery-dark">Marketing & Comunicazione</h4>
                <p class="text-xs uppercase tracking-widest text-gallery-muted max-w-md mx-auto">
                    Cura della progettazione grafica per pubblicazioni editoriali e sviluppo di materiali promozionali print e digital, unendo rigore di layout e strategia visiva per rafforzare l'identità del brand.
                </p>
            </div>

        </div>
    </div>

    <!-- FOOTER -->
    <footer class="bg-gallery-dark text-gallery-bg py-16 editorial-border-t">
        <div class="max-w-7xl mx-auto px-6 sm:px-10 flex flex-col sm:flex-row items-center justify-between gap-8">
            <div>
                <span class="font-serif font-semibold text-2xl tracking-wider uppercase block text-gallery-bg">Laura Macchi</span>
                <span class="text-xs text-gallery-muted tracking-widest uppercase mt-1 block">Visual Artist & Graphic Designer © 2026</span>
            </div>

            <div class="flex items-center gap-8 text-xs uppercase tracking-widest font-semibold">
                <a href="https://www.behance.net/lauramacchi4" target="_blank" rel="noopener noreferrer" class="hover:text-gallery-gold transition-colors">
                    Behance Portfolio ↗
                </a>
                <a href="#progetti" class="hover:text-gallery-gold transition-colors">
                    Torna Su ↑
					
<a href="Cv Macchi Laura.mp4" download="Cv Macchi Laura.mp4" 
   class="inline-flex items-center gap-2 px-6 py-3 rounded-xl bg-white text-neutral-900 font-semibold shadow-lg hover:bg-neutral-200 hover:scale-105 transition-all duration-300">
  <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 stroke-neutral-900" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
    <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
    <polyline points="7 10 12 15 17 10"></polyline>
    <line x1="12" y1="15" x2="12" y2="3"></line>
  </svg>
  <span>Scarica CV</span>
                </a>   

    <script>
        // Lucide Icons
        lucide.createIcons();

        // Mobile Menu
        const mobileToggle = document.getElementById('mobile-toggle');
        const mobileMenu = document.getElementById('mobile-menu');

        mobileToggle.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });

        document.querySelectorAll('.mobile-link').forEach(l => {
            l.addEventListener('click', () => mobileMenu.classList.add('hidden'));
        });

        // Filter Functionality
        const filterTabs = document.querySelectorAll('.filter-tab');
        const galleryCards = document.querySelectorAll('.gallery-card');

        filterTabs.forEach(tab => {
            tab.addEventListener('click', () => {
                filterTabs.forEach(t => t.classList.remove('active'));
                tab.classList.add('active');

                const cat = tab.getAttribute('data-filter');

                galleryCards.forEach(card => {
                    if (cat === 'all' || card.getAttribute('data-category') === cat) {
                        card.style.display = 'space-y-4';
                        card.style.display = 'block';
                    } else {
                        card.style.display = 'none';
                    }
                });
            });
        });

        // Lightbox Functions
        function openLightbox(id) {
            const m = document.getElementById(id);
            if (m) {
                m.classList.remove('hidden');
                document.body.style.overflow = 'hidden';
            }
        }

        function closeLightbox(id) {
            const m = document.getElementById(id);
            if (m) {
                m.classList.add('hidden');
                document.body.style.overflow = 'auto';
            }
        }

        // Copy Email to Clipboard
        function copyEmail() {
            const email = "laura.macchi.grafica@gmail.com";
            const temp = document.createElement("input");
            document.body.appendChild(temp);
            temp.value = email;
            temp.select();
            document.execCommand("copy");
            document.body.removeChild(temp);
            alert("Email copiata negli appunti: " + email);
        }

        // Contact Form Handle
        function handleContact(e) {
            e.preventDefault();
            const msg = document.getElementById('status-msg');
            msg.classList.remove('hidden');
            e.target.reset();
            setTimeout(() => {
                msg.classList.add('hidden');
            }, 6000);
        }
    </script>
