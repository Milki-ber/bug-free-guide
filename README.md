<!DOCTYPE html>
<html lang="en" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DELER BEROL | Esports & Gaming Realm</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts: Orbitron & Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Orbitron:wght@400;600;800;900&display=swap" rel="stylesheet">

    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        cyber: {
                            bg: '#090b10',
                            card: '#121624',
                            accent: '#00f0ff',
                            purple: '#9d4edd',
                            pink: '#ff007f',
                            gold: '#ffb703',
                            green: '#00ff66'
                        }
                    },
                    fontFamily: {
                        display: ['Orbitron', 'sans-serif'],
                        sans: ['Inter', 'sans-serif'],
                    },
                    boxShadow: {
                        'neon-cyan': '0 0 20px rgba(0, 240, 255, 0.4)',
                        'neon-purple': '0 0 20px rgba(157, 78, 221, 0.4)',
                        'neon-pink': '0 0 20px rgba(255, 0, 127, 0.4)',
                    }
                }
            }
        }
    </script>
    <style>
        html {
            scroll-behavior: smooth;
        }
        body {
            background-color: #090b10;
            color: #e2e8f0;
            overflow-x: hidden;
        }
        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #090b10;
        }
        ::-webkit-scrollbar-thumb {
            background: linear-gradient(to bottom, #00f0ff, #9d4edd);
            border-radius: 4px;
        }
        /* Glassmorphism & Cyber effects */
        .glass-panel {
            background: rgba(18, 22, 36, 0.75);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(0, 240, 255, 0.15);
        }
        .glass-panel-hover:hover {
            border-color: rgba(0, 240, 255, 0.6);
            box-shadow: 0 0 25px rgba(0, 240, 255, 0.25);
        }
        .text-glow-cyan {
            text-shadow: 0 0 10px rgba(0, 240, 255, 0.7), 0 0 20px rgba(0, 240, 255, 0.4);
        }
        .text-glow-purple {
            text-shadow: 0 0 10px rgba(157, 78, 221, 0.7), 0 0 20px rgba(157, 78, 221, 0.4);
        }
        .clip-cyber-btn {
            clip-path: polygon(12px 0%, 100% 0, 100% calc(100% - 12px), calc(100% - 12px) 100%, 0 100%, 0 12px);
        }
        .scanline {
            background: linear-gradient(to bottom, rgba(255,255,255,0), rgba(255,255,255,0) 50%, rgba(0, 240, 255, 0.05) 50%, rgba(0, 240, 255, 0.05));
            background-size: 100% 4px;
        }
        /* Custom Glowing Cursor Trail Effect element */
        #cursor-follower {
            pointer-events: none;
            position: fixed;
            width: 24px;
            height: 24px;
            border-radius: 50%;
            border: 2px solid #00f0ff;
            box-shadow: 0 0 15px #00f0ff;
            transform: translate(-50%, -50%);
            transition: width 0.15s, height 0.15s, border-color 0.15s;
            z-index: 9999;
        }
    </style>
</head>
<body class="font-sans antialiased text-slate-100 scanline relative">

    <!-- Interactive Background Canvas Particles -->
    <canvas id="cyber-canvas" class="fixed top-0 left-0 w-full h-full pointer-events-none z-0"></canvas>
    
    <!-- Custom Cursor Ring -->
    <div id="cursor-follower" class="hidden md:block"></div>

    <!-- Header & Navigation Bar -->
    <header class="sticky top-0 z-50 glass-panel border-b border-cyber-accent/20 bg-cyber-bg/90">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            
            <!-- Brand Logo -->
            <a href="#hero" class="flex items-center gap-3 group">
                <div class="w-10 h-10 rounded-lg bg-gradient-to-br from-cyber-accent to-cyber-purple flex items-center justify-center text-cyber-bg text-xl font-bold shadow-neon-cyan group-hover:scale-105 transition-transform">
                    <i class="fa-solid fa-gamepad"></i>
                </div>
                <div>
                    <span class="font-display font-black text-xl tracking-wider text-white group-hover:text-cyber-accent transition-colors">
                        DELER<span class="text-cyber-accent">BEROL</span>
                    </span>
                    <span class="block text-[10px] font-display uppercase tracking-widest text-cyber-purple font-semibold">Pro Streamer & Esports</span>
                </div>
            </a>

            <!-- Desktop Navigation Links -->
            <nav class="hidden md:flex items-center gap-8 font-display text-sm font-semibold tracking-wider">
                <a href="#hero" class="hover:text-cyber-accent transition-colors text-white">Home</a>
                <a href="#games" class="hover:text-cyber-accent transition-colors text-slate-300">Games</a>
                <a href="#stats" class="hover:text-cyber-accent transition-colors text-slate-300">Stats</a>
                <a href="#clips" class="hover:text-cyber-accent transition-colors text-slate-300">Clips</a>
                <a href="#setup" class="hover:text-cyber-accent transition-colors text-slate-300">Rig Setup</a>
                <a href="#community" class="hover:text-cyber-accent transition-colors text-slate-300">Community</a>
            </nav>

            <!-- Live Status Indicator & CTA -->
            <div class="flex items-center gap-4">
                <!-- LIVE NOW Indicator -->
                <div class="flex items-center gap-2 px-3 py-1.5 rounded-full bg-red-950/80 border border-red-500/40 text-red-400 text-xs font-display font-semibold tracking-wide shadow-sm">
                    <span class="relative flex h-2.5 w-2.5">
                      <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-red-400 opacity-75"></span>
                      <span class="relative inline-flex rounded-full h-2.5 w-2.5 bg-red-500"></span>
                    </span>
                    <span class="hidden sm:inline">LIVE NOW</span>
                </div>

                <!-- Watch Stream CTA -->
                <button onclick="openStreamModal()" class="hidden sm:flex items-center gap-2 px-5 py-2.5 bg-gradient-to-r from-cyber-accent to-cyber-purple text-cyber-bg font-display font-bold text-xs uppercase tracking-wider clip-cyber-btn shadow-neon-cyan hover:opacity-95 hover:scale-105 transition-all">
                    <i class="fa-solid fa-play text-sm"></i> Stream Realm
                </button>

                <!-- Mobile Menu Button -->
                <button id="mobileMenuBtn" class="md:hidden p-2.5 rounded-lg text-slate-300 hover:text-cyber-accent focus:outline-none">
                    <i class="fa-solid fa-bars text-xl"></i>
                </button>
            </div>
        </div>

        <!-- Mobile Nav Menu -->
        <div id="mobileMenu" class="hidden md:hidden glass-panel border-b border-cyber-accent/30 px-6 py-6 space-y-4 font-display text-sm tracking-wider">
            <a href="#hero" class="block text-white hover:text-cyber-accent font-semibold py-1">Home</a>
            <a href="#games" class="block text-slate-300 hover:text-cyber-accent font-semibold py-1">Games & Stream</a>
            <a href="#stats" class="block text-slate-300 hover:text-cyber-accent font-semibold py-1">Esports Stats</a>
            <a href="#clips" class="block text-slate-300 hover:text-cyber-accent font-semibold py-1">Highlights</a>
            <a href="#setup" class="block text-slate-300 hover:text-cyber-accent font-semibold py-1">Rig & Gear</a>
            <a href="#community" class="block text-slate-300 hover:text-cyber-accent font-semibold py-1">Join Community</a>
        </div>
    </header>

    <main class="relative z-10">

        <!-- Hero Section -->
        <section id="hero" class="relative py-16 md:py-28 overflow-hidden">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
                    
                    <!-- Left Hero Text Content -->
                    <div class="lg:col-span-7 space-y-6 text-center lg:text-left">
                        <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full glass-panel border border-cyber-accent/40 text-cyber-accent text-xs font-display font-semibold tracking-wider uppercase">
                            <i class="fa-solid fa-trophy text-cyber-gold"></i> Apex Predator & Champion Competitor
                        </div>

                        <h1 class="font-display text-4xl sm:text-6xl font-black uppercase tracking-tight leading-none text-white">
                            LEVEL UP WITH <br>
                            <span class="text-transparent bg-clip-text bg-gradient-to-r from-cyber-accent via-cyber-purple to-cyber-pink text-glow-cyan">
                                DELER BEROL
                            </span>
                        </h1>

                        <p class="text-slate-300 text-base sm:text-lg max-w-2xl mx-auto lg:mx-0 font-normal leading-relaxed">
                            Dominating the digital battlefield in Valorant, Apex Legends & FPS Arena tournaments. Watch live high-octane clutch streams, breakdown strategy, and join the elite <span class="text-cyber-accent font-semibold">Berol Army</span>.
                        </p>

                        <!-- Action Buttons -->
                        <div class="pt-2 flex flex-col sm:flex-row items-center justify-center lg:justify-start gap-4">
                            <button onclick="openStreamModal()" class="w-full sm:w-auto px-8 py-4 bg-gradient-to-r from-cyber-accent to-cyber-purple text-cyber-bg font-display font-black uppercase text-sm tracking-widest clip-cyber-btn shadow-neon-cyan hover:scale-105 transition-all flex items-center justify-center gap-3">
                                <i class="fa-brands fa-twitch text-lg"></i> Watch Live Broadcast
                            </button>
                            <a href="#community" class="w-full sm:w-auto px-8 py-4 glass-panel border-cyber-purple/50 hover:border-cyber-purple text-white font-display font-bold uppercase text-sm tracking-widest clip-cyber-btn hover:bg-cyber-purple/20 transition-all flex items-center justify-center gap-3">
                                <i class="fa-brands fa-discord text-lg text-cyber-purple"></i> Join Discord
                            </a>
                        </div>

                        <!-- Live Counter Badges -->
                        <div class="pt-8 grid grid-cols-3 gap-4 border-t border-slate-800/80">
                            <div class="glass-panel p-4 rounded-xl text-center">
                                <span class="block font-display text-2xl sm:text-3xl font-black text-cyber-accent" id="stat-followers">500K</span>
                                <span class="text-xs text-slate-400 uppercase font-display tracking-wider">Followers</span>
                            </div>
                            <div class="glass-panel p-4 rounded-xl text-center">
                                <span class="block font-display text-2xl sm:text-3xl font-black text-cyber-purple" id="stat-wins">1,420</span>
                                <span class="text-xs text-slate-400 uppercase font-display tracking-wider">Tournament Wins</span>
                            </div>
                            <div class="glass-panel p-4 rounded-xl text-center">
                                <span class="block font-display text-2xl sm:text-3xl font-black text-cyber-pink" id="stat-winrate">99.4%</span>
                                <span class="text-xs text-slate-400 uppercase font-display tracking-wider">Headshot Rate</span>
                            </div>
                        </div>
                    </div>

                    <!-- Right Hero Stream Preview Player -->
                    <div class="lg:col-span-5">
                        <div class="relative rounded-2xl glass-panel p-3 border-cyber-accent/30 shadow-neon-purple group">
                            <!-- Stream Player Container -->
                            <div class="relative aspect-video rounded-xl overflow-hidden bg-slate-950 flex items-center justify-center border border-slate-800">
                                <img src="https://images.unsplash.com/photo-1542751371-adc38448a05e?auto=format&fit=crop&w=800&q=80" alt="Stream Preview" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500 opacity-80">
                                
                                <div class="absolute inset-0 bg-gradient-to-t from-cyber-bg via-transparent to-transparent opacity-90"></div>

                                <!-- Center Play Button Trigger -->
                                <button onclick="openStreamModal()" class="absolute w-16 h-16 rounded-full bg-cyber-accent/90 text-cyber-bg flex items-center justify-center text-2xl shadow-neon-cyan hover:scale-110 transition-transform">
                                    <i class="fa-solid fa-play ml-1"></i>
                                </button>

                                <!-- Top Overlay Tag -->
                                <div class="absolute top-3 left-3 flex items-center gap-2 px-3 py-1 rounded bg-black/70 backdrop-blur-md text-xs font-display text-cyber-accent border border-cyber-accent/30">
                                    <i class="fa-solid fa-tower-broadcast text-red-500 animate-pulse"></i>
                                    <span>VALORANT RANK #1 RADIANT</span>
                                </div>

                                <!-- Bottom Chat Bubble Teaser -->
                                <div class="absolute bottom-3 left-3 right-3 bg-cyber-bg/90 backdrop-blur-md p-3 rounded-lg border border-slate-700/60 flex items-center justify-between text-xs font-mono">
                                    <div class="flex items-center gap-2 truncate">
                                        <span class="text-cyber-purple font-bold">@CyberViper:</span>
                                        <span class="text-slate-300 truncate">Insane 1v5 clutch on Haven! 🔥</span>
                                    </div>
                                    <span class="text-[10px] text-cyber-accent uppercase font-display">Just Now</span>
                                </div>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </section>

        <!-- Featured Games Showcase Section -->
        <section id="games" class="py-20 relative bg-cyber-card/40 border-y border-cyber-accent/10">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                
                <div class="flex flex-col md:flex-row md:items-end justify-between mb-12">
                    <div>
                        <span class="text-cyber-accent font-display text-xs tracking-widest uppercase font-bold">Featured Main Arena</span>
                        <h2 class="font-display text-3xl sm:text-4xl font-black text-white uppercase tracking-tight mt-1">
                            COMPETITIVE GAMES & BROADCASTS
                        </h2>
                    </div>
                    <!-- Game Category Tabs -->
                    <div class="mt-4 md:mt-0 flex flex-wrap gap-2 font-display text-xs">
                        <button onclick="filterGames('all')" class="game-tab-btn active px-4 py-2 rounded-lg glass-panel border-cyber-accent text-cyber-accent font-bold">ALL GAMES</button>
                        <button onclick="filterGames('fps')" class="game-tab-btn px-4 py-2 rounded-lg glass-panel border-slate-700 text-slate-300 hover:border-cyber-accent font-bold">FPS SHOOTERS</button>
                        <button onclick="filterGames('br')" class="game-tab-btn px-4 py-2 rounded-lg glass-panel border-slate-700 text-slate-300 hover:border-cyber-accent font-bold">BATTLE ROYALE</button>
                    </div>
                </div>

                <!-- Games Grid -->
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6" id="games-grid">
                    
                    <!-- Game Card 1 -->
                    <div class="game-card fps glass-panel rounded-2xl overflow-hidden glass-panel-hover transition-all duration-300 flex flex-col group" data-category="fps">
                        <div class="relative h-48 overflow-hidden">
                            <img src="https://images.unsplash.com/photo-1538481199705-c710c4e965fc?auto=format&fit=crop&w=600&q=80" alt="Valorant Arena" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500">
                            <span class="absolute top-3 right-3 px-2.5 py-1 rounded bg-cyber-purple/90 text-white font-display text-[10px] uppercase tracking-wider font-bold">Ranked Radiant</span>
                        </div>
                        <div class="p-5 flex-grow flex flex-col justify-between space-y-4">
                            <div>
                                <h3 class="font-display text-lg font-bold text-white group-hover:text-cyber-accent transition-colors">VALORANT PRO LEAGUE</h3>
                                <p class="text-xs text-slate-400 mt-1">Tactical 5v5 FPS shooter. Tactical execute, headshots, and main agent Duelist gameplay.</p>
                            </div>
                            <div class="flex items-center justify-between pt-2 border-t border-slate-800 text-xs font-display">
                                <span class="text-cyber-accent"><i class="fa-solid fa-users"></i> 14.2K Watching</span>
                                <button onclick="launchGameModal('Valorant Competitive')" class="text-white hover:text-cyber-accent uppercase font-bold text-[11px] flex items-center gap-1">Play Clips <i class="fa-solid fa-chevron-right text-[9px]"></i></button>
                            </div>
                        </div>
                    </div>

                    <!-- Game Card 2 -->
                    <div class="game-card br glass-panel rounded-2xl overflow-hidden glass-panel-hover transition-all duration-300 flex flex-col group" data-category="br">
                        <div class="relative h-48 overflow-hidden">
                            <img src="https://images.unsplash.com/photo-1511512578047-dfb367046420?auto=format&fit=crop&w=600&q=80" alt="Apex Legends" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500">
                            <span class="absolute top-3 right-3 px-2.5 py-1 rounded bg-cyber-accent/90 text-cyber-bg font-display text-[10px] uppercase tracking-wider font-bold">Apex Predator</span>
                        </div>
                        <div class="p-5 flex-grow flex flex-col justify-between space-y-4">
                            <div>
                                <h3 class="font-display text-lg font-bold text-white group-hover:text-cyber-accent transition-colors">APEX LEGENDS</h3>
                                <p class="text-xs text-slate-400 mt-1">High-speed movement battle royale with aggressive squad wipes and movement tech.</p>
                            </div>
                            <div class="flex items-center justify-between pt-2 border-t border-slate-800 text-xs font-display">
                                <span class="text-cyber-accent"><i class="fa-solid fa-users"></i> 8.9K Watching</span>
                                <button onclick="launchGameModal('Apex Legends Arena')" class="text-white hover:text-cyber-accent uppercase font-bold text-[11px] flex items-center gap-1">Play Clips <i class="fa-solid fa-chevron-right text-[9px]"></i></button>
                            </div>
                        </div>
                    </div>

                    <!-- Game Card 3 -->
                    <div class="game-card br glass-panel rounded-2xl overflow-hidden glass-panel-hover transition-all duration-300 flex flex-col group" data-category="br">
                        <div class="relative h-48 overflow-hidden">
                            <img src="https://images.unsplash.com/photo-1550745165-9bc0b252726f?auto=format&fit=crop&w=600&q=80" alt="Warzone Warzone" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500">
                            <span class="absolute top-3 right-3 px-2.5 py-1 rounded bg-cyber-pink/90 text-white font-display text-[10px] uppercase tracking-wider font-bold">Custom Lobby</span>
                        </div>
                        <div class="p-5 flex-grow flex flex-col justify-between space-y-4">
                            <div>
                                <h3 class="font-display text-lg font-bold text-white group-hover:text-cyber-accent transition-colors">COD WARZONE 3.0</h3>
                                <p class="text-xs text-slate-400 mt-1">Resurgence & Battle Royale high kill games with sniper accuracy setup.</p>
                            </div>
                            <div class="flex items-center justify-between pt-2 border-t border-slate-800 text-xs font-display">
                                <span class="text-cyber-accent"><i class="fa-solid fa-users"></i> 22.1K Watching</span>
                                <button onclick="launchGameModal('COD Warzone Stream')" class="text-white hover:text-cyber-accent uppercase font-bold text-[11px] flex items-center gap-1">Play Clips <i class="fa-solid fa-chevron-right text-[9px]"></i></button>
                            </div>
                        </div>
                    </div>

                    <!-- Game Card 4 -->
                    <div class="game-card fps glass-panel rounded-2xl overflow-hidden glass-panel-hover transition-all duration-300 flex flex-col group" data-category="fps">
                        <div class="relative h-48 overflow-hidden">
                            <img src="https://images.unsplash.com/photo-1560253023-3ec5d502959f?auto=format&fit=crop&w=600&q=80" alt="Cyberpunk City Arena" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500">
                            <span class="absolute top-3 right-3 px-2.5 py-1 rounded bg-cyber-gold/90 text-cyber-bg font-display text-[10px] uppercase tracking-wider font-bold">Speedrun #1</span>
                        </div>
                        <div class="p-5 flex-grow flex flex-col justify-between space-y-4">
                            <div>
                                <h3 class="font-display text-lg font-bold text-white group-hover:text-cyber-accent transition-colors">CYBER ARENA 2088</h3>
                                <p class="text-xs text-slate-400 mt-1">Neon cyberpunk arena battles with ultra fast reflex combat & boss speedruns.</p>
                            </div>
                            <div class="flex items-center justify-between pt-2 border-t border-slate-800 text-xs font-display">
                                <span class="text-cyber-accent"><i class="fa-solid fa-users"></i> 11.4K Watching</span>
                                <button onclick="launchGameModal('Cyber Arena 2088')" class="text-white hover:text-cyber-accent uppercase font-bold text-[11px] flex items-center gap-1">Play Clips <i class="fa-solid fa-chevron-right text-[9px]"></i></button>
                            </div>
                        </div>
                    </div>

                </div>

                <!-- Live Chat Simulator Interactive Widget -->
                <div class="mt-12 glass-panel p-6 rounded-2xl border-cyber-accent/20">
                    <div class="flex items-center justify-between pb-4 border-b border-slate-800">
                        <div class="flex items-center gap-2 font-display text-sm font-bold text-white">
                            <i class="fa-solid fa-comments text-cyber-accent"></i> STREAM REAL-TIME CHAT SIMULATOR
                        </div>
                        <span class="text-xs text-slate-400 font-mono" id="chat-count">1,842 Chatters Online</span>
                    </div>

                    <div id="chat-box" class="h-44 overflow-y-auto my-4 space-y-2 pr-2 font-mono text-xs">
                        <!-- Chat messages injected by JS dynamically -->
                    </div>

                    <form id="chat-form" class="flex gap-2">
                        <input type="text" id="chat-input" placeholder="Send a message to Deler Berol's chat..." class="flex-grow px-4 py-2.5 rounded-lg bg-slate-900 border border-slate-700 text-white focus:outline-none focus:border-cyber-accent text-xs">
                        <button type="submit" class="px-5 py-2.5 bg-cyber-accent text-cyber-bg font-display font-bold text-xs uppercase rounded-lg hover:bg-cyber-accent/80 transition-all">Send</button>
                    </form>
                </div>
            </div>
        </section>

        <!-- Esports Statistics Section -->
        <section id="stats" class="py-20 relative">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                
                <div class="text-center max-w-3xl mx-auto mb-16">
                    <span class="text-cyber-purple font-display text-xs tracking-widest uppercase font-bold">Competitive Legacy</span>
                    <h2 class="font-display text-3xl sm:text-4xl font-black text-white uppercase tracking-tight mt-1">
                        ESPORTS CAREER & METRICS
                    </h2>
                    <p class="text-slate-400 text-sm mt-3">Verified stats across global esports leagues and official community tournaments.</p>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                    
                    <div class="glass-panel p-6 rounded-2xl border-l-4 border-l-cyber-accent glass-panel-hover">
                        <div class="w-12 h-12 rounded-xl bg-cyber-accent/10 text-cyber-accent flex items-center justify-center text-xl mb-4">
                            <i class="fa-solid fa-crosshair"></i>
                        </div>
                        <h4 class="font-display text-3xl font-black text-white">68.4%</h4>
                        <p class="text-xs font-display uppercase tracking-wider text-slate-400 mt-1">Headshot Accuracy</p>
                        <p class="text-xs text-slate-500 mt-3">Ranked in top 0.01% among global VCT Radiant competitors.</p>
                    </div>

                    <div class="glass-panel p-6 rounded-2xl border-l-4 border-l-cyber-purple glass-panel-hover">
                        <div class="w-12 h-12 rounded-xl bg-cyber-purple/10 text-cyber-purple flex items-center justify-center text-xl mb-4">
                            <i class="fa-solid fa-trophy"></i>
                        </div>
                        <h4 class="font-display text-3xl font-black text-white">42</h4>
                        <p class="text-xs font-display uppercase tracking-wider text-slate-400 mt-1">Tournament Cups Won</p>
                        <p class="text-xs text-slate-500 mt-3">Including Major Apex Open & Regional Valorant Showdowns.</p>
                    </div>

                    <div class="glass-panel p-6 rounded-2xl border-l-4 border-l-cyber-pink glass-panel-hover">
                        <div class="w-12 h-12 rounded-xl bg-cyber-pink/10 text-cyber-pink flex items-center justify-center text-xl mb-4">
                            <i class="fa-solid fa-fire"></i>
                        </div>
                        <h4 class="font-display text-3xl font-black text-white">38 Kills</h4>
                        <p class="text-xs font-display uppercase tracking-wider text-slate-400 mt-1">Solo Kill Record</p>
                        <p class="text-xs text-slate-500 mt-3">Achieved in high-tier Warzone lobby solo-vs-squad match.</p>
                    </div>

                    <div class="glass-panel p-6 rounded-2xl border-l-4 border-l-cyber-gold glass-panel-hover">
                        <div class="w-12 h-12 rounded-xl bg-cyber-gold/10 text-cyber-gold flex items-center justify-center text-xl mb-4">
                            <i class="fa-solid fa-clock"></i>
                        </div>
                        <h4 class="font-display text-3xl font-black text-white">6,400+</h4>
                        <p class="text-xs font-display uppercase tracking-wider text-slate-400 mt-1">Total Broadcast Hours</p>
                        <p class="text-xs text-slate-500 mt-3">Consistent daily streaming with interactive subscriber events.</p>
                    </div>

                </div>
            </div>
        </section>

        <!-- Highlight & Clips Section -->
        <section id="clips" class="py-20 bg-cyber-card/40 border-y border-cyber-accent/10">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                
                <div class="flex flex-col md:flex-row md:items-end justify-between mb-12">
                    <div>
                        <span class="text-cyber-pink font-display text-xs tracking-widest uppercase font-bold">Unforgettable Moments</span>
                        <h2 class="font-display text-3xl sm:text-4xl font-black text-white uppercase tracking-tight mt-1">
                            HIGHLIGHT CLIPS GALLERY
                        </h2>
                    </div>
                    <!-- Filter Tags -->
                    <div class="mt-4 md:mt-0 flex flex-wrap gap-2 font-display text-xs" id="clip-filters">
                        <button onclick="filterClips('all')" class="clip-filter-btn active px-4 py-2 rounded-lg glass-panel border-cyber-accent text-cyber-accent font-bold">ALL HIGHLIGHTS</button>
                        <button onclick="filterClips('clutch')" class="clip-filter-btn px-4 py-2 rounded-lg glass-panel border-slate-700 text-slate-300 hover:border-cyber-accent font-bold">EPIC CLUTCHES</button>
                        <button onclick="filterClips('sniper')" class="clip-filter-btn px-4 py-2 rounded-lg glass-panel border-slate-700 text-slate-300 hover:border-cyber-accent font-bold">SNIPER SHOTS</button>
                    </div>
                </div>

                <!-- Clip Gallery Grid -->
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6" id="clips-grid">
                    
                    <!-- Clip 1 -->
                    <div class="clip-item clutch glass-panel rounded-2xl overflow-hidden glass-panel-hover group cursor-pointer" onclick="openVideoModal('1v5 Ace Clutch - Radiant Lobby', 'https://images.unsplash.com/photo-1542751371-adc38448a05e?auto=format&fit=crop&w=1000&q=80')">
                        <div class="relative aspect-video">
                            <img src="https://images.unsplash.com/photo-1542751371-adc38448a05e?auto=format&fit=crop&w=800&q=80" alt="Clip 1" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                            <div class="absolute inset-0 bg-gradient-to-t from-cyber-bg via-transparent to-transparent opacity-80"></div>
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-12 h-12 rounded-full bg-cyber-accent/90 text-cyber-bg flex items-center justify-center text-xl shadow-neon-cyan group-hover:scale-110 transition-transform">
                                    <i class="fa-solid fa-play ml-1"></i>
                                </div>
                            </div>
                            <span class="absolute bottom-3 right-3 px-2 py-1 bg-black/80 rounded font-mono text-[10px] text-cyber-accent">0:45</span>
                        </div>
                        <div class="p-4">
                            <span class="text-[10px] font-display uppercase tracking-wider text-cyber-purple font-bold">VALORANT</span>
                            <h4 class="font-display text-base font-bold text-white group-hover:text-cyber-accent transition-colors">1v5 Impossible Ace Clutch on Haven</h4>
                            <p class="text-xs text-slate-400 mt-1">100 HP against full armor squad with 5 seconds remaining.</p>
                        </div>
                    </div>

                    <!-- Clip 2 -->
                    <div class="clip-item sniper glass-panel rounded-2xl overflow-hidden glass-panel-hover group cursor-pointer" onclick="openVideoModal('No-Scope 360 Victory Shot', 'https://images.unsplash.com/photo-1511512578047-dfb367046420?auto=format&fit=crop&w=1000&q=80')">
                        <div class="relative aspect-video">
                            <img src="https://images.unsplash.com/photo-1511512578047-dfb367046420?auto=format&fit=crop&w=800&q=80" alt="Clip 2" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                            <div class="absolute inset-0 bg-gradient-to-t from-cyber-bg via-transparent to-transparent opacity-80"></div>
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-12 h-12 rounded-full bg-cyber-accent/90 text-cyber-bg flex items-center justify-center text-xl shadow-neon-cyan group-hover:scale-110 transition-transform">
                                    <i class="fa-solid fa-play ml-1"></i>
                                </div>
                            </div>
                            <span class="absolute bottom-3 right-3 px-2 py-1 bg-black/80 rounded font-mono text-[10px] text-cyber-accent">0:30</span>
                        </div>
                        <div class="p-4">
                            <span class="text-[10px] font-display uppercase tracking-wider text-cyber-pink font-bold">APEX LEGENDS</span>
                            <h4 class="font-display text-base font-bold text-white group-hover:text-cyber-accent transition-colors">360 Kraber No-Scope Jump Win</h4>
                            <p class="text-xs text-slate-400 mt-1">Final squad wipe mid-air off Octane jump pad.</p>
                        </div>
                    </div>

                    <!-- Clip 3 -->
                    <div class="clip-item clutch glass-panel rounded-2xl overflow-hidden glass-panel-hover group cursor-pointer" onclick="openVideoModal('30-Kill Victory Royale', 'https://images.unsplash.com/photo-1550745165-9bc0b252726f?auto=format&fit=crop&w=1000&q=80')">
                        <div class="relative aspect-video">
                            <img src="https://images.unsplash.com/photo-1550745165-9bc0b252726f?auto=format&fit=crop&w=800&q=80" alt="Clip 3" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                            <div class="absolute inset-0 bg-gradient-to-t from-cyber-bg via-transparent to-transparent opacity-80"></div>
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-12 h-12 rounded-full bg-cyber-accent/90 text-cyber-bg flex items-center justify-center text-xl shadow-neon-cyan group-hover:scale-110 transition-transform">
                                    <i class="fa-solid fa-play ml-1"></i>
                                </div>
                            </div>
                            <span class="absolute bottom-3 right-3 px-2 py-1 bg-black/80 rounded font-mono text-[10px] text-cyber-accent">1:15</span>
                        </div>
                        <div class="p-4">
                            <span class="text-[10px] font-display uppercase tracking-wider text-cyber-gold font-bold">WARZONE</span>
                            <h4 class="font-display text-base font-bold text-white group-hover:text-cyber-accent transition-colors">30 Kill Solo vs Squads Masterclass</h4>
                            <p class="text-xs text-slate-400 mt-1">Full match highlights breakdown with tactical positioning.</p>
                        </div>
                    </div>

                </div>
            </div>
        </section>

        <!-- Esports Rig & Hardware Setup Section -->
        <section id="setup" class="py-20 relative">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                
                <div class="text-center max-w-3xl mx-auto mb-16">
                    <span class="text-cyber-accent font-display text-xs tracking-widest uppercase font-bold">Pro Battle Station</span>
                    <h2 class="font-display text-3xl sm:text-4xl font-black text-white uppercase tracking-tight mt-1">
                        DELER'S RIG & GEAR SPECIFICATIONS
                    </h2>
                    <p class="text-slate-400 text-sm mt-3">Click any hardware item to reveal complete overclock parameters & sensitivity profiles.</p>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
                    
                    <!-- Hardware Selector Cards -->
                    <div class="lg:col-span-6 space-y-4">
                        
                        <div onclick="showGearDetail('cpu')" class="gear-card glass-panel p-5 rounded-2xl border-l-4 border-l-cyber-accent cursor-pointer hover:bg-slate-800/50 transition-all flex items-center justify-between">
                            <div class="flex items-center gap-4">
                                <div class="w-10 h-10 rounded-lg bg-cyber-accent/10 text-cyber-accent flex items-center justify-center text-lg">
                                    <i class="fa-solid fa-microchip"></i>
                                </div>
                                <div>
                                    <h4 class="font-display text-sm font-bold text-white">Processor & Graphics</h4>
                                    <p class="text-xs text-slate-400">Intel i9-14900KS | NVIDIA RTX 4090 24GB</p>
                                </div>
                            </div>
                            <i class="fa-solid fa-chevron-right text-xs text-cyber-accent"></i>
                        </div>

                        <div onclick="showGearDetail('mouse')" class="gear-card glass-panel p-5 rounded-2xl border-l-4 border-l-cyber-purple cursor-pointer hover:bg-slate-800/50 transition-all flex items-center justify-between">
                            <div class="flex items-center gap-4">
                                <div class="w-10 h-10 rounded-lg bg-cyber-purple/10 text-cyber-purple flex items-center justify-center text-lg">
                                    <i class="fa-solid fa-[#]"></i>
                                    <i class="fa-solid fa-hand-pointer"></i>
                                </div>
                                <div>
                                    <h4 class="font-display text-sm font-bold text-white">Esports Mouse & DPI</h4>
                                    <p class="text-xs text-slate-400">Custom Wireless 4K Polling | 800 DPI | 0.28 Sens</p>
                                </div>
                            </div>
                            <i class="fa-solid fa-chevron-right text-xs text-cyber-purple"></i>
                        </div>

                        <div onclick="showGearDetail('monitor')" class="gear-card glass-panel p-5 rounded-2xl border-l-4 border-l-cyber-pink cursor-pointer hover:bg-slate-800/50 transition-all flex items-center justify-between">
                            <div class="flex items-center gap-4">
                                <div class="w-10 h-10 rounded-lg bg-cyber-pink/10 text-cyber-pink flex items-center justify-center text-lg">
                                    <i class="fa-solid fa-desktop"></i>
                                </div>
                                <div>
                                    <h4 class="font-display text-sm font-bold text-white">Display & Refresh Rate</h4>
                                    <p class="text-xs text-slate-400">360Hz OLED 0.03ms Response Time Gaming Monitor</p>
                                </div>
                            </div>
                            <i class="fa-solid fa-chevron-right text-xs text-cyber-pink"></i>
                        </div>

                        <div onclick="showGearDetail('audio')" class="gear-card glass-panel p-5 rounded-2xl border-l-4 border-l-cyber-gold cursor-pointer hover:bg-slate-800/50 transition-all flex items-center justify-between">
                            <div class="flex items-center gap-4">
                                <div class="w-10 h-10 rounded-lg bg-cyber-gold/10 text-cyber-gold flex items-center justify-center text-lg">
                                    <i class="fa-solid fa-headphones"></i>
                                </div>
                                <div>
                                    <h4 class="font-display text-sm font-bold text-white">Audio & Broadcast Mic</h4>
                                    <p class="text-xs text-slate-400">Studio XLR Dynamic Mic + Planar Magnetic Headset</p>
                                </div>
                            </div>
                            <i class="fa-solid fa-chevron-right text-xs text-cyber-gold"></i>
                        </div>

                    </div>

                    <!-- Detail Display Box -->
                    <div class="lg:col-span-6">
                        <div class="glass-panel p-8 rounded-2xl border-cyber-accent/30 relative" id="gear-display">
                            <span class="text-[10px] font-display uppercase tracking-widest text-cyber-accent font-bold">SPECS INSPECTOR</span>
                            <h3 class="font-display text-2xl font-black text-white mt-1" id="gear-title">Intel i9-14900KS + RTX 4090</h3>
                            
                            <div class="my-6 space-y-3 font-mono text-xs text-slate-300" id="gear-specs">
                                <div class="flex justify-between py-2 border-b border-slate-800">
                                    <span class="text-slate-500">CPU Clock Speed:</span>
                                    <span class="text-cyber-accent font-bold">6.2 GHz Special Edition</span>
                                </div>
                                <div class="flex justify-between py-2 border-b border-slate-800">
                                    <span class="text-slate-500">RAM:</span>
                                    <span class="text-white">64GB DDR5 7200MHz CL34</span>
                                </div>
                                <div class="flex justify-between py-2 border-b border-slate-800">
                                    <span class="text-slate-500">Cooling System:</span>
                                    <span class="text-white">Custom Hardline Dual-Loop Liquid Cooling</span>
                                </div>
                                <div class="flex justify-between py-2 border-b border-slate-800">
                                    <span class="text-slate-500">Average FPS in Valorant:</span>
                                    <span class="text-cyber-green font-bold">750+ FPS Locked</span>
                                </div>
                            </div>

                            <p class="text-xs text-slate-400 italic" id="gear-desc">
                                "Built for absolute minimal latency, high-fps streaming, and multi-threaded rendering."
                            </p>
                        </div>
                    </div>

                </div>
            </div>
        </section>

        <!-- Community & Sponsorship Section -->
        <section id="community" class="py-20 bg-cyber-card/40 border-t border-cyber-accent/10">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="grid grid-cols-1 lg:grid-cols-12 gap-12">
                    
                    <!-- Community Callout -->
                    <div class="lg:col-span-5 space-y-6">
                        <span class="text-cyber-purple font-display text-xs tracking-widest uppercase font-bold">Berol Army Hub</span>
                        <h2 class="font-display text-3xl font-black text-white uppercase leading-tight">
                            JOIN THE OFFICIAL DISCORD COMMUNITY
                        </h2>
                        <p class="text-slate-300 text-sm leading-relaxed">
                            Connect with 50,000+ gamers. Participate in weekly sub-tournaments, grab custom gaming crosshair presets, and play in squad lobbies with Deler Berol.
                        </p>

                        <div class="glass-panel p-6 rounded-2xl border-cyber-purple/40 space-y-4">
                            <div class="flex items-center gap-4">
                                <div class="w-12 h-12 rounded-xl bg-cyber-purple/20 text-cyber-purple flex items-center justify-center text-2xl">
                                    <i class="fa-brands fa-discord"></i>
                                </div>
                                <div>
                                    <h4 class="font-display text-base font-bold text-white">Berol Army Discord</h4>
                                    <span class="text-xs text-cyber-accent font-mono"><i class="fa-solid fa-circle text-[8px] text-cyber-green mr-1"></i> 12,480 Active Members Online</span>
                                </div>
                            </div>

                            <a href="https://discord.com" target="_blank" class="block w-full text-center py-3 bg-cyber-purple hover:bg-cyber-purple/80 text-white font-display font-bold text-xs uppercase tracking-wider clip-cyber-btn transition-all shadow-neon-purple">
                                Join Server Now
                            </a>
                        </div>
                    </div>

                    <!-- Business Inquiry Form -->
                    <div class="lg:col-span-7">
                        <div class="glass-panel p-8 rounded-3xl border-cyber-accent/30 shadow-neon-cyan">
                            <div class="mb-6">
                                <h3 class="font-display text-2xl font-black text-white uppercase">BUSINESS & SPONSORSHIPS</h3>
                                <p class="text-xs text-slate-400 mt-1">Send sponsorship proposals, tournament invitations, or business inquiries.</p>
                            </div>

                            <div id="form-alert" class="hidden mb-4 p-4 rounded-xl text-xs font-mono"></div>

                            <form id="contact-form" class="space-y-4" novalidate>
                                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                                    <div>
                                        <label class="block text-xs font-display text-slate-300 uppercase tracking-wider mb-2">Your Name / Organization</label>
                                        <input type="text" id="form-name" class="w-full px-4 py-3 rounded-xl bg-slate-900/90 border border-slate-700 text-white focus:outline-none focus:border-cyber-accent text-xs" placeholder="e.g. Razer / RedBull Esports">
                                        <p id="err-name" class="hidden text-[10px] text-red-400 mt-1"></p>
                                    </div>
                                    <div>
                                        <label class="block text-xs font-display text-slate-300 uppercase tracking-wider mb-2">Business Email</label>
                                        <input type="email" id="form-email" class="w-full px-4 py-3 rounded-xl bg-slate-900/90 border border-slate-700 text-white focus:outline-none focus:border-cyber-accent text-xs" placeholder="sponsor@company.com">
                                        <p id="err-email" class="hidden text-[10px] text-red-400 mt-1"></p>
                                    </div>
                                </div>

                                <div>
                                    <label class="block text-xs font-display text-slate-300 uppercase tracking-wider mb-2">Subject</label>
                                    <input type="text" id="form-subject" class="w-full px-4 py-3 rounded-xl bg-slate-900/90 border border-slate-700 text-white focus:outline-none focus:border-cyber-accent text-xs" placeholder="Tournament Sponsorship Proposal">
                                    <p id="err-subject" class="hidden text-[10px] text-red-400 mt-1"></p>
                                </div>

                                <div>
                                    <label class="block text-xs font-display text-slate-300 uppercase tracking-wider mb-2">Inquiry Details</label>
                                    <textarea id="form-message" rows="4" class="w-full px-4 py-3 rounded-xl bg-slate-900/90 border border-slate-700 text-white focus:outline-none focus:border-cyber-accent text-xs" placeholder="Describe project scope, timelines, or event dates..."></textarea>
                                    <p id="err-message" class="hidden text-[10px] text-red-400 mt-1"></p>
                                </div>

                                <button type="submit" class="w-full py-4 bg-gradient-to-r from-cyber-accent to-cyber-purple text-cyber-bg font-display font-black text-xs uppercase tracking-widest clip-cyber-btn shadow-neon-cyan hover:scale-[1.01] transition-transform">
                                    Transmit Inquiry
                                </button>
                            </form>
                        </div>
                    </div>

                </div>
            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="bg-cyber-bg border-t border-slate-800 py-12 relative z-10">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row items-center justify-between gap-6">
            <div class="flex items-center gap-3">
                <div class="w-8 h-8 rounded bg-cyber-accent text-cyber-bg flex items-center justify-center font-bold">
                    <i class="fa-solid fa-gamepad"></i>
                </div>
                <span class="font-display font-bold text-white text-sm">DELER BEROL © <span id="year font-mono"></span>. ALL RIGHTS RESERVED.</span>
            </div>

            <!-- Social Links -->
            <div class="flex items-center gap-6 text-slate-400 text-lg">
                <a href="#" class="hover:text-cyber-accent transition-colors"><i class="fa-brands fa-twitch"></i></a>
                <a href="#" class="hover:text-cyber-accent transition-colors"><i class="fa-brands fa-youtube"></i></a>
                <a href="#" class="hover:text-cyber-accent transition-colors"><i class="fa-brands fa-x-twitter"></i></a>
                <a href="#" class="hover:text-cyber-accent transition-colors"><i class="fa-brands fa-tiktok"></i></a>
                <a href="#" class="hover:text-cyber-accent transition-colors"><i class="fa-brands fa-instagram"></i></a>
            </div>
        </div>
    </footer>

    <!-- Broadcast / Video Clip Modal Popup -->
    <div id="video-modal" class="fixed inset-0 z-50 hidden bg-black/90 backdrop-blur-xl flex items-center justify-center p-4">
        <div class="relative w-full max-w-4xl glass-panel p-4 rounded-3xl border-cyber-accent/40 shadow-neon-cyan">
            <!-- Modal Header -->
            <div class="flex items-center justify-between pb-3 mb-3 border-b border-slate-800">
                <h3 class="font-display text-lg font-bold text-white" id="modal-title">Stream Live Broadcast</h3>
                <button onclick="closeVideoModal()" class="w-8 h-8 rounded-full bg-slate-800 text-slate-300 hover:text-white flex items-center justify-center">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>
            <!-- Video Container Mockup -->
            <div class="relative aspect-video rounded-xl overflow-hidden bg-slate-950 flex items-center justify-center">
                <img id="modal-img" src="https://images.unsplash.com/photo-1542751371-adc38448a05e?auto=format&fit=crop&w=1200&q=80" class="w-full h-full object-cover">
                <div class="absolute inset-0 bg-black/40 flex flex-col items-center justify-center text-center p-6">
                    <div class="w-16 h-16 rounded-full bg-cyber-accent text-cyber-bg flex items-center justify-center text-2xl shadow-neon-cyan mb-4 animate-bounce">
                        <i class="fa-solid fa-play ml-1"></i>
                    </div>
                    <span class="font-display font-bold text-white text-lg">PLAYBACK STREAM READY</span>
                    <p class="text-xs text-slate-300 mt-1">Deler Berol Broadcaster Server Connection Active</p>
                </div>
            </div>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // Set dynamic footer year
            document.getElementById('year').textContent = new Date().getFullYear();

            // Custom Cursor Follower
            const follower = document.getElementById('cursor-follower');
            window.addEventListener('mousemove', (e) => {
                if (follower) {
                    follower.style.left = e.clientX + 'px';
                    follower.style.top = e.clientY + 'px';
                }
            });

            // Mobile Menu Toggle
            const mobileBtn = document.getElementById('mobileMenuBtn');
            const mobileMenu = document.getElementById('mobileMenu');
            if (mobileBtn && mobileMenu) {
                mobileBtn.addEventListener('click', () => {
                    mobileMenu.classList.toggle('hidden');
                });
            }

            // Interactive Background Cyber Particles Canvas
            const canvas = document.getElementById('cyber-canvas');
            if (canvas) {
                const ctx = canvas.getContext('2d');
                let width = canvas.width = window.innerWidth;
                let height = canvas.height = window.innerHeight;

                window.addEventListener('resize', () => {
                    width = canvas.width = window.innerWidth;
                    height = canvas.height = window.innerHeight;
                });

                const particles = [];
                const particleCount = Math.min(Math.floor(width / 20), 60);

                for (let i = 0; i < particleCount; i++) {
                    particles.push({
                        x: Math.random() * width,
                        y: Math.random() * height,
                        radius: Math.random() * 2 + 1,
                        vx: (Math.random() - 0.5) * 0.5,
                        vy: (Math.random() - 0.5) * 0.5,
                        color: Math.random() > 0.5 ? '#00f0ff' : '#9d4edd'
                    });
                }

                function drawCanvas() {
                    ctx.clearRect(0, 0, width, height);

                    for (let i = 0; i < particles.length; i++) {
                        let p = particles[i];
                        p.x += p.vx;
                        p.y += p.vy;

                        if (p.x < 0) p.x = width;
                        if (p.x > width) p.x = 0;
                        if (p.y < 0) p.y = height;
                        if (p.y > height) p.y = 0;

                        ctx.beginPath();
                        ctx.arc(p.x, p.y, p.radius, 0, Math.PI * 2);
                        ctx.fillStyle = p.color;
                        ctx.shadowBlur = 10;
                        ctx.shadowColor = p.color;
                        ctx.fill();

                        // Draw connection lines
                        for (let j = i + 1; j < particles.length; j++) {
                            let p2 = particles[j];
                            let dx = p.x - p2.x;
                            let dy = p.y - p2.y;
                            let dist = Math.sqrt(dx * dx + dy * dy);

                            if (dist < 120) {
                                ctx.beginPath();
                                ctx.moveTo(p.x, p.y);
                                ctx.lineTo(p2.x, p2.y);
                                ctx.strokeStyle = `rgba(0, 240, 255, ${1 - dist / 120 * 0.8})`;
                                ctx.lineWidth = 0.5;
                                ctx.stroke();
                            }
                        }
                    }

                    requestAnimationFrame(drawCanvas);
                }
                drawCanvas();
            }

            // Live Chat Simulator logic
            const chatBox = document.getElementById('chat-box');
            const chatForm = document.getElementById('chat-form');
            const chatInput = document.getElementById('chat-input');

            const defaultMessages = [
                { user: 'ViperX', color: '#00f0ff', msg: 'Deler that headshot was insane!' },
                { user: 'RadiantGod', color: '#9d4edd', msg: 'Berol Army on top! 🔥' },
                { user: 'NeonPulse', color: '#ff007f', msg: 'What sensitivity are you using?' },
                { user: 'ShadowAce', color: '#ffb703', msg: 'Subbed for 12 months hype!' },
            ];

            function renderMessages() {
                if (!chatBox) return;
                chatBox.innerHTML = '';
                defaultMessages.forEach(m => {
                    const line = document.createElement('div');
                    line.className = 'flex items-center gap-2';
                    line.innerHTML = `<span style="color: ${m.color}" class="font-bold">@${m.user}:</span> <span class="text-slate-300">${m.msg}</span>`;
                    chatBox.appendChild(line);
                });
                chatBox.scrollTop = chatBox.scrollHeight;
            }
            renderMessages();

            if (chatForm) {
                chatForm.addEventListener('submit', (e) => {
                    e.preventDefault();
                    const val = chatInput.value.trim();
                    if (val) {
                        defaultMessages.push({ user: 'You (Fan)', color: '#00ff66', msg: val });
                        if (defaultMessages.length > 8) defaultMessages.shift();
                        renderMessages();
                        chatInput.value = '';
                    }
                });
            }

            // Form Live Validation Logic
            const form = document.getElementById('contact-form');
            const nameIn = document.getElementById('form-name');
            const emailIn = document.getElementById('form-email');
            const subjectIn = document.getElementById('form-subject');
            const msgIn = document.getElementById('form-message');
            const alertBox = document.getElementById('form-alert');

            if (form) {
                form.addEventListener('submit', (e) => {
                    e.preventDefault();
                    let valid = true;

                    const nameVal = nameIn.value.trim();
                    const emailVal = emailIn.value.trim();
                    const subVal = subjectIn.value.trim();
                    const msgVal = msgIn.value.trim();

                    if (!nameVal) {
                        showError('err-name', nameIn, 'Name/Organization is required');
                        valid = false;
                    } else {
                        hideError('err-name', nameIn);
                    }

                    if (!emailVal || !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(emailVal)) {
                        showError('err-email', emailIn, 'Enter a valid business email');
                        valid = false;
                    } else {
                        hideError('err-email', emailIn);
                    }

                    if (!subVal) {
                        showError('err-subject', subjectIn, 'Subject line required');
                        valid = false;
                    } else {
                        hideError('err-subject', subjectIn);
                    }

                    if (!msgVal) {
                        showError('err-message', msgIn, 'Message detail required');
                        valid = false;
                    } else {
                        hideError('err-message', msgIn);
                    }

                    if (valid) {
                        alertBox.className = 'mb-4 p-4 rounded-xl text-xs font-mono bg-emerald-950/80 text-emerald-300 border border-emerald-500/50';
                        alertBox.textContent = 'SYSTEM TRANSMISSION SUCCESSFUL: Your sponsorship inquiry has been dispatched to Deler Berol management.';
                        alertBox.classList.remove('hidden');
                        form.reset();
                    }
                });
            }

            function showError(id, input, text) {
                const el = document.getElementById(id);
                if (el) {
                    el.textContent = text;
                    el.classList.remove('hidden');
                }
                input.classList.add('border-red-500');
            }

            function hideError(id, input) {
                const el = document.getElementById(id);
                if (el) el.classList.add('hidden');
                input.classList.remove('border-red-500');
            }
        });

        // Global Interactive Functions

        // Game Tab Filter
        function filterGames(category) {
            const cards = document.querySelectorAll('.game-card');
            const btns = document.querySelectorAll('.game-tab-btn');

            btns.forEach(b => {
                b.classList.remove('active', 'border-cyber-accent', 'text-cyber-accent');
                b.classList.add('border-slate-700', 'text-slate-300');
            });
            event.target.classList.add('active', 'border-cyber-accent', 'text-cyber-accent');

            cards.forEach(card => {
                if (category === 'all' || card.dataset.category === category) {
                    card.style.display = 'flex';
                } else {
                    card.style.display = 'none';
                }
            });
        }

        // Clip Tab Filter
        function filterClips(tag) {
            const items = document.querySelectorAll('.clip-item');
            const btns = document.querySelectorAll('.clip-filter-btn');

            btns.forEach(b => {
                b.classList.remove('active', 'border-cyber-accent', 'text-cyber-accent');
                b.classList.add('border-slate-700', 'text-slate-300');
            });
            event.target.classList.add('active', 'border-cyber-accent', 'text-cyber-accent');

            items.forEach(item => {
                if (tag === 'all' || item.classList.contains(tag)) {
                    item.style.display = 'block';
                } else {
                    item.style.display = 'none';
                }
            });
        }

        // Hardware Gear Inspector Toggle
        function showGearDetail(type) {
            const title = document.getElementById('gear-title');
            const specs = document.getElementById('gear-specs');
            const desc = document.getElementById('gear-desc');

            if (type === 'cpu') {
                title.textContent = 'Intel i9-14900KS + RTX 4090';
                specs.innerHTML = `
                    <div class="flex justify-between py-2 border-b border-slate-800"><span class="text-slate-500">CPU Clock Speed:</span><span class="text-cyber-accent font-bold">6.2 GHz Special Edition</span></div>
                    <div class="flex justify-between py-2 border-b border-slate-800"><span class="text-slate-500">RAM:</span><span class="text-white">64GB DDR5 7200MHz CL34</span></div>
                    <div class="flex justify-between py-2 border-b border-slate-800"><span class="text-slate-500">Cooling System:</span><span class="text-white">Custom Hardline Dual-Loop Liquid Cooling</span></div>
                    <div class="flex justify-between py-2 border-b border-slate-800"><span class="text-slate-500">Average FPS in Valorant:</span><span class="text-cyber-green font-bold">750+ FPS Locked</span></div>
                `;
                desc.textContent = '"Built for absolute minimal latency, high-fps streaming, and multi-threaded rendering."';
            } else if (type === 'mouse') {
                title.textContent = 'Custom 4K Polling Esports Mouse';
                specs.innerHTML = `
                    <div class="flex justify-between py-2 border-b border-slate-800"><span class="text-slate-500">DPI Setting:</span><span class="text-cyber-purple font-bold">800 DPI</span></div>
                    <div class="flex justify-between py-2 border-b border-slate-800"><span class="text-slate-500">In-Game Sens (Valorant):</span><span class="text-white">0.28 (eDPI 224)</span></div>
                    <div class="flex justify-between py-2 border-b border-slate-800"><span class="text-slate-500">Polling Rate:</span><span class="text-white">4000 Hz Ultra-Fast Response</span></div>
                    <div class="flex justify-between py-2 border-b border-slate-800"><span class="text-slate-500">Weight:</span><span class="text-cyber-accent font-bold">47g Featherweight</span></div>
                `;
                desc.textContent = '"Ultra low-friction glide with ceramic skates for pinpoint headshot precision."';
            } else if (type === 'monitor') {
                title.textContent = '360Hz OLED 0.03ms Display';
                specs.innerHTML = `
                    <div class="flex justify-between py-2 border-b border-slate-800"><span class="text-slate-500">Refresh Rate:</span><span class="text-cyber-pink font-bold">360Hz True OLED</span></div>
                    <div class="flex justify-between py-2 border-b border-slate-800"><span class="text-slate-500">Response Time:</span><span class="text-white">0.03ms GtG</span></div>
                    <div class="flex justify-between py-2 border-b border-slate-800"><span class="text-slate-500">Resolution:</span><span class="text-white">2560 x 1440 QHD</span></div>
                `;
                desc.textContent = '"Zero motion blur visual output ensuring instantaneous opponent detection."';
            } else if (type === 'audio') {
                title.textContent = 'Broadcast XLR Studio Mic & Audio';
                specs.innerHTML = `
                    <div class="flex justify-between py-2 border-b border-slate-800"><span class="text-slate-500">Microphone:</span><span class="text-cyber-gold font-bold">Shure SM7B Dynamic XLR</span></div>
                    <div class="flex justify-between py-2 border-b border-slate-800"><span class="text-slate-500">Interface:</span><span class="text-white">TC Helicon GoXLR Pro</span></div>
                    <div class="flex justify-between py-2 border-b border-slate-800"><span class="text-slate-500">Headphones:</span><span class="text-white">Sennheiser Open-Back Studio Reference</span></div>
                `;
                desc.textContent = '"Crystal clear broadcast quality audio with real-time DSP noise cancellation."';
            }
        }

        // Modal Controls
        function openStreamModal() {
            document.getElementById('modal-title').textContent = "DELER BEROL - LIVE BROADCAST REALM";
            document.getElementById('modal-img').src = "https://images.unsplash.com/photo-1542751371-adc38448a05e?auto=format&fit=crop&w=1200&q=80";
            document.getElementById('video-modal').classList.remove('hidden');
        }

        function launchGameModal(gameTitle) {
            document.getElementById('modal-title').textContent = gameTitle + " - Highlight Stream";
            document.getElementById('modal-img').src = "https://images.unsplash.com/photo-1511512578047-dfb367046420?auto=format&fit=crop&w=1200&q=80";
            document.getElementById('video-modal').classList.remove('hidden');
        }

        function openVideoModal(title, imageSrc) {
            document.getElementById('modal-title').textContent = title;
            document.getElementById('modal-img').src = imageSrc;
            document.getElementById('video-modal').classList.remove('hidden');
        }

        function closeVideoModal() {
            document.getElementById('video-modal').classList.add('hidden');
        }
    </script>
</body>
</html>
