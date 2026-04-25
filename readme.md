<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Santhosh Iyyappan — AI Systems Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;800;900&family=Share+Tech+Mono&family=Rajdhani:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>
:root {
  --cyan: #00F7FF;
  --purple: #7C3AED;
  --pink: #FF2D78;
  --green: #00FF88;
  --orange: #FF6B00;
  --dark: #030712;
  --dark2: #0a0f1e;
  --dark3: #0d1629;
  --grid: rgba(0,247,255,0.04);
  --glow: 0 0 20px rgba(0,247,255,0.3);
  --glow-purple: 0 0 20px rgba(124,58,237,0.4);
}

* { margin: 0; padding: 0; box-sizing: border-box; }

html { scroll-behavior: smooth; }

body {
  background: var(--dark);
  color: #e2e8f0;
  font-family: 'Rajdhani', sans-serif;
  overflow-x: hidden;
  cursor: none;
}

/* CUSTOM CURSOR */
#cursor {
  position: fixed;
  width: 20px; height: 20px;
  border: 2px solid var(--cyan);
  border-radius: 50%;
  pointer-events: none;
  z-index: 9999;
  transition: transform 0.1s, border-color 0.2s;
  mix-blend-mode: screen;
}
#cursor-dot {
  position: fixed;
  width: 4px; height: 4px;
  background: var(--cyan);
  border-radius: 50%;
  pointer-events: none;
  z-index: 9999;
  mix-blend-mode: screen;
}
body:hover #cursor { transform: scale(1); }

/* SCANLINES */
body::before {
  content: '';
  position: fixed;
  top: 0; left: 0; right: 0; bottom: 0;
  background: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,0,0,0.05) 2px, rgba(0,0,0,0.05) 4px);
  pointer-events: none;
  z-index: 1000;
}

/* GRID BG */
.grid-bg {
  position: fixed;
  inset: 0;
  background-image:
    linear-gradient(var(--grid) 1px, transparent 1px),
    linear-gradient(90deg, var(--grid) 1px, transparent 1px);
  background-size: 40px 40px;
  pointer-events: none;
  z-index: 0;
}

/* PARTICLES */
#particles { position: fixed; inset: 0; z-index: 0; pointer-events: none; }

/* NAV */
nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 500;
  padding: 14px 32px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: rgba(3,7,18,0.8);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid rgba(0,247,255,0.12);
}
.nav-logo {
  font-family: 'Orbitron', monospace;
  font-size: 18px;
  font-weight: 900;
  color: var(--cyan);
  text-shadow: var(--glow);
  letter-spacing: 2px;
}
.nav-links { display: flex; gap: 28px; }
.nav-links a {
  font-family: 'Share Tech Mono', monospace;
  font-size: 12px;
  color: rgba(226,232,240,0.6);
  text-decoration: none;
  letter-spacing: 1px;
  transition: color 0.2s;
}
.nav-links a:hover { color: var(--cyan); }
.nav-status {
  display: flex;
  align-items: center;
  gap: 8px;
  font-family: 'Share Tech Mono', monospace;
  font-size: 11px;
  color: var(--green);
}
.status-dot {
  width: 8px; height: 8px;
  background: var(--green);
  border-radius: 50%;
  animation: pulse-green 2s infinite;
}
@keyframes pulse-green {
  0%, 100% { box-shadow: 0 0 0 0 rgba(0,255,136,0.4); }
  50% { box-shadow: 0 0 0 6px rgba(0,255,136,0); }
}

/* WRAPPER */
.wrapper { position: relative; z-index: 10; }

/* HERO */
.hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 100px 24px 60px;
  text-align: center;
  position: relative;
}
.hero-eyebrow {
  font-family: 'Share Tech Mono', monospace;
  font-size: 12px;
  color: var(--cyan);
  letter-spacing: 4px;
  margin-bottom: 20px;
  opacity: 0;
  animation: fadeUp 0.8s 0.3s forwards;
}
.hero-name {
  font-family: 'Orbitron', monospace;
  font-size: clamp(40px, 7vw, 88px);
  font-weight: 900;
  line-height: 1;
  letter-spacing: -1px;
  margin-bottom: 10px;
  opacity: 0;
  animation: fadeUp 0.8s 0.5s forwards;
}
.hero-name .first { color: #fff; }
.hero-name .last {
  color: var(--cyan);
  text-shadow: 0 0 40px rgba(0,247,255,0.5);
}
.hero-title {
  font-family: 'Share Tech Mono', monospace;
  font-size: clamp(14px, 2.5vw, 22px);
  color: rgba(226,232,240,0.7);
  letter-spacing: 2px;
  margin-bottom: 32px;
  opacity: 0;
  animation: fadeUp 0.8s 0.7s forwards;
}
.hero-title span { color: var(--purple); }
.cgpa-badge {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 10px 24px;
  border: 1px solid rgba(0,247,255,0.3);
  border-radius: 4px;
  font-family: 'Share Tech Mono', monospace;
  font-size: 13px;
  color: var(--cyan);
  background: rgba(0,247,255,0.05);
  margin-bottom: 40px;
  opacity: 0;
  animation: fadeUp 0.8s 0.9s forwards;
}
.cgpa-badge .cgpa-num {
  font-size: 22px;
  font-weight: 700;
  font-family: 'Orbitron', monospace;
  color: var(--green);
  text-shadow: 0 0 15px rgba(0,255,136,0.5);
}
.hero-tags {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  justify-content: center;
  opacity: 0;
  animation: fadeUp 0.8s 1.1s forwards;
  margin-bottom: 50px;
}
.tag {
  padding: 6px 16px;
  background: rgba(124,58,237,0.15);
  border: 1px solid rgba(124,58,237,0.4);
  border-radius: 2px;
  font-family: 'Share Tech Mono', monospace;
  font-size: 11px;
  color: #c4b5fd;
  letter-spacing: 1px;
  transition: all 0.2s;
}
.tag:hover {
  background: rgba(124,58,237,0.3);
  border-color: var(--purple);
  color: #fff;
}
.hero-cta {
  display: flex;
  gap: 16px;
  opacity: 0;
  animation: fadeUp 0.8s 1.3s forwards;
}
.btn-primary {
  padding: 14px 32px;
  background: var(--cyan);
  color: var(--dark);
  font-family: 'Orbitron', monospace;
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 2px;
  border: none;
  cursor: pointer;
  text-decoration: none;
  display: inline-block;
  clip-path: polygon(8px 0%, 100% 0%, calc(100% - 8px) 100%, 0% 100%);
  transition: all 0.2s;
}
.btn-primary:hover { background: #fff; transform: translateY(-2px); }
.btn-secondary {
  padding: 14px 32px;
  background: transparent;
  color: var(--cyan);
  font-family: 'Orbitron', monospace;
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 2px;
  border: 1px solid var(--cyan);
  cursor: pointer;
  text-decoration: none;
  display: inline-block;
  clip-path: polygon(8px 0%, 100% 0%, calc(100% - 8px) 100%, 0% 100%);
  transition: all 0.2s;
}
.btn-secondary:hover { background: rgba(0,247,255,0.1); }

/* SCROLL INDICATOR */
.scroll-indicator {
  position: absolute;
  bottom: 30px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  opacity: 0;
  animation: fadeUp 0.8s 1.8s forwards;
}
.scroll-line {
  width: 1px;
  height: 50px;
  background: linear-gradient(to bottom, var(--cyan), transparent);
  animation: scrollPulse 2s infinite;
}
@keyframes scrollPulse {
  0% { opacity: 0; transform: scaleY(0); transform-origin: top; }
  50% { opacity: 1; transform: scaleY(1); }
  100% { opacity: 0; transform: scaleY(0); transform-origin: bottom; }
}
.scroll-text {
  font-family: 'Share Tech Mono', monospace;
  font-size: 10px;
  color: rgba(0,247,255,0.5);
  letter-spacing: 3px;
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

/* SECTION */
section { padding: 80px 24px; max-width: 1200px; margin: 0 auto; }
.section-header {
  display: flex;
  align-items: center;
  gap: 16px;
  margin-bottom: 50px;
}
.section-num {
  font-family: 'Share Tech Mono', monospace;
  font-size: 12px;
  color: var(--cyan);
  letter-spacing: 2px;
}
.section-title {
  font-family: 'Orbitron', monospace;
  font-size: clamp(20px, 3vw, 30px);
  font-weight: 800;
  color: #fff;
  letter-spacing: 2px;
}
.section-line {
  flex: 1;
  height: 1px;
  background: linear-gradient(to right, rgba(0,247,255,0.3), transparent);
}

/* LIVE STATS */
.live-stats {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 16px;
  margin-bottom: 60px;
}
.stat-card {
  background: rgba(10,15,30,0.8);
  border: 1px solid rgba(0,247,255,0.15);
  border-radius: 4px;
  padding: 24px;
  text-align: center;
  position: relative;
  overflow: hidden;
  transition: all 0.3s;
}
.stat-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 2px;
  background: var(--cyan);
}
.stat-card:hover {
  border-color: rgba(0,247,255,0.4);
  transform: translateY(-4px);
  box-shadow: 0 8px 30px rgba(0,247,255,0.1);
}
.stat-card.purple::before { background: var(--purple); }
.stat-card.purple { border-color: rgba(124,58,237,0.2); }
.stat-card.purple:hover { border-color: rgba(124,58,237,0.5); box-shadow: 0 8px 30px rgba(124,58,237,0.15); }
.stat-card.pink::before { background: var(--pink); }
.stat-card.green::before { background: var(--green); }
.stat-card.orange::before { background: var(--orange); }
.stat-value {
  font-family: 'Orbitron', monospace;
  font-size: 36px;
  font-weight: 900;
  color: var(--cyan);
  text-shadow: var(--glow);
  display: block;
  margin-bottom: 6px;
}
.stat-card.purple .stat-value { color: #c4b5fd; text-shadow: var(--glow-purple); }
.stat-card.pink .stat-value { color: #ff8ab0; text-shadow: 0 0 20px rgba(255,45,120,0.3); }
.stat-card.green .stat-value { color: var(--green); text-shadow: 0 0 20px rgba(0,255,136,0.3); }
.stat-label {
  font-family: 'Share Tech Mono', monospace;
  font-size: 11px;
  color: rgba(226,232,240,0.5);
  letter-spacing: 2px;
  text-transform: uppercase;
}
.stat-live {
  position: absolute;
  top: 10px; right: 10px;
  font-family: 'Share Tech Mono', monospace;
  font-size: 9px;
  color: var(--green);
  letter-spacing: 1px;
  display: flex;
  align-items: center;
  gap: 4px;
}
.live-dot {
  width: 5px; height: 5px;
  background: var(--green);
  border-radius: 50%;
  animation: pulse-green 1.5s infinite;
}

/* SKILLS MATRIX */
.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
}
.skill-category {
  background: rgba(10,15,30,0.8);
  border: 1px solid rgba(0,247,255,0.1);
  border-radius: 4px;
  padding: 28px;
  transition: all 0.3s;
}
.skill-category:hover {
  border-color: rgba(0,247,255,0.25);
  box-shadow: inset 0 0 40px rgba(0,247,255,0.03);
}
.skill-cat-title {
  font-family: 'Orbitron', monospace;
  font-size: 13px;
  font-weight: 700;
  color: var(--cyan);
  letter-spacing: 2px;
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  gap: 10px;
}
.skill-cat-title .cat-icon { font-size: 18px; }
.skill-item {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 14px;
}
.skill-name {
  font-family: 'Share Tech Mono', monospace;
  font-size: 12px;
  color: rgba(226,232,240,0.8);
  width: 110px;
  flex-shrink: 0;
}
.skill-bar-bg {
  flex: 1;
  height: 4px;
  background: rgba(255,255,255,0.05);
  border-radius: 2px;
  overflow: hidden;
}
.skill-bar {
  height: 100%;
  border-radius: 2px;
  background: linear-gradient(90deg, var(--cyan), var(--purple));
  width: 0%;
  transition: width 1.5s cubic-bezier(0.16, 1, 0.3, 1);
}
.skill-pct {
  font-family: 'Share Tech Mono', monospace;
  font-size: 11px;
  color: rgba(226,232,240,0.4);
  width: 36px;
  text-align: right;
}

/* PROJECTS */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
  gap: 20px;
}
.project-card {
  background: rgba(10,15,30,0.9);
  border: 1px solid rgba(0,247,255,0.1);
  border-radius: 4px;
  padding: 32px;
  position: relative;
  overflow: hidden;
  transition: all 0.3s;
  cursor: pointer;
}
.project-card::after {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at var(--mx, 50%) var(--my, 50%), rgba(0,247,255,0.05) 0%, transparent 60%);
  pointer-events: none;
  opacity: 0;
  transition: opacity 0.3s;
}
.project-card:hover::after { opacity: 1; }
.project-card:hover {
  border-color: rgba(0,247,255,0.3);
  transform: translateY(-6px);
  box-shadow: 0 20px 40px rgba(0,0,0,0.4);
}
.project-num {
  font-family: 'Orbitron', monospace;
  font-size: 60px;
  font-weight: 900;
  color: rgba(0,247,255,0.04);
  position: absolute;
  top: -10px;
  right: 20px;
  line-height: 1;
  pointer-events: none;
}
.project-tag {
  display: inline-block;
  padding: 4px 12px;
  background: rgba(124,58,237,0.2);
  border: 1px solid rgba(124,58,237,0.3);
  border-radius: 2px;
  font-family: 'Share Tech Mono', monospace;
  font-size: 10px;
  color: #c4b5fd;
  letter-spacing: 1px;
  margin-bottom: 16px;
}
.project-title {
  font-family: 'Orbitron', monospace;
  font-size: 16px;
  font-weight: 700;
  color: #fff;
  margin-bottom: 12px;
  letter-spacing: 1px;
}
.project-desc {
  font-size: 14px;
  color: rgba(226,232,240,0.6);
  line-height: 1.6;
  margin-bottom: 20px;
}
.project-stats {
  display: flex;
  gap: 16px;
  margin-bottom: 20px;
}
.project-stat {
  display: flex;
  align-items: center;
  gap: 6px;
  font-family: 'Share Tech Mono', monospace;
  font-size: 12px;
  color: rgba(226,232,240,0.5);
}
.project-stat .pstat-val { color: var(--cyan); }
.project-tech {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
}
.tech-chip {
  padding: 3px 10px;
  background: rgba(0,247,255,0.05);
  border: 1px solid rgba(0,247,255,0.15);
  border-radius: 2px;
  font-family: 'Share Tech Mono', monospace;
  font-size: 10px;
  color: rgba(0,247,255,0.7);
  letter-spacing: 0.5px;
}

/* TERMINAL */
.terminal {
  background: #030d1a;
  border: 1px solid rgba(0,247,255,0.2);
  border-radius: 6px;
  overflow: hidden;
  margin-bottom: 40px;
}
.terminal-bar {
  background: rgba(0,247,255,0.06);
  padding: 12px 18px;
  display: flex;
  align-items: center;
  gap: 8px;
  border-bottom: 1px solid rgba(0,247,255,0.1);
}
.term-btn {
  width: 10px; height: 10px;
  border-radius: 50%;
}
.term-btn.red { background: #FF5F57; }
.term-btn.yellow { background: #FFBD2E; }
.term-btn.green { background: #28C840; }
.term-title {
  font-family: 'Share Tech Mono', monospace;
  font-size: 11px;
  color: rgba(0,247,255,0.5);
  margin-left: 10px;
  letter-spacing: 1px;
}
.terminal-body {
  padding: 24px;
  font-family: 'Share Tech Mono', monospace;
  font-size: 13px;
  line-height: 1.8;
  min-height: 140px;
}
.term-line { display: flex; gap: 8px; }
.term-prompt { color: var(--green); }
.term-cmd { color: var(--cyan); }
.term-output { color: rgba(226,232,240,0.7); }
.term-output.success { color: var(--green); }
.term-output.error { color: var(--pink); }
.term-output.warn { color: var(--orange); }
#term-cursor {
  display: inline-block;
  width: 8px; height: 14px;
  background: var(--cyan);
  animation: blink 1s step-end infinite;
  vertical-align: middle;
}
@keyframes blink { 50% { opacity: 0; } }

/* === AI GAME === */
#game-section {
  padding: 80px 24px;
  max-width: 1200px;
  margin: 0 auto;
}
.game-container {
  background: rgba(3,7,18,0.95);
  border: 1px solid rgba(0,247,255,0.2);
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 0 60px rgba(0,247,255,0.05);
}
.game-header {
  background: rgba(0,247,255,0.05);
  padding: 18px 28px;
  border-bottom: 1px solid rgba(0,247,255,0.15);
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 12px;
}
.game-title {
  font-family: 'Orbitron', monospace;
  font-size: 16px;
  font-weight: 800;
  color: var(--cyan);
  letter-spacing: 3px;
  text-shadow: var(--glow);
}
.game-hud {
  display: flex;
  gap: 20px;
  align-items: center;
}
.hud-item {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.hud-label {
  font-family: 'Share Tech Mono', monospace;
  font-size: 9px;
  color: rgba(226,232,240,0.4);
  letter-spacing: 2px;
  margin-bottom: 2px;
}
.hud-value {
  font-family: 'Orbitron', monospace;
  font-size: 18px;
  font-weight: 700;
  color: var(--cyan);
}
.hud-value.purple { color: #c4b5fd; }
.hud-value.green { color: var(--green); }
.game-body {
  padding: 32px;
}
.game-question-area {
  min-height: 180px;
  background: rgba(0,247,255,0.02);
  border: 1px solid rgba(0,247,255,0.08);
  border-radius: 6px;
  padding: 28px;
  margin-bottom: 24px;
  position: relative;
}
.game-level-badge {
  position: absolute;
  top: 16px; right: 16px;
  font-family: 'Share Tech Mono', monospace;
  font-size: 10px;
  color: var(--orange);
  letter-spacing: 2px;
  padding: 4px 10px;
  border: 1px solid rgba(255,107,0,0.3);
  border-radius: 2px;
  background: rgba(255,107,0,0.1);
}
.game-q-category {
  font-family: 'Share Tech Mono', monospace;
  font-size: 11px;
  color: var(--purple);
  letter-spacing: 2px;
  margin-bottom: 14px;
}
.game-question {
  font-family: 'Rajdhani', sans-serif;
  font-size: 20px;
  font-weight: 600;
  color: #fff;
  line-height: 1.5;
}
.game-code {
  background: rgba(0,0,0,0.4);
  border: 1px solid rgba(0,247,255,0.1);
  border-radius: 4px;
  padding: 14px;
  margin-top: 14px;
  font-family: 'Share Tech Mono', monospace;
  font-size: 12px;
  color: var(--cyan);
  line-height: 1.7;
  white-space: pre;
  overflow-x: auto;
}
.game-options {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
  margin-bottom: 24px;
}
.game-option {
  padding: 16px 20px;
  background: rgba(10,15,30,0.8);
  border: 1px solid rgba(0,247,255,0.15);
  border-radius: 4px;
  font-family: 'Rajdhani', sans-serif;
  font-size: 15px;
  font-weight: 500;
  color: rgba(226,232,240,0.8);
  cursor: pointer;
  text-align: left;
  transition: all 0.2s;
  display: flex;
  align-items: center;
  gap: 12px;
}
.game-option:hover {
  border-color: rgba(0,247,255,0.4);
  background: rgba(0,247,255,0.06);
  color: #fff;
  transform: translateX(4px);
}
.game-option.correct {
  background: rgba(0,255,136,0.1);
  border-color: var(--green);
  color: var(--green);
}
.game-option.wrong {
  background: rgba(255,45,120,0.1);
  border-color: var(--pink);
  color: var(--pink);
}
.game-option.disabled { cursor: default; pointer-events: none; }
.opt-letter {
  width: 26px; height: 26px;
  border: 1px solid rgba(0,247,255,0.3);
  border-radius: 2px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Orbitron', monospace;
  font-size: 11px;
  font-weight: 700;
  color: var(--cyan);
  flex-shrink: 0;
}
.game-option.correct .opt-letter { border-color: var(--green); color: var(--green); }
.game-option.wrong .opt-letter { border-color: var(--pink); color: var(--pink); }
.game-feedback {
  padding: 16px 20px;
  border-radius: 4px;
  font-family: 'Share Tech Mono', monospace;
  font-size: 13px;
  line-height: 1.6;
  margin-bottom: 20px;
  display: none;
}
.game-feedback.show { display: block; animation: fadeUp 0.3s; }
.game-feedback.correct-fb {
  background: rgba(0,255,136,0.08);
  border: 1px solid rgba(0,255,136,0.2);
  color: var(--green);
}
.game-feedback.wrong-fb {
  background: rgba(255,45,120,0.08);
  border: 1px solid rgba(255,45,120,0.2);
  color: #ff8ab0;
}
.game-controls {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 12px;
}
.game-progress {
  display: flex;
  gap: 6px;
}
.progress-pip {
  width: 24px; height: 4px;
  background: rgba(255,255,255,0.1);
  border-radius: 2px;
  transition: background 0.3s;
}
.progress-pip.done { background: var(--cyan); }
.progress-pip.correct { background: var(--green); }
.progress-pip.wrong { background: var(--pink); }
.btn-next {
  padding: 12px 28px;
  background: var(--cyan);
  color: var(--dark);
  font-family: 'Orbitron', monospace;
  font-size: 11px;
  font-weight: 800;
  letter-spacing: 2px;
  border: none;
  cursor: pointer;
  clip-path: polygon(6px 0%, 100% 0%, calc(100% - 6px) 100%, 0% 100%);
  transition: all 0.2s;
}
.btn-next:hover { background: #fff; }
.btn-next:disabled { opacity: 0.4; cursor: not-allowed; }
.game-over-screen {
  display: none;
  text-align: center;
  padding: 40px;
}
.game-over-screen.show { display: block; animation: fadeUp 0.5s; }
.game-over-title {
  font-family: 'Orbitron', monospace;
  font-size: 32px;
  font-weight: 900;
  color: var(--cyan);
  text-shadow: var(--glow);
  margin-bottom: 16px;
}
.final-score {
  font-family: 'Orbitron', monospace;
  font-size: 64px;
  font-weight: 900;
  colo