# requiem
Proyek pertama saya dengan GitHub
```html
<!DOCTYPE html>
<html lang="id" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Wedding of Rian & Amanda - Undangan Pernikahan Digital Premium</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Alex+Brush&family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;0,700;1,400&family=Montserrat:wght@100;200;300;400;500;600;700&display=swap" rel="stylesheet">
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        /* Konfigurasi Font Mewah */
        .font-serif-luxury {
            font-family: 'Cormorant Garamond', serif;
        }
        .font-signature {
            font-family: 'Alex Brush', cursive;
        }
        .font-sans-modern {
            font-family: 'Montserrat', sans-serif;
        }

        /* Animasi Custom */
        @keyframes pulse-soft {
            0%, 100% { transform: scale(1); opacity: 0.9; }
            50% { transform: scale(1.05); opacity: 0.7; }
        }
        .animate-pulse-soft {
            animation: pulse-soft 4s cubic-bezier(0.4, 0, 0.6, 1) infinite;
        }

        @keyframes rotate-slow {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        .animate-rotate-slow {
            animation: rotate-slow 15s linear infinite;
        }

        /* Reveal on Scroll styling */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 1.2s cubic-bezier(0.215, 0.610, 0.355, 1);
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Glassmorphism premium effect */
        .glass-card {
            background: rgba(255, 255, 255, 0.04);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.08);
        }
        .glass-card-light {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        /* Sembunyikan Scrollbar default */
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #0f1319;
        }
        ::-webkit-scrollbar-thumb {
            background: #d4af37;
            border-radius: 3px;
        }
    </style>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        wedding: {
                            gold: '#d4af37',       /* Champagne / Gold */
                            goldDark: '#aa841c',
                            bgDark: '#0e1116',     /* Dark Mode Luxury default background */
                            cardDark: '#171c24',
                            textMuted: '#9aa5b5',
                            sage: '#8fa89b',
                            rose: '#c8a2c8'
                        }
                    }
                }
            }
        }
    </script>
</head>
<body class="bg-wedding-bgDark text-gray-100 font-sans-modern overflow-x-hidden relative">

    <!-- Loading Screen Elegan -->
    <div id="loading-screen" class="fixed inset-0 bg-wedding-bgDark z-[9999] flex flex-col items-center justify-center transition-all duration-1000">
        <div class="relative flex flex-col items-center">
            <div class="w-24 h-24 border-t-2 border-r-2 border-wedding-gold rounded-full animate-rotate-slow"></div>
            <div class="absolute inset-0 flex items-center justify-center">
                <span class="font-serif-luxury text-3xl font-light text-wedding-gold animate-pulse">R & A</span>
            </div>
            <h2 class="font-serif-luxury text-xl font-light tracking-[0.25em] text-[#d4af37] mt-8 animate-pulse">MEMUAT KEINDAHAN</h2>
            <p class="text-[10px] tracking-[0.4em] text-wedding-textMuted mt-2 uppercase">The Royal Wedding Invitation</p>
        </div>
    </div>

    <!-- Overlay Undangan Pembuka (Cover) -->
    <div id="wedding-cover" class="fixed inset-0 z-[80] flex flex-col items-center justify-center bg-cover bg-center transition-all duration-1000 relative" style="background-image: linear-gradient(to bottom, rgba(14, 17, 22, 0.95), rgba(14, 17, 22, 0.85)), url('https://lh3.googleusercontent.com/d/1SariMuliaUnivLogoSampleID789');">
        <!-- Bingkai Klasik Premium -->
        <div class="absolute inset-6 border border-wedding-gold/20 pointer-events-none rounded-xl"></div>
        <div class="absolute inset-8 border border-wedding-gold/10 pointer-events-none rounded-xl"></div>
        
        <div class="z-10 text-center max-w-lg px-6 flex flex-col items-center">
            <span class="text-[10px] tracking-[0.4em] text-wedding-gold uppercase font-semibold mb-4">UNDANGAN PERNIKAHAN DIGITAL</span>
            
            <div class="flex items-center justify-center gap-1 my-4">
                <div class="h-[1px] w-8 bg-wedding-gold/40"></div>
                <span class="text-xs uppercase tracking-widest text-wedding-textMuted font-light">The Wedding of</span>
                <div class="h-[1px] w-8 bg-wedding-gold/40"></div>
            </div>

            <h1 class="font-signature text-6xl md:text-8xl text-wedding-gold py-4 leading-tight">Rian & Amanda</h1>
            
            <p class="font-serif-luxury text-lg tracking-[0.15em] text-gray-200 mt-2 font-light">Minggu, 18 Oktober 2026</p>
            
            <!-- Ditujukan Kepada -->
            <div class="mt-10 p-6 glass-card rounded-2xl w-full border border-wedding-gold/30">
                <p class="text-[10px] tracking-[0.2em] text-wedding-textMuted uppercase mb-2">Kepada Yth. Bapak/Ibu/Saudara/i:</p>
                <h3 id="recipient-name" class="font-serif-luxury text-2xl text-white font-medium my-2">Tamu Undangan Istimewa</h3>
                <p class="text-[10px] text-wedding-textMuted italic mt-2">*Mohon maaf apabila ada kesalahan penulisan nama/gelar</p>
            </div>

            <!-- Tombol Buka Undangan -->
            <button onclick="openInvitation()" class="mt-8 group relative bg-gradient-to-r from-wedding-gold to-wedding-goldDark text-wedding-bgDark font-bold text-xs tracking-[0.25em] uppercase px-8 py-4 rounded-full overflow-hidden shadow-lg shadow-wedding-gold/10 transition-all active:scale-95 duration-300">
                <span class="relative z-10 flex items-center gap-2">
                    <i data-lucide="mail-open" class="w-4 h-4 animate-bounce"></i> BUKA UNDANGAN
                </span>
                <div class="absolute inset-0 bg-white opacity-0 group-hover:opacity-10 transition-opacity duration-300"></div>
            </button>
        </div>
    </div>

    <!-- Music Control (Floating Player) -->
    <div id="music-container" class="fixed bottom-6 left-6 z-[70] hidden">
        <audio id="bg-music" loop>
            <!-- Menggunakan Musik Latar Bebas Hak Cipta Premium (Instrumental Romantis) -->
            <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
        </audio>
        <button onclick="toggleMusic()" id="btn-music" class="w-12 h-12 rounded-full bg-wedding-gold hover:bg-wedding-goldDark text-wedding-bgDark flex items-center justify-center shadow-lg shadow-wedding-gold/20 transition-all duration-300 active:scale-90 relative">
            <span class="absolute inset-0 rounded-full bg-wedding-gold/30 animate-ping" id="music-ping"></span>
            <i data-lucide="music" id="music-icon" class="w-5 h-5 relative z-10"></i>
        </button>
    </div>

    <!-- Floating Navigation Bar -->
    <nav id="floating-nav" class="fixed bottom-6 left-1/2 -translate-x-1/2 z-[70] hidden glass-card rounded-full px-6 py-3 border border-wedding-gold/20 shadow-2xl">
        <ul class="flex items-center gap-6 md:gap-8">
            <li>
                <a href="#hero" class="text-wedding-textMuted hover:text-wedding-gold transition-colors duration-300 flex flex-col items-center gap-1">
                    <i data-lucide="home" class="w-4 h-4"></i>
                    <span class="text-[9px] uppercase tracking-wider font-light">Home</span>
                </a>
            </li>
            <li>
                <a href="#couple" class="text-wedding-textMuted hover:text-wedding-gold transition-colors duration-300 flex flex-col items-center gap-1">
                    <i data-lucide="heart" class="w-4 h-4"></i>
                    <span class="text-[9px] uppercase tracking-wider font-light">Mempelai</span>
                </a>
            </li>
            <li>
                <a href="#events" class="text-wedding-textMuted hover:text-wedding-gold transition-colors duration-300 flex flex-col items-center gap-1">
                    <i data-lucide="calendar" class="w-4 h-4"></i>
                    <span class="text-[9px] uppercase tracking-wider font-light">Acara</span>
                </a>
            </li>
            <li>
                <a href="#gallery" class="text-wedding-textMuted hover:text-wedding-gold transition-colors duration-300 flex flex-col items-center gap-1">
                    <i data-lucide="image" class="w-4 h-4"></i>
                    <span class="text-[9px] uppercase tracking-wider font-light">Galeri</span>
                </a>
            </li>
            <li>
                <a href="#rsvp" class="text-wedding-textMuted hover:text-wedding-gold transition-colors duration-300 flex flex-col items-center gap-1">
                    <i data-lucide="message-square" class="w-4 h-4"></i>
                    <span class="text-[9px] uppercase tracking-wider font-light">RSVP</span>
                </a>
            </li>
        </ul>
    </nav>

    <!-- CONTENT WRAPPER -->
    <div id="main-content" class="hidden">

        <!-- HERO SECTION (Parallax Ringan & Modern) -->
        <section id="hero" class="relative h-screen flex flex-col items-center justify-center text-center overflow-hidden">
            <!-- Background Image Parallax -->
            <div id="hero-bg" class="absolute inset-0 bg-cover bg-center transition-transform duration-700 ease-out z-0 scale-105" style="background-image: linear-gradient(to top, rgba(14, 17, 22, 1) 15%, rgba(14, 17, 22, 0.4) 50%, rgba(14, 17, 22, 0.8) 100%), url('https://lh3.googleusercontent.com/d/1SariMuliaUnivLogoSampleID789');"></div>
            
            <div class="relative z-10 max-w-xl px-6 flex flex-col items-center">
                <span class="text-[10px] tracking-[0.5em] text-wedding-gold uppercase mb-3 animate-pulse-soft">THE ROYAL CELEBRATION</span>
                <p class="font-serif-luxury text-sm tracking-[0.2em] text-gray-300 mb-6 font-light">Kami mengundang Anda untuk merayakan cinta kami</p>
                
                <h2 class="font-signature text-7xl md:text-9xl text-wedding-gold leading-none py-4">Rian & Amanda</h2>
                
                <!-- Countdown Box Modern -->
                <div class="mt-8 glass-card border border-wedding-gold/20 p-6 rounded-2xl w-full grid grid-cols-4 gap-3 max-w-md mx-auto">
                    <div class="text-center">
                        <span id="days" class="font-serif-luxury text-3xl md:text-4xl text-wedding-gold font-light block">00</span>
                        <span class="text-[9px] tracking-widest text-wedding-textMuted uppercase font-light">Hari</span>
                    </div>
                    <div class="text-center border-l border-white/10">
                        <span id="hours" class="font-serif-luxury text-3xl md:text-4xl text-wedding-gold font-light block">00</span>
                        <span class="text-[9px] tracking-widest text-wedding-textMuted uppercase font-light">Jam</span>
                    </div>
                    <div class="text-center border-l border-white/10">
                        <span id="minutes" class="font-serif-luxury text-3xl md:text-4xl text-wedding-gold font-light block">00</span>
                        <span class="text-[9px] tracking-widest text-wedding-textMuted uppercase font-light">Menit</span>
                    </div>
                    <div class="text-center border-l border-white/10">
                        <span id="seconds" class="font-serif-luxury text-3xl md:text-4xl text-wedding-gold font-light block">00</span>
                        <span class="text-[9px] tracking-widest text-wedding-textMuted uppercase font-light">Detik</span>
                    </div>
                </div>

                <div class="mt-8 flex flex-col items-center animate-bounce">
                    <span class="text-[9px] tracking-[0.3em] text-wedding-textMuted uppercase font-light mb-1">Scroll ke Bawah</span>
                    <i data-lucide="chevron-down" class="w-4 h-4 text-[#d4af37]"></i>
                </div>
            </div>
        </section>


        <!-- KATA SAMBUTAN / AYAT SUCI (Reveal Section) -->
        <section class="py-20 px-6 bg-wedding-bgDark flex flex-col items-center text-center relative">
            <div class="absolute top-0 left-1/2 -translate-x-1/2 w-40 h-[1px] bg-gradient-to-r from-transparent via-wedding-gold/30 to-transparent"></div>
            
            <div class="max-w-3xl reveal space-y-6">
                <i data-lucide="quote" class="w-10 h-10 text-wedding-gold/30 mx-auto"></i>
                <h3 class="font-serif-luxury text-2xl md:text-3xl text-wedding-gold font-light italic">"Dan di antara tanda-tanda (kebesaran)-Nya ialah Dia menciptakan pasangan-pasangan untukmu dari jenismu sendiri, agar kamu cenderung dan merasa tenteram kepadanya, dan Dia menjadikan di antaramu rasa kasih dan sayang."</h3>
                <p class="text-xs tracking-widest text-wedding-textMuted uppercase">— QS. Ar-Rum: 21</p>
            </div>
        </section>


        <!-- MEMPELAI SECTION -->
        <section id="couple" class="py-24 px-6 bg-gradient-to-b from-wedding-bgDark to-wedding-cardDark flex flex-col items-center">
            <div class="max-w-5xl w-full">
                <!-- Section Title -->
                <div class="text-center mb-16 reveal">
                    <span class="text-[10px] tracking-[0.4em] text-wedding-gold uppercase font-semibold">MEMPELAI YANG BERBAHAGIA</span>
                    <h2 class="font-serif-luxury text-4xl md:text-5xl font-light text-white mt-2">Dua Hati, Satu Janji</h2>
                    <div class="w-24 h-[1.5px] bg-wedding-gold mx-auto mt-4"></div>
                </div>

                <!-- Mempelai Grid -->
                <div class="grid grid-cols-1 md:grid-cols-2 gap-16 md:gap-8 items-center">
                    
                    <!-- Mempelai Pria -->
                    <div class="flex flex-col items-center text-center reveal space-y-6">
                        <div class="relative w-64 h-64 md:w-72 md:h-72 rounded-full overflow-hidden border-2 border-[#d4af37]/30 p-2 group">
                            <div class="absolute inset-0 border border-[#d4af37]/10 rounded-full animate-pulse-soft"></div>
                            <img src="https://lh3.googleusercontent.com/d/1DosenSignatureSampleID123" alt="Foto Pengantin Pria" class="w-full h-full object-cover rounded-full filter grayscale hover:grayscale-0 transition-all duration-700 scale-105 group-hover:scale-100" onerror="this.src='https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?auto=format&fit=crop&q=80&w=400'">
                        </div>
                        <div class="space-y-2">
                            <h3 class="font-serif-luxury text-3xl font-light text-white tracking-wide">Rian Baskoro, S.T.</h3>
                            <p class="text-xs uppercase tracking-widest text-wedding-gold font-medium">Putra sulung dari:</p>
                            <p class="font-serif-luxury text-lg text-gray-300 font-light">Bapak Ir. Hermawan Baskoro</p>
                            <p class="font-serif-luxury text-lg text-gray-300 font-light">& Ibu Dr. Endah Pertiwi</p>
                        </div>
                        <div class="flex items-center gap-4 text-wedding-textMuted text-xs font-light">
                            <a href="#" class="hover:text-wedding-gold transition-colors duration-300 flex items-center gap-1">
                                <i data-lucide="instagram" class="w-3.5 h-3.5"></i> @rian_baskoro
                            </a>
                        </div>
                    </div>

                    <!-- Mempelai Wanita -->
                    <div class="flex flex-col items-center text-center reveal space-y-6">
                        <div class="relative w-64 h-64 md:w-72 md:h-72 rounded-full overflow-hidden border-2 border-[#d4af37]/30 p-2 group">
                            <div class="absolute inset-0 border border-[#d4af37]/10 rounded-full animate-pulse-soft"></div>
                            <img src="https://lh3.googleusercontent.com/d/1KaprodiSignatureSampleID456" alt="Foto Pengantin Wanita" class="w-full h-full object-cover rounded-full filter grayscale hover:grayscale-0 transition-all duration-700 scale-105 group-hover:scale-100" onerror="this.src='https://images.unsplash.com/photo-1494790108377-be9c29b29330?auto=format&fit=crop&q=80&w=400'">
                        </div>
                        <div class="space-y-2">
                            <h3 class="font-serif-luxury text-3xl font-light text-white tracking-wide">Amanda Clarissa, M.B.A.</h3>
                            <p class="text-xs uppercase tracking-widest text-wedding-gold font-medium">Putri bungsu dari:</p>
                            <p class="font-serif-luxury text-lg text-gray-300 font-light">Bapak Prof. H. Wijaya Setyo</p>
                            <p class="font-serif-luxury text-lg text-gray-300 font-light">& Ibu Hj. Kartini Setyo</p>
                        </div>
                        <div class="flex items-center gap-4 text-wedding-textMuted text-xs font-light">
                            <a href="#" class="hover:text-wedding-gold transition-colors duration-300 flex items-center gap-1">
                                <i data-lucide="instagram" class="w-3.5 h-3.5"></i> @amanda_clarissa
                            </a>
                        </div>
                    </div>

                </div>
            </div>
        </section>


        <!-- ACARA PERNIKAHAN SECTION -->
        <section id="events" class="py-24 px-6 bg-wedding-bgDark flex flex-col items-center relative overflow-hidden">
            <!-- Decorative circle -->
            <div class="absolute -left-32 top-1/3 w-96 h-96 bg-wedding-gold/5 rounded-full blur-3xl"></div>
            <div class="absolute -right-32 bottom-1/3 w-96 h-96 bg-wedding-gold/5 rounded-full blur-3xl"></div>

            <div class="max-w-5xl w-full relative z-10">
                <!-- Section Title -->
                <div class="text-center mb-16 reveal">
                    <span class="text-[10px] tracking-[0.4em] text-wedding-gold uppercase font-semibold">TANGGAL & WAKTU ACARA</span>
                    <h2 class="font-serif-luxury text-4xl md:text-5xl font-light text-white mt-2">Momen Bahagia</h2>
                    <div class="w-24 h-[1.5px] bg-wedding-gold mx-auto mt-4"></div>
                </div>

                <!-- Event Grid -->
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8 lg:gap-12">
                    
                    <!-- Akad Nikah Card -->
                    <div class="glass-card p-8 md:p-12 rounded-3xl border border-wedding-gold/15 flex flex-col justify-between item