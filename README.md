<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>John - Software Engineer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
            color: #fff;
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* Header Section */
        .header {
            text-align: center;
            padding: 60px 20px;
            position: relative;
            overflow: hidden;
        }
        
        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0) 70%);
            transform: rotate(30deg);
            z-index: -1;
            animation: shine 8s infinite linear;
        }
        
        @keyframes shine {
            0% { transform: rotate(30deg) translateX(-100%); }
            100% { transform: rotate(30deg) translateX(100%); }
        }
        
        .profile-img {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            object-fit: cover;
            border: 4px solid #fff;
            box-shadow: 0 0 30px rgba(0, 255, 255, 0.5);
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0px); }
        }
        
        h1 {
            font-size: 3.5rem;
            margin: 20px 0 10px;
            background: linear-gradient(45deg, #00ccff, #00ff99);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: glow 2s ease-in-out infinite alternate;
        }
        
        @keyframes glow {
            from { text-shadow: 0 0 10px #00ccff, 0 0 20px #00ccff; }
            to { text-shadow: 0 0 20px #00ff99, 0 0 30px #00ff99; }
        }
        
        h2 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: #cccccc;
        }
        
        .tagline {
            font-size: 1.2rem;
            max-width: 600px;
            margin: 0 auto 30px;
            color: #aaaaaa;
        }
        
        /* Stats Section */
        .stats-section {
            padding: 40px 0;
            text-align: center;
        }
        
        .section-title {
            font-size: 2.5rem;
            margin-bottom: 40px;
            position: relative;
            display: inline-block;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, #00ccff, #00ff99);
            border-radius: 2px;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            margin-bottom: 50px;
        }
        
        .stat-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            animation: fadeIn 1s ease-out;
        }
        
        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
        }
        
        .stat-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: #00ff99;
        }
        
        .stat-number {
            font-size: 2.8rem;
            font-weight: 700;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #00ccff, #00ff99);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .stat-label {
            font-size: 1.1rem;
            color: #cccccc;
        }
        
        /* Charts Section */
        .charts-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }
        
        .chart-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .chart-title {
            text-align: center;
            margin-bottom: 20px;
            font-size: 1.4rem;
            color: #00ff99;
        }
        
        /* Skills Section */
        .skills-section {
            padding: 60px 0;
        }
        
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
        }
        
        .skill-item {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            transition: transform 0.3s ease;
            animation: fadeIn 1s ease-out;
        }
        
        .skill-item:hover {
            transform: scale(1.05);
        }
        
        .skill-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: #00ccff;
        }
        
        .skill-name {
            font-size: 1.2rem;
            margin-bottom: 10px;
        }
        
        /* Footer */
        .footer {
            text-align: center;
            padding: 40px 0;
            margin-top: 40px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .social-link {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: linear-gradient(45deg, #00ccff, #00ff99);
            display: flex;
            align-items: center;
            justify-content: center;
            color: #000;
            font-size: 1.5rem;
            text-decoration: none;
            transition: transform 0.3s ease;
        }
        
        .social-link:hover {
            transform: scale(1.1) rotate(10deg);
        }
        
        .copyright {
            color: #aaaaaa;
            font-size: 1rem;
        }
        
        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            h2 {
                font-size: 1.5rem;
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
            }
            
            .charts-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80" alt="John" class="profile-img">
            <h1>John Doe</h1>
            <h2>Software Engineer</h2>
            <p class="tagline">Crafting clean, efficient code and building innovative solutions to complex problems</p>
        </header>
        
        
        <section class="stats-section">
            <h2 class="section-title">GitHub Statistics</h2>
            
            <div class="stats-grid">
                <div class="stat-card">
                    <i class="fas fa-code-branch stat-icon"></i>
                    <div class="stat-number" id="repos">127</div>
                    <div class="stat-label">Repositories</div>
                </div>
                
                <div class="stat-card">
                    <i class="fas fa-star stat-icon"></i>
                    <div class="stat-number" id="stars">548</div>
                    <div class="stat-label">Stars Earned</div>
                </div>
                
                <div class="stat-card">
                    <i class="fas fa-code-commit stat-icon"></i>
                    <div class="stat-number" id="commits">1,842</div>
                    <div class="stat-label">Commits</div>
                </div>
                
                <div class="stat-card">
                    <i classfas fa-users stat-icon"></i>
                    <div class="stat-number" id="followers">327</div>
                    <div class="stat-label">Followers</div>
                </div>
            </div>
            
            <div class="charts-container">
                <div class="chart-card">
                    <h3 class="chart-title">Language Distribution</h3>
                    <canvas id="languageChart"></canvas>
                </div>
                
                <div class="chart-card">
                    <h3 class="chart-title">Weekly Activity</h3>
                    <canvas id="activityChart"></canvas>
                </div>
            </div>
        </section>
        
        <!-- Skills Section -->
        <section class="skills-section">
            <h2 class="section-title">Technical Skills</h2>
            
            <div class="skills-grid">
                <div class="skill-item">
                    <i class="fab fa-js skill-icon"></i>
                    <h3 class="skill-name">JavaScript</h3>
                </div>
                
                <div class="skill-item">
                    <i class="fab fa-python skill-icon"></i>
                    <h3 class="skill-name">Python</h3>
                </div>
                
                <div class="skill-item">
                    <i class="fab fa-java skill-icon"></i>
                    <h3 class="skill-name">Java</h3>
                </div>
                
                <div class="skill-item">
                    <i class="fab fa-react skill-icon"></i>
                    <h3 class="skill-name">React</h3>
                </div>
                
                <div class="skill-item">
                    <i class="fas fa-database skill-icon"></i>
                    <h3 class="skill-name">SQL & NoSQL</h3>
                </div>
                
                <div class="skill-item">
                    <i class="fas fa-cloud skill-icon"></i>
                    <h3 class="skill-name">Cloud Services</h3>
                </div>
            </div>
        </section>
        
        <!-- Footer -->
        <footer class="footer">
            <div class="social-links">
                <a href="#" class="social-link"><i class="fab fa-github"></i></a>
                <a href="#" class="social-link"><i class="fab fa-linkedin-in"></i></a>
                <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                <a href="#" class="social-link"><i class="fas fa-envelope"></i></a>
            </div>
            <p class="copyright">© 2023 John Doe. All rights reserved.</p>
        </footer>
    </div>

    <script>
        // Animate statistic numbers
        function animateValue(id, start, end, duration) {
            const obj = document.getElementById(id);
            let startTimestamp = null;
            const step = (timestamp) => {
                if (!startTimestamp) startTimestamp = timestamp;
                const progress = Math.min((timestamp - startTimestamp) / duration, 1);
                obj.innerHTML = Math.floor(progress * (end - start) + start);
                if (progress < 1) {
                    window.requestAnimationFrame(step);
                }
            };
            window.requestAnimationFrame(step);
        }
        
        // Initialize after page load
        document.addEventListener('DOMContentLoaded', function() {
            // Animate stats
            animateValue("repos", 0, 127, 2000);
            animateValue("stars", 0, 548, 2000);
            animateValue("commits", 0, 1842, 2000);
            animateValue("followers", 0, 327, 2000);
            
            // Language chart
            const langCtx = document.getElementById('languageChart').getContext('2d');
            const languageChart = new Chart(langCtx, {
                type: 'doughnut',
                data: {
                    labels: ['JavaScript', 'Python', 'Java', 'TypeScript', 'HTML/CSS', 'Other'],
                    datasets: [{
                        data: [35, 25, 20, 10, 5, 5],
                        backgroundColor: [
                            '#f0db4f', '#306998', '#f89820', '#007acc', '#e44d26', '#888888'
                        ],
                        borderWidth: 0
                    }]
                },
                options: {
                    responsive: true,
                    plugins: {
                        legend: {
                            position: 'bottom',
                            labels: {
                                color: '#fff'
                            }
                        }
                    }
                }
            });
            
            // Activity chart
            const actCtx = document.getElementById('activityChart').getContext('2d');
            const activityChart = new Chart(actCtx, {
                type: 'bar',
                data: {
                    labels: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
                    datasets: [{
                        label: 'Commits',
                        data: [12, 19, 7, 15, 22, 5, 8],
                        backgroundColor: 'rgba(0, 255, 153, 0.7)',
                        borderColor: 'rgba(0, 255, 153, 1)',
                        borderWidth: 1
                    }]
                },
                options: {
                    responsive: true,
                    scales: {
                        y: {
                            beginAtZero: true,
                            ticks: {
                                color: '#ccc'
                            },
                            grid: {
                                color: 'rgba(255, 255, 255, 0.1)'
                            }
                        },
                        x: {
                            ticks: {
                                color: '#ccc'
                            },
                            grid: {
                                color: 'rgba(255, 255, 255, 0.1)'
                            }
                        }
                    },
                    plugins: {
                        legend: {
                            labels: {
                                color: '#fff'
                            }
                        }
                    }
                }
            });
        });
    </script>
</body>
</html>
