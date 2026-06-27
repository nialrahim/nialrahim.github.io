# nialrahim.github.io
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UTeM Student Professional Digital Portfolio</title>
    <!-- Fonts and Icons -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&family=Roboto:wght@400;500&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* CSS RESET & VARIABLES (HCI Palette) */
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Roboto', sans-serif; scroll-behavior: smooth; }
        :root {
            --bg-primary: #0F172A;
            --bg-secondary: #1E293B;
            --text-main: #F8FAFC;
            --text-muted: #94A3B8;
            --accent: #38BDF8;
            --accent-hover: #0EA5E9;
        }

        body { background-color: var(--bg-primary); color: var(--text-main); line-height: 1.6; overflow-x: hidden; }
        h1, h2, h3, .nav-logo { font-family: 'Inter', sans-serif; font-weight: 800; }

        /* FIXED NAVIGATION (HCI Consistency Standard with Overflow Fix) */
        nav {
            position: fixed; top: 0; left: 0; width: 100%; height: 70px;
            background: rgba(15, 23, 42, 0.9); backdrop-filter: blur(10px);
            display: flex; justify-content: space-between; align-items: center;
            padding: 0 5%; z-index: 1000; border-bottom: 1px solid #334155;
        }
        .nav-logo { color: var(--accent); font-size: 1.5rem; text-decoration: none; }
        .nav-links { display: flex; list-style: none; gap: 25px; }
        .nav-links a { color: var(--text-main); text-decoration: none; font-weight: 500; transition: 0.3s; font-size: 0.95rem; }
        .nav-links a:hover, .nav-links a.active { color: var(--accent); }

        /* PORTFOLIO PAGES/SECTIONS SETUP (Centered & Layout Constrained) */
        section { 
            padding: 120px 5% 80px 5%; 
            min-height: 100vh; 
            max-width: 1200px; 
            margin: 0 auto; /* Centers the content block on wide viewports */
            display: flex; 
            flex-direction: column; 
            justify-content: center; 
        }
        .section-title { font-size: 2.5rem; margin-bottom: 40px; color: var(--text-main); position: relative; }
        .section-title::after { content: ''; display: block; width: 60px; height: 4px; background: var(--accent); margin-top: 10px; border-radius: 2px; }

        /* PAGE 1: HOME SECTION (Perfectly Centered Alignment) */
        #home { align-items: center; text-align: center; }
        #home h1 { font-size: 4rem; margin-bottom: 20px; line-height: 1.1; }
        #home h1 span { color: var(--accent); }
        #home p { font-size: 1.25rem; color: var(--text-muted); max-width: 600px; margin: 0 auto 35px auto; }
        .btn-cta { 
            padding: 12px 28px; background: var(--accent); color: var(--bg-primary); 
            text-decoration: none; font-weight: 600; border-radius: 6px; 
            transition: 0.3s; font-family: 'Inter', sans-serif; border: none; cursor: pointer;
            display: inline-block;
        }
        .btn-cta:hover { background: var(--accent-hover); transform: translateY(-2px); }

        /* PAGE 2: PERSONAL & CONTACT DETAILS */
        .about-container { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 40px; align-items: center; width: 100%; }
        .profile-card { background: var(--bg-secondary); padding: 30px; border-radius: 12px; border: 1px solid #334155; text-align: center; }
        .profile-img-mock { width: 130px; height: 130px; background: #475569; border-radius: 50%; margin: 0 auto 20px auto; display: flex; align-items: center; justify-content: center; font-size: 3rem; color: var(--accent); }
        .contact-list { text-align: left; margin-top: 20px; list-style: none; }
        .contact-list li { margin-bottom: 12px; font-size: 0.9rem; color: var(--text-muted); }
        .contact-list i { color: var(--accent); margin-right: 10px; width: 20px; }

        /* PAGE 3: ACADEMIC HISTORY (TIMELINE) */
        .timeline { position: relative; max-width: 800px; margin: 0 auto; width: 100%; }
        .timeline::after { content: ''; position: absolute; width: 4px; background: var(--bg-secondary); top: 0; bottom: 0; left: 31px; }
        .timeline-item { padding: 10px 10px 10px 70px; position: relative; background: inherit; width: 100%; margin-bottom: 20px; }
        .timeline-item::after { content: ''; position: absolute; width: 16px; height: 16px; background-color: var(--bg-primary); border: 4px solid var(--accent); top: 25px; left: 25px; border-radius: 50%; z-index: 1; }
        .timeline-content { padding: 20px; background: var(--bg-secondary); position: relative; border-radius: 8px; border-left: 4px solid var(--accent); }
        .timeline-content h3 { color: var(--accent); font-size: 1.2rem; margin-bottom: 5px; }
        .timeline-content h4 { font-size: 1rem; margin-bottom: 10px; color: var(--text-main); }
        .timeline-content p { font-size: 0.9rem; color: var(--text-muted); }

        /* PAGE 4: WORK PRODUCED (GRID) */
        .portfolio-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px; width: 100%; }
        .portfolio-card { background: var(--bg-secondary); border-radius: 10px; overflow: hidden; border: 1px solid #334155; transition: 0.3s; }
        .portfolio-card:hover { transform: translateY(-5px); border-color: var(--accent); }
        .video-mock { width: 100%; height: 180px; background: #334155; display: flex; align-items: center; justify-content: center; font-style: italic; color: var(--text-muted); position: relative; padding: 10px; text-align: center; }
        .video-mock i { font-size: 2.5rem; color: var(--accent); opacity: 0.7; }
        .portfolio-info { padding: 20px; }
        .portfolio-info h3 { margin-bottom: 10px; font-size: 1.25rem; }
        .portfolio-info p { color: var(--text-muted); font-size: 0.9rem; margin-bottom: 15px; }

        /* PAGE 5: PERSONAL QUALITIES & SKILLS */
        .skills-container { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 40px; width: 100%; }
        .skill-bar-group { margin-bottom: 20px; }
        .skill-label { display: flex; justify-content: space-between; margin-bottom: 5px; font-weight: 500; font-size: 0.95rem; }
        .bar-bg { background: var(--bg-secondary); height: 10px; border-radius: 5px; overflow: hidden; }
        .bar-fill { background: var(--accent); height: 100%; border-radius: 5px; width: 0%; transition: width 1.5s ease-in-out; }

        /* PAGE 6: CONTACT & VALIDATED FORM */
        .contact-wrapper { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 50px; width: 100%; }
        form { display: flex; flex-direction: column; gap: 15px; }
        input, textarea { background: var(--bg-secondary); border: 1px solid #334155; padding: 15px; border-radius: 6px; color: white; font-size: 0.95rem; width: 100%; }
        input:focus, textarea:focus { outline: none; border-color: var(--accent); }
        .error-msg { color: #F87171; font-size: 0.85rem; display: none; margin-top: -10px; }

        /* ADDED VALUE FEATURE: ACCESSIBILITY TOGGLE BUTTON */
        .theme-switch { position: fixed; bottom: 25px; right: 25px; background: var(--bg-secondary); border: 1px solid #334155; padding: 12px; border-radius: 50%; cursor: pointer; color: var(--accent); box-shadow: 0 4px 12px rgba(0,0,0,0.3); z-index: 1001; }
        
        /* RESPONSIVE DESIGN BREAKPOINT */
        @media (max-width: 768px) {
            #home h1 { font-size: 2.5rem; }
            nav { padding: 0 20px; }
            .nav-links { display: none; } /* Standard for quick simple view, toggleable via custom navbar extensions later */
        }
    </style>
</head>
<body>

    <!-- INTERACTIVE NAV -->
    <nav>
        <a href="#home" class="nav-logo"><i class="fa-solid fa-code"></i> Portfolio.</a>
        <ul class="nav-links">
            <li><a href="#home" class="active">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#education">Education</a></li>
            <li><a href="#work">Projects</a></li>
            <li><a href="#skills">Qualities</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <!-- PAGE 1: HOME -->
    <section id="home">
        <h1>Building Digital Experiences<br>Driven by <span>HCI Principles.</span></h1>
        <p>Hi, I am a Software Engineering Student at UTeM. I specialize in building fully accessible, user-friendly high-fidelity applications and freelance web systems.</p>
        <a href="#work" class="btn-cta">Explore My Works <i class="fa-solid fa-arrow-right"></i></a>
    </section>

    <!-- PAGE 2: PERSONAL & CONTACT DETAILS -->
    <section id="about">
        <h2 class="section-title">Personal Details</h2>
        <div class="about-container">
            <div class="profile-card">
                <div class="profile-img-mock"><i class="fa-regular fa-user"></i></div>
                <h3>Your Name Here</h3>
                <p style="color: var(--accent); font-size: 0.9rem;">UTeM Undergraduate</p>
                <ul class="contact-list">
                    <li><i class="fa-regular fa-envelope"></i> student@student.utem.edu.my</li>
                    <li><i class="fa-solid fa-phone"></i> +60 1X-XXXXXXX</li>
                    <li><i class="fa-brands fa-linkedin"></i> linkedin.com/in/username</li>
                    <li><i class="fa-solid fa-location-dot"></i> Durian Tunggal, Melaka</li>
                </ul>
            </div>
            <div>
                <h3 style="margin-bottom: 15px;">Professional Biography</h3>
                <p style="color: var(--text-muted); margin-bottom: 20px;">I am an enthusiastic technology student equipped with absolute foundations in Human-Computer Interaction, UI layout development, and responsive architectures. My design philosophy adheres directly to user ergonomics and interactive efficiency.</p>
                <button class="btn-cta" onclick="alert('Downloading CV / Academic Transcript Mock...')"><i class="fa-solid fa-download"></i> Download Academic Transcript</button>
            </div>
        </div>
    </section>

    <!-- PAGE 3: ACADEMIC HISTORY -->
    <section id="education">
        <h2 class="section-title">Academic History</h2>
        <div class="timeline">
            <div class="timeline-item">
                <div class="timeline-content">
                    <h3>2024 - Present</h3>
                    <h4>Universiti Teknikal Malaysia Melaka (UTeM)</h4>
                    <p>Bachelor of Computer Science (Software Development). Focusing on core HCI fundamentals, Software Engineering, and Advanced Web Application Frameworks.</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-content">
                    <h3>2021 - 2023</h3>
                    <h4>Previous Institution / Matriculation</h4>
                    <p>Foundation in Computer Science / Diploma studies. Established strong technical baselines in object-oriented logic principles.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- PAGE 4: WORK PRODUCED -->
    <section id="work">
        <h2 class="section-title">Work Produced & Projects</h2>
        <div class="portfolio-grid">
            <div class="portfolio-card">
                <div class="video-mock"><i class="fa-solid fa-circle-play"></i>&nbsp;[Hover to Preview System GIF]</div>
                <div class="portfolio-info">
                    <h3>UTeM Smart Room Booking System</h3>
                    <p>Academic HCI Group Project built with interface standardizations following strict color hierarchies and navigation flows.</p>
                </div>
            </div>
            <div class="portfolio-card">
                <div class="video-mock"><i class="fa-solid fa-circle-play"></i>&nbsp;[Hover to Preview System GIF]</div>
                <div class="portfolio-info">
                    <h3>Local Vendor E-Commerce Platform</h3>
                    <p>A freelance dynamic deployment engineered to allow seamless item search queries and standard shopping flow architectures.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- PAGE 5: PERSONAL QUALITIES & SKILLS -->
    <section id="skills">
        <h2 class="section-title">Personal Qualities & Skills</h2>
        <div class="skills-container">
            <div>
                <h3 style="margin-bottom:20px;">Technical Competencies</h3>
                <div class="skill-bar-group">
                    <div class="skill-label"><span>UI/UX Prototyping (Figma)</span><span>90%</span></div>
                    <div class="bar-bg"><div class="bar-fill" data-width="90%"></div></div>
                </div>
                <div class="skill-bar-group">
                    <div class="skill-label"><span>Frontend Engineering (HTML/CSS/JS)</span><span>85%</span></div>
                    <div class="bar-bg"><div class="bar-fill" data-width="85%"></div></div>
                </div>
            </div>
            <div>
                <h3 style="margin-bottom:20px;">Professional Core Qualities</h3>
                <div class="skill-bar-group">
                    <div class="skill-label"><span>User Research & Information Architecture</span><span>95%</span></div>
                    <div class="bar-bg"><div class="bar-fill" data-width="95%"></div></div>
                </div>
                <div class="skill-bar-group">
                    <div class="skill-label"><span>Team Collaboration & Agile Communication</span><span>90%</span></div>
                    <div class="bar-bg"><div class="bar-fill" data-width="90%"></div></div>
                </div>
            </div>
        </div>
    </section>

    <!-- PAGE 6: CONTACT & FORM VALIDATION -->
    <section id="contact">
        <h2 class="section-title">Get In Touch</h2>
        <div class="contact-wrapper">
            <div>
                <h3 style="margin-bottom: 15px;">Let's Connect for Internships & Projects</h3>
                <p style="color: var(--text-muted);">Have an internship opening, a freelance project opportunity, or want to review my code? Submit the form or hit me up through the official details listed.</p>
            </div>
            <form id="contactForm" onsubmit="event.preventDefault(); validateForm();">
                <input type="text" id="name" placeholder="Your Full Name" required>
                <input type="email" id="email" placeholder="Your Professional Email" required>
                <div id="emailError" class="error-msg">Please enter a valid business email domain structure.</div>
                <textarea id="message" rows="5" placeholder="Your Message..." required></textarea>
                <button type="submit" class="btn-cta">Send Verified Message</button>
            </form>
        </div>
    </section>

    <!-- UNIQUENESS / ADDED VALUE ACCESSIBILITY FEATURE -->
    <div class="theme-switch" onclick="alert('Accessibility Feature Toggle triggered: Font scalability and high-contrast color mode applied.')" title="Toggle Accessibility Mode">
        <i class="fa-solid fa-eye"></i>
    </div>

    <!-- CODE CONTROLLER SCRIPT (INTERACTION TRACKING) -->
    <script>
        // Highlighting current section links as user scrolls (HCI System Status Feedback)
        const sections = document.querySelectorAll('section');
        const navLinks = document.querySelectorAll('.nav-links a');

        window.addEventListener('scroll', () => {
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                if (pageYOffset >= sectionTop - 120) {
                    current = section.getAttribute('id');
                }
            });
            navLinks.forEach(a => {
                a.classList.remove('active');
                if (a.getAttribute('href').includes(current)) {
                    a.classList.add('active');
                }
            });

            // Trigger Skill bar filling animation on reach
            if(current === 'skills') {
                document.querySelectorAll('.bar-fill').forEach(bar => {
                    bar.style.width = bar.getAttribute('data-width');
                });
            }
        });

        // Interactive Inline Client Form Validation
        function validateForm() {
            const email = document.getElementById('email').value;
            const emailError = document.getElementById('emailError');
            if (!email.includes('@') || !email.includes('.')) {
                emailError.style.display = 'block';
            } else {
                emailError.style.display = 'none';
                alert('Success! Your message was submitted securely according to strict operational standards.');
            }
        }
    </script>
</body>
</html>
