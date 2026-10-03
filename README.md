# solar-power-x
Articles, documentation, and image gallery showcasing solar power systems and green energy technologies.
```html
<!DOCTYPE html>
<html lang="bn" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Solar Power X - প্রফেশনাল সোলার সলিউশন ও গাইড</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        brand: {
                            50: '#fffbebeb',
                            100: '#fef3c7',
                            400: '#facc15',
                            500: '#eab308',
                            600: '#ca8a04',
                            700: '#a16207',
                            900: '#713f12',
                        },
                        solarGreen: {
                            500: '#10b981',
                            600: '#059669',
                        },
                        darkBg: '#0b0f19',
                        darkCard: '#111827',
                        glassBg: 'rgba(17, 24, 39, 0.75)',
                    },
                    fontFamily: {
                        sans: ['Hind Siliguri', 'Inter', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <!-- Google Fonts for Bengali -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Hind+Siliguri:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        body {
            font-family: 'Hind Siliguri', sans-serif;
        }
        .glass {
            background: rgba(17, 24, 39, 0.7);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.08);
        }
        .glass-light {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(0, 0, 0, 0.08);
        }
        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #0b0f19;
        }
        ::-webkit-scrollbar-thumb {
            background: #374151;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #eab308;
        }
    </style>
</head>
<body class="bg-gray-100 dark:bg-darkBg text-gray-800 dark:text-gray-100 min-h-screen transition-colors duration-300 flex flex-col justify-between">

    <!-- Sticky Header Navigation -->
    <header class="sticky top-0 z-40 w-full glass dark:glass border-b border-gray-200 dark:border-gray-800 transition-colors">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <!-- Logo & Branding -->
                <div class="flex items-center space-x-3 space-x-reverse cursor-pointer" onclick="switchTab('articles')">
                    <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-amber-500 via-amber-400 to-emerald-500 flex items-center justify-center shadow-lg shadow-amber-500/20 text-slate-950 font-bold text-xl">
                        <i class="fa-solid font-bold fa-solar-panel"></i>
                    </div>
                    <div>
                        <span class="text-xl font-bold bg-gradient-to-r from-amber-400 via-yellow-300 to-emerald-400 bg-clip-text text-transparent">Solar Power X</span>
                        <span class="text-xs block text-emerald-500 font-medium tracking-wide">ইঞ্জিনিয়ারিং পোর্টাল</span>
                    </div>
                </div>

                <!-- Desktop Navigation Links -->
                <nav class="hidden md:flex space-x-1 lg:space-x-2 text-sm font-semibold">
                    <button onclick="switchTab('articles')" id="nav-articles" class="nav-btn px-4 py-2 rounded-lg transition-all text-amber-500 bg-amber-500/10">
                        <i class="fa-solid fa-newspaper mr-1.5"></i> আর্টিকেলস ও গাইড
                    </button>
                    <button onclick="switchTab('calculator')" id="nav-calculator" class="nav-btn px-4 py-2 rounded-lg text-gray-600 dark:text-gray-300 hover:text-amber-500 hover:bg-gray-100 dark:hover:bg-gray-800 transition-all">
                        <i class="fa-solid fa-calculator mr-1.5"></i> সোলার ক্যালকুলেটর
                    </button>
                    <button onclick="switchTab('diagrams')" id="nav-diagrams" class="nav-btn px-4 py-2 rounded-lg text-gray-600 dark:text-gray-300 hover:text-amber-500 hover:bg-gray-100 dark:hover:bg-gray-800 transition-all">
                        <i class="fa-solid fa-diagram-project mr-1.5"></i> সেফটি ও ডায়াগ্রাম
                    </button>
                </nav>

                <!-- Search & Actions -->
                <div class="flex items-center space-x-2 md:space-x-3">
                    <!-- Global Search Input -->
                    <div class="relative hidden sm:block">
                        <input type="text" id="searchInput" oninput="filterArticles()" placeholder="প্যানেল, ইনভার্টার, কেবল খুঁজুন..." 
                            class="w-48 lg:w-64 pl-9 pr-3 py-1.5 text-xs rounded-lg bg-gray-200 dark:bg-gray-800 text-gray-800 dark:text-gray-200 focus:outline-none focus:ring-2 focus:ring-amber-500 border border-gray-300 dark:border-gray-700">
                        <i class="fa-solid fa-magnifying-glass absolute left-3 top-2.5 text-gray-400 text-xs"></i>
                    </div>

                    <!-- Theme Toggle -->
                    <button onclick="toggleTheme()" class="p-2 rounded-lg bg-gray-200 dark:bg-gray-800 text-gray-600 dark:text-amber-400 hover:bg-gray-300 dark:hover:bg-gray-700 transition">
                        <i id="themeIcon" class="fa-solid fa-moon"></i>
                    </button>

                    <!-- Three-dot Menu Icon -->
                    <button onclick="toggleDevModal()" class="p-2 rounded-lg bg-amber-500/10 text-amber-500 border border-amber-500/20 hover:bg-amber-500/20 transition text-lg" title="ডেভেলপার তথ্য ও সেটিংস">
                        <i class="fa-solid fa-ellipsis-vertical"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Navigation Bottom Bar -->
        <div class="md:hidden flex justify-around border-t border-gray-200 dark:border-gray-800 bg-white/90 dark:bg-gray-900/90 py-2 text-xs font-semibold">
            <button onclick="switchTab('articles')" class="flex flex-col items-center text-amber-500">
                <i class="fa-solid fa-newspaper text-base mb-1"></i> আর্টিকেলস
            </button>
            <button onclick="switchTab('calculator')" class="flex flex-col items-center text-gray-500 dark:text-gray-400">
                <i class="fa-solid fa-calculator text-base mb-1"></i> ক্যালকুলেটর
            </button>
            <button onclick="switchTab('diagrams')" class="flex flex-col items-center text-gray-500 dark:text-gray-400">
                <i class="fa-solid fa-diagram-project text-base mb-1"></i> সেফটি গাইড
            </button>
        </div>
    </header>

    <!-- Hero Banner -->
    <section class="relative bg-gradient-to-b from-amber-500/10 via-emerald-500/5 to-transparent py-10 md:py-16 border-b border-gray-200 dark:border-gray-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-12 gap-8 items-center">
                <div class="md:col-span-7 space-y-4">
                    <span class="inline-flex items-center px-3 py-1 rounded-full text-xs font-semibold bg-amber-500/10 text-amber-500 border border-amber-500/30">
                        <i class="fa-solid fa-bolt mr-1.5"></i> আধুনিক সোলার টেকনোলজি হাব
                    </span>
                    <h1 class="text-3xl sm:text-4xl lg:text-5xl font-extrabold tracking-tight leading-tight">
                        নবায়নযোগ্য শক্তিতে <span class="bg-gradient-to-r from-amber-400 to-emerald-400 bg-clip-text text-transparent">স্বাবলম্বী হোন</span> প্রফেশনাল গাইডের সাহায্যে
                    </h1>
                    <p class="text-gray-600 dark:text-gray-400 text-sm md:text-base leading-relaxed">
                        সোলার প্যানেল সিস্টেম, অন-গ্রিড, অফ-গ্রিড ও হাইব্রিড ইনভার্টার, লিথিয়াম ব্যাটারি, নেট মিটারিং, সঠিক কেবল সাইজিং এবং প্রয়োজনীয় সেফটি প্রটেকশনের সম্পূর্ণ ইঞ্জিনিয়ারিং গাইড।
                    </p>

                    <!-- Admin Mode Indicator / Toggle Bar -->
                    <div class="pt-2 flex items-center space-x-3">
                        <button onclick="toggleAdminPrompt()" id="adminStatusBtn" class="px-4 py-2 rounded-xl text-xs font-semibold border border-dashed border-gray-400 dark:border-gray-600 text-gray-600 dark:text-gray-300 hover:border-amber-500 transition flex items-center">
                            <i class="fa-solid fa-user-shield mr-2 text-amber-500"></i>
                            <span id="adminStatusText">অ্যাডমিন মোড (লগইন করুন)</span>
                        </button>
                        <button onclick="openAddPostModal()" id="addPostBtn" class="hidden px-4 py-2 rounded-xl text-xs font-bold bg-amber-500 hover:bg-amber-600 text-slate-950 transition shadow-lg shadow-amber-500/20 flex items-center">
                            <i class="fa-solid fa-plus mr-1.5"></i> নতুন আর্টেকেল লিখুন
                        </button>
                    </div>
                </div>

                <!-- Dynamic Quick Stats Widget -->
                <div class="md:col-span-5 grid grid-cols-2 gap-4">
                    <div class="p-4 rounded-2xl glass dark:bg-gray-900/60 border border-gray-200 dark:border-gray-800 shadow-xl">
                        <div class="text-amber-500 text-2xl font-bold mb-1" id="statArticles">08</div>
                        <div class="text-xs text-gray-500 dark:text-gray-400">প্রফেশনাল গাইডলাইন</div>
                    </div>
                    <div class="p-4 rounded-2xl glass dark:bg-gray-900/60 border border-gray-200 dark:border-gray-800 shadow-xl">
                        <div class="text-emerald-500 text-2xl font-bold mb-1">100%</div>
                        <div class="text-xs text-gray-500 dark:text-gray-400">সঠিক সাইজিং ও ম্যাপিং</div>
                    </div>
                    <div class="p-4 rounded-2xl glass dark:bg-gray-900/60 border border-gray-200 dark:border-gray-800 shadow-xl">
                        <div class="text-blue-500 text-2xl font-bold mb-1">LiFePO4</div>
                        <div class="text-xs text-gray-500 dark:text-gray-400">ব্যাটারি প্রযুক্তি বিশ্লেষণ</div>
                    </div>
                    <div class="p-4 rounded-2xl glass dark:bg-gray-900/60 border border-gray-200 dark:border-gray-800 shadow-xl">
                        <div class="text-purple-500 text-2xl font-bold mb-1">DC / AC</div>
                        <div class="text-xs text-gray-500 dark:text-gray-400">সম্পূর্ণ প্রটেকশন সিস্টেম</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8 flex-grow w-full">
        
        <!-- SECTION 1: ARTICLES TAB -->
        <div id="tab-articles" class="tab-content block">
            <!-- Filter Categories -->
            <div class="flex items-center space-x-2 overflow-x-auto pb-4 mb-6 border-b border-gray-200 dark:border-gray-800 text-xs sm:text-sm">
                <button onclick="filterCategory('all')" class="cat-btn active px-4 py-2 rounded-xl font-medium bg-amber-500 text-slate-950 whitespace-nowrap shadow-md">সবগুলো</button>
                <button onclick="filterCategory('panel')" class="cat-btn px-4 py-2 rounded-xl font-medium bg-gray-200 dark:bg-gray-800 text-gray-700 dark:text-gray-300 hover:bg-amber-500/20 whitespace-nowrap">সোলার প্যানেল</button>
                <button onclick="filterCategory('inverter')" class="cat-btn px-4 py-2 rounded-xl font-medium bg-gray-200 dark:bg-gray-800 text-gray-700 dark:text-gray-300 hover:bg-amber-500/20 whitespace-nowrap">ইনভার্টার ও চার্জ কন্ট্রোলার</button>
                <button onclick="filterCategory('battery')" class="cat-btn px-4 py-2 rounded-xl font-medium bg-gray-200 dark:bg-gray-800 text-gray-700 dark:text-gray-300 hover:bg-amber-500/20 whitespace-nowrap">ব্যাটারি প্রযুক্তি</button>
                <button onclick="filterCategory('cable')" class="cat-btn px-4 py-2 rounded-xl font-medium bg-gray-200 dark:bg-gray-800 text-gray-700 dark:text-gray-300 hover:bg-amber-500/20 whitespace-nowrap">কেবল ও সাইজিং</button>
                <button onclick="filterCategory('safety')" class="cat-btn px-4 py-2 rounded-xl font-medium bg-gray-200 dark:bg-gray-800 text-gray-700 dark:text-gray-300 hover:bg-amber-500/20 whitespace-nowrap">সেফটি ও প্রটেকশন</button>
            </div>

            <!-- Articles Cards Grid -->
            <div id="articlesGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Articles will be injected by JavaScript -->
            </div>
        </div>

        <!-- SECTION 2: SOLAR CALCULATOR TAB -->
        <div id="tab-calculator" class="tab-content hidden">
            <div class="max-w-4xl mx-auto bg-white dark:bg-darkCard rounded-3xl p-6 sm:p-8 border border-gray-200 dark:border-gray-800 shadow-2xl">
                <div class="mb-6 border-b border-gray-200 dark:border-gray-800 pb-4">
                    <h2 class="text-2xl font-bold text-amber-500 flex items-center">
                        <i class="fa-solid fa-calculator mr-2.5"></i> প্রফেশনাল সোলার লোড ও ইনভার্টার সাইজিং ক্যালকুলেটর
                    </h2>
                    <p class="text-xs sm:text-sm text-gray-500 dark:text-gray-400 mt-1">
                        আপনার বাসার প্রয়োজনীয় ডিভাইসের সংখ্যা দিয়ে সোলার প্যানেল, ইনভার্টার, লিথিয়াম/টিউবুলার ব্যাটারি এবং ডিসি কেবলের মাপ বের করুন।
                    </p>
                </div>

                <!-- Input Appliance Table -->
                <div class="space-y-4 mb-8">
                    <div class="grid grid-cols-12 gap-2 text-xs font-bold text-gray-500 dark:text-gray-400 px-2">
                        <div class="col-span-5 sm:col-span-4">ডিভাইসের নাম</div>
                        <div class="col-span-3 sm:col-span-3">ওয়াট (Watt)</div>
                        <div class="col-span-2 sm:col-span-2">সংখ্যা</div>
                        <div class="col-span-2 sm:col-span-3">দৈনিক ব্যবহার (ঘণ্টা)</div>
                    </div>

                    <!-- Appliance Rows -->
                    <div id="applianceRows" class="space-y-3">
                        <!-- Dynamic appliance rows -->
                    </div>

                    <button onclick="addApplianceRow()" class="px-4 py-2 text-xs font-semibold rounded-lg bg-emerald-500/10 text-emerald-500 hover:bg-emerald-500/20 transition flex items-center">
                        <i class="fa-solid fa-plus mr-1.5"></i> নতুন ডিভাইস যোগ করুন
                    </button>
                </div>

                <!-- Calculate Action Button -->
                <button onclick="calculateSolarSystem()" class="w-full py-3.5 rounded-2xl bg-gradient-to-r from-amber-500 to-amber-600 hover:from-amber-600 hover:to-amber-700 text-slate-950 font-bold text-lg shadow-xl shadow-amber-500/20 transition flex items-center justify-center">
                    <i class="fa-solid fa-bolt mr-2"></i> সিস্টেম সাইজ হিসাব করুন
                </button>

                <!-- Calculation Results Panel -->
                <div id="calcResults" class="hidden mt-8 p-6 rounded-2xl bg-gray-50 dark:bg-gray-900 border border-amber-500/30 space-y-6 animate-fade-in">
                    <h3 class="text-lg font-bold text-amber-500 border-b border-gray-200 dark:border-gray-800 pb-2 flex items-center">
                        <i class="fa-solid fa-square-poll-vertical mr-2"></i> আপনার সোলার সিস্টেমের প্রস্তাবিত পরিমাপ
                    </h3>

                    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4">
                        <div class="p-4 rounded-xl bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700">
                            <span class="text-xs text-gray-500">মোট রানিং লোড</span>
                            <div class="text-xl font-extrabold text-amber-500" id="resTotalWatt">0 W</div>
                        </div>
                        <div class="p-4 rounded-xl bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700">
                            <span class="text-xs text-gray-500">দৈনিক শক্তি চাহিদা</span>
                            <div class="text-xl font-extrabold text-blue-500" id="resTotalWh">0 Wh / দিন</div>
                        </div>
                        <div class="p-4 rounded-xl bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700">
                            <span class="text-xs text-gray-500">প্রস্তাবিত সোলার প্যানেল</span>
                            <div class="text-xl font-extrabold text-emerald-500" id="resSolarPanel">0 Watt</div>
                        </div>
                        <div class="p-4 rounded-xl bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700">
                            <span class="text-xs text-gray-500">ইনভার্টার ক্যাপাসিটি</span>
                            <div class="text-xl font-extrabold text-purple-500" id="resInverter">0 kVA</div>
                        </div>
                        <div class="p-4 rounded-xl bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700">
                            <span class="text-xs text-gray-500">ব্যাটারি স্টোরেজ (LiFePO4/Tubular)</span>
                            <div class="text-xl font-extrabold text-amber-400" id="resBattery">0 Ah (24V)</div>
                        </div>
                        <div class="p-4 rounded-xl bg-white dark:bg-gray-800 border border-gray-200 dark:border-gray-700">
                            <span class="text-xs text-gray-500">প্রস্তাবিত ডিসি কেবল সাইজ</span>
                            <div class="text-xl font-extrabold text-rose-500" id="resCable">0 Sq-mm</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- SECTION 3: SAFETY & DIAGRAMS TAB -->
        <div id="tab-diagrams" class="tab-content hidden">
            <div class="space-y-8">
                <!-- Interactive Wiring Visualizer -->
                <div class="p-6 sm:p-8 rounded-3xl bg-white dark:bg-darkCard border border-gray-200 dark:border-gray-800 shadow-2xl">
                    <h2 class="text-2xl font-bold text-amber-500 mb-2">
                        <i class="fa-solid fa-sitemap mr-2"></i> হাইব্রিড সোলার সিস্টেম কানেকশন ডায়াগ্রাম ও সেফটি আর্কিটেকচার
                    </h2>
                    <p class="text-sm text-gray-500 dark:text-gray-400 mb-6">
                        একটি আদর্শ ও নিরাপদ সোলার ইন্সটলেশনে কোন স্থানে কোন সেফটি ডিভাইস (SPD, MCB, Fuse, Isolator) বসাতে হয় তার ইন্টারঅ্যাক্টিভ চিত্র।
                    </p>

                    <!-- Interactive Diagram Container -->
                    <div class="relative overflow-x-auto p-6 rounded-2xl bg-slate-900 text-white border border-gray-800 min-w-[700px]">
                        <div class="flex items-center justify-between gap-4">
                            <!-- Panels -->
                            <div class="flex flex-col items-center p-4 rounded-xl bg-amber-500/10 border border-amber-500/30 w-36 text-center">
                                <