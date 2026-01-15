<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mohammad Rafiqul Islam - Textile Designer Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background: #f8f9fa;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 120px 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg width="100" height="100" xmlns="http://www.w3.org/2000/svg"><rect width="100" height="100" fill="none"/><path d="M0,0 L50,50 L0,100 L100,100 L50,50 L100,0 Z" fill="rgba(255,255,255,0.03)"/></svg>');
            opacity: 0.3;
        }
        
        .hero-content {
            position: relative;
            z-index: 1;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 10px;
            font-weight: 700;
            animation: fadeInUp 0.8s ease;
        }
        
        .hero .subtitle {
            font-size: 1.4rem;
            margin-bottom: 30px;
            opacity: 0.95;
            font-weight: 300;
            animation: fadeInUp 1s ease;
        }
        
        .hero-buttons {
            margin-top: 30px;
            animation: fadeInUp 1.2s ease;
        }
        
        .btn {
            display: inline-block;
            padding: 14px 35px;
            background: white;
            color: #667eea;
            text-decoration: none;
            border-radius: 30px;
            margin: 8px;
            font-weight: 600;
            font-size: 1rem;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.2);
        }
        
        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Section */
        .section {
            padding: 80px 20px;
        }
        
        .section-title {
            text-align: center;
            font-size: 2.8rem;
            margin-bottom: 15px;
            color: #2d3748;
            font-weight: 700;
        }
        
        .section-subtitle {
            text-align: center;
            font-size: 1.1rem;
            color: #718096;
            margin-bottom: 60px;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }
        
        /* About Section */
        .about {
            background: white;
        }
        
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
            margin-bottom: 50px;
        }
        
        .about-text p {
            margin-bottom: 20px;
            font-size: 1.1rem;
            line-height: 1.9;
            color: #4a5568;
        }
        
        .about-img {
            text-align: center;
        }
        
        .about-img img {
            max-width: 100%;
            border-radius: 15px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.15);
        }
        
        /* Stats Cards */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }
        
        .stat-card {
            background: #f7fafc;
            padding: 35px;
            border-radius: 15px;
            text-align: center;
            border: 2px solid #e2e8f0;
            transition: all 0.3s ease;
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
            border-color: #667eea;
            box-shadow: 0 10px 30px rgba(102,126,234,0.1);
        }
        
        .stat-card .icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
        }
        
        .stat-card h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: #2d3748;
        }
        
        .stat-card p {
            color: #718096;
            font-size: 0.95rem;
        }
        
        /* Portfolio Section */
        .portfolio {
            background: #f7fafc;
        }
        
        .filter-buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 50px;
            flex-wrap: wrap;
        }
        
        .filter-btn {
            padding: 12px 30px;
            background: white;
            border: 2px solid #e2e8f0;
            border-radius: 25px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            color: #4a5568;
            transition: all 0.3s ease;
        }
        
        .filter-btn:hover,
        .filter-btn.active {
            background: #667eea;
            color: white;
            border-color: #667eea;
            transform: translateY(-2px);
        }
        
        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 35px;
        }
        
        .portfolio-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            transition: all 0.4s ease;
            cursor: pointer;
        }
        
        .portfolio-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.15);
        }
        
        .portfolio-card img {
            width: 100%;
            height: 280px;
            object-fit: cover;
            transition: transform 0.4s ease;
        }
        
        .portfolio-card:hover img {
            transform: scale(1.05);
        }
        
        .portfolio-info {
            padding: 25px;
        }
        
        .portfolio-info h3 {
            font-size: 1.4rem;
            margin-bottom: 8px;
            color: #2d3748;
            font-weight: 600;
        }
        
        .portfolio-info p {
            color: #718096;
            font-size: 0.95rem;
            margin-bottom: 15px;
        }
        
        .category {
            display: inline-block;
            padding: 6px 16px;
            background: #edf2f7;
            color: #667eea;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
        }
        
        /* Contact Section */
        .contact {
            background: white;
        }
        
        .contact-wrapper {
            display: grid;
            grid-template-columns: 1fr 1.2fr;
            gap: 60px;
            align-items: start;
        }
        
        .contact-info {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 50px;
            border-radius: 20px;
        }
        
        .contact-info h3 {
            font-size: 2rem;
            margin-bottom: 30px;
        }
        
        .contact-item {
            margin-bottom: 30px;
            display: flex;
            align-items: start;
            gap: 15px;
        }
        
        .contact-item .icon {
            font-size: 1.5rem;
            margin-top: 5px;
        }
        
        .contact-item div h4 {
            font-size: 1.1rem;
            margin-bottom: 5px;
            font-weight: 600;
        }
        
        .contact-item div p {
            opacity: 0.9;
            font-size: 1rem;
        }
        
        .contact-form {
            background: #f7fafc;
            padding: 50px;
            border-radius: 20px;
        }
        
        .form-group {
            margin-bottom: 25px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #2d3748;
            font-size: 1rem;
        }
        
        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 14px 18px;
            border: 2px solid #e2e8f0;
            border-radius: 10px;
            font-size: 1rem;
            font-family: inherit;
            transition: all 0.3s ease;
        }
        
        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #667eea;
            box-shadow: 0 0 0 3px rgba(102,126,234,0.1);
        }
        
        .form-group textarea {
            resize: vertical;
            min-height: 150px;
        }
        
        .submit-btn {
            width: 100%;
            padding: 16px;
            background: #667eea;
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .submit-btn:hover {
            background: #5568d3;
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(102,126,234,0.3);
        }
        
        /* Footer */
        .footer {
            background: #2d3748;
            color: white;
            padding: 50px 20px 30px;
            text-align: center;
        }
        
        .social-links {
            margin: 30px 0;
            display: flex;
            justify-content: center;
            gap: 20px;
        }
        
        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            background: rgba(255,255,255,0.1);
            color: white;
            text-decoration: none;
            border-radius: 50%;
            font-size: 1.3rem;
            transition: all 0.3s ease;
        }
        
        .social-links a:hover {
            background: #667eea;
            transform: translateY(-5px);
        }
        
        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        /* Responsive */
        @media (max-width: 968px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .about-grid,
            .contact-wrapper {
                grid-template-columns: 1fr;
            }
            
            .portfolio-grid {
                grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            }
            
            .section-title {
                font-size: 2.2rem;
            }
        }
        
        @media (max-width: 640px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero .subtitle {
                font-size: 1.1rem;
            }
            
            .btn {
                padding: 12px 25px;
                font-size: 0.95rem;
            }
            
            .portfolio-grid {
                grid-template-columns: 1fr;
            }
            
            .filter-buttons {
                gap: 10px;
            }
            
            .filter-btn {
                padding: 10px 20px;
                font-size: 0.9rem;
            }
            
            .contact-form,
            .contact-info {
                padding: 30px;
            }
        }
    </style>
</head>
<body>
    <!-- Hero Section -->
    <div class="hero">
        <div class="hero-content">
            <h1>Mohammad Rafiqul Islam</h1>
            <p class="subtitle">Textile Designer | Traditional & Modern Designs</p>
            <div class="hero-buttons">
                <a href="#about" class="btn">আমার সম্পর্কে</a>
                <a href="#portfolio" class="btn">পোর্টফোলিও</a>
                <a href="#contact" class="btn">যোগাযোগ</a>
            </div>
        </div>
    </div>

    <!-- About Section -->
    <div class="about section" id="about">
        <div class="container">
            <h2 class="section-title">আমার সম্পর্কে</h2>
            <p class="section-subtitle">একজন অভিজ্ঞ টেক্সটাইল ডিজাইনার যিনি ঐতিহ্যবাহী বাংলাদেশী ডিজাইনের সাথে আধুনিক শিল্পকলার সমন্বয় করেন</p>
            
            <div class="about-grid">
                <div class="about-text">
                    <p>আমি মোহাম্মদ রফিকুল ইসলাম, একজন অভিজ্ঞ টেক্সটাইল ডিজাইনার। আমার বিশেষত্ব হলো ঐতিহ্যবাহী বাংলাদেশী ডিজাইনের সাথে আধুনিক শিল্পকলার সমন্বয়।</p>
                    <p>১০+ বছরের অভিজ্ঞতা নিয়ে আমি বিভিন্ন ধরনের টেক্সটাইল ডিজাইন তৈরি করেছি - Traditional Patterns, Modern Prints, Embroidery Designs এবং আরও অনেক কিছু।</p>
                    <p>আমার লক্ষ্য হলো প্রতিটি ডিজাইনে বাংলাদেশের সাংস্কৃতিক ঐতিহ্য এবং আধুনিক রুচির সুন্দর মিশ্রণ তৈরি করা।</p>
                </div>
                <div class="about-img">
                    <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=500&h=600&fit=crop" alt="Textile Designer">
                </div>
            </div>

            <div class="stats-grid">
                <div class="stat-card">
                    <div class="icon">🎓</div>
                    <h3>Experience</h3>
                    <p>১০+ বছরের পেশাগত অভিজ্ঞতা</p>
                </div>
                <div class="stat-card">
                    <div class="icon">📚</div>
                    <h3>Education</h3>
                    <p>Textile Design এ স্নাতক</p>
                </div>
                <div class="stat-card">
                    <div class="icon">🏆</div>
                    <h3>Achievements</h3>
                    <p>জাতীয় এবং আন্তর্জাতিক পুরস্কার</p>
                </div>
            </div>
        </div>
    </div>

    <!-- Portfolio Section -->
    <div class="portfolio section" id="portfolio">
        <div class="container">
            <h2 class="section-title">Portfolio</h2>
            <p class="section-subtitle">আমার সেরা কাজের সংগ্রহ - ঐতিহ্যবাহী থেকে আধুনিক ডিজাইন</p>
            
            <div class="filter-buttons">
                <button class="filter-btn active" data-filter="all">All</button>
                <button class="filter-btn" data-filter="traditional">Traditional</button>
                <button class="filter-btn" data-filter="modern">Modern</button>
                <button class="filter-btn" data-filter="prints">Prints</button>
                <button class="filter-btn" data-filter="embroidery">Embroidery</button>
            </div>

            <div class="portfolio-grid">
                <div class="portfolio-card" data-category="traditional">
                    <img src="https://images.unsplash.com/photo-1509987750768-c61042f1bab6?w=400&h=300&fit=crop" alt="Traditional Jamdani">
                    <div class="portfolio-info">
                        <h3>Traditional Jamdani Textile</h3>
                        <p>ঐতিহ্যবাহী জামদানি নকশা</p>
                        <span class="category">Traditional</span>
                    </div>
                </div>

                <div class="portfolio-card" data-category="modern">
                    <img src="https://images.unsplash.com/photo-1558769132-cb1aea3c8565?w=400&h=300&fit=crop" alt="Modern Print">
                    <div class="portfolio-info">
                        <h3>Vibrant Folk Abstract</h3>
                        <p>আধুনিক জ্যামিতিক প্রিন্ট</p>
                        <span class="category">Modern</span>
                    </div>
                </div>

                <div class="portfolio-card" data-category="embroidery">
                    <img src="https://images.unsplash.com/photo-1539109136881-3be0616acf4b?w=400&h=300&fit=crop" alt="Embroidery">
                    <div class="portfolio-info">
                        <h3>Kantha Embroidery</h3>
                        <p>কাঁথা সূচিকর্ম ডিজাইন</p>
                        <span class="category">Embroidery</span>
                    </div>
                </div>

                <div class="portfolio-card" data-category="prints">
                    <img src="https://images.unsplash.com/photo-1617078827511-e8c36f7c6a4b?w=400&h=300&fit=crop" alt="Batik">
                    <div class="portfolio-info">
                        <h3>Batik Print Collection</h3>
                        <p>ব্যাটিক প্রিন্ট কালেকশন</p>
                        <span class="category">Prints</span>
                    </div>
                </div>

                <div class="portfolio-card" data-category="traditional">
                    <img src="https://images.unsplash.com/photo-1610701596007-11502861dcfa?w=400&h=300&fit=crop" alt="Block Print">
                    <div class="portfolio-info">
                        <h3>Hand Block Print</h3>
                        <p>হাতে ব্লক প্রিন্ট</p>
                        <span class="category">Traditional</span>
                    </div>
                </div>

                <div class="portfolio-card" data-category="modern">
                    <img src="https://images.unsplash.com/photo-1515886657613-9f3515b0c78f?w=400&h=300&fit=crop" alt="Contemporary">
                    <div class="portfolio-info">
                        <h3>Contemporary Fusion</h3>
                        <p>সমসাময়িক ফিউশন ডিজাইন</p>
                        <span class="category">Modern</span>
                    </div>
                </div>

                <div class="portfolio-card" data-category="embroidery">
                    <img src="https://images.unsplash.com/photo-1590736969955-71cc94901144?w=400&h=300&fit=crop" alt="Embroidery Work">
                    <div class="portfolio-info">
                        <h3>Intricate Embroidery</h3>
                        <p>জটিল সূচিকর্ম কাজ</p>
                        <span class="category">Embroidery</span>
                    </div>
                </div>

                <div class="portfolio-card" data-category="prints">
                    <img src="https://images.unsplash.com/photo-1601924994987-69e26d50dc26?w=400&h=300&fit=crop" alt="Silk Texture">
                    <div class="portfolio-info">
                        <h3>Luxury Silk Texture</h3>
                        <p>বিলাসবহুল সিল্ক টেক্সচার</p>
                        <span class="category">Prints</span>
                    </div>
                </div>

                <div class="portfolio-card" data-category="traditional">
                    <img src="https://images.unsplash.com/photo-1582730147172-b9ca530a43b5?w=400&h=300&fit=crop" alt="Organic Cotton">
                    <div class="portfolio-info">
                        <h3>Organic Cotton Weave</h3>
                        <p>জৈব তুলা বুনন</p>
                        <span class="category">Traditional</span>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Contact Section -->
    <div class="contact section" id="contact">
        <div class="container">
            <h2 class="section-title">Get In Touch</h2>
            <p class="section-subtitle">যোগাযোগ করুন এবং আপনার প্রজেক্ট সম্পর্কে আলোচনা করুন</p>
            
            <div class="contact-wrapper">
                <div class="contact-info">
                    <h3>Contact Information</h3>
                    
                    <div class="contact-item">
                        <div class="icon">📧</div>
                        <div>
                            <h4>Email</h4>
                            <p>rafiqul.textile@gmail.com</p>
                        </div>
                    </div>

                    <div class="contact-item">
                        <div class="icon">📱</div>
                        <div>
                            <h4>Phone</h4>
                            <p>+880 1XXX-XXXXXX</p>
                        </div>
                    </div>

                    <div class="contact-item">
                        <div class="icon">📍</div>
                        <div>
                            <h4>Business Address</h4>
                            <p>Dhaka, Bangladesh<br>Tejgaon, Dhaka - 1208</p>
                        </div>
                    </div>
                </div>

                <div class="contact-form">
                    <form>
                        <div class="form-group">
                            <label for="name">Name</label>
                            <input type="text" id="name" placeholder="আপনার নাম লিখুন" required>
                        </div>

                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" placeholder="আপনার ইমেইল লিখুন" required>
                        </div>

                        <div class="form-group">
                            <label for="message">Message</label>
                            <textarea id="message" placeholder="আপনার বার্তা লিখুন" required></textarea>
                        </div>

                        <button type="submit" class="submit-btn">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <div class="footer">
        <div class="container">
            <p>&copy; 2025 Mohammad Rafiqul Islam - Textile Designer</p>
            <div class="social-links">
                <a href="#" title="Facebook">f</a>
                <a href="#" title="Instagram">📷</a>
                <a href="#" title="LinkedIn">in</a>
                <a href="#" title="WhatsApp">💬</a>
            </div>
            <p style="margin-top:20px; opacity:0.8;">Made with ❤️ by Md. Nur Islam</p>
        </div>
    </div>

    <script>
        // Smooth Scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Portfolio Filter
        const filterButtons = document.querySelectorAll('.filter-btn');
        const portfolioCards = document.querySelectorAll('.portfolio-card');

        filterButtons.forEach(button => {
            button.addEventListener('click', () => {
                // Remove active class from all buttons
                filterButtons.forEach(btn => btn.classList.remove('active'));
                // Add active class to clicked button
                button.classList.add('active');

                const filterValue = button.getAttribute('data-filter');

                portfolioCards.forEach(card => {
                    if (filterValue === 'all') {
                        card.style.display = 'block';
                        setTimeout(() => {
                            card.style.opacity = '1';
                            card.style.transform = 'scale(1)';
                        }, 10);
                    } else {
                        if (card.getAttribute('data-category') === filterValue) {
                            card.style.display = 'block';
                            setTimeout(() => {
                                card.style.opacity = '1';
                                card.style.transform = 'scale(1)';
                            }, 10);
                        } else {
                            card.style.opacity = '0';
                            card.style.transform = 'scale(0.8)';
                            setTimeout(() => {
                                card.style.display = 'none';
                            }, 300);
                        }
                    }
                });
            });
        });

        // Form Submission
        document.querySelector('.contact-form form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('ধন্যবাদ! আপনার বার্তা পাঠানো হয়েছে। শীঘ্রই আমি আপনার সাথে যোগাযোগ করব।');
            this.reset();
        });
    </script>
</body>
</html>
