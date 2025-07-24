<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Edward Flowers | Project & Operations Management</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700;800&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Warm Neutrals -->
    <!-- Application Structure Plan: The SPA is designed as an interactive professional narrative. It replaces the static, linear resume format with dynamic, thematic sections. The structure includes a prominent hero section for immediate impact, a key achievements dashboard with animated stats to quantify success, an interactive career timeline to visualize growth, and a skills grid for quick assessment. This user-centric design allows recruiters to quickly grasp key qualifications and explore details on demand, which is more effective for engagement than a traditional document. -->
    <!-- Visualization & Content Choices: 
        - Professional Summary (Inform): A clean, prominent text block. Method: HTML/Tailwind.
        - Key Achievements (Engage/Inform): Animated number counters for key metrics (e.g., exceeding goals by 35%). Goal: To draw immediate attention to quantifiable success. Interaction: Numbers animate on scroll. Method: JS (IntersectionObserver).
        - Professional Experience (Organize/Explore): An interactive vertical timeline. Goal: To showcase career progression cleanly. Interaction: Clicking a job title reveals its details. Method: JS.
        - Areas of Expertise (Inform/Organize): A responsive grid of skills. Goal: For quick, scannable assessment of capabilities. Interaction: Subtle hover effect. Method: HTML/Tailwind.
        - All choices are implemented without external graphics libraries, focusing on a lightweight, professional presentation.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #F8F9FA;
            color: #212529;
        }
        .nav-link {
            transition: color 0.3s, border-bottom-color 0.3s;
            border-bottom: 2px solid transparent;
        }
        .nav-link.active, .nav-link:hover {
            color: #0d6efd;
            border-bottom-color: #0d6efd;
        }
        .timeline-item {
            border-left: 3px solid #dee2e6;
        }
        .timeline-item.active {
            border-left: 3px solid #0d6efd;
        }
        .timeline-item-title {
            transition: background-color 0.3s;
        }
        .timeline-item-title:hover {
            background-color: #e9ecef;
        }
        .details-panel {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease-in-out, opacity 0.5s ease-in-out;
            opacity: 0;
        }
        .details-panel.open {
            max-height: 500px;
            opacity: 1;
        }
        .skill-card {
            transition: transform 0.2s, box-shadow 0.2s;
        }
        .skill-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.08);
        }
    </style>
</head>
<body class="antialiased">

    <header id="header" class="bg-white/90 backdrop-blur-lg sticky top-0 z-50 shadow-sm">
        <nav class="container mx-auto px-6 py-3 flex justify-between items-center">
            <a href="#" class="text-2xl font-extrabold text-gray-800">Edward Flowers</a>
            <div class="hidden md:flex items-center space-x-8">
                <a href="#summary" class="nav-link font-medium text-gray-600">Summary</a>
                <a href="#experience" class="nav-link font-medium text-gray-600">Experience</a>
                <a href="#skills" class="nav-link font-medium text-gray-600">Skills</a>
                <a href="#education" class="nav-link font-medium text-gray-600">Education</a>
            </div>
            <a href="mailto:Sirflowers03@gmail.com" class="hidden sm:inline-block bg-blue-600 text-white font-bold py-2 px-5 rounded-lg hover:bg-blue-700 transition-colors">Contact Me</a>
        </nav>
    </header>

    <main class="container mx-auto px-6">

        <section id="summary" class="text-center py-20 md:py-28">
            <h1 class="text-4xl md:text-6xl font-extrabold text-gray-900 leading-tight">Project & Operations Management</h1>
            <p class="max-w-3xl mx-auto mt-6 text-lg text-gray-600">
                Dynamic and results-oriented management professional with over 10 years of experience leading teams, driving sales growth, and managing successful business operations. A decorated U.S. Army veteran with a proven ability to develop and implement strategic plans, exceed performance goals, and foster a culture of excellence.
            </p>
            <div class="mt-8 flex justify-center gap-4">
                <a href="https://www.linkedin.com/in/edward-flowers-34717010b/" target="_blank" class="bg-gray-800 text-white font-bold py-3 px-6 rounded-lg hover:bg-gray-900 transition-colors">View LinkedIn</a>
                <a href="#experience" class="bg-gray-200 text-gray-800 font-bold py-3 px-6 rounded-lg hover:bg-gray-300 transition-colors">Explore Experience</a>
            </div>
        </section>

        <section id="achievements" class="py-16">
             <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-gray-800">Key Achievements</h2>
                <p class="mt-2 text-gray-600">A snapshot of quantifiable success across various roles.</p>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8 text-center">
                <div class="bg-white p-8 rounded-xl shadow-md">
                    <p class="text-5xl font-extrabold text-blue-600" data-target="35">0</p>
                    <p class="mt-2 text-lg font-medium text-gray-700">Exceeded Monthly Goals by up to 35%</p>
                </div>
                <div class="bg-white p-8 rounded-xl shadow-md">
                    <p class="text-5xl font-extrabold text-blue-600" data-target="3">0</p>
                    <p class="mt-2 text-lg font-medium text-gray-700">"Advisor of the Month" Awards</p>
                </div>
                <div class="bg-white p-8 rounded-xl shadow-md">
                    <p class="text-5xl font-extrabold text-blue-600" data-target="2">0</p>
                    <p class="mt-2 text-lg font-medium text-gray-700">Consecutive Years as "Top Performer"</p>
                </div>
            </div>
        </section>

        <section id="experience" class="py-20">
            <div class="text-center mb-16">
                <h2 class="text-3xl font-bold text-gray-800">Professional Experience</h2>
                <p class="mt-2 text-gray-600 max-w-2xl mx-auto">An interactive timeline of my career progression. Click each role to view details and key accomplishments.</p>
            </div>
            <div id="timeline-container" class="max-w-4xl mx-auto">
            </div>
        </section>

        <section id="skills" class="py-16">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-gray-800">Areas of Expertise</h2>
                <p class="mt-2 text-gray-600">A collection of core competencies and professional skills.</p>
            </div>
            <div id="skills-grid" class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-5">
            </div>
        </section>

        <section id="education" class="py-20">
            <div class="bg-blue-600 text-white rounded-2xl p-12 text-center">
                <h2 class="text-3xl font-bold">Education</h2>
                <p class="mt-4 text-xl font-medium">Bachelor of Business Management</p>
                <p class="text-blue-200">Expected Graduation: January 2025</p>
                <p class="mt-2 text-blue-200">Grand Canyon University, Phoenix, AZ | GPA: 3.47</p>
            </div>
        </section>

    </main>

    <footer class="bg-gray-800 text-white mt-20">
        <div class="container mx-auto px-6 py-10 text-center">
            <h3 class="text-2xl font-bold">Ready to Connect?</h3>
            <p class="mt-2 text-gray-300">I'm always open to discussing new opportunities and challenges.</p>
            <div class="mt-6">
                <a href="mailto:Sirflowers03@gmail.com" class="bg-white text-gray-800 font-bold py-3 px-8 rounded-lg hover:bg-gray-200 transition-colors">Email Me</a>
            </div>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const experienceData = [
                {
                    role: "Owner",
                    company: "Hacienda Service Team",
                    dates: "July 2022 - Present",
                    details: [
                        "Launched and manage all aspects of a residential cleaning service, including business planning, marketing, client acquisition, and operational oversight.",
                        "Drive business growth by ensuring high-quality service delivery and cultivating a strong reputation for customer satisfaction.",
                        "Implement standard operating procedures for cleaning techniques, staff training, and equipment maintenance to ensure efficiency and quality control."
                    ]
                },
                {
                    role: "Business Development Manager",
                    company: "Caribou",
                    dates: "July 2021 - January 2023",
                    details: [
                        "Developed and executed strategic plans to identify, qualify, and onboard new clients, consistently exceeding monthly acquisition goals by 35%.",
                        "Provided expert consultative support to clients, analyzing their financial needs to tailor solutions that met budget and service objectives.",
                        "Recognized as 'Advisor of the Month' (March 2022, June and August) for outstanding sales performance and excellence in client satisfaction."
                    ]
                },
                {
                    role: "Office Manager / Lead Sales Agent",
                    company: "Allstate Insurance",
                    dates: "September 2015 - August 2018",
                    details: [
                        "Led and coached a team of sales and customer service representatives, achieving 'Top Performer' recognition in both 2016 and 2017.",
                        "Drove team performance to exceed monthly sales goals by 15% for two consecutive years.",
                        "Developed and implemented comprehensive training programs to equip team members with the product knowledge and sales skills needed to succeed."
                    ]
                },
                {
                    role: "Certified Food Manager / Culinary Operations Manager",
                    company: "United States Army",
                    dates: "August 2003 - July 2012",
                    details: [
                        "Managed all culinary operations for a military unit, with full responsibility for budget administration, inventory control, and supply chain management.",
                        "Led and motivated teams in a high-pressure environment to ensure the efficient and hygienic preparation and delivery of meals on a large scale.",
                        "Successfully implemented cost-saving measures and improved operational procedures, fostering a positive and productive work environment."
                    ]
                }
            ];

            const timelineContainer = document.getElementById('timeline-container');
            experienceData.forEach((job, index) => {
                const item = document.createElement('div');
                item.className = 'timeline-item relative pl-8 pb-8';
                
                const dot = document.createElement('div');
                dot.className = 'absolute top-1 left-[-7px] w-4 h-4 bg-white border-4 border-blue-600 rounded-full';
                item.appendChild(dot);

                const title = document.createElement('div');
                title.className = 'timeline-item-title cursor-pointer p-4 rounded-lg';
                title.innerHTML = `
                    <p class="font-bold text-lg text-gray-800">${job.role}</p>
                    <p class="text-sm text-gray-600">${job.company} | ${job.dates}</p>
                `;
                item.appendChild(title);

                const detailsPanel = document.createElement('div');
                detailsPanel.className = 'details-panel ml-4 mt-2';
                const ul = document.createElement('ul');
                ul.className = 'list-disc pl-5 space-y-2 text-gray-700';
                job.details.forEach(detail => {
                    const li = document.createElement('li');
                    li.textContent = detail;
                    ul.appendChild(li);
                });
                detailsPanel.appendChild(ul);
                item.appendChild(detailsPanel);

                timelineContainer.appendChild(item);

                title.addEventListener('click', () => {
                    const wasOpen = detailsPanel.classList.contains('open');
                    
                    document.querySelectorAll('.details-panel.open').forEach(panel => panel.classList.remove('open'));
                    document.querySelectorAll('.timeline-item.active').forEach(i => i.classList.remove('active'));

                    if (!wasOpen) {
                        detailsPanel.classList.add('open');
                        item.classList.add('active');
                    }
                });

                if (index === 0) {
                    title.click();
                }
            });

            const skills = [
                "Team Leadership & Development", "Project & Operations Management", "Business Development", "Sales Strategy",
                "P&L Analysis", "Budget Management", "Customer Relationship Management", "Process Improvement",
                "Training & Mentorship", "Strategic Planning", "Negotiation", "Vendor Relations"
            ];
            const skillsGrid = document.getElementById('skills-grid');
            skills.forEach(skill => {
                const card = document.createElement('div');
                card.className = 'skill-card bg-white p-4 rounded-lg shadow-sm text-center';
                card.innerHTML = `<p class="font-medium text-gray-700">${skill}</p>`;
                skillsGrid.appendChild(card);
            });

            const counters = document.querySelectorAll('[data-target]');
            const animateCounter = (el) => {
                const target = +el.dataset.target;
                let count = 0;
                const updateCount = () => {
                    const increment = target / 100;
                    if (count < target) {
                        count = Math.ceil(count + increment);
                        el.innerText = count;
                        requestAnimationFrame(updateCount);
                    } else {
                        el.innerText = target;
                    }
                };
                updateCount();
            };

            const observerOptions = { threshold: 0.5 };
            const counterObserver = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        animateCounter(entry.target);
                        observer.unobserve(entry.target);
                    }
                });
            }, observerOptions);
            counters.forEach(counter => counterObserver.observe(counter));
            
            const navLinks = document.querySelectorAll('.nav-link');
            const sections = document.querySelectorAll('section');
            const navObserver = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        navLinks.forEach(link => {
                            link.classList.toggle('active', link.getAttribute('href').substring(1) === entry.target.id);
                        });
                    }
                });
            }, { rootMargin: "-30% 0px -70% 0px" });
            sections.forEach(section => navObserver.observe(section));
        });
    </script>
</body>
</html>
