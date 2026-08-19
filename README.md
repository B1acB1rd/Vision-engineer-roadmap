<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Autonomous Vision Engineer — Project-First Roadmap</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:ital,wght@0,300;0,400;0,500;1,300&family=Bebas+Neue&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #06070f;
  --bg2: #0c0e1a;
  --bg3: #111425;
  --border: #1e2235;
  --text: #c2c8e0;
  --muted: #5a6080;
  --s1: #00d4ff;
  --s2: #39ff14;
  --s3: #ff6b35;
  --s4: #b44fff;
  --s5: #ff3cac;
  --s6: #ffd700;
  --white: #f0f2ff;
}
* { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body { background: var(--bg); color: var(--text); font-family: 'DM Sans', sans-serif; font-size: 14px; line-height: 1.6; }

.hero {
  position: relative; padding: 72px 60px 52px; overflow: hidden; border-bottom: 1px solid var(--border);
}
.hero-grid {
  position: absolute; inset: 0;
  background-image: linear-gradient(rgba(0,212,255,0.03) 1px, transparent 1px), linear-gradient(90deg, rgba(0,212,255,0.03) 1px, transparent 1px);
  background-size: 40px 40px;
}
.hero-glow { position: absolute; inset: 0; background: radial-gradient(ellipse at 15% 50%, rgba(0,212,255,0.06) 0%, transparent 50%), radial-gradient(ellipse at 85% 20%, rgba(180,79,255,0.05) 0%, transparent 50%); }
.hero-content { position: relative; max-width: 900px; }
.hero-label { font-family: 'DM Mono', monospace; font-size: 10px; letter-spacing: 6px; color: var(--s1); opacity: 0.7; margin-bottom: 16px; text-transform: uppercase; }
.hero-title { font-family: 'Bebas Neue', sans-serif; font-size: clamp(48px, 8vw, 92px); color: var(--white); line-height: 0.9; letter-spacing: 2px; margin-bottom: 8px; }
.hero-title span { color: var(--s1); }
.hero-sub { font-family: 'DM Mono', monospace; font-size: 12px; color: var(--muted); letter-spacing: 3px; margin-bottom: 12px; }
.hero-note { font-size: 13px; color: #6878a8; max-width: 620px; line-height: 1.7; margin-bottom: 28px; }
.hero-stats { display: flex; gap: 40px; flex-wrap: wrap; }
.stat { display: flex; flex-direction: column; gap: 4px; }
.stat-num { font-family: 'Bebas Neue', sans-serif; font-size: 32px; color: var(--white); line-height: 1; }
.stat-label { font-family: 'DM Mono', monospace; font-size: 9px; letter-spacing: 3px; color: var(--muted); text-transform: uppercase; }

.stage-nav {
  position: sticky; top: 0; z-index: 100;
  background: rgba(6,7,15,0.96); backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--border); padding: 0 60px;
  display: flex; overflow-x: auto;
}
.stage-nav::-webkit-scrollbar { display: none; }
.nav-btn {
  background: none; border: none; border-bottom: 2px solid transparent;
  padding: 16px 18px; cursor: pointer;
  font-family: 'DM Mono', monospace; font-size: 9px; letter-spacing: 3px;
  color: var(--muted); text-transform: uppercase; white-space: nowrap; transition: all 0.2s;
}
.nav-btn:hover { color: var(--white); }

.main { padding: 0 60px 80px; max-width: 1100px; }

.stage { padding: 56px 0; border-bottom: 1px solid var(--border); }
.stage:last-child { border-bottom: none; }

.stage-header { display: grid; grid-template-columns: auto 1fr; gap: 24px; align-items: start; margin-bottom: 12px; }
.stage-number { font-family: 'Bebas Neue', sans-serif; font-size: 80px; line-height: 0.85; opacity: 0.1; color: var(--white); user-select: none; }
.stage-tag { display: inline-block; font-family: 'DM Mono', monospace; font-size: 8px; letter-spacing: 4px; padding: 3px 10px; border-radius: 2px; margin-bottom: 8px; text-transform: uppercase; }
.stage-name { font-family: 'Bebas Neue', sans-serif; font-size: 40px; line-height: 1; margin-bottom: 4px; }
.stage-subtitle { font-family: 'DM Mono', monospace; font-size: 11px; color: var(--muted); letter-spacing: 2px; margin-bottom: 6px; }
.stage-duration { font-family: 'DM Mono', monospace; font-size: 10px; color: var(--muted); opacity: 0.5; }
.stage-desc { font-size: 13px; line-height: 1.8; color: #7888a8; max-width: 740px; margin: 16px 0 32px 104px; }

/* PROJECTS — PRIMARY */
.projects-section { margin-left: 104px; margin-bottom: 32px; }
.projects-label { font-family: 'DM Mono', monospace; font-size: 9px; letter-spacing: 5px; text-transform: uppercase; color: var(--muted); margin-bottom: 16px; padding-bottom: 8px; border-bottom: 1px solid var(--border); }

.project-card {
  border: 1px solid var(--border); border-radius: 6px; margin-bottom: 16px;
  background: var(--bg2); overflow: hidden;
}
.project-card-header {
  padding: 18px 20px 14px; border-bottom: 1px solid var(--border);
  display: flex; justify-content: space-between; align-items: flex-start; gap: 12px;
}
.project-num { font-family: 'Bebas Neue', sans-serif; font-size: 36px; line-height: 1; opacity: 0.15; color: var(--white); margin-right: 4px; }
.project-title-block { flex: 1; }
.project-name { font-size: 15px; font-weight: 600; color: var(--white); margin-bottom: 3px; }
.project-tagline { font-size: 12px; color: var(--muted); font-style: italic; }
.project-badges { display: flex; gap: 6px; flex-wrap: wrap; align-items: flex-start; }
.badge { font-family: 'DM Mono', monospace; font-size: 8px; letter-spacing: 2px; padding: 3px 8px; border-radius: 2px; white-space: nowrap; }
.badge-core { background: rgba(57,255,20,0.1); color: #39ff14; border: 1px solid rgba(57,255,20,0.25); }
.badge-stretch { background: rgba(255,107,53,0.1); color: #ff6b35; border: 1px solid rgba(255,107,53,0.25); }
.badge-phone { background: rgba(0,212,255,0.08); color: var(--s1); border: 1px solid rgba(0,212,255,0.2); }
.badge-laptop { background: rgba(180,79,255,0.08); color: var(--s4); border: 1px solid rgba(180,79,255,0.2); }
.badge-sim { background: rgba(255,215,0,0.08); color: var(--s6); border: 1px solid rgba(255,215,0,0.2); }
.badge-kaggle { background: rgba(255,60,172,0.08); color: var(--s5); border: 1px solid rgba(255,60,172,0.2); }

.project-body { padding: 18px 20px; }
.project-goal { font-size: 13px; color: var(--text); line-height: 1.7; margin-bottom: 14px; }
.project-steps { margin-bottom: 14px; }
.project-steps-label { font-family: 'DM Mono', monospace; font-size: 9px; letter-spacing: 3px; color: var(--muted); text-transform: uppercase; margin-bottom: 8px; }
.step { display: flex; gap: 10px; padding: 7px 0; border-bottom: 1px solid rgba(255,255,255,0.04); font-size: 12px; color: #8898b8; line-height: 1.6; align-items: flex-start; }
.step:last-child { border-bottom: none; }
.step-n { font-family: 'DM Mono', monospace; font-size: 10px; min-width: 20px; opacity: 0.4; margin-top: 1px; }
.project-learn { font-family: 'DM Mono', monospace; font-size: 10px; color: var(--muted); margin-bottom: 10px; }
.project-learn span { color: var(--text); }
.project-tools { display: flex; flex-wrap: wrap; gap: 6px; }
.tool-chip { font-family: 'DM Mono', monospace; font-size: 9px; padding: 3px 10px; background: var(--bg); border: 1px solid var(--border); border-radius: 2px; color: #7888a8; }

/* MATH REFERENCE — COMPACT */
.math-ref { margin-left: 104px; margin-bottom: 24px; }
.math-ref-toggle {
  width: 100%; background: var(--bg2); border: 1px solid var(--border); border-radius: 4px;
  padding: 12px 16px; cursor: pointer; display: flex; justify-content: space-between; align-items: center;
  font-family: 'DM Mono', monospace; font-size: 9px; letter-spacing: 3px; color: var(--muted); text-transform: uppercase;
}
.math-ref-toggle:hover { border-color: #2e3245; color: var(--white); }
.math-ref-body { display: none; border: 1px solid var(--border); border-top: none; border-radius: 0 0 4px 4px; background: var(--bg2); padding: 16px; }
.math-ref-body.open { display: block; }
.math-row { display: grid; grid-template-columns: 180px 1fr; gap: 12px; padding: 9px 0; border-bottom: 1px solid rgba(255,255,255,0.04); font-size: 12px; align-items: start; }
.math-row:last-child { border-bottom: none; padding-bottom: 0; }
.math-topic { font-weight: 600; color: var(--white); }
.math-why { color: var(--muted); line-height: 1.5; }
.math-src { font-family: 'DM Mono', monospace; font-size: 9px; color: var(--muted); opacity: 0.6; margin-top: 2px; }

/* BOOKS & PAPERS — COMPACT */
.refs-grid { margin-left: 104px; display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-bottom: 24px; }
.refs-grid.full { grid-template-columns: 1fr; }
.ref-block { background: var(--bg2); border: 1px solid var(--border); border-radius: 4px; overflow: hidden; }
.ref-head { padding: 10px 16px; border-bottom: 1px solid var(--border); font-family: 'DM Mono', monospace; font-size: 9px; letter-spacing: 3px; color: var(--muted); text-transform: uppercase; }
.ref-body { padding: 12px 16px; }
.ref-item { padding: 8px 0; border-bottom: 1px solid rgba(255,255,255,0.04); }
.ref-item:last-child { border-bottom: none; padding-bottom: 0; }
.ref-title { font-size: 12px; color: var(--white); margin-bottom: 2px; line-height: 1.4; }
.ref-sub { font-family: 'DM Mono', monospace; font-size: 10px; color: var(--muted); }

/* EXIT EXAM */
.exit-block { margin-left: 104px; padding: 16px 20px; border-radius: 4px; border-left: 3px solid; margin-bottom: 8px; }
.exit-label { font-family: 'DM Mono', monospace; font-size: 8px; letter-spacing: 4px; text-transform: uppercase; margin-bottom: 6px; }
.exit-text { font-size: 12px; line-height: 1.8; color: #7888a8; }

/* CAPSTONE */
.capstone { margin-left: 104px; margin-top: 32px; padding: 28px; border-radius: 6px; border: 1px solid rgba(255,215,0,0.2); background: linear-gradient(135deg, rgba(255,215,0,0.04) 0%, transparent 100%); }
.capstone-label { font-family: 'DM Mono', monospace; font-size: 8px; letter-spacing: 5px; color: var(--s6); margin-bottom: 10px; text-transform: uppercase; }
.capstone-title { font-family: 'Bebas Neue', sans-serif; font-size: 26px; color: var(--white); margin-bottom: 10px; }
.capstone-desc { font-size: 13px; color: #7888a8; line-height: 1.8; margin-bottom: 16px; }
.capstone-req { display: flex; gap: 10px; padding: 7px 0; border-bottom: 1px solid rgba(255,215,0,0.08); font-size: 12px; color: var(--text); }
.capstone-req:last-child { border-bottom: none; }
.req-bullet { color: var(--s6); }

/* COLOR UTILS */
.s1-color{color:var(--s1)} .s2-color{color:var(--s2)} .s3-color{color:var(--s3)} .s4-color{color:var(--s4)} .s5-color{color:var(--s5)} .s6-color{color:var(--s6)}
.s1-tag{background:rgba(0,212,255,0.1);color:var(--s1);border:1px solid rgba(0,212,255,0.3)}
.s2-tag{background:rgba(57,255,20,0.1);color:var(--s2);border:1px solid rgba(57,255,20,0.3)}
.s3-tag{background:rgba(255,107,53,0.1);color:var(--s3);border:1px solid rgba(255,107,53,0.3)}
.s4-tag{background:rgba(180,79,255,0.1);color:var(--s4);border:1px solid rgba(180,79,255,0.3)}
.s5-tag{background:rgba(255,60,172,0.1);color:var(--s5);border:1px solid rgba(255,60,172,0.3)}
.s6-tag{background:rgba(255,215,0,0.1);color:var(--s6);border:1px solid rgba(255,215,0,0.3)}
.s1-exit{background:rgba(0,212,255,0.06);border-left-color:var(--s1)}
.s2-exit{background:rgba(57,255,20,0.06);border-left-color:var(--s2)}
.s3-exit{background:rgba(255,107,53,0.06);border-left-color:var(--s3)}
.s4-exit{background:rgba(180,79,255,0.06);border-left-color:var(--s4)}
.s5-exit{background:rgba(255,60,172,0.06);border-left-color:var(--s5)}

@media(max-width:768px){
  .hero{padding:40px 20px 32px}
  .stage-nav{padding:0 20px}
  .main{padding:0 20px 60px}
  .stage-desc,.projects-section,.math-ref,.refs-grid,.exit-block,.capstone{margin-left:0}
  .refs-grid{grid-template-columns:1fr}
  .stage-number{font-size:48px}
  .math-row{grid-template-columns:1fr}
}
</style>
</head>
<body>

<div class="hero">
  <div class="hero-grid"></div>
  <div class="hero-glow"></div>
  <div class="hero-content">
    <div class="hero-label">Autonomous Vision Engineer // Project-First Roadmap v2</div>
    <div class="hero-title">BUILD YOUR WAY<br>TO <span>AUTONOMOUS</span><br>VISION</div>
    <div class="hero-sub">Phone + Laptop · No GPU Required Until Stage 4</div>
    <div class="hero-note">Every project in this roadmap runs on your laptop and phone. Math is here as a reference — you read it when a project breaks and you need to understand why. Not before.</div>
    <div class="hero-stats">
      <div class="stat"><div class="stat-num">6</div><div class="stat-label">Stages</div></div>
      <div class="stat"><div class="stat-num">28</div><div class="stat-label">Projects</div></div>
      <div class="stat"><div class="stat-num">📱+💻</div><div class="stat-label">Your Hardware</div></div>
      <div class="stat"><div class="stat-num">0</div><div class="stat-label">GPU Needed Early</div></div>
    </div>
  </div>
</div>

<div class="stage-nav" id="stageNav">
  <button class="nav-btn active" onclick="nav('s1',this)" style="color:var(--s1);border-bottom-color:var(--s1)">Stage 1 — See</button>
  <button class="nav-btn" onclick="nav('s2',this)">Stage 2 — Perceive</button>
  <button class="nav-btn" onclick="nav('s3',this)">Stage 3 — Locate</button>
  <button class="nav-btn" onclick="nav('s4',this)">Stage 4 — Map</button>
  <button class="nav-btn" onclick="nav('s5',this)">Stage 5 — Plan</button>
  <button class="nav-btn" onclick="nav('s6',this)">Stage 6 — Full System</button>
</div>

<div class="main">

<!-- ===== STAGE 1 ===== -->
<div class="stage" id="s1">
  <div class="stage-header">
    <div class="stage-number">01</div>
    <div class="stage-meta">
      <div class="stage-tag s1-tag">Start Here — Right Now</div>
      <div class="stage-name s1-color">Teach a Machine to See</div>
      <div class="stage-subtitle">Camera Geometry · Lenses · Image Pipelines</div>
      <div class="stage-duration">6–8 weeks · Phone + Laptop · No GPU</div>
    </div>
  </div>
  <div class="stage-desc">You have a phone. That phone has a camera. That camera is the most sophisticated sensor available to you right now — it has a lens, a sensor, focal length, intrinsic parameters. Your first job is to understand it completely, build things with it, and learn what it cannot do alone.</div>

  <div class="projects-section">
    <div class="projects-label">Projects — Do These In Order</div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">01</div>
        <div class="project-title-block">
          <div class="project-name">Your Phone as a CV Sensor</div>
          <div class="project-tagline">Stream your phone camera to your laptop and process it in real time</div>
        </div>
        <div class="project-badges"><span class="badge badge-phone">📱 PHONE</span><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Your phone is your primary sensor for all of Stage 1 and 2. This project sets up the pipeline: phone camera → WiFi stream → Python on laptop → processed output. Everything else builds on this.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Install IP Webcam app on your phone (Android) or EpocCam (iOS). This streams your camera over WiFi as an MJPEG or RTSP stream.</div>
          <div class="step"><span class="step-n">2</span>On your laptop, open the stream with OpenCV: <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">cap = cv2.VideoCapture('http://YOUR_PHONE_IP:8080/video')</code></div>
          <div class="step"><span class="step-n">3</span>Display the live feed in a window. Draw the current FPS on screen. You now have a live CV feed.</div>
          <div class="step"><span class="step-n">4</span>Add basic processing: convert to grayscale, apply Gaussian blur, run Canny edge detection. Display all four versions side by side.</div>
          <div class="step"><span class="step-n">5</span>Save a recording to disk. You now have a sensor pipeline you will reuse for every project in Stages 1–3.</div>
        </div>
        <div class="project-learn">You learn: <span>OpenCV video capture, basic image processing, building a reusable sensor pipeline</span></div>
        <div class="project-tools"><span class="tool-chip">OpenCV</span><span class="tool-chip">IP Webcam / EpocCam</span><span class="tool-chip">Python</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">02</div>
        <div class="project-title-block">
          <div class="project-name">Calibrate Your Phone Camera</div>
          <div class="project-tagline">Find the exact mathematical model of your phone's lens</div>
        </div>
        <div class="project-badges"><span class="badge badge-phone">📱 PHONE</span><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Camera calibration gives you the intrinsic matrix K — the mathematical description of your phone's camera. Focal length, principal point, distortion coefficients. Without this, you cannot do stereo depth, SLAM, or pose estimation accurately. This is the foundation of everything.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Print a chessboard pattern (9×6 inner corners). Tape it flat on a wall or table.</div>
          <div class="step"><span class="step-n">2</span>Record 25–30 short video clips of the chessboard from different angles, distances, and rotations. Vary the tilt significantly.</div>
          <div class="step"><span class="step-n">3</span>Extract frames from the video. Use <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">cv2.findChessboardCorners()</code> to detect the corners in each frame.</div>
          <div class="step"><span class="step-n">4</span>Feed all detected corners into <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">cv2.calibrateCamera()</code>. It outputs your intrinsic matrix K and distortion coefficients.</div>
          <div class="step"><span class="step-n">5</span>Undistort a photo using the calibration. Compare the distorted vs undistorted image — straight lines should now be straight.</div>
          <div class="step"><span class="step-n">6</span>Save K and the distortion coefficients to a file. You will use these in almost every future project.</div>
        </div>
        <div class="project-learn">You learn: <span>What focal length means physically, what the intrinsic matrix is, why lens distortion exists, how calibration works</span></div>
        <div class="project-tools"><span class="tool-chip">OpenCV</span><span class="tool-chip">NumPy</span><span class="tool-chip">Printed chessboard</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">03</div>
        <div class="project-title-block">
          <div class="project-name">Homography — Flatten Any Surface</div>
          <div class="project-tagline">Map your phone camera view onto a flat plane mathematically</div>
        </div>
        <div class="project-badges"><span class="badge badge-phone">📱 PHONE</span><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">A homography is a mathematical transformation between two views of the same flat surface. Point your phone at a notebook, a document, or the floor. The homography lets you correct the perspective — as if you were looking straight down from above. Used in document scanning, lane detection, and bird's-eye-view driving maps.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Stream your phone camera pointing at a flat surface — a piece of paper with text, or a notebook.</div>
          <div class="step"><span class="step-n">2</span>Manually click 4 corner points of the flat surface in the image. Store them as source points.</div>
          <div class="step"><span class="step-n">3</span>Define 4 destination points — a rectangle of the same proportions, as if viewed from directly above.</div>
          <div class="step"><span class="step-n">4</span>Use <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">cv2.findHomography()</code> to compute H. Apply it with <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">cv2.warpPerspective()</code>.</div>
          <div class="step"><span class="step-n">5</span>Make it real-time — do this on every frame. Point your phone at the floor and produce a live bird's-eye-view of the ground. This is exactly what autonomous car cameras do for lane mapping.</div>
        </div>
        <div class="project-learn">You learn: <span>What a homography matrix is and does, perspective correction, bird's-eye-view transforms for autonomous driving</span></div>
        <div class="project-tools"><span class="tool-chip">OpenCV</span><span class="tool-chip">NumPy</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">04</div>
        <div class="project-title-block">
          <div class="project-name">Feature Matching Between Two Views</div>
          <div class="project-tagline">Find the same physical points across two different photos of the same scene</div>
        </div>
        <div class="project-badges"><span class="badge badge-phone">📱 PHONE</span><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Take two photos of your room from slightly different positions with your phone. Write code that finds matching points across both images — the same corner of a chair, the same spot on a wall — and draws lines connecting them. This is the first step of visual odometry and SLAM.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Take two photos of the same scene from slightly different positions. Transfer to laptop.</div>
          <div class="step"><span class="step-n">2</span>Detect ORB keypoints in both images: <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">orb = cv2.ORB_create(); kp, des = orb.detectAndCompute(img, None)</code></div>
          <div class="step"><span class="step-n">3</span>Match descriptors between images using BFMatcher. Filter by Lowe's ratio test to remove bad matches.</div>
          <div class="step"><span class="step-n">4</span>Draw the matches with <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">cv2.drawMatches()</code>. You should see coloured lines connecting corresponding points.</div>
          <div class="step"><span class="step-n">5</span>Using your calibration from Project 02, compute the Essential Matrix from the matches. Decompose it to recover the relative rotation R and translation t between the two camera positions.</div>
          <div class="step"><span class="step-n">6</span>Print R and t. You just estimated where your phone moved between the two photos using only the images.</div>
        </div>
        <div class="project-learn">You learn: <span>Feature detection, descriptor matching, the essential matrix, recovering camera motion — the core of visual odometry</span></div>
        <div class="project-tools"><span class="tool-chip">OpenCV</span><span class="tool-chip">NumPy</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">05</div>
        <div class="project-title-block">
          <div class="project-name">Vanishing Point Detector</div>
          <div class="project-tagline">Find where parallel lines meet — the geometry of roads and corridors</div>
        </div>
        <div class="project-badges"><span class="badge badge-phone">📱 PHONE</span><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-stretch">STRETCH</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Point your phone down a straight road or corridor. In the image, the parallel edges of the road converge to a single point — the vanishing point. This point encodes the direction of travel. Autonomous vehicles use vanishing points to understand road orientation. Detect it automatically.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Capture a video of walking down a straight corridor or road with your phone.</div>
          <div class="step"><span class="step-n">2</span>On each frame: convert to grayscale, apply Canny edges, run Hough Line Transform to detect line segments.</div>
          <div class="step"><span class="step-n">3</span>Filter lines by angle — keep only lines with significant slope (not horizontal noise).</div>
          <div class="step"><span class="step-n">4</span>Find the intersection of the dominant left-side and right-side lines. That intersection is your vanishing point.</div>
          <div class="step"><span class="step-n">5</span>Draw the vanishing point as a circle on the video. It should stay roughly in the centre of the road as you walk.</div>
        </div>
        <div class="project-learn">You learn: <span>Hough transform, line geometry, vanishing points — the projective geometry concept you studied in H&Z made real</span></div>
        <div class="project-tools"><span class="tool-chip">OpenCV</span><span class="tool-chip">NumPy</span></div>
      </div>
    </div>
  </div>

  <div class="math-ref">
    <button class="math-ref-toggle" onclick="toggleMath(this)">
      <span>📐 Math Reference — Read When a Project Breaks</span><span>▼</span>
    </button>
    <div class="math-ref-body">
      <div class="math-row"><div><div class="math-topic">Homogeneous Coordinates</div><div class="math-src">H&Z Chapter 2.2</div></div><div class="math-why">Why we add a third number to 2D points. Needed when Project 03 (homography) gives you strange results.</div></div>
      <div class="math-row"><div><div class="math-topic">The Projection Matrix</div><div class="math-src">H&Z Chapter 6.1–6.2</div></div><div class="math-why">The math behind what calibrateCamera() computes in Project 02. Read when you want to understand what K actually means.</div></div>
      <div class="math-row"><div><div class="math-topic">The Essential Matrix</div><div class="math-src">H&Z Chapter 9.6</div></div><div class="math-why">The math behind recovering R and t in Project 04. Read when the rotation output doesn't make sense.</div></div>
      <div class="math-row"><div><div class="math-topic">Vanishing Points & Line at Infinity</div><div class="math-src">H&Z Chapter 2.2.2</div></div><div class="math-why">Exactly what you built in Project 05 — the formal explanation of why parallel lines meet.</div></div>
    </div>
  </div>

  <div class="refs-grid">
    <div class="ref-block">
      <div class="ref-head s1-color">Books</div>
      <div class="ref-body">
        <div class="ref-item"><div class="ref-title">Multiple View Geometry in CV</div><div class="ref-sub">Hartley & Zisserman — Ch. 2, 6, 7, 9</div></div>
        <div class="ref-item"><div class="ref-title">Programming CV with Python</div><div class="ref-sub">Jan Erik Solem — code companion</div></div>
      </div>
    </div>
    <div class="ref-block">
      <div class="ref-head s1-color">Papers</div>
      <div class="ref-body">
        <div class="ref-item"><div class="ref-title">A Flexible New Technique for Camera Calibration</div><div class="ref-sub">Zhang, 2000 — the math behind calibrateCamera()</div></div>
        <div class="ref-item"><div class="ref-title">ORB: An Efficient Alternative to SIFT or SURF</div><div class="ref-sub">Rublee et al., 2011</div></div>
      </div>
    </div>
  </div>

  <div class="exit-block s1-exit">
    <div class="exit-label s1-color">Stage 1 Exit — You Are Ready When</div>
    <div class="exit-text">You have a working phone-to-laptop camera pipeline. You have your phone's intrinsic matrix K saved to a file. You can detect features in two images, match them, and recover the relative camera motion. You understand what a homography does without needing to look it up.</div>
  </div>
</div>

<!-- ===== STAGE 2 ===== -->
<div class="stage" id="s2">
  <div class="stage-header">
    <div class="stage-number">02</div>
    <div class="stage-meta">
      <div class="stage-tag s2-tag">Perception</div>
      <div class="stage-name s2-color">Understand Every Pixel</div>
      <div class="stage-subtitle">Depth · Motion · Semantics · Tracking</div>
      <div class="stage-duration">6–8 weeks · Phone + Laptop · Kaggle for model training</div>
    </div>
  </div>
  <div class="stage-desc">Bounding boxes are not enough. A self-driving car needs to know how far away everything is, what it is, and whether it is moving. This stage builds the perception stack — the eyes of an autonomous system.</div>

  <div class="projects-section">
    <div class="projects-label">Projects — Do These In Order</div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">06</div>
        <div class="project-title-block">
          <div class="project-name">Real-Time Depth on Your Phone Feed</div>
          <div class="project-tagline">Every pixel gets a distance estimate in metres</div>
        </div>
        <div class="project-badges"><span class="badge badge-phone">📱 PHONE</span><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Stream your phone camera. Run ZoeDepth or MiDaS on every frame. Overlay a colour heatmap showing distance — blue is far, red is close. Click on any pixel and print its estimated distance in metres. This is monocular depth estimation — the single most important perception skill for camera-only autonomous navigation.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Install ZoeDepth: <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">pip install git+https://github.com/isl-org/ZoeDepth.git</code>. Load the ZoeN model.</div>
          <div class="step"><span class="step-n">2</span>Connect your phone stream from Stage 1. Sample every 3rd frame for processing (CPU is slow).</div>
          <div class="step"><span class="step-n">3</span>Run ZoeDepth on each sampled frame. It outputs a depth map — a 2D array where each value is estimated distance in metres.</div>
          <div class="step"><span class="step-n">4</span>Apply a colour map: <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">cv2.applyColorMap(depth_normalized, cv2.COLORMAP_PLASMA)</code>. Overlay it on the original frame.</div>
          <div class="step"><span class="step-n">5</span>Add a mouse click callback — when you click a pixel, print the depth value at that location. Walk around your room and verify the numbers make sense.</div>
          <div class="step"><span class="step-n">6</span>Record a video of you walking toward a wall. Plot a graph of the centre pixel's depth over time. It should decrease smoothly as you approach.</div>
        </div>
        <div class="project-learn">You learn: <span>Monocular depth estimation, depth maps, how neural networks can estimate 3D from 2D</span></div>
        <div class="project-tools"><span class="tool-chip">ZoeDepth</span><span class="tool-chip">OpenCV</span><span class="tool-chip">PyTorch</span><span class="tool-chip">NumPy</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">07</div>
        <div class="project-title-block">
          <div class="project-name">Optical Flow — See What Moves</div>
          <div class="project-tagline">Map the velocity of every pixel between frames</div>
        </div>
        <div class="project-badges"><span class="badge badge-phone">📱 PHONE</span><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Walk around with your phone. Optical flow computes — for every pixel — how much it moved between this frame and the last. Visualise the flow field as arrows or as a colour wheel image. This is how autonomous cars detect moving obstacles and estimate their own motion.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Record a video walking around your room or outside — ideally with some moving objects (a fan, a person walking past).</div>
          <div class="step"><span class="step-n">2</span>Implement dense Farneback optical flow: <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">flow = cv2.calcOpticalFlowFarneback(prev_gray, curr_gray, None, 0.5, 3, 15, 3, 5, 1.2, 0)</code></div>
          <div class="step"><span class="step-n">3</span>Convert flow to HSV colour image — hue encodes direction, saturation encodes magnitude. Display it.</div>
          <div class="step"><span class="step-n">4</span>Compute the flow magnitude map. Pixels with high magnitude are moving fast. Threshold it to create a binary motion mask.</div>
          <div class="step"><span class="step-n">5</span>Find the Focus of Expansion — the point all flow vectors point away from when you move forward. This is your direction of travel. Mark it on the frame with a crosshair.</div>
          <div class="step"><span class="step-n">6</span>Test with a moving object in the scene — a ball rolling, a hand waving. The moving object should stand out in the motion mask even when your camera is stationary.</div>
        </div>
        <div class="project-learn">You learn: <span>Optical flow, ego-motion, moving obstacle detection, focus of expansion for direction estimation</span></div>
        <div class="project-tools"><span class="tool-chip">OpenCV</span><span class="tool-chip">NumPy</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">08</div>
        <div class="project-title-block">
          <div class="project-name">Semantic Scene Segmentation on Driving Video</div>
          <div class="project-tagline">Label every pixel: road, car, pedestrian, sky, building</div>
        </div>
        <div class="project-badges"><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-kaggle">☁ KAGGLE</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Download a dashcam video from YouTube. Run SegFormer (pretrained on Cityscapes — the autonomous driving dataset) on every frame. Colour each pixel by class. Road is green, cars are red, pedestrians are yellow, sky is blue. Output the full annotated video. This is what every self-driving car's perception stack does.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Download a dashcam YouTube video using yt-dlp. Choose a clear daytime urban driving video, 1–2 minutes long.</div>
          <div class="step"><span class="step-n">2</span>Load SegFormer pretrained on Cityscapes from HuggingFace: <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">nvidia/segformer-b2-finetuned-cityscapes-1024-1024</code></div>
          <div class="step"><span class="step-n">3</span>Process each frame through the model. Get the predicted class label per pixel.</div>
          <div class="step"><span class="step-n">4</span>Map each class to a colour. Blend the colour mask with the original frame at 50% opacity.</div>
          <div class="step"><span class="step-n">5</span>Write all frames back to a video file. Watch it play back — you should see the road, cars, and pedestrians all correctly coloured in real time.</div>
          <div class="step"><span class="step-n">6</span>Extract the "road" mask from each frame. Compute the drivable area as a percentage of the frame. Plot it over time — it drops when intersections appear.</div>
        </div>
        <div class="project-learn">You learn: <span>Semantic segmentation, Cityscapes classes, HuggingFace model loading, drivable area estimation</span></div>
        <div class="project-tools"><span class="tool-chip">HuggingFace Transformers</span><span class="tool-chip">SegFormer</span><span class="tool-chip">OpenCV</span><span class="tool-chip">yt-dlp</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">09</div>
        <div class="project-title-block">
          <div class="project-name">Multi-Object Tracker on Street Video</div>
          <div class="project-tagline">Give every car and pedestrian a persistent ID across frames</div>
        </div>
        <div class="project-badges"><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Detect every car, pedestrian, and cyclist in a driving video. Assign each one a persistent ID that stays the same across frames — "Pedestrian #3" is #3 whether they're 50m away or 5m away. Track their trajectories over time. This is what autonomous cars use to predict whether something will cross your path.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Use YOLOv8 (ultralytics) for detection — it runs on CPU. Detect only vehicles and pedestrians.</div>
          <div class="step"><span class="step-n">2</span>Install ByteTrack or use the built-in tracker in ultralytics: <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">model.track(source=video, persist=True)</code></div>
          <div class="step"><span class="step-n">3</span>Draw bounding boxes with persistent IDs on each frame. Use a different colour per ID.</div>
          <div class="step"><span class="step-n">4</span>Store the centroid position of each tracked object per frame. Draw trajectory trails showing where each object has been.</div>
          <div class="step"><span class="step-n">5</span>Compute speed of each object in pixels/frame. Flag objects whose trajectory is heading toward the camera centre — potential collision candidates.</div>
        </div>
        <div class="project-learn">You learn: <span>Detection + tracking pipeline, persistent IDs, trajectory analysis, collision risk estimation</span></div>
        <div class="project-tools"><span class="tool-chip">YOLOv8 (ultralytics)</span><span class="tool-chip">ByteTrack</span><span class="tool-chip">OpenCV</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">10</div>
        <div class="project-title-block">
          <div class="project-name">Full Perception Stack — Live on Your Phone</div>
          <div class="project-tagline">Depth + Segmentation + Tracking in one live pipeline</div>
        </div>
        <div class="project-badges"><span class="badge badge-phone">📱 PHONE</span><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-stretch">STRETCH</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Combine everything from Stage 2 into one live pipeline. Phone camera feeds into your laptop. Every frame: YOLOv8 detects objects, ByteTrack assigns IDs, ZoeDepth estimates distance. Output on screen: "Car #2 — 8.3m, approaching." This is a real autonomous perception stack running on consumer hardware.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Start your phone stream. For each frame, run detection first (fastest), then depth only on detected object regions (not full frame — too slow).</div>
          <div class="step"><span class="step-n">2</span>For each tracked object, sample the depth values within its bounding box. Take the median as the distance estimate.</div>
          <div class="step"><span class="step-n">3</span>Display: bounding box + ID + class + distance in metres. Use different colours per class.</div>
          <div class="step"><span class="step-n">4</span>Add a proximity alert: if any object is estimated within 2m, flash a red warning on screen and print an alert.</div>
          <div class="step"><span class="step-n">5</span>Record a 2-minute demo video of you walking around campus or outside. This is your first portfolio piece.</div>
        </div>
        <div class="project-learn">You learn: <span>System integration, performance optimisation on CPU, building a real-time pipeline</span></div>
        <div class="project-tools"><span class="tool-chip">YOLOv8</span><span class="tool-chip">ZoeDepth</span><span class="tool-chip">ByteTrack</span><span class="tool-chip">OpenCV</span></div>
      </div>
    </div>
  </div>

  <div class="math-ref">
    <button class="math-ref-toggle" onclick="toggleMath(this)">
      <span>📐 Math Reference — Read When a Project Breaks</span><span>▼</span>
    </button>
    <div class="math-ref-body">
      <div class="math-row"><div><div class="math-topic">Optical Flow Equation</div><div class="math-src">Szeliski Ch. 9.1</div></div><div class="math-why">The brightness constancy assumption — why optical flow works and when it fails (fast motion, lighting changes).</div></div>
      <div class="math-row"><div><div class="math-topic">Depth from Stereo — Disparity</div><div class="math-src">H&Z Ch. 12 / Szeliski Ch. 12</div></div><div class="math-why">Why monocular depth is ambiguous and how stereo resolves it. Read when ZoeDepth gives wrong results.</div></div>
      <div class="math-row"><div><div class="math-topic">CNN Architectures</div><div class="math-src">Goodfellow Ch. 9</div></div><div class="math-why">How SegFormer and ZoeDepth work internally. Read when you want to understand why they fail on certain inputs.</div></div>
    </div>
  </div>

  <div class="refs-grid">
    <div class="ref-block">
      <div class="ref-head s2-color">Key Papers</div>
      <div class="ref-body">
        <div class="ref-item"><div class="ref-title">ZoeDepth: Zero-shot Transfer by Combining Relative and Metric Depth</div><div class="ref-sub">Bhat et al., 2023</div></div>
        <div class="ref-item"><div class="ref-title">SegFormer: Simple and Efficient Design for Semantic Segmentation</div><div class="ref-sub">Xie et al., 2021</div></div>
        <div class="ref-item"><div class="ref-title">ByteTrack: Multi-Object Tracking by Associating Every Detection Box</div><div class="ref-sub">Zhang et al., 2022</div></div>
        <div class="ref-item"><div class="ref-title">RAFT: Recurrent All-Pairs Field Transforms for Optical Flow</div><div class="ref-sub">Teed & Deng, 2020</div></div>
      </div>
    </div>
    <div class="ref-block">
      <div class="ref-head s2-color">Datasets to Know</div>
      <div class="ref-body">
        <div class="ref-item"><div class="ref-title">Cityscapes</div><div class="ref-sub">Urban driving segmentation — 19 classes. What SegFormer was trained on.</div></div>
        <div class="ref-item"><div class="ref-title">KITTI</div><div class="ref-sub">Driving dataset with depth ground truth from LiDAR. Use for evaluation.</div></div>
        <div class="ref-item"><div class="ref-title">nuScenes</div><div class="ref-sub">Multi-sensor autonomous driving dataset. 1000 scenes with camera + LiDAR.</div></div>
      </div>
    </div>
  </div>

  <div class="exit-block s2-exit">
    <div class="exit-label s2-color">Stage 2 Exit — You Are Ready When</div>
    <div class="exit-text">You have a live pipeline that takes your phone camera feed, estimates depth per object, segments the scene by class, and tracks objects with persistent IDs. You have a recorded demo video you can show someone. You understand why monocular depth is ambiguous and what optical flow measures.</div>
  </div>
</div>

<!-- ===== STAGE 3 ===== -->
<div class="stage" id="s3">
  <div class="stage-header">
    <div class="stage-number">03</div>
    <div class="stage-meta">
      <div class="stage-tag s3-tag">Localisation</div>
      <div class="stage-name s3-color">Know Where You Are</div>
      <div class="stage-subtitle">Visual Odometry · SLAM · Sensor Fusion</div>
      <div class="stage-duration">8–10 weeks · Phone + Laptop · No GPU</div>
    </div>
  </div>
  <div class="stage-desc">Your perception stack tells you what is around you. Now you need to know where you are. No GPS. No map given to you. Just your camera. This is SLAM — the hardest and most important problem in autonomous navigation.</div>

  <div class="projects-section">
    <div class="projects-label">Projects — Do These In Order</div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">11</div>
        <div class="project-title-block">
          <div class="project-name">Visual Odometry — Track Your Phone's Movement</div>
          <div class="project-tagline">Estimate where your phone moved using only the camera</div>
        </div>
        <div class="project-badges"><span class="badge badge-phone">📱 PHONE</span><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Walk through your house slowly holding your phone steady. Your code estimates how the camera moved between every consecutive pair of frames — forward, sideways, rotation. Chain all these estimates together into a trajectory. Draw the top-down path your phone took on a 2D plot. This is visual odometry — the core of SLAM.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Record a slow, steady walk through your house with your phone. Hold it at chest height, move smoothly.</div>
          <div class="step"><span class="step-n">2</span>For each consecutive frame pair: detect ORB features, match them, filter with RANSAC.</div>
          <div class="step"><span class="step-n">3</span>Using your calibration matrix K from Project 02, compute the Essential Matrix from the matches.</div>
          <div class="step"><span class="step-n">4</span>Decompose E into R and t. This gives you the rotation and translation between the two frames.</div>
          <div class="step"><span class="step-n">5</span>Chain all R and t values together — each step is relative to the previous. Accumulate the global position over all frames.</div>
          <div class="step"><span class="step-n">6</span>Plot the X-Z trajectory (top-down view) on a live Matplotlib window. Watch your path being drawn as the video plays.</div>
          <div class="step"><span class="step-n">7</span>Walk a square path and check if the plotted trajectory looks roughly square. Notice the drift — small errors compound over time. This drift is why loop closure exists.</div>
        </div>
        <div class="project-learn">You learn: <span>Visual odometry pipeline, pose chaining, scale ambiguity, drift — why SLAM needs more than pure VO</span></div>
        <div class="project-tools"><span class="tool-chip">OpenCV</span><span class="tool-chip">NumPy</span><span class="tool-chip">Matplotlib</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">12</div>
        <div class="project-title-block">
          <div class="project-name">ORB-SLAM3 — Map Your Room</div>
          <div class="project-tagline">Walk around your room and produce a 3D point cloud map</div>
        </div>
        <div class="project-badges"><span class="badge badge-phone">📱 PHONE</span><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Install ORB-SLAM3. Feed it your phone camera stream or a recorded video. Walk around your room slowly. ORB-SLAM3 builds a sparse 3D point cloud map of your room and tracks your camera position within it in real time. Export the map and visualise it in Open3D. This is what a Mars rover does.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Build ORB-SLAM3 from source on your machine (Linux via WSL on Windows). Follow the official build instructions carefully.</div>
          <div class="step"><span class="step-n">2</span>Create a calibration YAML file for your phone camera using the K matrix and distortion coefficients from Project 02.</div>
          <div class="step"><span class="step-n">3</span>Record a video of your room — slow, steady, covering all walls. At least 2 minutes. Good lighting is critical.</div>
          <div class="step"><span class="step-n">4</span>Run ORB-SLAM3 in monocular mode on your video. Watch the real-time visualisation — keypoints, map points, camera trajectory.</div>
          <div class="step"><span class="step-n">5</span>Export the map points and trajectory. Load them in Open3D and visualise the 3D reconstruction of your room.</div>
          <div class="step"><span class="step-n">6</span>Walk a loop — return to your starting position. Watch ORB-SLAM3 detect the loop closure and correct the accumulated drift. The map should snap into alignment.</div>
        </div>
        <div class="project-learn">You learn: <span>Full SLAM pipeline, loop closure, map building, why professional SLAM beats your VO from Project 11</span></div>
        <div class="project-tools"><span class="tool-chip">ORB-SLAM3</span><span class="tool-chip">Open3D</span><span class="tool-chip">WSL (Windows Subsystem for Linux)</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">13</div>
        <div class="project-title-block">
          <div class="project-name">Kalman Filter — Smooth Noisy Sensor Data</div>
          <div class="project-tagline">Build the algorithm that fuses GPS, IMU, and vision in every self-driving car</div>
        </div>
        <div class="project-badges"><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Implement a Kalman filter from scratch. Simulate a robot moving in a straight line with noisy position measurements. The Kalman filter fuses the noisy measurements with a motion model to produce a smooth, accurate estimate. This is inside every phone, drone, and self-driving car. Build it yourself — no library.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Simulate a robot moving at constant velocity. Generate true positions. Add Gaussian noise to create "sensor measurements."</div>
          <div class="step"><span class="step-n">2</span>Implement the 5 Kalman filter equations from scratch in NumPy: predict step (state + covariance), update step (Kalman gain, new state, new covariance).</div>
          <div class="step"><span class="step-n">3</span>Run the filter on your noisy measurements. Plot three lines: true position, noisy measurements, filtered estimate. The filter should track truth far better than raw measurements.</div>
          <div class="step"><span class="step-n">4</span>Tune the process noise Q and measurement noise R. Observe how increasing Q makes the filter trust measurements more (faster but noisier). Decreasing Q makes it trust the motion model more (smoother but slower to react).</div>
          <div class="step"><span class="step-n">5</span>Apply it to your VO trajectory from Project 11. Smooth the noisy pose estimates with the Kalman filter.</div>
        </div>
        <div class="project-learn">You learn: <span>Kalman filter equations, predict-update cycle, noise covariance tuning, why sensor fusion exists</span></div>
        <div class="project-tools"><span class="tool-chip">NumPy</span><span class="tool-chip">Matplotlib</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">14</div>
        <div class="project-title-block">
          <div class="project-name">Phone IMU + Camera Fusion</div>
          <div class="project-tagline">Combine your phone's accelerometer with the camera for better odometry</div>
        </div>
        <div class="project-badges"><span class="badge badge-phone">📱 PHONE</span><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-stretch">STRETCH</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Your phone has an accelerometer and gyroscope — an IMU. Record a synchronised camera + IMU data sequence. Fuse both using a Kalman filter. The IMU gives fast, high-rate motion estimates. The camera corrects drift. Together they produce better localisation than either alone. This is Visual-Inertial Odometry — what DJI drones use.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Use the Sensor Logger app (iOS/Android) to record synchronised camera frames and IMU data to CSV. Shake your phone to calibrate.</div>
          <div class="step"><span class="step-n">2</span>Integrate the IMU accelerometer data to estimate velocity and position. Plot this raw IMU trajectory — it will drift badly within seconds.</div>
          <div class="step"><span class="step-n">3</span>Compute your visual odometry trajectory from the same sequence using Project 11's pipeline.</div>
          <div class="step"><span class="step-n">4</span>Implement a simple complementary filter: fuse IMU (high rate, drifts) with VO (low rate, accurate). Use IMU for fast updates, correct with VO periodically.</div>
          <div class="step"><span class="step-n">5</span>Compare trajectories: raw IMU, raw VO, fused. The fused version should be smoother than VO and more accurate than raw IMU.</div>
        </div>
        <div class="project-learn">You learn: <span>IMU integration, sensor fusion, why VIO outperforms pure visual or pure inertial odometry</span></div>
        <div class="project-tools"><span class="tool-chip">Sensor Logger App</span><span class="tool-chip">NumPy</span><span class="tool-chip">Matplotlib</span><span class="tool-chip">OpenCV</span></div>
      </div>
    </div>
  </div>

  <div class="math-ref">
    <button class="math-ref-toggle" onclick="toggleMath(this)">
      <span>📐 Math Reference — Read When a Project Breaks</span><span>▼</span>
    </button>
    <div class="math-ref-body">
      <div class="math-row"><div><div class="math-topic">Kalman Filter Equations</div><div class="math-src">Thrun, Probabilistic Robotics Ch. 3</div></div><div class="math-why">The full derivation. Read after Project 13 when you want to understand why the equations are what they are.</div></div>
      <div class="math-row"><div><div class="math-topic">Lie Groups SO(3) and SE(3)</div><div class="math-src">Barfoot, State Estimation Ch. 7</div></div><div class="math-why">Why rotations cannot be averaged like regular numbers. Read when Project 11's trajectory has strange jumps in orientation.</div></div>
      <div class="math-row"><div><div class="math-topic">Bundle Adjustment</div><div class="math-src">H&Z Ch. 18</div></div><div class="math-why">How ORB-SLAM3 refines its map globally. Read after Project 12 when you want to understand what happens after loop closure.</div></div>
    </div>
  </div>

  <div class="refs-grid">
    <div class="ref-block">
      <div class="ref-head s3-color">Key Papers</div>
      <div class="ref-body">
        <div class="ref-item"><div class="ref-title">ORB-SLAM3: An Accurate Open-Source Library for Visual, Visual-Inertial and Multimap SLAM</div><div class="ref-sub">Campos et al., 2021</div></div>
        <div class="ref-item"><div class="ref-title">DROID-SLAM: Deep Visual SLAM for Monocular, Stereo, and RGB-D Cameras</div><div class="ref-sub">Teed & Deng, 2021</div></div>
        <div class="ref-item"><div class="ref-title">VINS-Mono: A Robust and Versatile Monocular Visual-Inertial State Estimator</div><div class="ref-sub">Qin et al., 2018</div></div>
      </div>
    </div>
    <div class="ref-block">
      <div class="ref-head s3-color">Primary Books</div>
      <div class="ref-body">
        <div class="ref-item"><div class="ref-title">Probabilistic Robotics</div><div class="ref-sub">Thrun, Burgard, Fox — the SLAM bible</div></div>
        <div class="ref-item"><div class="ref-title">State Estimation for Robotics</div><div class="ref-sub">Timothy Barfoot — modern SLAM math</div></div>
      </div>
    </div>
  </div>

  <div class="exit-block s3-exit">
    <div class="exit-label s3-color">Stage 3 Exit — You Are Ready When</div>
    <div class="exit-text">You have built a visual odometry system from scratch and understand why it drifts. You have run ORB-SLAM3 on your phone video and produced a 3D map of your room. You have implemented a Kalman filter from scratch without any library. You can explain what loop closure does in plain English.</div>
  </div>
</div>

<!-- ===== STAGE 4 ===== -->
<div class="stage" id="s4">
  <div class="stage-header">
    <div class="stage-number">04</div>
    <div class="stage-meta">
      <div class="stage-tag s4-tag">Mapping</div>
      <div class="stage-name s4-color">Build the World</div>
      <div class="stage-subtitle">Occupancy Grids · 3D Reconstruction · Neural Maps</div>
      <div class="stage-duration">6–8 weeks · Laptop + Kaggle for NeRF training</div>
    </div>
  </div>
  <div class="stage-desc">You know where you are. Now build a representation of the world detailed enough to navigate it. From simple occupancy grids to photorealistic neural scenes — the right map depends on the task.</div>

  <div class="projects-section">
    <div class="projects-label">Projects — Do These In Order</div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">15</div>
        <div class="project-title-block">
          <div class="project-name">Occupancy Grid — Floor Plan of Your Room</div>
          <div class="project-tagline">Turn your SLAM point cloud into a 2D navigable map</div>
        </div>
        <div class="project-badges"><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Take the 3D point cloud from your ORB-SLAM3 map (Project 12). Project it onto a 2D top-down grid. Mark each cell occupied or free. Output a floor plan of your room — the same kind of map a Roomba uses. This is the simplest useful map for navigation.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Load your ORB-SLAM3 map points from the saved file. Each point is an (x, y, z) coordinate.</div>
          <div class="step"><span class="step-n">2</span>Filter out outlier points (very high or low z values — ceiling and floor noise). Keep only points near the wall height.</div>
          <div class="step"><span class="step-n">3</span>Define a 2D grid with cell size 0.1m. For each point, find which grid cell it falls in (using x and z, ignoring y height). Mark that cell occupied.</div>
          <div class="step"><span class="step-n">4</span>Apply morphological dilation to thicken the walls slightly. Fill enclosed regions as free space.</div>
          <div class="step"><span class="step-n">5</span>Visualise the grid — occupied cells black, free cells white, unknown cells grey. Compare it to an actual photo of your room's floor plan.</div>
        </div>
        <div class="project-learn">You learn: <span>Occupancy grids, point cloud processing, the map representation used by every mobile robot</span></div>
        <div class="project-tools"><span class="tool-chip">Open3D</span><span class="tool-chip">NumPy</span><span class="tool-chip">OpenCV</span><span class="tool-chip">Matplotlib</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">16</div>
        <div class="project-title-block">
          <div class="project-name">COLMAP — 3D Reconstruct a Real Place</div>
          <div class="project-tagline">Turn 50 phone photos into a 3D mesh you can fly through</div>
        </div>
        <div class="project-badges"><span class="badge badge-phone">📱 PHONE</span><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Take 50–80 photos of a building, outdoor space, or large room with your phone from many angles. Feed them into COLMAP. It will reconstruct the 3D geometry of the scene — a sparse point cloud, then a dense mesh. This is Structure from Motion — what Google Maps Street View uses to build 3D city models.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Download the COLMAP Windows binary from colmap.github.io. No installation needed — just unzip and run.</div>
          <div class="step"><span class="step-n">2</span>Take photos: walk around the subject, overlap each photo 60–70% with the previous. Shoot from different heights. Avoid pure rotations with no translation.</div>
          <div class="step"><span class="step-n">3</span>In COLMAP: File → New Project. Set image folder. Run automatic reconstruction. Watch the sparse point cloud build incrementally.</div>
          <div class="step"><span class="step-n">4</span>Run Dense Reconstruction (MVS). This takes longer but produces a full surface mesh.</div>
          <div class="step"><span class="step-n">5</span>Export the mesh. Open it in MeshLab (free) or Open3D. Fly through your 3D reconstruction.</div>
          <div class="step"><span class="step-n">6</span>Note where COLMAP fails — reflective surfaces, textureless walls, moving objects. These are the same failure modes autonomous systems face.</div>
        </div>
        <div class="project-learn">You learn: <span>The full SfM pipeline, when reconstruction fails and why, dense vs sparse maps</span></div>
        <div class="project-tools"><span class="tool-chip">COLMAP</span><span class="tool-chip">MeshLab</span><span class="tool-chip">Open3D</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">17</div>
        <div class="project-title-block">
          <div class="project-name">NeRF — Neural 3D Scene from Your Phone Photos</div>
          <div class="project-tagline">Train a neural network that can render your scene from any angle</div>
        </div>
        <div class="project-badges"><span class="badge badge-phone">📱 PHONE</span><span class="badge badge-kaggle">☁ KAGGLE</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Take 60+ photos of an object or small space with your phone. Train a NeRF on Kaggle (free GPU). The NeRF learns to render the scene from any viewpoint — it has memorised the geometry and appearance as a neural network. Render a 360° flythrough video. This is how Meta, Google, and NVIDIA are building the metaverse.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Photograph a subject from 60+ angles in a sphere pattern. Good subjects: a shoe, a plant, a sculpture, a corner of a room. Consistent lighting is critical.</div>
          <div class="step"><span class="step-n">2</span>Run COLMAP on the photos to get camera poses. NerfStudio needs to know where each photo was taken.</div>
          <div class="step"><span class="step-n">3</span>On Kaggle: upload your images + COLMAP output. Install NerfStudio. Run: <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">ns-train nerfacto --data /path/to/data</code></div>
          <div class="step"><span class="step-n">4</span>Monitor training loss. After ~10k steps, render some test views. After ~30k steps, render the full 360° flythrough video.</div>
          <div class="step"><span class="step-n">5</span>Export the NeRF as a mesh. Compare the mesh quality to your COLMAP dense reconstruction from Project 16.</div>
        </div>
        <div class="project-learn">You learn: <span>Neural radiance fields, volume rendering concept, novel view synthesis — the frontier of 3D mapping</span></div>
        <div class="project-tools"><span class="tool-chip">NerfStudio</span><span class="tool-chip">COLMAP</span><span class="tool-chip">Kaggle (free GPU)</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">18</div>
        <div class="project-title-block">
          <div class="project-name">Semantic Map — Label Your 3D World</div>
          <div class="project-tagline">Every point in your map knows what it is</div>
        </div>
        <div class="project-badges"><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-stretch">STRETCH</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Take your ORB-SLAM3 room map. For every keyframe image, run your segmentation model from Stage 2. Project the semantic labels onto the 3D point cloud. Every point is now labelled: floor, wall, chair, door. This is a semantic map — a robot with this map can navigate to "the chair" or "the door" using language commands.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Load your ORB-SLAM3 keyframe images and associated map points.</div>
          <div class="step"><span class="step-n">2</span>Run SegFormer on each keyframe image. Get per-pixel class labels.</div>
          <div class="step"><span class="step-n">3</span>For each 3D map point: find which keyframes it appears in, sample the segmentation label at its projected pixel location, assign the majority-vote label.</div>
          <div class="step"><span class="step-n">4</span>Visualise in Open3D with colour per class — floor grey, walls white, furniture coloured.</div>
          <div class="step"><span class="step-n">5</span>Query the map: "find all points labelled door." Compute the centroid. This is the door's 3D location. A robot can now navigate to it.</div>
        </div>
        <div class="project-learn">You learn: <span>Semantic mapping, projecting 2D labels into 3D, language-grounded navigation</span></div>
        <div class="project-tools"><span class="tool-chip">ORB-SLAM3</span><span class="tool-chip">SegFormer</span><span class="tool-chip">Open3D</span><span class="tool-chip">NumPy</span></div>
      </div>
    </div>
  </div>

  <div class="math-ref">
    <button class="math-ref-toggle" onclick="toggleMath(this)">
      <span>📐 Math Reference — Read When a Project Breaks</span><span>▼</span>
    </button>
    <div class="math-ref-body">
      <div class="math-row"><div><div class="math-topic">Volume Rendering Equation</div><div class="math-src">PBRT Ch. 11 / NeRF paper Sec. 4</div></div><div class="math-why">The integral NeRF optimises. Read after Project 17 when you want to understand why NeRF works.</div></div>
      <div class="math-row"><div><div class="math-topic">Occupancy Grid Math</div><div class="math-src">Thrun, Probabilistic Robotics Ch. 9</div></div><div class="math-why">The log-odds update equation. Read after Project 15 to understand how occupancy probabilities are updated from sensor data.</div></div>
    </div>
  </div>

  <div class="exit-block s4-exit">
    <div class="exit-label s4-color">Stage 4 Exit — You Are Ready When</div>
    <div class="exit-text">You have an occupancy grid of your room. You have a 3D NeRF of a real object trained with your phone photos. You have a semantic 3D map where every point has a class label. You can explain the difference between sparse and dense reconstruction.</div>
  </div>
</div>

<!-- ===== STAGE 5 ===== -->
<div class="stage" id="s5">
  <div class="stage-header">
    <div class="stage-number">05</div>
    <div class="stage-meta">
      <div class="stage-tag s5-tag">Planning & Control</div>
      <div class="stage-name s5-color">Move Through the World</div>
      <div class="stage-subtitle">Path Planning · Simulation · Control</div>
      <div class="stage-duration">8–10 weeks · Laptop + PyBullet + CARLA</div>
    </div>
  </div>
  <div class="stage-desc">You can see, you know where you are, you have a map. Now you must decide where to go and actually get there. This stage connects everything to motion — the output is not an image but a command: turn left, speed up, stop.</div>

  <div class="projects-section">
    <div class="projects-label">Projects — Do These In Order</div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">19</div>
        <div class="project-title-block">
          <div class="project-name">A* Path Planner on Your Room Map</div>
          <div class="project-tagline">Plan a path from your door to your desk on the real map you built</div>
        </div>
        <div class="project-badges"><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Take your occupancy grid from Stage 4. Pick a start cell and a goal cell. Run A* to find the shortest path around obstacles. Visualise the path on the map. This is the most practical project in the entire roadmap — A* runs on virtually every mobile robot ever built.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Implement A* from scratch in Python. Use a priority queue (heapq). The heuristic is Euclidean distance to goal.</div>
          <div class="step"><span class="step-n">2</span>Load your occupancy grid. Occupied cells have infinite cost. Free cells have cost 1.</div>
          <div class="step"><span class="step-n">3</span>Run A* from a start cell to a goal cell. Visualise the explored cells in grey and the final path in green on the grid image.</div>
          <div class="step"><span class="step-n">4</span>Add path smoothing — the raw A* path is jagged because it follows grid cells. Apply a simple smoothing algorithm to produce a curved path.</div>
          <div class="step"><span class="step-n">5</span>Make it interactive: click start and goal positions on the map image. Re-run A* and display the new path. You now have a working path planning UI.</div>
        </div>
        <div class="project-learn">You learn: <span>A* algorithm, priority queues, path smoothing, the full perception-to-planning connection</span></div>
        <div class="project-tools"><span class="tool-chip">NumPy</span><span class="tool-chip">OpenCV</span><span class="tool-chip">Matplotlib</span><span class="tool-chip">heapq</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">20</div>
        <div class="project-title-block">
          <div class="project-name">First Robot in PyBullet</div>
          <div class="project-tagline">A simulated wheeled robot that you drive with code</div>
        </div>
        <div class="project-badges"><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-sim">🖥 SIMULATOR</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Set up PyBullet. Load a wheeled robot model (the Husky or R2D2 that comes with PyBullet). Write Python code to control its wheel velocities. Drive it around a simulated room. Add walls as obstacles. This is your first simulated robot — everything from here runs in simulation before real hardware.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Install PyBullet: <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">pip install pybullet</code>. Run the examples: <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">python -m pybullet_data</code></div>
          <div class="step"><span class="step-n">2</span>Load the Husky robot URDF. Set up gravity, a ground plane, and some box obstacles.</div>
          <div class="step"><span class="step-n">3</span>Control the robot by setting joint velocities on the wheel joints. Write a simple function: <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">drive(forward_speed, turn_speed)</code></div>
          <div class="step"><span class="step-n">4</span>Read the robot's position and orientation from PyBullet each step. Log and plot the trajectory.</div>
          <div class="step"><span class="step-n">5</span>Implement keyboard control — arrow keys drive the robot. Drive it around avoiding obstacles manually.</div>
        </div>
        <div class="project-learn">You learn: <span>PyBullet setup, URDF robot models, simulation step loop, motor control</span></div>
        <div class="project-tools"><span class="tool-chip">PyBullet</span><span class="tool-chip">Python</span><span class="tool-chip">NumPy</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">21</div>
        <div class="project-title-block">
          <div class="project-name">Vision-Guided Robot — See and Navigate</div>
          <div class="project-tagline">Give your simulated robot a camera and make it navigate autonomously</div>
        </div>
        <div class="project-badges"><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-sim">🖥 SIMULATOR</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Add a camera to your PyBullet robot. The robot must navigate from start to goal using only its camera feed. Run your depth estimator on the camera image to detect obstacles. Build a local occupancy grid. Run A* to plan a path. Execute the path with a PID controller. This is the complete autonomous navigation loop in simulation.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Attach a virtual camera to the robot using PyBullet's computeViewMatrix and computeProjectionMatrix. Render the camera image each step.</div>
          <div class="step"><span class="step-n">2</span>Run MiDaS (faster than ZoeDepth on CPU) on each camera frame. Build a local 2D occupancy grid from the depth output.</div>
          <div class="step"><span class="step-n">3</span>Run A* on the local grid to find a path to the goal direction.</div>
          <div class="step"><span class="step-n">4</span>Implement a PID controller: compute heading error to next waypoint. Convert to left/right wheel speed commands. Send to robot.</div>
          <div class="step"><span class="step-n">5</span>Run a full trial: place the robot at one end of a room with 3 obstacles between it and the goal. Watch it navigate autonomously using only camera.</div>
        </div>
        <div class="project-learn">You learn: <span>The full perception-planning-control loop, PID control, integrating all previous components into one system</span></div>
        <div class="project-tools"><span class="tool-chip">PyBullet</span><span class="tool-chip">MiDaS</span><span class="tool-chip">NumPy</span><span class="tool-chip">OpenCV</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">22</div>
        <div class="project-title-block">
          <div class="project-name">CARLA — Your First Self-Driving Car</div>
          <div class="project-tagline">Get a car driving itself in a full urban simulation</div>
        </div>
        <div class="project-badges"><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-sim">🖥 SIMULATOR</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Install CARLA. Spawn a car with a camera sensor. Read the camera feed via the CARLA Python API. Run your lane detection (Project 05's vanishing point) and depth estimation on the feed. Implement a simple lane-following controller. Watch the car drive itself down a road in a full simulated city.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Download CARLA 0.9.15 from carla.org. Extract and run CarlaUE4.exe. It will open a city simulation.</div>
          <div class="step"><span class="step-n">2</span>In a separate terminal, connect with Python: <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">import carla; client = carla.Client('localhost', 2000)</code></div>
          <div class="step"><span class="step-n">3</span>Spawn a vehicle and attach a camera sensor to it. Set up a callback to receive camera images as NumPy arrays.</div>
          <div class="step"><span class="step-n">4</span>Process each frame: run your bird's-eye-view homography transform. Detect lane markings. Estimate the car's lateral offset from lane centre.</div>
          <div class="step"><span class="step-n">5</span>Send steering commands proportional to lane offset: <code style="background:#111;padding:2px 6px;border-radius:2px;font-size:11px">vehicle.apply_control(carla.VehicleControl(throttle=0.3, steer=steer_value))</code></div>
          <div class="step"><span class="step-n">6</span>Run it on a straight road first, then a curved road. Record the camera feed + steering output as a video. This is your second portfolio piece.</div>
        </div>
        <div class="project-learn">You learn: <span>CARLA API, sensor callbacks, lane detection, proportional control — your first real self-driving car demo</span></div>
        <div class="project-tools"><span class="tool-chip">CARLA 0.9.15</span><span class="tool-chip">OpenCV</span><span class="tool-chip">NumPy</span><span class="tool-chip">Python</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">23</div>
        <div class="project-title-block">
          <div class="project-name">Imitation Learning Driver in CARLA</div>
          <div class="project-tagline">Train a neural network to drive by watching you drive</div>
        </div>
        <div class="project-badges"><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-kaggle">☁ KAGGLE</span><span class="badge badge-stretch">STRETCH</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Drive a CARLA car manually using keyboard. Record every camera frame paired with your steering and throttle inputs. Train a small CNN on Kaggle that takes an image and predicts your control outputs. Deploy it back in CARLA. Watch it drive the way you drove — learned entirely from your demonstrations. This is the NVIDIA end-to-end driving approach from 2016, which you will recreate.</div>
        <div class="project-steps">
          <div class="project-steps-label">Steps</div>
          <div class="step"><span class="step-n">1</span>Drive the CARLA car manually for 20 minutes on several routes. Record: frame image + (steering, throttle) to CSV. Collect ~10,000 frame-label pairs.</div>
          <div class="step"><span class="step-n">2</span>On Kaggle: build a dataset class. Augment with random brightness, horizontal flip (flip image + negate steering).</div>
          <div class="step"><span class="step-n">3</span>Build a CNN: 5 conv layers + 3 FC layers. Output: steering value (-1 to 1) and throttle (0 to 1). Use MSE loss.</div>
          <div class="step"><span class="step-n">4</span>Train for 50 epochs. Validate on a held-out set. Monitor that both steering and throttle losses decrease.</div>
          <div class="step"><span class="step-n">5</span>Deploy in CARLA: load the model, feed each camera frame, send the predicted controls to the vehicle. Record a video of autonomous driving.</div>
        </div>
        <div class="project-learn">You learn: <span>Imitation learning, end-to-end driving, data collection for autonomous systems, the NVIDIA 2016 approach</span></div>
        <div class="project-tools"><span class="tool-chip">CARLA</span><span class="tool-chip">PyTorch</span><span class="tool-chip">Kaggle GPU</span><span class="tool-chip">OpenCV</span></div>
      </div>
    </div>
  </div>

  <div class="math-ref">
    <button class="math-ref-toggle" onclick="toggleMath(this)">
      <span>📐 Math Reference — Read When a Project Breaks</span><span>▼</span>
    </button>
    <div class="math-ref-body">
      <div class="math-row"><div><div class="math-topic">PID Control</div><div class="math-src">Any control systems textbook, Ch. 1</div></div><div class="math-why">Why your robot oscillates or overshoots. Read when Project 21's robot wiggles instead of going straight.</div></div>
      <div class="math-row"><div><div class="math-topic">A* and Dijkstra's Algorithm</div><div class="math-src">LaValle, Planning Algorithms Ch. 2</div></div><div class="math-why">The formal proof of A* optimality. Read after Project 19 when you want to understand why A* is guaranteed to find the shortest path.</div></div>
      <div class="math-row"><div><div class="math-topic">Backpropagation</div><div class="math-src">Goodfellow, Deep Learning Ch. 6</div></div><div class="math-why">How your CNN in Project 23 actually learns. Read when training loss won't decrease.</div></div>
    </div>
  </div>

  <div class="refs-grid">
    <div class="ref-block">
      <div class="ref-head s5-color">Key Papers</div>
      <div class="ref-body">
        <div class="ref-item"><div class="ref-title">End to End Learning for Self-Driving Cars</div><div class="ref-sub">Bojarski et al., NVIDIA, 2016 — what Project 23 recreates</div></div>
        <div class="ref-item"><div class="ref-title">Learning to Drive in a Day</div><div class="ref-sub">Kendall et al., Wayve, 2019</div></div>
        <div class="ref-item"><div class="ref-title">UniAD: Planning-Oriented Autonomous Driving</div><div class="ref-sub">Hu et al., CVPR 2023 Best Paper</div></div>
      </div>
    </div>
    <div class="ref-block">
      <div class="ref-head s5-color">Primary Books</div>
      <div class="ref-body">
        <div class="ref-item"><div class="ref-title">Planning Algorithms</div><div class="ref-sub">LaValle — free at lavalle.pl/planning</div></div>
        <div class="ref-item"><div class="ref-title">Probabilistic Robotics</div><div class="ref-sub">Thrun — Ch. 6, 7 on planning under uncertainty</div></div>
      </div>
    </div>
  </div>

  <div class="exit-block s5-exit">
    <div class="exit-label s5-color">Stage 5 Exit — You Are Ready When</div>
    <div class="exit-text">You have a simulated robot navigating autonomously in PyBullet using only its camera. You have a CARLA car following lanes. You have a CNN trained on your own driving data that controls a car in simulation. You have two portfolio demo videos. You are no longer a beginner.</div>
  </div>
</div>

<!-- ===== STAGE 6 ===== -->
<div class="stage" id="s6">
  <div class="stage-header">
    <div class="stage-number">06</div>
    <div class="stage-meta">
      <div class="stage-tag s6-tag">Full Stack</div>
      <div class="stage-name s6-color">The Complete System</div>
      <div class="stage-subtitle">Integration · Research · Portfolio · Deployment</div>
      <div class="stage-duration">12–16 weeks · Full hardware + Cloud</div>
    </div>
  </div>
  <div class="stage-desc">Everything you have built becomes one system. You are not working on components anymore — you are an autonomous vision engineer. This stage is about building the capstone that proves it, and pushing into the research frontier.</div>

  <div class="projects-section">
    <div class="projects-label">Projects</div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">24</div>
        <div class="project-title-block">
          <div class="project-name">RRT* Planner with Dynamic Obstacles</div>
          <div class="project-tagline">Plan paths in spaces too complex for grid search</div>
        </div>
        <div class="project-badges"><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-core">CORE</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Implement RRT and RRT* from scratch. Test in a 2D environment with polygon obstacles. Show that RRT* produces shorter paths as samples increase. Then use it in PyBullet for a robot arm reaching around obstacles — where grid-based A* cannot work because the configuration space is too high-dimensional.</div>
        <div class="project-tools"><span class="tool-chip">NumPy</span><span class="tool-chip">Matplotlib</span><span class="tool-chip">PyBullet</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">25</div>
        <div class="project-title-block">
          <div class="project-name">3D Gaussian Splat Your Campus</div>
          <div class="project-tagline">Build a real-time navigable neural map of a real location</div>
        </div>
        <div class="project-badges"><span class="badge badge-phone">📱 PHONE</span><span class="badge badge-kaggle">☁ KAGGLE</span><span class="badge badge-stretch">STRETCH</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Walk around a building at FUNAAB taking 200+ photos. Run COLMAP for poses. Train a 3D Gaussian Splat on Kaggle. The result renders at real-time framerates unlike NeRF. Navigate through your neural reconstruction of a real place you know. This is the current frontier of neural mapping for autonomous systems.</div>
        <div class="project-tools"><span class="tool-chip">gaussian-splatting repo</span><span class="tool-chip">COLMAP</span><span class="tool-chip">Kaggle GPU</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">26</div>
        <div class="project-title-block">
          <div class="project-name">Language-Commanded Robot</div>
          <div class="project-tagline">"Go to the door" — robot executes using your semantic map</div>
        </div>
        <div class="project-badges"><span class="badge badge-laptop">💻 LAPTOP</span><span class="badge badge-sim">🖥 SIMULATOR</span><span class="badge badge-stretch">STRETCH</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Combine your semantic map from Stage 4 with your navigation system from Stage 5. Type a command — "navigate to the chair" — the system looks up the chair's location in the semantic map, plans a path with A*, and executes it in PyBullet. Language to motion, end to end.</div>
        <div class="project-tools"><span class="tool-chip">PyBullet</span><span class="tool-chip">Semantic Map</span><span class="tool-chip">A*</span><span class="tool-chip">Python</span></div>
      </div>
    </div>

    <div class="project-card">
      <div class="project-card-header">
        <div class="project-num">27</div>
        <div class="project-title-block">
          <div class="project-name">Reproduce a Research Paper</div>
          <div class="project-tagline">Pick one paper and build exactly what it describes from scratch</div>
        </div>
        <div class="project-badges"><span class="badge badge-kaggle">☁ KAGGLE</span><span class="badge badge-stretch">RESEARCH</span></div>
      </div>
      <div class="project-body">
        <div class="project-goal">Pick one paper from your reading list — RAFT, DepthPro, or SuperPoint are good candidates. Read it fully. Implement it from scratch in PyTorch. Train on the dataset they used. Compare your results to theirs. Write a brief report. This is your first research contribution and the standard interview task at top robotics companies.</div>
        <div class="project-tools"><span class="tool-chip">PyTorch</span><span class="tool-chip">Kaggle GPU</span><span class="tool-chip">Weights & Biases</span></div>
      </div>
    </div>
  </div>

  <!-- CAPSTONE -->
  <div class="capstone">
    <div class="capstone-label">Final Project — Your Portfolio Centrepiece</div>
    <div class="capstone-title">Camera-Only Autonomous Navigator in CARLA</div>
    <div class="capstone-desc">Build a complete autonomous navigation system in CARLA that operates using only camera input — no GPS, no LiDAR, no ground truth position. Navigate from start to goal in an urban environment, handling dynamic obstacles, intersections, and failure conditions. Every component is one you built yourself in the previous 27 projects.</div>
    <div class="capstone-req"><span class="req-bullet">◆</span><span>Perception — semantic segmentation + monocular depth from camera only (Stage 2)</span></div>
    <div class="capstone-req"><span class="req-bullet">◆</span><span>Localisation — visual odometry to estimate position without GPS (Stage 3)</span></div>
    <div class="capstone-req"><span class="req-bullet">◆</span><span>Mapping — occupancy grid built incrementally from depth (Stage 4)</span></div>
    <div class="capstone-req"><span class="req-bullet">◆</span><span>Planning — A* or RRT on the occupancy grid to reach goal (Stage 5)</span></div>
    <div class="capstone-req"><span class="req-bullet">◆</span><span>Control — PID controller executing the path (Stage 5)</span></div>
    <div class="capstone-req"><span class="req-bullet">◆</span><span>Dynamic obstacles — detect, track, and replan around moving agents (Stage 2)</span></div>
    <div class="capstone-req"><span class="req-bullet">◆</span><span>Failure handling — graceful recovery when components fail</span></div>
    <div class="capstone-req"><span class="req-bullet">◆</span><span>Documentation — written technical report + demo video posted publicly</span></div>
  </div>

  <div class="refs-grid" style="margin-top:24px">
    <div class="ref-block">
      <div class="ref-head s6-color">Frontier Papers to Read in Stage 6</div>
      <div class="ref-body">
        <div class="ref-item"><div class="ref-title">BEVFormer: Bird's-Eye-View Representation from Multi-Camera Images</div><div class="ref-sub">Li et al., 2022</div></div>
        <div class="ref-item"><div class="ref-title">BEVFusion: Multi-Task Multi-Sensor Fusion</div><div class="ref-sub">Liu et al., 2023</div></div>
        <div class="ref-item"><div class="ref-title">OpenVLA: An Open-Source Vision-Language-Action Model</div><div class="ref-sub">Kim et al., 2024</div></div>
        <div class="ref-item"><div class="ref-title">π0: A Vision-Language-Action Flow Model</div><div class="ref-sub">Black et al., 2024</div></div>
        <div class="ref-item"><div class="ref-title">Wayve GAIA-1: A Generative World Model for Autonomous Driving</div><div class="ref-sub">Hu et al., 2023</div></div>
      </div>
    </div>
    <div class="ref-block">
      <div class="ref-head s6-color">Tools Added in Stage 6</div>
      <div class="ref-body">
        <div class="ref-item"><div class="ref-title">ROS2</div><div class="ref-sub">Standard robotics middleware — required for hardware deployment</div></div>
        <div class="ref-item"><div class="ref-title">nuScenes + Waymo Datasets</div><div class="ref-sub">Real autonomous driving data for training and benchmarking</div></div>
        <div class="ref-item"><div class="ref-title">Weights & Biases</div><div class="ref-sub">Experiment tracking — log every training run</div></div>
        <div class="ref-item"><div class="ref-title">MMDetection3D</div><div class="ref-sub">3D detection framework — for when you add LiDAR</div></div>
      </div>
    </div>
  </div>
</div>

</div><!-- end main -->

<script>
function nav(id, btn) {
  document.getElementById(id).scrollIntoView({ behavior: 'smooth', block: 'start' });
  document.querySelectorAll('.nav-btn').forEach(b => { b.classList.remove('active'); b.style.color=''; b.style.borderBottomColor=''; });
  btn.classList.add('active');
  const c = {s1:'var(--s1)',s2:'var(--s2)',s3:'var(--s3)',s4:'var(--s4)',s5:'var(--s5)',s6:'var(--s6)'};
  btn.style.color = c[id]; btn.style.borderBottomColor = c[id];
}
function toggleMath(btn) {
  const body = btn.nextElementSibling;
  body.classList.toggle('open');
  btn.querySelector('span:last-child').textContent = body.classList.contains('open') ? '▲' : '▼';
}
const stages = ['s1','s2','s3','s4','s5','s6'];
const navBtns = document.querySelectorAll('.nav-btn');
const colors = ['var(--s1)','var(--s2)','var(--s3)','var(--s4)','var(--s5)','var(--s6)'];
window.addEventListener('scroll', () => {
  let cur = 0;
  stages.forEach((id,i) => { const el=document.getElementById(id); if(el && window.scrollY >= el.offsetTop-120) cur=i; });
  navBtns.forEach((b,i) => { b.classList.remove('active'); b.style.color=''; b.style.borderBottomColor=''; });
  navBtns[cur].classList.add('active'); navBtns[cur].style.color=colors[cur]; navBtns[cur].style.borderBottomColor=colors[cur];
});
</script>
</body>
</html>
