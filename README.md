# TAPSA
TAPSA WEBSITE
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TAPSA SJUT - Pharmaceutical Students' Platform</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #1a1a1a;
            background: #f5f5f5;
        }
        
        /* Color Scheme */
        :root {
            --dark-blue: #1a3a52;
            --blue: #2E5C8A;
            --orange: #E67E22;
            --white: #FFFFFF;
            --black: #1a1a1a;
            --light-gray: #f8f9fa;
            --border-gray: #e0e0e0;
        }
        
        /* Navigation */
        nav {
            background: var(--dark-blue);
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: var(--white);
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        
        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        
        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }
        
        .nav-links a {
            color: var(--white);
            text-decoration: none;
            font-size: 0.95rem;
            transition: color 0.3s;
        }
        
        .nav-links a:hover {
            color: var(--orange);
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--dark-blue) 0%, var(--blue) 100%);
            color: var(--white);
            padding: 5rem 2rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 500px;
            height: 500px;
            background: rgba(230, 126, 34, 0.1);
            border-radius: 50%;
        }
        
        .hero-content {
            position: relative;
            z-index: 1;
            max-width: 800px;
            margin: 0 auto;
        }
        
        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            font-weight: 600;
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.95;
        }
        
        .cta-button {
            display: inline-block;
            background: var(--orange);
            color: var(--white);
            padding: 0.8rem 2.5rem;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            transition: all 0.3s;
            text-decoration: none;
        }
        
        .cta-button:hover {
            background: #d35a0a;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(230, 126, 34, 0.3);
        }
        
        /* Main Content */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }
        
        .section {
            padding: 4rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            font-size: 2rem;
            color: var(--dark-blue);
            font-weight: 600;
        }
        
        .section-subtitle {
            text-align: center;
            color: var(--blue);
            margin-bottom: 2rem;
            font-size: 1rem;
        }
        
        /* Features Grid */
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }
        
        .feature-card {
            background: var(--white);
            padding: 2rem;
            border-radius: 8px;
            border: 1px solid var(--border-gray);
            transition: all 0.3s;
            text-align: center;
        }
        
        .feature-card:hover {
            box-shadow: 0 8px 20px rgba(26, 58, 82, 0.15);
            transform: translateY(-5px);
        }
        
        .feature-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--orange);
        }
        
        .feature-card h3 {
            color: var(--dark-blue);
            margin-bottom: 0.8rem;
            font-size: 1.3rem;
        }
        
        .feature-card p {
            color: #666;
            font-size: 0.95rem;
            line-height: 1.6;
        }
        
        /* Modules Showcase */
        .modules-showcase {
            background: var(--light-gray);
            border-radius: 8px;
            padding: 2rem;
            margin-bottom: 3rem;
        }
        
        .module-tabs {
            display: flex;
            gap: 0.5rem;
            margin-bottom: 2rem;
            flex-wrap: wrap;
            border-bottom: 2px solid var(--border-gray);
        }
        
        .module-tab {
            padding: 1rem 1.5rem;
            background: transparent;
            border: none;
            border-bottom: 3px solid transparent;
            cursor: pointer;
            font-size: 0.95rem;
            font-weight: 500;
            color: var(--black);
            transition: all 0.3s;
        }
        
        .module-tab.active {
            color: var(--orange);
            border-bottom-color: var(--orange);
        }
        
        .module-tab:hover {
            color: var(--blue);
        }
        
        .module-content {
            display: none;
            animation: fadeIn 0.4s;
        }
        
        .module-content.active {
            display: block;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        .module-details {
            background: var(--white);
            padding: 2rem;
            border-radius: 6px;
            border-left: 4px solid var(--orange);
        }
        
        .module-details h4 {
            color: var(--dark-blue);
            margin-bottom: 1rem;
            font-size: 1.2rem;
        }
        
        .module-details ul {
            list-style: none;
            margin-left: 0;
        }
        
        .module-details li {
            padding: 0.5rem 0;
            padding-left: 1.5rem;
            position: relative;
            color: #555;
        }
        
        .module-details li:before {
            content: '✓';
            position: absolute;
            left: 0;
            color: var(--orange);
            font-weight: bold;
        }
        
        /* Roles Section */
        .roles-section {
            background: var(--white);
            padding: 3rem 2rem;
            border-radius: 8px;
            border: 1px solid var(--border-gray);
        }
        
        .roles-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }
        
        .role-card {
            background: linear-gradient(135deg, var(--dark-blue), var(--blue));
            color: var(--white);
            padding: 2rem;
            border-radius: 6px;
            transition: all 0.3s;
        }
        
        .role-card:hover {
            box-shadow: 0 8px 20px rgba(230, 126, 34, 0.25);
            transform: scale(1.05);
        }
        
        .role-card h4 {
            font-size: 1.2rem;
            margin-bottom: 0.8rem;
            color: var(--orange);
        }
        
        .role-card p {
            font-size: 0.9rem;
            line-height: 1.5;
            opacity: 0.95;
        }
        
        .role-card ul {
            list-style: none;
            margin-top: 1rem;
            font-size: 0.85rem;
        }
        
        .role-card li {
            padding: 0.3rem 0;
        }
        
        .role-card li:before {
            content: '→ ';
            color: var(--orange);
            font-weight: bold;
        }
        
        /* Stats Section */
        .stats-section {
            background: linear-gradient(135deg, var(--dark-blue) 0%, var(--blue) 100%);
            color: var(--white);
            padding: 3rem 2rem;
            border-radius: 8px;
            margin: 3rem 0;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            text-align: center;
        }
        
        .stat-item h3 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            color: var(--orange);
        }
        
        .stat-item p {
            font-size: 1rem;
            opacity: 0.9;
        }
        
        /* Footer */
        footer {
            background: var(--dark-blue);
            color: var(--white);
            padding: 3rem 2rem;
            text-align: center;
            margin-top: 4rem;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
            text-align: left;
        }
        
        .footer-section h5 {
            color: var(--orange);
            margin-bottom: 1rem;
            font-size: 1rem;
        }
        
        .footer-section ul {
            list-style: none;
        }
        
        .footer-section a {
            color: var(--white);
            text-decoration: none;
            font-size: 0.9rem;
            transition: color 0.3s;
            display: block;
            margin-bottom: 0.5rem;
        }
        
        .footer-section a:hover {
            color: var(--orange);
        }
        
        .footer-bottom {
            border-top: 1px solid rgba(255,255,255,0.1);
            padding-top: 2rem;
            font-size: 0.9rem;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .nav-links {
                gap: 1rem;
                font-size: 0.85rem;
            }
            
            .module-tabs {
                flex-direction: column;
            }
            
            .section-title {
                font-size: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="logo">
            <i class="fas fa-capsules"></i> TAPSA SJUT
        </div>
        <ul class="nav-links">
            <li><a href="#features">Features</a></li>
            <li><a href="#modules">Modules</a></li>
            <li><a href="#roles">Roles</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>TAPSA SJUT Platform</h1>
            <p>Comprehensive Digital Ecosystem for Pharmaceutical Students</p>
            <p style="font-size: 1rem; opacity: 0.9; margin-bottom: 2rem;">Streamline administration, enhance engagement, and empower leadership</p>
            <button class="cta-button">Get Started</button>
        </div>
    </section>

    <div class="container">
        <!-- Features Section -->
        <section class="section" id="features">
            <h2 class="section-title">Core Platform Features</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-users"></i></div>
                    <h3>Member Management</h3>
                    <p>Streamline onboarding, profiles, fee tracking, and digital identification with automated verification systems.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-vote-yea"></i></div>
                    <h3>Digital Elections</h3>
                    <p>Secure, transparent, and verifiable student elections with real-time results and comprehensive audit logs.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-book"></i></div>
                    <h3>Academic Resources</h3>
                    <p>Centralized access to lecture notes, past papers, practical manuals, and research materials.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-bell"></i></div>
                    <h3>Communication Hub</h3>
                    <p>Real-time announcements, push notifications, event management, and instant member engagement.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-chart-bar"></i></div>
                    <h3>Analytics Dashboard</h3>
                    <p>Comprehensive metrics on members, fees, attendance, events, and organizational growth trends.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon"><i class="fas fa-lock"></i></div>
                    <h3>Secure Infrastructure</h3>
                    <p>Enterprise-grade security with role-based access control and encrypted data management.</p>
                </div>
            </div>
        </section>

        <!-- Modules Showcase -->
        <section class="section" id="modules">
            <h2 class="section-title">Platform Modules</h2>
            <div class="modules-showcase">
                <div class="module-tabs">
                    <button class="module-tab active" onclick="switchModule(0, this)"><i class="fas fa-id-card"></i> Member Portal</button>
                    <button class="module-tab" onclick="switchModule(1, this)"><i class="fas fa-user-tie"></i> Leadership Dashboard</button>
                    <button class="module-tab" onclick="switchModule(2, this)"><i class="fas fa-graduation-cap"></i> Academic Hub</button>
                    <button class="module-tab" onclick="switchModule(3, this)"><i class="fas fa-calendar-check"></i> Events & Attendance</button>
                    <button class="module-tab" onclick="switchModule(4, this)"><i class="fas fa-file-contract"></i> Constitution & Docs</button>
                </div>

                <div class="module-content active">
                    <div class="module-details">
                        <h4><i class="fas fa-id-card" style="margin-right: 0.5rem;"></i>Member Portal</h4>
                        <ul>
                            <li>Personalized welcome message and membership status</li>
                            <li>Upcoming events feed and real-time announcements</li>
                            <li>Active polls and secure digital election access</li>
                            <li>Digital membership card with QR code</li>
                            <li>Quick links to academic resources</li>
                            <li>Fee payment tracking and receipts</li>
                        </ul>
                    </div>
                </div>

                <div class="module-content">
                    <div class="module-details">
                        <h4><i class="fas fa-user-tie" style="margin-right: 0.5rem;"></i>Leadership Dashboard</h4>
                        <ul>
                            <li>Total member counts and registration metrics</li>
                            <li>Pending membership approvals overview</li>
                            <li>Payment summaries and financial tracking</li>
                            <li>Event management and attendance statistics</li>
                            <li>Election status and results monitoring</li>
                            <li>Granular permission management</li>
                        </ul>
                    </div>
                </div>

                <div class="module-content">
                    <div class="module-details">
                        <h4><i class="fas fa-graduation-cap" style="margin-right: 0.5rem;"></i>Academic Hub</h4>
                        <ul>
                            <li>Lecture notes and past papers repository</li>
                            <li>Practical manuals and research materials</li>
                            <li>Class timetables and schedules</li>
                            <li>Internship opportunities distribution</li>
                            <li>Integration with jlibrary.co.tz</li>
                            <li>Advanced search and download tracking</li>
                        </ul>
                    </div>
                </div>

                <div class="module-content">
                    <div class="module-details">
                        <h4><i class="fas fa-calendar-check" style="margin-right: 0.5rem;"></i>Events & Attendance</h4>
                        <ul>
                            <li>QR-code based attendance tracking</li>
                            <li>Event registration and capacity management</li>
                            <li>Venue mapping and speaker information</li>
                            <li>Photo galleries and event documentation</li>
                            <li>Automated attendance logging (Present/Late/Absent)</li>
                            <li>Event history and analytics</li>
                        </ul>
                    </div>
                </div>

                <div class="module-content">
                    <div class="module-details">
                        <h4><i class="fas fa-file-contract" style="margin-right: 0.5rem;"></i>Constitution & Governance</h4>
                        <ul>
                            <li>Full digital access to TAPSA constitution</li>
                            <li>Advanced full-text search capability</li>
                            <li>Bookmarking and text highlighting</li>
                            <li>Offline reading mode and PDF download</li>
                            <li>Leadership directory with profiles</li>
                            <li>Committee structures and responsibilities</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- Statistics Section -->
        <section class="stats-section">
            <div class="stats-grid">
                <div class="stat-item">
                    <h3>100%</h3>
                    <p>Digital Documentation</p>
                </div>
                <div class="stat-item">
                    <h3>24/7</h3>
                    <p>Platform Access</p>
                </div>
                <div class="stat-item">
                    <h3>Real-Time</h3>
                    <p>Notifications</p>
                </div>
                <div class="stat-item">
                    <h3>Secure</h3>
                    <p>Voting System</p>
                </div>
            </div>
        </section>

        <!-- Roles & Access Control -->
        <section class="section" id="roles">
            <h2 class="section-title">User Roles & Access</h2>
            <div class="roles-section">
                <p style="margin-bottom: 2rem; color: #555; text-align: center;">Comprehensive role-based access control designed for effective organizational management</p>
                <div class="roles-grid">
                    <div class="role-card">
                        <h4>Chairperson & VP</h4>
                        <p>Executive Leadership & System Control</p>
                        <ul>
                            <li>System ownership & control</li>
                            <li>Approve announcements</li>
                            <li>Financial oversight</li>
                            <li>Strategic decisions</li>
                        </ul>
                    </div>
                    <div class="role-card">
                        <h4>Secretary</h4>
                        <p>Administrative Operations</p>
                        <ul>
                            <li>Member registration</li>
                            <li>Approve profiles</li>
                            <li>Meeting coordination</li>
                            <li>Document management</li>
                        </ul>
                    </div>
                    <div class="role-card">
                        <h4>Treasurer</h4>
                        <p>Financial Management</p>
                        <ul>
                            <li>Fee tracking</li>
                            <li>Payment approval</li>
                            <li>Budget preparation</li>
                            <li>Financial reports</li>
                        </ul>
                    </div>
                    <div class="role-card">
                        <h4>Academic Officer</h4>
                        <p>Academic Resources</p>
                        <ul>
                            <li>Upload materials</li>
                            <li>Manage seminars</li>
                            <li>Research distribution</li>
                            <li>Internship postings</li>
                        </ul>
                    </div>
                    <div class="role-card">
                        <h4>Media & Publicity</h4>
                        <p>Information Dissemination</p>
                        <ul>
                            <li>Photo & video upload</li>
                            <li>Social media updates</li>
                            <li>Event promotion</li>
                            <li>Branding management</li>
                        </ul>
                    </div>
                    <div class="role-card">
                        <h4>Election Committee</h4>
                        <p>Electoral Oversight</p>
                        <ul>
                            <li>Manage nominations</li>
                            <li>Verify candidates</li>
                            <li>Oversee voting</li>
                            <li>Archive results</li>
                        </ul>
                    </div>
                    <div class="role-card">
                        <h4>Committee Chairperson</h4>
                        <p>Committee Leadership</p>
                        <ul>
                            <li>Committee coordination</li>
                            <li>Meeting management</li>
                            <li>Project tracking</li>
                            <li>Performance reports</li>
                        </ul>
                    </div>
                    <div class="role-card">
                        <h4>Ordinary Member</h4>
                        <p>Active Participation</p>
                        <ul>
                            <li>View announcements</li>
                            <li>Register for events</li>
                            <li>Pay membership fees</li>
                            <li>Vote in elections</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- Call to Action -->
        <section class="section" style="text-align: center;">
            <h2 class="section-title">Ready to Transform Your Organization?</h2>
            <p style="font-size: 1.1rem; color: #666; margin-bottom: 2rem; max-width: 600px; margin-left: auto; margin-right: auto;">Join hundreds of pharmaceutical students using TAPSA SJUT to streamline operations, improve communication, and enhance academic excellence.</p>
            <button class="cta-button" id="contact">Access the Platform</button>
        </section>
    </div>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h5>Platform</h5>
                <ul>
                    <li><a href="#">Features</a></li>
                    <li><a href="#">Modules</a></li>
                    <li><a href="#">Pricing</a></li>
                    <li><a href="#">Documentation</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h5>Organization</h5>
                <ul>
                    <li><a href="#">About TAPSA</a></li>
                    <li><a href="#">Leadership</a></li>
                    <li><a href="#">Committees</a></li>
                    <li><a href="#">Constitution</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h5>Support</h5>
                <ul>
                    <li><a href="#">Help Center</a></li>
                    <li><a href="#">Contact Us</a></li>
                    <li><a href="#">Privacy Policy</a></li>
                    <li><a href="#">Terms & Conditions</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h5>SJUT</h5>
                <ul>
                    <li><a href="#">St. John's University</a></li>
                    <li><a href="#">Pharmacy Department</a></li>
                    <li><a href="#">Academic Calendar</a></li>
                    <li><a href="#">Resources</a></li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2024 TAPSA SJUT. All rights reserved. | Tanzania Pharmaceutical Students' Association - St. John's University of Tanzania</p>
        </div>
    </footer>

    <script>
        function switchModule(index, button) {
            // Hide all content
            document.querySelectorAll('.module-content').forEach(el => {
                el.classList.remove('active');
            });
            
            // Remove active class from all buttons
            document.querySelectorAll('.module-tab').forEach(btn => {
                btn.classList.remove('active');
            });
            
            // Show selected content and highlight button
            document.querySelectorAll('.module-content')[index].classList.add('active');
            button.classList.add('active');
        }
        
        // Smooth scroll for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });
    </script>
</body>
</html>
