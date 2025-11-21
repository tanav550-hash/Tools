<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Comprehensive numerology calculator with detailed explanations. Calculate your Life Path, Destiny, Soul Urge, Personality, and Maturity numbers. Learn about numerology meanings and interpretations.">
    <meta name="keywords" content="numerology, life path number, destiny number, soul urge, personality number, birth date numerology, name numerology, numerology calculator">
    <meta name="author" content="Numerology Insights">
    <title>Advanced Numerology Calculator - Discover Your Complete Numerology Profile</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #6a5acd;
            --primary-dark: #5a4abc;
            --secondary-color: #9370db;
            --accent-color: #dda0dd;
            --text-color: #333;
            --light-text: #fff;
            --bg-color: #f9f9f9;
            --card-bg: #ffffff;
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --radius: 10px;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: var(--light-text);
            padding: 2rem 0;
            text-align: center;
            box-shadow: var(--shadow);
            position: relative;
            overflow: hidden;
        }

        header::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><path d="M0,0 L100,0 L100,100 Z" fill="rgba(255,255,255,0.1)"/></svg>');
            background-size: cover;
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            position: relative;
        }

        .subtitle {
            font-size: 1.2rem;
            opacity: 0.9;
            position: relative;
        }

        main {
            padding: 2rem 0;
        }

        .calculator-section {
            background-color: var(--card-bg);
            border-radius: var(--radius);
            padding: 2rem;
            box-shadow: var(--shadow);
            margin-bottom: 2rem;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        input, select {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            transition: border 0.3s;
        }

        input:focus, select:focus {
            border-color: var(--primary-color);
            outline: none;
        }

        button {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: var(--light-text);
            border: none;
            padding: 12px 24px;
            border-radius: 5px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            justify-content: center;
        }

        button i {
            margin-right: 8px;
        }

        button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
        }

        .button-secondary {
            background: linear-gradient(135deg, #6c757d, #868e96);
        }

        .results-section {
            display: none;
            background-color: var(--card-bg);
            border-radius: var(--radius);
            padding: 2rem;
            box-shadow: var(--shadow);
            margin-bottom: 2rem;
        }

        .results-section.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .results-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .number-cards {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .number-card {
            background: linear-gradient(135deg, var(--secondary-color), var(--accent-color));
            color: var(--light-text);
            border-radius: var(--radius);
            padding: 1.5rem;
            text-align: center;
            transition: transform 0.3s;
            position: relative;
            overflow: hidden;
        }

        .number-card:hover {
            transform: translateY(-5px);
        }

        .number-card::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: rgba(255, 255, 255, 0.5);
        }

        .number-value {
            font-size: 3rem;
            font-weight: 700;
            margin: 1rem 0;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        }

        .number-title {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
        }

        .number-description {
            font-size: 1rem;
            line-height: 1.5;
        }

        .detailed-results {
            background-color: #f8f9fa;
            border-radius: var(--radius);
            padding: 1.5rem;
            margin-top: 1.5rem;
        }

        .detailed-results h3 {
            color: var(--primary-color);
            margin-bottom: 1rem;
            border-bottom: 2px solid var(--accent-color);
            padding-bottom: 0.5rem;
        }

        .info-section {
            background-color: var(--card-bg);
            border-radius: var(--radius);
            padding: 2rem;
            box-shadow: var(--shadow);
            margin-bottom: 2rem;
        }

        .info-section h2 {
            color: var(--primary-color);
            margin-bottom: 1rem;
            border-bottom: 2px solid var(--accent-color);
            padding-bottom: 0.5rem;
        }

        .tab-container {
            margin-top: 1.5rem;
        }

        .tabs {
            display: flex;
            border-bottom: 1px solid #ddd;
            margin-bottom: 1.5rem;
            flex-wrap: wrap;
        }

        .tab {
            padding: 12px 20px;
            cursor: pointer;
            border-bottom: 3px solid transparent;
            transition: all 0.3s;
            font-weight: 600;
        }

        .tab.active {
            border-bottom: 3px solid var(--primary-color);
            color: var(--primary-color);
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        .number-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-top: 1.5rem;
        }

        .number-item {
            background-color: #f5f5f5;
            border-radius: 8px;
            padding: 1.5rem;
            border-left: 4px solid var(--primary-color);
            transition: transform 0.3s;
        }

        .number-item:hover {
            transform: translateY(-3px);
        }

        .number-item h3 {
            color: var(--primary-color);
            margin-bottom: 0.5rem;
            display: flex;
            align-items: center;
        }

        .number-item h3 span {
            background: var(--primary-color);
            color: white;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            margin-right: 10px;
            font-size: 0.9rem;
        }

        .ads-section {
            background-color: var(--card-bg);
            border-radius: var(--radius);
            padding: 2rem;
            box-shadow: var(--shadow);
            margin-bottom: 2rem;
            text-align: center;
        }

        .ad-placeholder {
            background-color: #f0f0f0;
            height: 250px;
            display: flex;
            align-items: center;
            justify-content: center;
            border: 2px dashed #ccc;
            border-radius: 5px;
            margin: 1rem 0;
        }

        footer {
            background-color: var(--primary-color);
            color: var(--light-text);
            text-align: center;
            padding: 1.5rem 0;
            margin-top: 2rem;
        }

        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 1rem;
        }

        .footer-links {
            display: flex;
            gap: 1.5rem;
            flex-wrap: wrap;
            justify-content: center;
        }

        .footer-links a {
            color: var(--light-text);
            text-decoration: none;
            transition: opacity 0.3s;
        }

        .footer-links a:hover {
            opacity: 0.8;
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2rem;
            }
            
            .number-grid, .number-cards {
                grid-template-columns: 1fr;
            }
            
            .calculator-section, .results-section, .info-section, .ads-section {
                padding: 1.5rem;
            }
            
            .results-header {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .tabs {
                flex-direction: column;
            }
            
            .tab {
                border-bottom: 1px solid #ddd;
                border-left: 3px solid transparent;
            }
            
            .tab.active {
                border-left: 3px solid var(--primary-color);
                border-bottom: 1px solid #ddd;
            }
        }

        @media (max-width: 480px) {
            h1 {
                font-size: 1.8rem;
            }
            
            .number-value {
                font-size: 2.5rem;
            }
            
            .calculator-section, .results-section, .info-section, .ads-section {
                padding: 1rem;
            }
        }

        .tooltip {
            position: relative;
            display: inline-block;
            border-bottom: 1px dotted var(--primary-color);
            cursor: help;
            margin-left: 5px;
        }

        .tooltip .tooltiptext {
            visibility: hidden;
            width: 200px;
            background-color: var(--primary-color);
            color: #fff;
            text-align: center;
            border-radius: 6px;
            padding: 10px;
            position: absolute;
            z-index: 1;
            bottom: 125%;
            left: 50%;
            margin-left: -100px;
            opacity: 0;
            transition: opacity 0.3s;
            font-size: 0.9rem;
            font-weight: normal;
        }

        .tooltip:hover .tooltiptext {
            visibility: visible;
            opacity: 1;
        }

        .calculation-steps {
            background: #f8f9fa;
            border-radius: 8px;
            padding: 1rem;
            margin-top: 1rem;
            font-size: 0.9rem;
        }

        .calculation-steps h4 {
            margin-bottom: 0.5rem;
            color: var(--primary-color);
        }

        .save-results {
            display: flex;
            gap: 1rem;
            margin-top: 1.5rem;
            flex-wrap: wrap;
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <h1><i class="fas fa-star-of-life"></i> Advanced Numerology Calculator</h1>
            <p class="subtitle">Discover your complete numerology profile with detailed interpretations</p>
        </div>
    </header>

    <main class="container">
        <section class="calculator-section">
            <h2>Calculate Your Numerology Numbers</h2>
            <p>Enter your full name (as per birth certificate) and birth date to discover your complete numerology profile.</p>
            
            <form id="numerology-form">
                <div class="form-group">
                    <label for="full-name">Full Name <span class="tooltip">?
                        <span class="tooltiptext">Enter your full birth name for accurate calculations</span>
                    </span></label>
                    <input type="text" id="full-name" placeholder="Enter your full name" required>
                </div>
                
                <div class="form-group">
                    <label for="birth-date">Birth Date</label>
                    <input type="date" id="birth-date" required>
                </div>
                
                <button type="submit"><i class="fas fa-calculator"></i> Calculate My Numbers</button>
            </form>
        </section>

        <section id="results" class="results-section">
            <div class="results-header">
                <h2>Your Numerology Profile</h2>
                <div>
                    <button id="calculate-again" class="button-secondary"><i class="fas fa-redo"></i> Calculate Again</button>
                </div>
            </div>
            
            <div class="number-cards">
                <div class="number-card">
                    <h3 class="number-title">Life Path Number</h3>
                    <div class="number-value" id="life-path-number">7</div>
                    <p class="number-description" id="life-path-description">Your Life Path Number reveals your life's purpose and the challenges you'll face.</p>
                </div>
                
                <div class="number-card">
                    <h3 class="number-title">Destiny Number</h3>
                    <div class="number-value" id="destiny-number">5</div>
                    <p class="number-description" id="destiny-description">Your Destiny Number indicates your natural talents and abilities.</p>
                </div>
                
                <div class="number-card">
                    <h3 class="number-title">Soul Urge Number</h3>
                    <div class="number-value" id="soul-urge-number">3</div>
                    <p class="number-description" id="soul-urge-description">Your Soul Urge Number reveals your inner desires and motivations.</p>
                </div>

                <div class="number-card">
                    <h3 class="number-title">Personality Number</h3>
                    <div class="number-value" id="personality-number">8</div>
                    <p class="number-description" id="personality-description">Your Personality Number shows how others perceive you.</p>
                </div>

                <div class="number-card">
                    <h3 class="number-title">Maturity Number</h3>
                    <div class="number-value" id="maturity-number">6</div>
                    <p class="number-description" id="maturity-description">Your Maturity Number reveals your developed self later in life.</p>
                </div>
            </div>

            <div class="detailed-results">
                <h3><i class="fas fa-info-circle"></i> Detailed Interpretation</h3>
                <div id="detailed-interpretation">
                    <p>Your complete numerology profile reveals a fascinating picture of your life's purpose, talents, and challenges. Based on your numbers, you have a unique combination of traits that shape your personality and destiny.</p>
                    
                    <div class="calculation-steps">
                        <h4>How your numbers were calculated:</h4>
                        <p><strong>Life Path Number:</strong> Derived from your birth date by reducing day, month, and year to single digits and summing them.</p>
                        <p><strong>Destiny Number:</strong> Calculated from your full birth name using the Pythagorean numerology system.</p>
                        <p><strong>Soul Urge Number:</strong> Based on the vowels in your name, representing your inner desires.</p>
                        <p><strong>Personality Number:</strong> Derived from the consonants in your name, showing how others see you.</p>
                        <p><strong>Maturity Number:</strong> The sum of your Life Path and Destiny numbers, revealing your developed self.</p>
                    </div>
                </div>
            </div>

            <div class="save-results">
                <button id="print-results"><i class="fas fa-print"></i> Print Results</button>
                <button id="save-pdf" class="button-secondary"><i class="fas fa-file-pdf"></i> Save as PDF</button>
            </div>
        </section>

        <section class="ads-section">
            <h2>Support Our Site</h2>
            <p>Please consider disabling your ad blocker to support our free numerology service.</p>
            <div class="ad-placeholder">
                <!-- AdSense Ad Unit -->
                <!-- Replace with your AdSense code -->
                <p>AdSense Ad Unit (320x250)</p>
            </div>
        </section>

        <section class="info-section">
            <h2><i class="fas fa-book-open"></i> Understanding Numerology</h2>
            <p>Numerology is an ancient metaphysical science that explores the mystical relationship between numbers and events in our lives. By calculating numbers from your name and birth date, numerology can reveal insights about your personality, life purpose, and future potential.</p>
            
            <div class="tab-container">
                <div class="tabs">
                    <div class="tab active" data-tab="numbers">Number Meanings</div>
                    <div class="tab" data-tab="history">History</div>
                    <div class="tab" data-tab="methods">Calculation Methods</div>
                    <div class="tab" data-tab="master">Master Numbers</div>
                </div>
                
                <div class="tab-content active" id="numbers-content">
                    <h3>What Each Number Means</h3>
                    <div class="number-grid">
                        <div class="number-item">
                            <h3><span>1</span> The Leader</h3>
                            <p><strong>Positive Traits:</strong> Independent, ambitious, determined, pioneering</p>
                            <p><strong>Challenges:</strong> Can be overly assertive, impatient, or domineering</p>
                            <p><strong>Life Purpose:</strong> To learn independence and lead others</p>
                        </div>
                        <div class="number-item">
                            <h3><span>2</span> The Diplomat</h3>
                            <p><strong>Positive Traits:</strong> Cooperative, sensitive, intuitive, peaceful</p>
                            <p><strong>Challenges:</strong> Can be overly sensitive, indecisive, or dependent</p>
                            <p><strong>Life Purpose:</strong> To create harmony and work in partnerships</p>
                        </div>
                        <div class="number-item">
                            <h3><span>3</span> The Communicator</h3>
                            <p><strong>Positive Traits:</strong> Creative, expressive, social, optimistic</p>
                            <p><strong>Challenges:</strong> Can be scattered, superficial, or dramatic</p>
                            <p><strong>Life Purpose:</strong> To inspire others through self-expression</p>
                        </div>
                        <div class="number-item">
                            <h3><span>4</span> The Builder</h3>
                            <p><strong>Positive Traits:</strong> Practical, disciplined, hardworking, reliable</p>
                            <p><strong>Challenges:</strong> Can be rigid, stubborn, or overly cautious</p>
                            <p><strong>Life Purpose:</strong> To create stability and structure</p>
                        </div>
                        <div class="number-item">
                            <h3><span>5</span> The Freedom Seeker</h3>
                            <p><strong>Positive Traits:</strong> Adventurous, versatile, progressive, curious</p>
                            <p><strong>Challenges:</strong> Can be restless, irresponsible, or inconsistent</p>
                            <p><strong>Life Purpose:</strong> To embrace change and experience life fully</p>
                        </div>
                        <div class="number-item">
                            <h3><span>6</span> The Nurturer</h3>
                            <p><strong>Positive Traits:</strong> Responsible, caring, compassionate, harmonious</p>
                            <p><strong>Challenges:</strong> Can be meddling, self-righteous, or worrisome</p>
                            <p><strong>Life Purpose:</strong> To create harmony and care for others</p>
                        </div>
                        <div class="number-item">
                            <h3><span>7</span> The Seeker</h3>
                            <p><strong>Positive Traits:</strong> Analytical, intuitive, spiritual, perceptive</p>
                            <p><strong>Challenges:</strong> Can be withdrawn, skeptical, or pessimistic</p>
                            <p><strong>Life Purpose:</strong> To seek truth and understand life's mysteries</p>
                        </div>
                        <div class="number-item">
                            <h3><span>8</span> The Powerhouse</h3>
                            <p><strong>Positive Traits:</strong> Ambitious, authoritative, efficient, organized</p>
                            <p><strong>Challenges:</strong> Can be materialistic, workaholic, or controlling</p>
                            <p><strong>Life Purpose:</strong> To master material power and achieve success</p>
                        </div>
                        <div class="number-item">
                            <h3><span>9</span> The Humanitarian</h3>
                            <p><strong>Positive Traits:</strong> Compassionate, generous, idealistic, artistic</p>
                            <p><strong>Challenges:</strong> Can be emotionally volatile, self-sacrificing, or scattered</p>
                            <p><strong>Life Purpose:</strong> To serve humanity and make the world better</p>
                        </div>
                    </div>
                </div>
                
                <div class="tab-content" id="history-content">
                    <h3>The History of Numerology</h3>
                    <p>Numerology is one of the oldest studies of numbers, dating back thousands of years. The ancient civilizations of Babylon, Egypt, Greece, and China all practiced some form of numerology.</p>
                    
                    <p><strong>Pythagoras</strong>, the Greek mathematician and philosopher (c. 570–495 BCE), is often credited with formalizing numerology in the Western world. He believed that the universe is built upon the power of numbers and that everything can be expressed in numerical terms.</p>
                    
                    <p>In the East, numerology has been an integral part of Chinese culture for millennia, particularly in practices like Feng Shui. The Chinese system assigns different meanings to numbers than the Western system.</p>
                    
                    <p>Modern numerology primarily uses the Pythagorean system, which assigns numbers 1-9 to the letters of the alphabet. This system was further developed in the early 20th century by L. Dow Balliett and Dr. Juno Jordan.</p>
                </div>
                
                <div class="tab-content" id="methods-content">
                    <h3>Numerology Calculation Methods</h3>
                    <p>There are several systems for calculating numerology numbers, but the most common is the Pythagorean system:</p>
                    
                    <div class="number-item">
                        <h4>Pythagorean Conversion Chart</h4>
                        <p>1: A, J, S</p>
                        <p>2: B, K, T</p>
                        <p>3: C, L, U</p>
                        <p>4: D, M, V</p>
                        <p>5: E, N, W</p>
                        <p>6: F, O, X</p>
                        <p>7: G, P, Y</p>
                        <p>8: H, Q, Z</p>
                        <p>9: I, R</p>
                    </div>
                    
                    <p><strong>Life Path Number:</strong> Calculated from your full birth date. Add the day, month, and year separately, reduce each to a single digit or master number, then add those together and reduce again if necessary.</p>
                    
                    <p><strong>Destiny Number:</strong> Calculated from your full birth name. Convert each letter to its corresponding number, add them together, and reduce to a single digit or master number.</p>
                    
                    <p><strong>Soul Urge Number:</strong> Uses only the vowels in your name to represent your inner desires and motivations.</p>
                    
                    <p><strong>Personality Number:</strong> Uses only the consonants in your name to show how others perceive you.</p>
                </div>
                
                <div class="tab-content" id="master-content">
                    <h3>Master Numbers</h3>
                    <p>In numerology, the numbers 11, 22, and 33 are considered Master Numbers and are not reduced to single digits. These numbers carry higher spiritual vibrations and greater potential, but also greater challenges.</p>
                    
                    <div class="number-item">
                        <h3><span>11</span> The Illuminator</h3>
                        <p><strong>Characteristics:</strong> Intuitive, inspirational, idealistic, visionary</p>
                        <p><strong>Challenges:</strong> Nervous energy, sensitivity to environments, high expectations</p>
                        <p><strong>Life Purpose:</strong> To inspire humanity and bring spiritual illumination</p>
                    </div>
                    
                    <div class="number-item">
                        <h3><span>22</span> The Master Builder</h3>
                        <p><strong>Characteristics:</strong> Practical visionary, ambitious, powerful, transformational</p>
                        <p><strong>Challenges:</strong> Can become dictatorial, overly ambitious, or manipulative</p>
                        <p><strong>Life Purpose:</strong> To turn dreams into reality on a large scale</p>
                    </div>
                    
                    <div class="number-item">
                        <h3><span>33</span> The Master Teacher</h3>
                        <p><strong>Characteristics:</strong> Compassionate, healing, inspirational, selfless</p>
                        <p><strong>Challenges:</strong> Can become a martyr, overly responsible, or codependent</p>
                        <p><strong>Life Purpose:</strong> To uplift and inspire humanity through love and compassion</p>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <div class="footer-content">
                <p>&copy; 2023 Advanced Numerology Calculator. All rights reserved.</p>
                <p>This tool is for entertainment and self-discovery purposes only.</p>
                <div class="footer-links">
                    <a href="#">Privacy Policy</a>
                    <a href="#">Terms of Service</a>
                    <a href="#">Contact Us</a>
                    <a href="#">About Numerology</a>
                </div>
            </div>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const form = document.getElementById('numerology-form');
            const resultsSection = document.getElementById('results');
            const calculateAgainBtn = document.getElementById('calculate-again');
            const printBtn = document.getElementById('print-results');
            const savePdfBtn = document.getElementById('save-pdf');
            const tabs = document.querySelectorAll('.tab');
            const tabContents = document.querySelectorAll('.tab-content');
            
            // Numerology number descriptions
            const numberDescriptions = {
                1: "You are a natural leader with strong individuality and determination. Your path involves learning independence and pioneering new directions. You have the potential to achieve great things through your initiative and originality.",
                2: "You are cooperative and diplomatic, with a natural ability to create harmony. Your path involves partnership and learning balance. Your sensitivity and intuition make you an excellent mediator and team player.",
                3: "You are creative and expressive, with a gift for communication. Your path involves self-expression and bringing joy to others. Your optimism and enthusiasm inspire those around you.",
                4: "You are practical and disciplined, with a strong sense of responsibility. Your path involves building solid foundations and creating stability. Your reliability and hard work ensure long-term success.",
                5: "You are adventurous and freedom-loving, with a versatile nature. Your path involves embracing change and experiencing life fully. Your adaptability and curiosity lead to diverse experiences.",
                6: "You are nurturing and responsible, with a strong sense of service. Your path involves creating harmony and caring for others. Your compassion and reliability make you a pillar of your community.",
                7: "You are analytical and spiritual, with a deep inner wisdom. Your path involves seeking truth and understanding life's mysteries. Your intuition and perceptiveness give you unique insights.",
                8: "You are ambitious and authoritative, with strong business sense. Your path involves mastering material power and achieving success. Your organizational skills and determination lead to accomplishment.",
                9: "You are compassionate and idealistic, with a global perspective. Your path involves humanitarian service and universal love. Your generosity and vision inspire positive change.",
                11: "You are an intuitive illuminator with high ideals and spiritual insight. Your path involves inspiring others and bringing spiritual awareness. Your sensitivity and vision can transform lives.",
                22: "You are a master builder with the ability to turn dreams into reality. Your path involves large-scale projects that benefit humanity. Your practical vision and ambition create lasting legacies.",
                33: "You are a master teacher with profound compassion and healing abilities. Your path involves uplifting humanity through selfless service. Your loving nature inspires others to their highest potential."
            };
            
            // Tab functionality
            tabs.forEach(tab => {
                tab.addEventListener('click', () => {
                    const tabId = tab.getAttribute('data-tab');
                    
                    // Remove active class from all tabs and contents
                    tabs.forEach(t => t.classList.remove('active'));
                    tabContents.forEach(c => c.classList.remove('active'));
                    
                    // Add active class to clicked tab and corresponding content
                    tab.classList.add('active');
                    document.getElementById(`${tabId}-content`).classList.add('active');
                });
            });
            
            // Calculate life path number from birth date
            function calculateLifePathNumber(birthDate) {
                const date = new Date(birthDate);
                const day = date.getDate();
                const month = date.getMonth() + 1; // Months are 0-indexed
                const year = date.getFullYear();
                
                // Reduce each component to a single digit or master number
                const dayReduced = reduceNumber(day);
                const monthReduced = reduceNumber(month);
                const yearReduced = reduceNumber(year);
                
                // Sum and reduce again
                const sum = dayReduced + monthReduced + yearReduced;
                return reduceNumber(sum);
            }
            
            // Calculate destiny number from name
            function calculateDestinyNumber(name) {
                // Pythagorean numerology chart
                const numerologyChart = {
                    'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5, 'f': 6, 'g': 7, 'h': 8, 'i': 9,
                    'j': 1, 'k': 2, 'l': 3, 'm': 4, 'n': 5, 'o': 6, 'p': 7, 'q': 8, 'r': 9,
                    's': 1, 't': 2, 'u': 3, 'v': 4, 'w': 5, 'x': 6, 'y': 7, 'z': 8
                };
                
                let sum = 0;
                
                // Remove spaces and convert to lowercase
                const cleanName = name.replace(/\s+/g, '').toLowerCase();
                
                // Calculate sum of all letters
                for (let i = 0; i < cleanName.length; i++) {
                    const char = cleanName[i];
                    if (numerologyChart[char]) {
                        sum += numerologyChart[char];
                    }
                }
                
                // Reduce to single digit or master number
                return reduceNumber(sum);
            }
            
            // Calculate soul urge number (vowels in name)
            function calculateSoulUrgeNumber(name) {
                const vowels = ['a', 'e', 'i', 'o', 'u'];
                const numerologyChart = {
                    'a': 1, 'e': 5, 'i': 9, 'o': 6, 'u': 3
                };
                
                let sum = 0;
                const cleanName = name.toLowerCase();
                
                // Calculate sum of vowels
                for (let i = 0; i < cleanName.length; i++) {
                    const char = cleanName[i];
                    if (vowels.includes(char) && numerologyChart[char]) {
                        sum += numerologyChart[char];
                    }
                }
                
                // Reduce to single digit or master number
                return reduceNumber(sum);
            }
            
            // Calculate personality number (consonants in name)
            function calculatePersonalityNumber(name) {
                const vowels = ['a', 'e', 'i', 'o', 'u'];
                const numerologyChart = {
                    'b': 2, 'c': 3, 'd': 4, 'f': 6, 'g': 7, 'h': 8, 'j': 1, 'k': 2, 'l': 3,
                    'm': 4, 'n': 5, 'p': 7, 'q': 8, 'r': 9, 's': 1, 't': 2, 'v': 4, 'w': 5,
                    'x': 6, 'y': 7, 'z': 8
                };
                
                let sum = 0;
                const cleanName = name.toLowerCase();
                
                // Calculate sum of consonants
                for (let i = 0; i < cleanName.length; i++) {
                    const char = cleanName[i];
                    if (!vowels.includes(char) && numerologyChart[char]) {
                        sum += numerologyChart[char];
                    }
                }
                
                // Reduce to single digit or master number
                return reduceNumber(sum);
            }
            
            // Calculate maturity number (life path + destiny)
            function calculateMaturityNumber(lifePath, destiny) {
                return reduceNumber(lifePath + destiny);
            }
            
            // Helper function to reduce numbers to single digit or master number
            function reduceNumber(num) {
                // If it's already a master number, return it
                if (num === 11 || num === 22 || num === 33) {
                    return num;
                }
                
                // Otherwise, reduce to single digit
                while (num > 9) {
                    let sum = 0;
                    const digits = num.toString().split('');
                    for (let digit of digits) {
                        sum += parseInt(digit);
                    }
                    num = sum;
                    
                    // Check if it became a master number during reduction
                    if (num === 11 || num === 22 || num === 33) {
                        return num;
                    }
                }
                return num;
            }
            
            // Form submission handler
            form.addEventListener('submit', function(e) {
                e.preventDefault();
                
                const fullName = document.getElementById('full-name').value;
                const birthDate = document.getElementById('birth-date').value;
                
                if (!fullName || !birthDate) {
                    alert('Please enter both your name and birth date.');
                    return;
                }
                
                // Calculate numbers
                const lifePathNumber = calculateLifePathNumber(birthDate);
                const destinyNumber = calculateDestinyNumber(fullName);
                const soulUrgeNumber = calculateSoulUrgeNumber(fullName);
                const personalityNumber = calculatePersonalityNumber(fullName);
                const maturityNumber = calculateMaturityNumber(lifePathNumber, destinyNumber);
                
                // Update results
                document.getElementById('life-path-number').textContent = lifePathNumber;
                document.getElementById('destiny-number').textContent = destinyNumber;
                document.getElementById('soul-urge-number').textContent = soulUrgeNumber;
                document.getElementById('personality-number').textContent = personalityNumber;
                document.getElementById('maturity-number').textContent = maturityNumber;
                
                document.getElementById('life-path-description').textContent = numberDescriptions[lifePathNumber] || "Your Life Path Number reveals your life's purpose and the challenges you'll face.";
                document.getElementById('destiny-description').textContent = numberDescriptions[destinyNumber] || "Your Destiny Number indicates your natural talents and abilities.";
                document.getElementById('soul-urge-description').textContent = numberDescriptions[soulUrgeNumber] || "Your Soul Urge Number reveals your inner desires and motivations.";
                document.getElementById('personality-description').textContent = numberDescriptions[personalityNumber] || "Your Personality Number shows how others perceive you.";
                document.getElementById('maturity-description').textContent = numberDescriptions[maturityNumber] || "Your Maturity Number reveals your developed self later in life.";
                
                // Update detailed interpretation
                const detailedElement = document.getElementById('detailed-interpretation');
                detailedElement.innerHTML = `
                    <p>Your complete numerology profile reveals a fascinating picture of your life's purpose, talents, and challenges. Based on your numbers, you have a unique combination of traits that shape your personality and destiny.</p>
                    <p><strong>Life Path ${lifePathNumber}:</strong> ${numberDescriptions[lifePathNumber]}</p>
                    <p><strong>Destiny ${destinyNumber}:</strong> ${numberDescriptions[destinyNumber]}</p>
                    <p><strong>Soul Urge ${soulUrgeNumber}:</strong> ${numberDescriptions[soulUrgeNumber]}</p>
                    <p><strong>Personality ${personalityNumber}:</strong> ${numberDescriptions[personalityNumber]}</p>
                    <p><strong>Maturity ${maturityNumber}:</strong> ${numberDescriptions[maturityNumber]}</p>
                    
                    <div class="calculation-steps">
                        <h4>How your numbers were calculated:</h4>
                        <p><strong>Life Path Number (${lifePathNumber}):</strong> Derived from your birth date (${birthDate}) by reducing day, month, and year to single digits and summing them.</p>
                        <p><strong>Destiny Number (${destinyNumber}):</strong> Calculated from your full birth name (${fullName}) using the Pythagorean numerology system.</p>
                        <p><strong>Soul Urge Number (${soulUrgeNumber}):</strong> Based on the vowels in your name, representing your inner desires.</p>
                        <p><strong>Personality Number (${personalityNumber}):</strong> Derived from the consonants in your name, showing how others see you.</p>
                        <p><strong>Maturity Number (${maturityNumber}):</strong> The sum of your Life Path (${lifePathNumber}) and Destiny (${destinyNumber}) numbers, revealing your developed self.</p>
                    </div>
                `;
                
                // Show results section
                resultsSection.classList.add('active');
                
                // Scroll to results
                resultsSection.scrollIntoView({ behavior: 'smooth' });
            });
            
            // Calculate again button
            calculateAgainBtn.addEventListener('click', function() {
                resultsSection.classList.remove('active');
                form.reset();
                document.getElementById('full-name').focus();
            });
            
            // Print results button
            printBtn.addEventListener('click', function() {
                window.print();
            });
            
            // Save as PDF button (placeholder functionality)
            savePdfBtn.addEventListener('click', function() {
                alert('PDF export functionality would be implemented with a library like jsPDF in a production environment.');
            });
        });
    </script>
</body>
</html>
