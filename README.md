# Emadyad.github.io
<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FBI Persian Roleplay - Academy</title>
    <!-- فونت‌های گوگل -->
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;700;900&display=swap" rel="stylesheet">
    <!-- آیکون‌ها -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --bg-dark: #0c0d10;
            --bg-card: #16181e;
            --bg-card-hover: #1f222a;
            --text-main: #ffffff;
            --text-muted: #8b8f9e;
            --accent-gold: #d4af37;
            --accent-blue: #3b82f6;
            --border-color: #2a2d36;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }
        body {
            font-family: 'Vazirmatn', sans-serif;
            background-color: var(--bg-dark);
            color: var(--text-main);
            display: flex;
            height: 100vh;
            overflow: hidden;
        }

        /* Sidebar */
        .sidebar {
            width: 260px;
            background-color: var(--bg-card);
            padding: 20px;
            border-left: 1px solid var(--border-color);
            display: flex;
            flex-direction: column;
            gap: 20px;
            overflow-y: auto;
        }
        .logo-area { display: flex; align-items: center; gap: 15px; padding-bottom: 20px; border-bottom: 1px solid var(--border-color); }
        .logo-icon { font-size: 40px; color: var(--text-main); }
        .logo-text h2 { font-size: 20px; font-weight: 900; letter-spacing: 1px; }
        .logo-text p { font-size: 12px; color: var(--text-muted); }
        
        .menu-title { font-size: 12px; color: var(--text-muted); text-transform: uppercase; margin-top: 10px; }
        .menu-item {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 12px 15px;
            border-radius: 8px;
            cursor: pointer;
            transition: 0.3s;
            color: var(--text-muted);
        }
        .menu-item:hover, .menu-item.active { background-color: var(--bg-card-hover); color: var(--text-main); }
        .menu-item.active { border-right: 3px solid var(--accent-gold); }

        /* Main Content */
        .main-content {
            flex: 1;
            padding: 20px 40px;
            overflow-y: auto;
        }

        /* Header */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding-bottom: 20px;
            border-bottom: 1px solid var(--border-color);
        }
        .nav-links { display: flex; gap: 25px; color: var(--text-muted); }
        .nav-links span { cursor: pointer; display: flex; align-items: center; gap: 8px; }
        .nav-links span:hover, .nav-links span.active { color: var(--text-main); }
        .user-profile { display: flex; align-items: center; gap: 10px; background: var(--bg-card); padding: 8px 15px; border-radius: 20px; }
        .user-avatar { width: 35px; height: 35px; border-radius: 50%; background: #333; }
        .user-info { text-align: right; }
        .user-info p { font-size: 14px; font-weight: bold; }
        .user-info small { color: var(--text-muted); font-size: 12px; }

        /* Hero Banner */
        .hero-banner {
            background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.8)), url('https://images.unsplash.com/photo-1531859798720-2c43e1e668db?q=80&w=2070&auto=format&fit=crop') center/cover;
            height: 280px;
            border-radius: 15px;
            margin-top: 25px;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            text-align: center;
            position: relative;
        }
        .hero-banner h1 { font-size: 60px; letter-spacing: 5px; color: #d1d1d1; text-shadow: 0 0 10px rgba(255,255,255,0.2); font-weight: 900; }
        .hero-banner h3 { font-size: 24px; color: var(--accent-gold); margin-top: -10px; }
        .hero-banner p { color: white; margin-top: 10px; font-weight: bold; }

        /* Dashboard Layout */
        .dashboard-grid {
            display: grid;
            grid-template-columns: 1fr 320px;
            gap: 25px;
            margin-top: 25px;
        }

        /* Courses */
        .section-title { display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px; }
        .section-title h3 { font-size: 18px; }
        .section-title span { color: var(--text-muted); font-size: 14px; cursor: pointer; }
        
        .courses-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 20px;
        }
        .course-card {
            background: var(--bg-card);
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid var(--border-color);
        }
        .course-img { height: 120px; background: #333; position: relative; }
        .course-img img { width: 100%; height: 100%; object-fit: cover; opacity: 0.7; }
        .course-info { padding: 15px; }
        .course-info h4 { font-size: 15px; margin-bottom: 5px; }
        .course-meta { display: flex; justify-content: space-between; font-size: 12px; color: var(--text-muted); }
        .progress-text { color: var(--accent-gold); }

        /* Right Sidebar */
        .right-sidebar { display: flex; flex-direction: column; gap: 20px; }
        .widget-box {
            background: var(--bg-card);
            padding: 20px;
            border-radius: 12px;
            border: 1px solid var(--border-color);
        }
        .widget-box h4 { font-size: 16px; margin-bottom: 15px; display: flex; align-items: center; gap: 10px; }
        
        /* Progress Circle */
        .progress-circle-container { text-align: center; padding: 10px 0; }
        .circle-chart { width: 80px; height: 80px; border-radius: 50%; border: 8px solid #2a2d36; border-top: 8px solid var(--accent-gold); display: flex; justify-content: center; align-items: center; margin: 0 auto; font-size: 20px; font-weight: bold; }
        .level-stats { display: flex; justify-content: space-between; margin-top: 10px; font-size: 14px; color: var(--text-muted); }

        /* Training Path */
        .path-container {
            background: var(--bg-card);
            padding: 20px;
            border-radius: 12px;
            margin-top: 25px;
            border: 1px solid var(--border-color);
            display: flex;
            justify-content: space-between;
            align-items: center;
            overflow-x: auto;
        }
        .path-step { text-align: center; min-width: 80px; position: relative; }
        .path-icon { width: 35px; height: 35px; background: #2a2d36; border-radius: 50%; display: flex; justify-content: center; align-items: center; margin: 0 auto 8px; border: 2px solid transparent; }
        .path-step.completed .path-icon { background: var(--accent-gold); border-color: var(--accent-gold); color: black; }
        .path-step.active .path-icon { border-color: var(--accent-gold); }
        .path-step p { font-size: 10px; color: var(--text-muted); }
        
        /* Announcements */
        .announcement-item { display: flex; gap: 15px; margin-bottom: 15px; border-bottom: 1px solid var(--border-color); padding-bottom: 10px; }
        .announcement-icon { background: #1e293b; width: 30px; height: 30px; border-radius: 50%; display: flex; justify-content: center; align-items: center; color: var(--accent-blue); }
        .announcement-text h5 { font-size: 14px; }
        .announcement-text p { font-size: 12px; color: var(--text-muted); margin-top: 3px; }
    </style>
</head>
<body>

    <!-- Sidebar -->
    <aside class="sidebar">
        <div class="logo-area">
            <i class="fas fa-shield-halved logo-icon"></i>
            <div class="logo-text">
                <h2>F.B.I</h2>
                <p>Persian Roleplay</p>
            </div>
        </div>

        <div class="menu-title">F.B.I Menu</div>
        <div class="menu-item"><i class="fas fa-th-large"></i> Overview</div>
        <div class="menu-item active"><i class="fas fa-book-open"></i> Training Courses</div>
        <div class="menu-item"><i class="fas fa-file-alt"></i> Practical Guide</div>
        <div class="menu-item"><i class="fas fa-folder-open"></i> Field Manuals</div>
        <div class="menu-item"><i class="fas fa-users"></i> Briefing Room</div>
        
        <div class="menu-title" style="margin-top: 20px;">Quick Access</div>
        <div class="menu-item"><i class="fas fa-calendar-check"></i> Daily Training</div>
        <div class="menu-item"><i class="fas fa-check-circle"></i> Exam Center</div>
    </aside>

    <!-- Main Content -->
    <main class="main-content">
        <!-- Header -->
        <header>
            <div class="nav-links">
                <span class="active"><i class="fas fa-chart-pie"></i> DASHBOARD</span>
                <span><i class="fas fa-graduation-cap"></i> TRAINING</span>
                <span><i class="fas fa-book"></i> HANDBOOK</span>
                <span><i class="fas fa-trophy"></i> EVALUATION</span>
                <span><i class="fas fa-users"></i> COMMUNITY</span>
            </div>
            <div class="user-profile">
                <div class="user-info">
                    <p>Agent_Baryad</p>
                    <small>Level 7</small>
                </div>
                <div class="user-avatar"></div>
            </div>
        </header>

        <!-- Hero Banner -->
        <div class="hero-banner">
            <h1>F.B.I</h1>
            <h3>TRAINING ACADEMY</h3>
            <p>PROFESSIONALISM - HONOR - TRUST</p>
        </div>

        <!-- Dashboard Grid -->
        <div class="dashboard-grid">
            <!-- Left Column -->
            <div class="left-col">
                <div class="section-title">
                    <h3><i class="fas fa-arrow-right" style="color:var(--accent-gold); margin-left: 10px;"></i> TRAINING COURSES</h3>
                    <span>VIEW ALL</span>
                </div>
                <div class="courses-grid">
                    <div class="course-card">
                        <div class="course-img"><img src="https://images.unsplash.com/photo-1581091226825-a6a2a5aee158?q=80&w=2070&auto=format&fit=crop" alt="Firearms"></div>
                        <div class="course-info">
                            <h4>FIREARMS TRAINING</h4>
                            <div class="course-meta"><span><i class="fas fa-layer-group"></i> Level 1</span> <span>6 Modules</span></div>
                            <div class="course-meta" style="margin-top:5px;"><span class="progress-text">75%</span></div>
                        </div>
                    </div>
                    <div class="course-card">
                        <div class="course-img"><img src="https://images.unsplash.com/photo-1563986768609-322da13575f3?q=80&w=2070&auto=format&fit=crop" alt="Surveillance"></div>
                        <div class="course-info">
                            <h4>SURVEILLANCE OPS</h4>
                            <div class="course-meta"><span><i class="fas fa-layer-group"></i> Level 2</span> <span>6 Modules</span></div>
                            <div class="course-meta" style="margin-top:5px;"><span class="progress-text">60%</span></div>
                        </div>
                    </div>
                </div>

                <!-- Training Path -->
                <div class="section-title" style="margin-top:20px;">
                    <h3><i class="fas fa-arrow-right" style="color:var(--accent-gold); margin-left: 10px;"></i> TRAINING PATH</h3>
                </div>
                <div class="path-container">
                    <div class="path-step completed">
                        <div class="path-icon"><i class="fas fa-check"></i></div>
                        <p>RECRUIT</p>
                    </div>
                    <div class="path-step completed">
                        <div class="path-icon"><i class="fas fa-check"></i></div>
                        <p>PROBATIONARY</p>
                    </div>
                    <div class="path-step active">
                        <div class="path-icon"><i class="fas fa-star"></i></div>
                        <p>SPECIAL AGENT</p>
                    </div>
                    <div class="path-step">
                        <div class="path-icon"><i class="fas fa-lock"></i></div>
                        <p>SENIOR AGENT</p>
                    </div>
                    <div class="path-step">
                        <div class="path-icon"><i class="fas fa-lock"></i></div>
                        <p>SUPERVISORY</p>
                    </div>
                </div>
            </div>

            <!-- Right Sidebar -->
            <div class="right-sidebar">
                <div class="widget-box">
                    <h4><i class="fas fa-chart-pie"></i> AGENT PROGRESS</h4>
                    <div class="progress-circle-container">
                        <div class="circle-chart">67%</div>
                        <div class="level-stats" style="margin-top:15px;">
                            <span>Current Level <br> <strong style="font-size: 24px; color:white;">7</strong></span>
                            <span>XP - 6,700 / 10,000</span>
                        </div>
                    </div>
                </div>

                <div class="widget-box">
                    <h4><i class="fas fa-calendar-alt"></i> UPCOMING TRAINING</h4>
                    <div style="display:flex; gap:10px; align-items:center; margin-bottom:15px;">
                        <div style="width:40px; height:40px; background:#333; border-radius:5px;"></div>
                        <div>
                            <p style="font-size:14px; font-weight:bold;">Tactical Driving</p>
                            <p style="font-size:12px; color:var(--text-muted);">In 2 days</p>
                        </div>
                    </div>
                    <div style="display:flex; gap:10px; align-items:center;">
                        <div style="width:40px; height:40px; background:#333; border-radius:5px;"></div>
                        <div>
                            <p style="font-size:14px; font-weight:bold;">Interrogation</p>
                            <p style="font-size:12px; color:var(--text-muted);">In 4 days</p>
                        </div>
                    </div>
                </div>

                <div class="widget-box">
                    <h4><i class="fas fa-bullhorn"></i> ANNOUNCEMENTS</h4>
                    <div class="announcement-item">
                        <div class="announcement-icon"><i class="fas fa-info"></i></div>
                        <div class="announcement-text">
                            <h5>به‌روزرسانی دوره‌ها</h5>
                            <p>دوره Advanced Tactics به آکادمی اضافه شد.</p>
                        </div>
                    </div>
                    <div class="announcement-item">
                        <div class="announcement-icon"><i class="fas fa-cog"></i></div>
                        <div class="announcement-text">
                            <h5>به‌روزرسانی سیستم</h5>
                            <p>سیستم ارزیابی و کوئست‌ها به‌روز شد.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</body>
</html>
