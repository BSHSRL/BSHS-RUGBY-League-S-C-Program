# BSHS-RUGBY-League-S-C-Program
Strength and conditioning RL
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
<title>Bundaberg SHS — RL Academy</title>
<link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@400;600;700;800;900&family=Barlow:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
:root {
  --navy: #0D2137;
  --navy2: #122840;
  --gold: #C9A227;
  --gold2: #E8B930;
  --blue: #1B4F8A;
  --steel: #2E6DA4;
  --ltblue: #D6E4F2;
  --pale: #EBF3FB;
  --white: #FFFFFF;
  --off: #F8F9FA;
  --gray: #8896A7;
  --border: rgba(255,255,255,0.08);
  --green: #1A7A42;
  --ltgreen: #D4EDDA;
  --orange: #C05020;
  --ltorange: #FAEAEA;
  --purple: #5A2A7A;
  --ltpurple: #EDE0F3;
  --teal: #1A7A7A;
  --ltteal: #D0EDED;
  --card: rgba(255,255,255,0.04);
  --card-hover: rgba(255,255,255,0.07);
  --radius: 12px;
  --radius-sm: 8px;
}
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { font-size: 16px; scroll-behavior: smooth; }
body {
  font-family: 'Barlow', sans-serif;
  background: var(--navy);
  color: var(--white);
  min-height: 100vh;
  overflow-x: hidden;
}

/* ── Scrollbar ─────────────────────────────────────────────────────────────── */
::-webkit-scrollbar { width: 4px; }
::-webkit-scrollbar-track { background: var(--navy); }
::-webkit-scrollbar-thumb { background: var(--gold); border-radius: 4px; }

/* ── Layout ────────────────────────────────────────────────────────────────── */
#app { display: flex; flex-direction: column; min-height: 100vh; }
.screen { display: none; flex-direction: column; min-height: 100vh; }
.screen.active { display: flex; }

/* ── Login Screen ──────────────────────────────────────────────────────────── */
#login {
  justify-content: center; align-items: center;
  background: linear-gradient(160deg, #0a1a2e 0%, #0D2137 40%, #0f2d50 100%);
  position: relative; overflow: hidden;
}
.login-bg {
  position: absolute; inset: 0; pointer-events: none;
  background: radial-gradient(ellipse 60% 40% at 50% -10%, rgba(201,162,39,0.12) 0%, transparent 70%),
              radial-gradient(ellipse 40% 30% at 90% 80%, rgba(27,79,138,0.2) 0%, transparent 60%);
}
.login-grid {
  position: absolute; inset: 0; pointer-events: none;
  background-image: linear-gradient(rgba(255,255,255,0.02) 1px, transparent 1px),
                    linear-gradient(90deg, rgba(255,255,255,0.02) 1px, transparent 1px);
  background-size: 40px 40px;
}
.login-box {
  position: relative; z-index: 1;
  width: 100%; max-width: 420px; padding: 0 24px;
}
.login-logo {
  text-align: center; margin-bottom: 40px;
}
.login-logo-badge {
  display: inline-block;
  background: var(--gold);
  color: var(--navy);
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 900;
  font-size: 11px;
  letter-spacing: 3px;
  padding: 6px 16px;
  border-radius: 3px;
  margin-bottom: 16px;
}
.login-title {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 900;
  font-size: 48px;
  line-height: 0.95;
  color: var(--white);
  margin-bottom: 8px;
}
.login-title span { color: var(--gold); }
.login-sub {
  font-size: 14px; color: var(--gray); letter-spacing: 0.5px;
}
.login-card {
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: var(--radius);
  padding: 28px;
  backdrop-filter: blur(10px);
}
.login-card h3 {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 700; font-size: 20px; letter-spacing: 1px;
  margin-bottom: 20px; color: var(--gold);
}
.form-group { margin-bottom: 16px; }
.form-group label {
  display: block; font-size: 11px; font-weight: 600;
  letter-spacing: 1.5px; color: var(--gray); margin-bottom: 6px;
  text-transform: uppercase;
}
.form-group input, .form-group select {
  width: 100%; padding: 12px 14px;
  background: rgba(255,255,255,0.06);
  border: 1px solid rgba(255,255,255,0.12);
  border-radius: var(--radius-sm);
  color: var(--white); font-family: 'Barlow', sans-serif; font-size: 15px;
  transition: border-color 0.2s;
  -webkit-appearance: none;
}
.form-group input:focus, .form-group select:focus {
  outline: none; border-color: var(--gold);
  background: rgba(255,255,255,0.08);
}
.form-group select option { background: var(--navy); color: var(--white); }
.btn {
  display: block; width: 100%; padding: 14px;
  background: var(--gold); color: var(--navy);
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 800; font-size: 16px; letter-spacing: 2px;
  border: none; border-radius: var(--radius-sm); cursor: pointer;
  transition: all 0.2s; text-transform: uppercase;
}
.btn:hover { background: var(--gold2); transform: translateY(-1px); box-shadow: 0 4px 20px rgba(201,162,39,0.3); }
.btn:active { transform: translateY(0); }
.btn-outline {
  background: transparent;
  border: 2px solid var(--gold);
  color: var(--gold);
}
.btn-outline:hover { background: rgba(201,162,39,0.1); transform: none; box-shadow: none; }
.btn-sm {
  display: inline-block; width: auto; padding: 8px 18px;
  font-size: 13px; letter-spacing: 1.5px;
}
.btn-ghost {
  background: rgba(255,255,255,0.06); color: var(--white);
  border: 1px solid rgba(255,255,255,0.1);
}
.btn-ghost:hover { background: rgba(255,255,255,0.1); }
.btn-green { background: var(--green); color: var(--white); }
.btn-green:hover { background: #1d8a4a; box-shadow: 0 4px 20px rgba(26,122,66,0.3); }
.btn-danger { background: var(--orange); color: var(--white); }
.login-switch {
  text-align: center; margin-top: 16px;
  font-size: 13px; color: var(--gray);
}
.login-switch a { color: var(--gold); cursor: pointer; font-weight: 600; text-decoration: none; }
.login-switch a:hover { text-decoration: underline; }

/* ── Main App Layout ───────────────────────────────────────────────────────── */
#main { flex-direction: row; }
.sidebar {
  width: 220px; flex-shrink: 0;
  background: rgba(0,0,0,0.25);
  border-right: 1px solid var(--border);
  display: flex; flex-direction: column;
  position: sticky; top: 0; height: 100vh;
}
.sidebar-logo {
  padding: 20px 18px 16px;
  border-bottom: 1px solid var(--border);
}
.sidebar-logo .badge {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 800; font-size: 10px; letter-spacing: 2px;
  color: var(--gold); background: rgba(201,162,39,0.15);
  padding: 3px 8px; border-radius: 3px; display: inline-block; margin-bottom: 6px;
}
.sidebar-logo h2 {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 900; font-size: 18px; line-height: 1.1;
}
.sidebar-logo h2 span { color: var(--gold); }
.sidebar-nav { flex: 1; padding: 12px 0; overflow-y: auto; }
.nav-section {
  font-size: 9px; font-weight: 700; letter-spacing: 2px;
  color: rgba(255,255,255,0.3); text-transform: uppercase;
  padding: 12px 18px 4px;
}
.nav-item {
  display: flex; align-items: center; gap: 10px;
  padding: 9px 18px; cursor: pointer; font-size: 13.5px; font-weight: 500;
  color: rgba(255,255,255,0.6); transition: all 0.15s;
  border-left: 3px solid transparent;
}
.nav-item:hover { background: rgba(255,255,255,0.04); color: var(--white); }
.nav-item.active {
  background: rgba(201,162,39,0.08); color: var(--gold);
  border-left-color: var(--gold);
}
.nav-item .icon { font-size: 16px; flex-shrink: 0; }
.sidebar-user {
  padding: 14px 18px;
  border-top: 1px solid var(--border);
}
.sidebar-user .name {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 700; font-size: 15px; color: var(--white);
}
.sidebar-user .pos { font-size: 12px; color: var(--gray); }
.sidebar-user .logout {
  font-size: 11px; color: var(--gray); cursor: pointer; margin-top: 4px;
}
.sidebar-user .logout:hover { color: var(--orange); }

.main-content { flex: 1; overflow-y: auto; min-height: 100vh; }

/* ── Mobile Nav ────────────────────────────────────────────────────────────── */
.mobile-header {
  display: none;
  background: var(--navy2); border-bottom: 1px solid var(--border);
  padding: 12px 16px; align-items: center; justify-content: space-between;
  position: sticky; top: 0; z-index: 100;
}
.mobile-header h2 {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 900; font-size: 20px;
}
.mobile-header h2 span { color: var(--gold); }
.hamburger { font-size: 22px; cursor: pointer; padding: 4px; }
.mobile-menu {
  display: none; position: fixed; inset: 0; z-index: 200;
  background: rgba(0,0,0,0.6); backdrop-filter: blur(4px);
}
.mobile-menu.open { display: block; }
.mobile-menu-panel {
  position: absolute; top: 0; left: 0; bottom: 0; width: 260px;
  background: #0a1e32; padding: 20px 0;
  animation: slideIn 0.25s ease;
}
@keyframes slideIn { from { transform: translateX(-100%); } to { transform: translateX(0); } }
.mobile-close {
  position: absolute; top: 16px; right: 16px; font-size: 22px; cursor: pointer;
}

/* ── Page Sections ─────────────────────────────────────────────────────────── */
.page { padding: 28px; max-width: 960px; }
.page-header { margin-bottom: 28px; }
.page-header .eyebrow {
  font-size: 11px; font-weight: 700; letter-spacing: 2.5px;
  color: var(--gold); text-transform: uppercase; margin-bottom: 6px;
}
.page-header h1 {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 900; font-size: 36px; line-height: 1;
}
.page-header p { font-size: 14px; color: var(--gray); margin-top: 6px; }

/* ── Cards ─────────────────────────────────────────────────────────────────── */
.card {
  background: var(--card); border: 1px solid var(--border);
  border-radius: var(--radius); padding: 20px;
  transition: background 0.15s;
}
.card:hover { background: var(--card-hover); }
.card-title {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 700; font-size: 18px; letter-spacing: 0.5px;
  margin-bottom: 4px;
}
.card-sub { font-size: 13px; color: var(--gray); }
.grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
.grid-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
.grid-4 { display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px; }

/* ── Stat tiles ────────────────────────────────────────────────────────────── */
.stat-tile {
  background: var(--card); border: 1px solid var(--border);
  border-radius: var(--radius); padding: 16px 18px;
  border-top: 3px solid var(--gold);
}
.stat-tile .num {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 900; font-size: 36px; line-height: 1;
  color: var(--gold);
}
.stat-tile .label { font-size: 12px; color: var(--gray); margin-top: 2px; }

/* ── Progress bar ─────────────────────────────────────────────────────────── */
.progress-bar {
  height: 6px; background: rgba(255,255,255,0.08);
  border-radius: 3px; overflow: hidden; margin-top: 10px;
}
.progress-bar .fill {
  height: 100%; border-radius: 3px;
  background: linear-gradient(90deg, var(--gold), var(--gold2));
  transition: width 0.6s ease;
}

/* ── Workout section ───────────────────────────────────────────────────────── */
.week-tabs {
  display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 20px;
}
.week-tab {
  padding: 7px 14px; border-radius: 20px; cursor: pointer;
  font-size: 12px; font-weight: 600; letter-spacing: 0.5px;
  background: rgba(255,255,255,0.06); color: var(--gray);
  border: 1px solid rgba(255,255,255,0.08); transition: all 0.15s;
}
.week-tab:hover { background: rgba(255,255,255,0.1); color: var(--white); }
.week-tab.active { background: var(--gold); color: var(--navy); border-color: var(--gold); }
.week-tab.completed { background: rgba(26,122,66,0.2); color: var(--green); border-color: var(--green); }
.week-tab.completed.active { background: var(--green); color: var(--white); }

.phase-badge {
  display: inline-block; padding: 3px 10px; border-radius: 3px;
  font-size: 10px; font-weight: 700; letter-spacing: 2px;
  text-transform: uppercase; margin-bottom: 12px;
}
.phase-gpp { background: rgba(26,122,66,0.2); color: #4ade80; }
.phase-acc { background: rgba(27,79,138,0.3); color: #60a5fa; }
.phase-trans { background: rgba(90,42,122,0.3); color: #c084fc; }
.phase-real { background: rgba(192,80,32,0.3); color: #fb923c; }

.session-tabs {
  display: flex; gap: 0; margin-bottom: 20px;
  background: rgba(255,255,255,0.04); border-radius: var(--radius-sm);
  padding: 3px; border: 1px solid var(--border);
}
.session-tab {
  flex: 1; padding: 9px; text-align: center; cursor: pointer;
  border-radius: 6px; font-size: 12px; font-weight: 600; letter-spacing: 0.5px;
  color: var(--gray); transition: all 0.15s;
}
.session-tab.active { background: var(--navy2); color: var(--white); box-shadow: 0 1px 4px rgba(0,0,0,0.3); }

.exercise-card {
  background: rgba(255,255,255,0.03); border: 1px solid rgba(255,255,255,0.06);
  border-radius: var(--radius); margin-bottom: 12px; overflow: hidden;
}
.exercise-header {
  display: flex; align-items: center; justify-content: space-between;
  padding: 14px 16px; cursor: pointer; gap: 12px;
}
.exercise-header:hover { background: rgba(255,255,255,0.03); }
.ex-name {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 700; font-size: 17px; flex: 1;
}
.ex-target {
  font-size: 12px; color: var(--gold); font-weight: 600;
  background: rgba(201,162,39,0.1); padding: 3px 9px; border-radius: 3px;
  white-space: nowrap;
}
.ex-chevron { font-size: 14px; color: var(--gray); transition: transform 0.2s; }
.ex-chevron.open { transform: rotate(180deg); }
.exercise-body { padding: 0 16px 16px; display: none; }
.exercise-body.open { display: block; }
.ex-cue {
  font-size: 13px; color: var(--gray); margin-bottom: 12px;
  padding: 10px 12px; background: rgba(255,255,255,0.03);
  border-left: 3px solid var(--gold); border-radius: 0 4px 4px 0;
}
.set-log-grid {
  display: grid; grid-template-columns: 70px 1fr 1fr 80px; gap: 6px;
  margin-bottom: 6px;
}
.set-log-grid .header-cell {
  font-size: 10px; font-weight: 700; letter-spacing: 1.5px;
  color: rgba(255,255,255,0.3); text-transform: uppercase;
  text-align: center;
}
.set-log-grid input {
  padding: 8px; background: rgba(255,255,255,0.06);
  border: 1px solid rgba(255,255,255,0.1);
  border-radius: 6px; color: var(--white);
  font-family: 'Barlow', sans-serif; font-size: 14px; text-align: center;
  width: 100%; transition: border-color 0.15s;
}
.set-log-grid input:focus { outline: none; border-color: var(--gold); background: rgba(255,255,255,0.08); }
.set-label {
  display: flex; align-items: center; justify-content: center;
  font-size: 12px; font-weight: 700; color: var(--gray);
}
.rpe-select {
  padding: 8px; background: rgba(255,255,255,0.06);
  border: 1px solid rgba(255,255,255,0.1);
  border-radius: 6px; color: var(--white);
  font-family: 'Barlow', sans-serif; font-size: 13px;
  width: 100%; -webkit-appearance: none;
}
.save-session-bar {
  position: sticky; bottom: 0; padding: 16px 0;
  background: linear-gradient(to top, var(--navy) 60%, transparent);
  margin-top: 12px;
}
.session-notes textarea {
  width: 100%; padding: 10px 12px;
  background: rgba(255,255,255,0.05); border: 1px solid rgba(255,255,255,0.1);
  border-radius: var(--radius-sm); color: var(--white);
  font-family: 'Barlow', sans-serif; font-size: 13px; resize: vertical; min-height: 70px;
}
.session-notes textarea:focus { outline: none; border-color: var(--gold); }
.session-notes label {
  display: block; font-size: 10px; font-weight: 700; letter-spacing: 1.5px;
  color: var(--gray); text-transform: uppercase; margin-bottom: 6px;
}

/* ── Dashboard ─────────────────────────────────────────────────────────────── */
.dash-hero {
  background: linear-gradient(135deg, rgba(27,79,138,0.3) 0%, rgba(13,33,55,0.6) 100%);
  border: 1px solid rgba(27,79,138,0.3); border-radius: var(--radius);
  padding: 24px; margin-bottom: 24px; position: relative; overflow: hidden;
}
.dash-hero::before {
  content: ''; position: absolute; right: -20px; top: -20px;
  width: 180px; height: 180px;
  background: radial-gradient(circle, rgba(201,162,39,0.08) 0%, transparent 70%);
}
.dash-hero .greeting {
  font-size: 13px; color: var(--gray); margin-bottom: 4px;
}
.dash-hero .hero-name {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 900; font-size: 32px; line-height: 1; margin-bottom: 8px;
}
.dash-hero .hero-name span { color: var(--gold); }
.dash-hero .hero-meta { font-size: 13px; color: rgba(255,255,255,0.5); }

.streak-card {
  background: linear-gradient(135deg, rgba(201,162,39,0.15) 0%, rgba(201,162,39,0.05) 100%);
  border: 1px solid rgba(201,162,39,0.2);
  border-radius: var(--radius); padding: 16px 18px;
  display: flex; align-items: center; gap: 14px;
}
.streak-icon { font-size: 32px; }
.streak-num {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 900; font-size: 38px; color: var(--gold); line-height: 1;
}
.streak-label { font-size: 12px; color: var(--gray); }

.motto-card {
  background: linear-gradient(135deg, rgba(90,42,122,0.2) 0%, rgba(13,33,55,0.4) 100%);
  border: 1px solid rgba(90,42,122,0.2); border-radius: var(--radius); padding: 20px;
}
.motto-label { font-size: 10px; font-weight: 700; letter-spacing: 2px; color: #c084fc; text-transform: uppercase; margin-bottom: 8px; }
.motto-text {
  font-size: 17px; font-weight: 500; color: var(--white); line-height: 1.5;
  margin-bottom: 6px;
}
.motto-text em { color: var(--gold); font-style: italic; }
.motto-author { font-size: 12px; color: var(--gray); }
.motto-theme { font-size: 10px; font-weight: 700; letter-spacing: 2px; color: #c084fc; text-transform: uppercase; margin-top: 8px; }

.next-session-card {
  background: linear-gradient(135deg, rgba(26,122,66,0.15) 0%, rgba(13,33,55,0.4) 100%);
  border: 1px solid rgba(26,122,66,0.2); border-radius: var(--radius); padding: 18px;
}
.nsc-label { font-size: 10px; font-weight: 700; letter-spacing: 2px; color: #4ade80; text-transform: uppercase; margin-bottom: 8px; }
.nsc-title { font-family: 'Barlow Condensed', sans-serif; font-weight: 800; font-size: 22px; margin-bottom: 4px; }
.nsc-meta { font-size: 13px; color: var(--gray); }

.recent-sessions { }
.session-row {
  display: flex; align-items: center; gap: 12px;
  padding: 12px 0; border-bottom: 1px solid var(--border);
}
.session-row:last-child { border-bottom: none; }
.session-dot {
  width: 8px; height: 8px; border-radius: 50%;
  background: var(--green); flex-shrink: 0;
}
.session-info { flex: 1; }
.session-info .s-name { font-size: 14px; font-weight: 500; }
.session-info .s-date { font-size: 12px; color: var(--gray); }
.session-rpe {
  font-size: 12px; font-weight: 700; color: var(--gold);
  background: rgba(201,162,39,0.1); padding: 3px 8px; border-radius: 3px;
}

/* ── Wellbeing ─────────────────────────────────────────────────────────────── */
.wellbeing-domain {
  display: flex; align-items: center; gap: 12px; margin-bottom: 16px;
}
.domain-name {
  width: 90px; font-size: 13px; font-weight: 600; color: var(--gray); flex-shrink: 0;
}
.rating-dots {
  display: flex; gap: 6px; flex: 1;
}
.rating-dot {
  flex: 1; height: 36px; border-radius: 6px; cursor: pointer;
  background: rgba(255,255,255,0.06); border: 1px solid rgba(255,255,255,0.1);
  display: flex; align-items: center; justify-content: center;
  font-size: 12px; font-weight: 700; color: var(--gray);
  transition: all 0.15s;
}
.rating-dot:hover { background: rgba(255,255,255,0.12); }
.rating-dot.selected-1 { background: #7f1d1d; border-color: #ef4444; color: #fff; }
.rating-dot.selected-2 { background: #78350f; border-color: #f97316; color: #fff; }
.rating-dot.selected-3 { background: #1e3a5f; border-color: #3b82f6; color: #fff; }
.rating-dot.selected-4 { background: #14532d; border-color: #22c55e; color: #fff; }
.rating-dot.selected-5 { background: #14532d; border-color: #4ade80; color: #4ade80; font-size: 14px; }
.flag-card {
  background: rgba(192,80,32,0.15); border: 1px solid rgba(192,80,32,0.3);
  border-radius: var(--radius); padding: 14px 16px; margin-top: 16px;
}
.flag-card .flag-title { font-size: 13px; font-weight: 700; color: var(--orange); margin-bottom: 4px; }
.flag-card p { font-size: 13px; color: rgba(255,255,255,0.7); }

/* ── Testing ───────────────────────────────────────────────────────────────── */
.test-row {
  display: flex; align-items: center; gap: 12px;
  padding: 12px 0; border-bottom: 1px solid var(--border);
}
.test-name { flex: 1; font-size: 14px; }
.test-target { font-size: 11px; color: var(--gray); }
.test-input-group { display: flex; gap: 6px; align-items: center; }
.test-input {
  width: 90px; padding: 7px 10px;
  background: rgba(255,255,255,0.06); border: 1px solid rgba(255,255,255,0.1);
  border-radius: 6px; color: var(--white); font-family: 'Barlow', sans-serif;
  font-size: 14px; text-align: center;
}
.test-input:focus { outline: none; border-color: var(--gold); }
.test-unit { font-size: 11px; color: var(--gray); }
.test-badge {
  font-size: 11px; font-weight: 700; padding: 3px 8px; border-radius: 3px;
}
.badge-good { background: rgba(26,122,66,0.2); color: #4ade80; }
.badge-work { background: rgba(192,80,32,0.2); color: #fb923c; }
.badge-ok { background: rgba(27,79,138,0.2); color: #60a5fa; }

/* ── Toast ─────────────────────────────────────────────────────────────────── */
.toast {
  position: fixed; bottom: 24px; right: 24px; z-index: 999;
  background: var(--navy2); border: 1px solid var(--green);
  color: var(--white); padding: 12px 20px; border-radius: var(--radius-sm);
  font-size: 14px; font-weight: 500;
  transform: translateY(80px); opacity: 0;
  transition: all 0.3s ease;
  display: flex; align-items: center; gap: 8px;
}
.toast.show { transform: translateY(0); opacity: 1; }
.toast.error { border-color: var(--orange); }

/* ── Responsive ────────────────────────────────────────────────────────────── */
@media (max-width: 768px) {
  .sidebar { display: none; }
  .mobile-header { display: flex; }
  .page { padding: 16px; }
  .grid-2 { grid-template-columns: 1fr; }
  .grid-3 { grid-template-columns: 1fr 1fr; }
  .grid-4 { grid-template-columns: 1fr 1fr; }
  .set-log-grid { grid-template-columns: 50px 1fr 1fr 70px; gap: 4px; }
  .login-title { font-size: 38px; }
}
@media (max-width: 480px) {
  .grid-3 { grid-template-columns: 1fr; }
  .grid-4 { grid-template-columns: 1fr 1fr; }
  .week-tabs { gap: 4px; }
  .week-tab { padding: 6px 10px; font-size: 11px; }
}

/* ── Section divider ───────────────────────────────────────────────────────── */
.section-title {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 700; font-size: 16px; letter-spacing: 1.5px;
  text-transform: uppercase; color: rgba(255,255,255,0.5);
  margin: 24px 0 12px; display: flex; align-items: center; gap: 10px;
}
.section-title::after { content: ''; flex: 1; height: 1px; background: var(--border); }

.divider { height: 1px; background: var(--border); margin: 20px 0; }

/* ── Info bar ──────────────────────────────────────────────────────────────── */
.info-bar {
  background: rgba(27,79,138,0.15); border: 1px solid rgba(27,79,138,0.2);
  border-left: 3px solid var(--steel); border-radius: var(--radius-sm);
  padding: 10px 14px; font-size: 13px; color: rgba(255,255,255,0.7);
  margin-bottom: 16px;
}

.empty-state {
  text-align: center; padding: 48px 24px; color: var(--gray);
}
.empty-state .es-icon { font-size: 40px; margin-bottom: 12px; }
.empty-state p { font-size: 15px; }
</style>
</head>
<body>
<div id="app">

  <!-- ═══════════════ LOGIN SCREEN ═══════════════ -->
  <div id="login" class="screen active">
    <div class="login-bg"></div>
    <div class="login-grid"></div>
    <div class="login-box">
      <div class="login-logo">
        <div class="login-logo-badge">BUNDABERG SHS</div>
        <div class="login-title">RL<br><span>ACADEMY</span></div>
        <div class="login-sub">Student Training Portal</div>
      </div>
      <div class="login-card" id="login-form-card">
        <h3>SIGN IN</h3>
        <div class="form-group">
          <label>Your Name</label>
          <input id="login-name" type="text" placeholder="First Last" autocomplete="name">
        </div>
        <div class="form-group">
          <label>PIN (4 digits)</label>
          <input id="login-pin" type="password" inputmode="numeric" maxlength="4" placeholder="••••">
        </div>
        <button class="btn" onclick="doLogin()">SIGN IN</button>
        <div class="login-switch">New here? <a onclick="showReg()">Create account</a></div>
      </div>

      <div class="login-card" id="reg-form-card" style="display:none">
        <h3>CREATE ACCOUNT</h3>
        <div class="form-group">
          <label>Full Name</label>
          <input id="reg-name" type="text" placeholder="First Last">
        </div>
        <div class="form-group">
          <label>Year Level</label>
          <select id="reg-year">
            <option>Year 8</option><option>Year 9</option><option>Year 10</option>
            <option>Year 11</option><option>Year 12</option>
          </select>
        </div>
        <div class="form-group">
          <label>Position</label>
          <select id="reg-pos">
            <option>Fullback</option><option>Wing</option><option>Centre</option>
            <option>Five-Eight</option><option>Halfback</option><option>Hooker</option>
            <option>Prop</option><option>Second Row</option><option>Lock</option>
            <option>Utility</option>
          </select>
        </div>
        <div class="form-group">
          <label>Create PIN (4 digits)</label>
          <input id="reg-pin" type="password" inputmode="numeric" maxlength="4" placeholder="••••">
        </div>
        <button class="btn" onclick="doRegister()">CREATE ACCOUNT</button>
        <div class="login-switch">Already have an account? <a onclick="showLogin()">Sign in</a></div>
      </div>
    </div>
  </div>

  <!-- ═══════════════ MAIN APP ═══════════════ -->
  <div id="main" class="screen">

    <!-- Mobile header -->
    <div class="mobile-header">
      <div>
        <h2>RL <span>ACADEMY</span></h2>
      </div>
      <div class="hamburger" onclick="toggleMobileMenu()">☰</div>
    </div>

    <!-- Mobile menu overlay -->
    <div class="mobile-menu" id="mobile-menu" onclick="closeMobileMenu(event)">
      <div class="mobile-menu-panel">
        <div class="mobile-close" onclick="toggleMobileMenu()">✕</div>
        <div id="mobile-nav-content"></div>
      </div>
    </div>

    <!-- Sidebar -->
    <nav class="sidebar">
      <div class="sidebar-logo">
        <div class="badge">BSHS</div>
        <h2>RL <span>ACADEMY</span></h2>
      </div>
      <div class="sidebar-nav" id="sidebar-nav"></div>
      <div class="sidebar-user" id="sidebar-user"></div>
    </nav>

    <!-- Content -->
    <div class="main-content" id="main-content">
      <!-- Pages injected here -->
    </div>
  </div>
</div>

<!-- Toast -->
<div class="toast" id="toast"></div>

<script>
// ════════════════════════════════════════════════════════════════════════════
// DATA — 9 Weeks of Workouts
// ════════════════════════════════════════════════════════════════════════════
const WEEKS = [
  { wk:1, phase:"GPP", label:"GPP — Phase 1", theme:"Build Your Base — Technique First",
    motto:"We suffer more in imagination than in reality.", thinker:"Seneca", focus:"DISCIPLINE",
    mon:{ title:"Monday S&C — Strength", focus:"Perfect technique. Do NOT go heavy yet.",
      intensity:"65-70%", exercises:[
        {name:"Back Squat", target:"4 × 8 reps", cue:"Knees track toes. Full depth. Tempo 3-1-X.", sets:4},
        {name:"Romanian Deadlift", target:"3 × 10 reps", cue:"Hip hinge. Feel the hamstring load.", sets:3},
        {name:"Nordic Hamstring Curl", target:"3 × 5 reps", cue:"Lower as slowly as possible — 3–5 sec eccentric.", sets:3},
        {name:"Step-Up (weighted)", target:"3 × 10/side", cue:"Drive through the heel. Equal weight each side.", sets:3},
        {name:"Glute Bridge (banded)", target:"3 × 15", cue:"Posterior chain activation. Squeeze at the top.", sets:3},
        {name:"McGill Bird Dog", target:"2 × 10/side", cue:"Neutral spine. Slow and controlled.", sets:2},
        {name:"Pallof Press", target:"2 × 12/side", cue:"Anti-rotation. Brace — don't twist.", sets:2},
      ]},
    wed:{ title:"Wednesday S&C — Power & Speed", focus:"Speed is a skill. Quality over quantity.",
      intensity:"60-65%",exercises:[
        {name:"A-March / A-Skip / B-Skip", target:"3 × 15m each", cue:"Sprint mechanics warm-up. Tall posture.", sets:3},
        {name:"Acceleration Runs", target:"3 × 15m", cue:"Forward lean. Drive phase. Don't stand up early.", sets:3},
        {name:"Hang Power Clean (or DB Hang Snatch)", target:"4 × 4", cue:"Triple extension — ankle, knee, hip. Fast elbows.", sets:4},
        {name:"Box Jump", target:"3 × 4", cue:"Land softly. Full reset between reps.", sets:3},
        {name:"Broad Jump", target:"3 × 3", cue:"Max effort. Measure and record your distance.", sets:3},
        {name:"40m Runs @ 80%", target:"4 × 40m", cue:"Not flat out — 80%. Stay within 5% of your first rep.", sets:4},
      ]},
    fri:{ title:"Friday S&C — Athletic Development", focus:"Upper body + neck work is non-negotiable.",
      intensity:"70-75%",exercises:[
        {name:"Bench Press", target:"4 × 8 reps", cue:"Retract scapulae before descent. Tempo 3-1-1.", sets:4},
        {name:"DB Incline Press", target:"3 × 10", cue:"Upper chest. Control the descent.", sets:3},
        {name:"Bent-Over Row", target:"4 × 8", cue:"Neutral spine. Retract at the top.", sets:4},
        {name:"Weighted Pull-Up / Lat Pulldown", target:"3 × 8", cue:"Full range. No kipping.", sets:3},
        {name:"Plate Shrug", target:"3 × 15", cue:"Neck & trap work — non-negotiable for contact sport.", sets:3},
        {name:"Face Pull (rope)", target:"3 × 20", cue:"Posterior deltoid. External rotators. Slow and controlled.", sets:3},
        {name:"Band Neck Isometrics", target:"3 × 10s × 4 directions", cue:"Front, back, each side. Protects your brain.", sets:3},
        {name:"Copenhagen Plank", target:"3 × 20s/side", cue:"Groin resilience. Critical for RL.", sets:3},
      ]},
  },
  { wk:2, phase:"GPP", label:"GPP — Phase 1", theme:"Consistency — Same movements, add confidence",
    motto:"Well-being is realised by small steps, but it is no small thing.", thinker:"Zeno of Citium", focus:"CONSISTENCY",
    mon:{ title:"Monday S&C — Strength", focus:"Add 2.5kg if last week felt controlled.",
      intensity:"67-72%", exercises:[
        {name:"Back Squat", target:"4 × 8 reps", cue:"Add 2.5kg from Week 1 if form was solid.", sets:4},
        {name:"Romanian Deadlift", target:"3 × 10 reps", cue:"Same weight or slightly heavier. Feel the range.", sets:3},
        {name:"Nordic Hamstring Curl", target:"3 × 5 reps", cue:"Slow eccentric. Build the resilience.", sets:3},
        {name:"Lateral Band Walk", target:"3 × 15/side", cue:"Hip abductor strength for lateral defence.", sets:3},
        {name:"Single-Leg RDL", target:"3 × 8/side", cue:"Unilateral balance. Addresses side-to-side deficit.", sets:3},
        {name:"McGill Bird Dog", target:"2 × 10/side", cue:"Spine-sparing core work.", sets:2},
        {name:"Pallof Press", target:"2 × 12/side", cue:"Increase resistance slightly from Week 1.", sets:2},
      ]},
    wed:{ title:"Wednesday S&C — Power & Speed", focus:"Build on Week 1 speed work.", intensity:"62-67%",
      exercises:[
        {name:"Sprint Mechanics Warm-Up", target:"3 × 15m drill", cue:"Wall drills first. Apply to running.", sets:3},
        {name:"Flying 20m Runs", target:"3 × (jog 10m + sprint 20m)", cue:"Jog into it. Top-end speed. Tall posture.", sets:3},
        {name:"Hang Power Clean", target:"4 × 4 @ 62%", cue:"Consistent technique. Don't rush the catch.", sets:4},
        {name:"Lateral Bound", target:"3 × 5/side", cue:"Stick the landing. Re-bound immediately.", sets:3},
        {name:"Box Jump", target:"3 × 4", cue:"Step down between reps. Quality not fatigue.", sets:3},
        {name:"40m Runs @ 82%", target:"4 × 40m", cue:"Slightly harder than Week 1.", sets:4},
      ]},
    fri:{ title:"Friday S&C — Athletic Development", focus:"Match Week 1 weights. Move with intent.",
      intensity:"70-75%",exercises:[
        {name:"Bench Press", target:"4 × 8", cue:"Same weight as Week 1 or +2.5kg if clean.", sets:4},
        {name:"Bent-Over Row", target:"4 × 8", cue:"Retract scapulae. Pull to the hip, not the armpit.", sets:4},
        {name:"Single-Arm DB Row", target:"3 × 10/side", cue:"Addresses shoulder asymmetry — common in RL.", sets:3},
        {name:"Plate Shrug", target:"3 × 15", cue:"Heavy. Protect the neck.", sets:3},
        {name:"DB Lateral Raise", target:"3 × 15", cue:"Slow — 3 seconds down. Shoulder health.", sets:3},
        {name:"Band Neck Isometrics", target:"3 × 10s × 4 directions", cue:"Build the habit.", sets:3},
        {name:"McGill Side Plank", target:"2 × 30s/side", cue:"Lateral core stability.", sets:2},
      ]},
  },
  { wk:3, phase:"GPP", label:"GPP — Phase 1", theme:"Volume Peak — Highest reps of the program",
    motto:"Fire is the test of gold; adversity, of strong men.", thinker:"Seneca", focus:"ADVERSITY",
    mon:{ title:"Monday S&C — Strength (Volume Peak)", focus:"More reps this week is intentional. Build the engine.",
      intensity:"65-70%", exercises:[
        {name:"Back Squat", target:"4 × 10 reps", cue:"Highest rep week. Focus on depth and breathing.", sets:4},
        {name:"Romanian Deadlift", target:"3 × 12 reps", cue:"Build volume in the posterior chain.", sets:3},
        {name:"Step-Up (weighted)", target:"3 × 12/side", cue:"Unilateral leg development. Slow and controlled.", sets:3},
        {name:"Nordic Hamstring Curl", target:"3 × 5", cue:"Maintain slow eccentric regardless of fatigue.", sets:3},
        {name:"Copenhagen Plank", target:"3 × 25s/side", cue:"Groin strength building. Don't let hips sag.", sets:3},
        {name:"McGill Bird Dog", target:"3 × 10/side", cue:"Extra set this week.", sets:3},
        {name:"Pallof Press", target:"3 × 12/side", cue:"Anti-rotation strength.", sets:3},
      ]},
    wed:{ title:"Wednesday S&C — Power & Speed (Volume Peak)", focus:"5 conditioning reps this week.",
      intensity:"60-65%",exercises:[
        {name:"Sprint Warm-Up", target:"4 × 15m drill", cue:"Extra volume warm-up this week.", sets:4},
        {name:"Flying 20m Runs", target:"3 × (jog 10m + sprint 20m)", cue:"Quality maintained across all reps.", sets:3},
        {name:"Hang Power Clean", target:"4 × 5 @ 60%", cue:"Extra rep per set. Maintain triple extension.", sets:4},
        {name:"Box Jump", target:"4 × 4", cue:"Extra set. Still quality — step down between reps.", sets:4},
        {name:"Hurdle Hop + Sprint 10m", target:"3 × ", cue:"Hop over hurdles then sprint immediately.", sets:3},
        {name:"40m Runs @ 80%", target:"5 × 40m", cue:"Extra conditioning rep. Maintain split time.", sets:5},
      ]},
    fri:{ title:"Friday S&C — Athletic Development (Volume Peak)", focus:"Peak volume week — embrace it.",
      intensity:"70-75%",exercises:[
        {name:"Bench Press", target:"4 × 10", cue:"Highest rep set on bench. Maintain control.", sets:4},
        {name:"DB Incline Press", target:"3 × 10", cue:"Consistent load from previous weeks.", sets:3},
        {name:"Bent-Over Row", target:"4 × 10", cue:"High volume pull week.", sets:4},
        {name:"Plate Shrug", target:"3 × 15", cue:"Neck protection work.", sets:3},
        {name:"Face Pull", target:"3 × 20", cue:"Posterior shoulder health.", sets:3},
        {name:"Band Neck Isometrics", target:"4 × 10s × 4 directions", cue:"Extra set this week.", sets:4},
        {name:"Copenhagen Plank", target:"3 × 25s/side", cue:"Building groin resilience.", sets:3},
      ]},
  },
  { wk:4, phase:"ACC", label:"Accumulation — Phase 2", theme:"Getting Stronger — Weight goes up, reps come down",
    motto:"Make the best use of what is in your power, and take the rest as it happens.", thinker:"Epictetus", focus:"CONTROL",
    mon:{ title:"Monday S&C — Max Strength", focus:"HEAVIER now. 5 sets of 5. Long rests. Perfect form.",
      intensity:"75-80%", exercises:[
        {name:"Back Squat", target:"5 × 5 @ 75-80%", cue:"Big jump in intensity. Take 3-4 min rest between sets.", sets:5},
        {name:"Romanian Deadlift", target:"4 × 8", cue:"Load increases. Maintain hip hinge quality.", sets:4},
        {name:"Single-Leg RDL", target:"3 × 8/side", cue:"Unilateral deficit work. Go heavier than GPP.", sets:3},
        {name:"Nordic Hamstring Curl", target:"3 × 5", cue:"Maintain. Injury prevention does not reduce.", sets:3},
        {name:"Broad Jump (post-squat)", target:"3 × 3", cue:"Post-activation potentiation — heavy squat then power output.", sets:3},
        {name:"McGill Bird Dog", target:"3 × 8/side", cue:"Spine care under higher load weeks.", sets:3},
      ]},
    wed:{ title:"Wednesday S&C — Power & Speed", focus:"Power work intensifies. Full recovery between runs.",
      intensity:"65-70%",exercises:[
        {name:"Sprint Mechanics", target:"3 × 15m + 4 × 20m fly", cue:"Acceleration + top-end in same session.", sets:7},
        {name:"Hang Power Clean", target:"4 × 4 @ 65%", cue:"Heavier than GPP. Fast elbows. Consistent catch.", sets:4},
        {name:"Box Jump", target:"4 × 4", cue:"Height is the target. Reset fully between reps.", sets:4},
        {name:"Depth Jump (40cm box)", target:"3 × 4", cue:"Reactive strength. Minimal ground contact.", sets:3},
        {name:"Lateral Bound", target:"3 × 5/side", cue:"Power in lateral plane — mirrors defensive first step.", sets:3},
        {name:"40m Runs @ 85%", target:"4 × 40m (2 min rest)", cue:"Increased intensity from GPP. Maintain split.", sets:4},
      ]},
    fri:{ title:"Friday S&C — Athletic Development", focus:"Push:Pull ratio is critical for shoulder health.",
      intensity:"72-78%",exercises:[
        {name:"Bench Press", target:"4 × 6 @ 72-78%", cue:"Reps drop, load increases. Retract scapulae always.", sets:4},
        {name:"Bent-Over Row", target:"4 × 6", cue:"Match or exceed bench load for push:pull balance.", sets:4},
        {name:"Weighted Pull-Up", target:"3 × 6-8", cue:"Add weight if bodyweight is easy. Full range.", sets:3},
        {name:"Single-Arm DB Row", target:"3 × 10/side", cue:"Heavier than GPP. Control the movement.", sets:3},
        {name:"Plate Shrug (heavy)", target:"3 × 15", cue:"Go heavier than GPP phase.", sets:3},
        {name:"Face Pull", target:"3 × 20", cue:"External rotators. Don't reduce this ever.", sets:3},
        {name:"Band Neck Isometrics", target:"3 × 10s × 4 directions", cue:"Non-negotiable.", sets:3},
      ]},
  },
  { wk:5, phase:"ACC", label:"Accumulation — Phase 2", theme:"Load Week — Push your numbers",
    motto:"The impediment to action advances action. What stands in the way becomes the way.", thinker:"Marcus Aurelius", focus:"RESILIENCE",
    mon:{ title:"Monday S&C — Max Strength (Load Week)", focus:"Add 2.5–5kg from last week if it felt solid.",
      intensity:"78-83%", exercises:[
        {name:"Back Squat", target:"5 × 5 @ 78-83%", cue:"Heaviest squat of the program so far. Earn it.", sets:5},
        {name:"Romanian Deadlift", target:"4 × 8", cue:"Heavier than Week 4. Maintain range.", sets:4},
        {name:"Nordic Hamstring Curl", target:"3 × 6", cue:"Extra rep per set. Slow eccentric.", sets:3},
        {name:"Step-Up (weighted)", target:"3 × 8/side", cue:"Heavier load. Slow and controlled.", sets:3},
        {name:"Broad Jump (post-squat)", target:"3 × 3", cue:"PAP continues. Max effort jumps.", sets:3},
        {name:"Copenhagen Plank", target:"3 × 30s/side", cue:"Time increases. Build groin resilience.", sets:3},
        {name:"McGill Bird Dog", target:"4 × 8/side", cue:"Extra set under heavier training week.", sets:4},
      ]},
    wed:{ title:"Wednesday S&C — Power & Speed (Load Week)", focus:"Best performances this week. Push yourself.",
      intensity:"67-72%",exercises:[
        {name:"Sprint Mechanics", target:"4 × 15m + 4 × 20m fly", cue:"Extra acceleration run this week.", sets:8},
        {name:"Hang Power Clean", target:"4 × 4 @ 67%", cue:"Progressing load. Triple extension focus.", sets:4},
        {name:"Box Jump", target:"4 × 4", cue:"Height should be increasing from Week 1.", sets:4},
        {name:"Depth Jump", target:"3 × 4", cue:"Reactive strength. Touch the ground and go.", sets:3},
        {name:"Hurdle Hop + Sprint 10m", target:"3 × ", cue:"Explosive combo drill.", sets:3},
        {name:"40m Runs @ 88%", target:"3 × (4 × 40m)", cue:"Sets of 4. 20s rest within set, 3 min between sets.", sets:12},
      ]},
    fri:{ title:"Friday S&C — Athletic Development (Load Week)", focus:"Higher intensity on all upper body lifts.",
      intensity:"75-80%",exercises:[
        {name:"Bench Press", target:"4 × 6 @ 75-80%", cue:"Load increases again. Controlled descent.", sets:4},
        {name:"Bent-Over Row", target:"4 × 6", cue:"Match pushing load.", sets:4},
        {name:"Weighted Pull-Up", target:"3 × 6", cue:"Heavier than Week 4.", sets:3},
        {name:"Plate Shrug", target:"3 × 15 (heavier)", cue:"Trap development for contact sport.", sets:3},
        {name:"DB Lateral Raise", target:"3 × 15", cue:"3-second eccentric. Shoulder health.", sets:3},
        {name:"Face Pull", target:"3 × 20", cue:"Increase resistance slightly.", sets:3},
        {name:"Band Neck Isometrics", target:"3 × 10s × 4 directions", cue:"Every Friday. Every week.", sets:3},
        {name:"Pallof Press", target:"4 × 12/side", cue:"Extra set this week.", sets:4},
      ]},
  },
  { wk:6, phase:"ACC", label:"Accumulation — Phase 2", theme:"Strength Test Week — Find your new 5RM",
    motto:"It is impossible for a man to learn what he thinks he already knows.", thinker:"Epictetus", focus:"HUMILITY",
    mon:{ title:"Monday S&C — Strength Test", focus:"Find a weight that challenges you for 4 reps. Record it.",
      intensity:"82-87%", exercises:[
        {name:"Back Squat", target:"4 × 4 @ 82-87%", cue:"Test week. Find the heavy end of your range.", sets:4},
        {name:"Romanian Deadlift", target:"4 × 6", cue:"Strong hip hinge under heavier load.", sets:4},
        {name:"Nordic Hamstring Curl", target:"3 × 6", cue:"Maintain injury prevention work.", sets:3},
        {name:"Broad Jump (post-squat)", target:"3 × 3", cue:"Post-activation potentiation. Max effort.", sets:3},
        {name:"Lateral Band Walk", target:"3 × 15/side", cue:"Hip abductor strength for defensive line speed.", sets:3},
        {name:"Copenhagen Plank", target:"3 × 30s/side", cue:"Groin resilience. Consistent.", sets:3},
      ]},
    wed:{ title:"Wednesday S&C — Power & Speed Test", focus:"Try to set personal bests on sprint and jump.",
      intensity:"70-75%",exercises:[
        {name:"Sprint Test — 5m & 40m", target:"3 trials each", cue:"Record your best time. This is your baseline test.", sets:3},
        {name:"Broad Jump Test", target:"3 trials", cue:"Record your best distance.", sets:3},
        {name:"Hang Power Clean", target:"4 × 3 @ 70%", cue:"Heavier load — fewer reps. Quality triple extension.", sets:4},
        {name:"Box Jump (test height)", target:"4 × 3", cue:"Record your max height this week.", sets:4},
        {name:"40m Runs @ 88%", target:"3 × (4 × 40m)", cue:"Conditioning maintained.", sets:12},
      ]},
    fri:{ title:"Friday S&C — Upper Body Strength Test", focus:"Record your 4–5RM on bench and row.",
      intensity:"80-87%",exercises:[
        {name:"Bench Press", target:"4 × 4 @ 80-87%", cue:"Test week. Record your heaviest set.", sets:4},
        {name:"Bent-Over Row", target:"4 × 6", cue:"Load matches bench. Record it.", sets:4},
        {name:"Weighted Pull-Up", target:"3 × 5", cue:"Add more weight. Test your ceiling.", sets:3},
        {name:"Plate Shrug (heavy)", target:"3 × 15", cue:"Heavier than any previous week.", sets:3},
        {name:"Face Pull", target:"3 × 20", cue:"Rotator cuff health. Don't skip.", sets:3},
        {name:"Band Neck Isometrics", target:"3 × 10s × 4 directions", cue:"Consistent. Every week.", sets:3},
        {name:"McGill Big 3", target:"2 rounds", cue:"Bird Dog + Side Plank + Modified Curl-Up.", sets:2},
      ]},
  },
  { wk:7, phase:"TRANS", label:"Transmutation — Phase 3", theme:"Power Phase — Lift heavy then jump/sprint",
    motto:"Difficulties strengthen the mind, as labour does the body.", thinker:"Seneca", focus:"PRESSURE",
    mon:{ title:"Monday S&C — Contrast Training", focus:"CONTRAST: Heavy squat → immediate broad jumps.",
      intensity:"85-90%", exercises:[
        {name:"Back Squat", target:"4 × 3 @ 85-90%", cue:"HEAVIEST squats yet. 3-4 min rest. Spot mandatory.", sets:4},
        {name:"Broad Jump (immediately post-squat)", target:"3 × 4 after EACH squat set", cue:"PAP window — jump max within 60s of finishing the squat set.", sets:3},
        {name:"Romanian Deadlift", target:"3 × 6", cue:"Strength maintained. Focus on range of motion.", sets:3},
        {name:"Nordic Hamstring Curl", target:"3 × 6", cue:"Non-negotiable injury prevention.", sets:3},
        {name:"Step-Up (weighted)", target:"3 × 8/side", cue:"Unilateral strength for sprinting.", sets:3},
        {name:"McGill Bird Dog", target:"3 × 10/side", cue:"Spine stability under heavy loading.", sets:3},
        {name:"Copenhagen Plank", target:"4 × 30s/side", cue:"Groin resilience peak.", sets:4},
      ]},
    wed:{ title:"Wednesday S&C — Explosive Power (Heaviest Olympic Phase)", focus:"Heaviest power work of the year.",
      intensity:"70-78%",exercises:[
        {name:"Sprint Mechanics (max effort)", target:"3 × 10m + 3 × 20m fly", cue:"MAXIMUM intent. Record times.", sets:6},
        {name:"Hang Power Clean", target:"5 × 3 @ 70-75%", cue:"Heaviest cleans yet. Fast elbows. Hard catch.", sets:5},
        {name:"Box Jump", target:"4 × 4", cue:"Max height. Full reset.", sets:4},
        {name:"Depth Jump", target:"4 × 4", cue:"Reactive strength at its peak.", sets:4},
        {name:"Lateral Bound", target:"4 × 5/side", cue:"Extra set. Horizontal power.", sets:4},
        {name:"40m Runs @ 90%", target:"3 × (4 × 40m)", cue:"Approaching maximum intensity.", sets:12},
      ]},
    fri:{ title:"Friday S&C — Upper Body Power", focus:"Contrast: Heavy bench → explosive push-ups.",
      intensity:"80-87%",exercises:[
        {name:"Bench Press", target:"4 × 4 @ 82-87%", cue:"Heavy. Explosive intent on the concentric.", sets:4},
        {name:"Explosive Push-Up (post-bench)", target:"3 × 5 clap push-ups", cue:"Contrast with bench. Express power.", sets:3},
        {name:"Bent-Over Row", target:"4 × 6", cue:"Maintain pulling volume.", sets:4},
        {name:"Weighted Pull-Up", target:"3 × 5", cue:"Heavy. Full range.", sets:3},
        {name:"Full Neck/Trap Protocol", target:"Shrug+LR+Face Pull+Iso", cue:"Full sequence. Every Friday. Non-negotiable.", sets:3},
        {name:"Pallof Press", target:"4 × 10/side", cue:"Anti-rotation at high load weeks.", sets:4},
        {name:"McGill Side Plank", target:"3 × 30s/side", cue:"Lateral stability.", sets:3},
      ]},
  },
  { wk:8, phase:"TRANS", label:"Transmutation — Phase 3", theme:"Explosive Power Peak — Maximum intent every rep",
    motto:"There is no easy way from the earth to the stars.", thinker:"Seneca", focus:"SACRIFICE",
    mon:{ title:"Monday S&C — Power Peak (Heaviest Week)", focus:"HEAVIEST week. Maximum effort.",
      intensity:"87-92%", exercises:[
        {name:"Back Squat", target:"4 × 3 @ 87-92%", cue:"HEAVIEST week of the program. Earn every rep.", sets:4},
        {name:"Box Jump (post-squat)", target:"3 × 4 after each squat set", cue:"PAP at maximum. Explosive.", sets:3},
        {name:"Romanian Deadlift", target:"3 × 5", cue:"Heavier than any previous RDL.", sets:3},
        {name:"Single-Leg RDL", target:"3 × 6/side", cue:"Unilateral strength at its peak.", sets:3},
        {name:"Nordic Hamstring Curl", target:"3 × 6", cue:"Heavier band or higher angle. Push the eccentric.", sets:3},
        {name:"Copenhagen Plank", target:"4 × 30s/side", cue:"Groin peak.", sets:4},
        {name:"Pallof Press", target:"4 × 12/side", cue:"Core stability at maximum loading week.", sets:4},
      ]},
    wed:{ title:"Wednesday S&C — Explosive Power (Max)", focus:"Personal best attempts on all power work.",
      intensity:"75-78%",exercises:[
        {name:"Sprint Mechanics + Sprint Test", target:"3 × 10m + 4 × 20m fly (max)", cue:"Test yourself. Record times.", sets:7},
        {name:"Hang Power Clean / DB Hang Snatch", target:"4 × 3 @ 75-78%", cue:"Heaviest clean of the program.", sets:4},
        {name:"Box Jump (max height test)", target:"4 × 4", cue:"Record your max height.", sets:4},
        {name:"Depth Jump", target:"4 × 4", cue:"Peak reactive strength.", sets:4},
        {name:"Hurdle Hop + Sprint 10m", target:"4 × ", cue:"Extra set at peak week.", sets:4},
        {name:"40m Runs @ 92%", target:"3 × (4 × 40m)", cue:"Hardest conditioning of the program.", sets:12},
      ]},
    fri:{ title:"Friday S&C — Upper Body Peak", focus:"Push every lift to its peak this week.",
      intensity:"85-90%",exercises:[
        {name:"Bench Press", target:"4 × 3 @ 85-90%", cue:"Peak bench week. Spotter mandatory. Max effort.", sets:4},
        {name:"Bent-Over Row", target:"4 × 5", cue:"Match pressing weight.", sets:4},
        {name:"Weighted Pull-Up", target:"3 × 5", cue:"Heaviest pull-up weight of the program.", sets:3},
        {name:"Single-Arm DB Row", target:"3 × 10/side", cue:"Heavier than any previous week.", sets:3},
        {name:"Full Neck/Trap Protocol", target:"Full sequence", cue:"Shrug → Lateral Raise → Face Pull → Neck Iso.", sets:3},
        {name:"McGill Big 3", target:"2 rounds (full)", cue:"Spine health at max load week.", sets:2},
        {name:"Copenhagen Plank", target:"4 × 30s/side", cue:"Peak groin work.", sets:4},
      ]},
  },
  { wk:9, phase:"REAL", label:"Realisation — Peak Week", theme:"Low volume, max intent — feel fast and powerful",
    motto:"Begin at once to live, and count each separate day as a separate life.", thinker:"Seneca", focus:"MOMENTUM",
    mon:{ title:"Monday S&C — Peak Week (Low Volume)", focus:"DELOAD volume, not intensity. Less reps — same weight.",
      intensity:"88-93%", exercises:[
        {name:"Back Squat", target:"3 × 3 @ 88-93%", cue:"Heaviest weight, fewest reps. You should feel FAST after this.", sets:3},
        {name:"Broad Jump", target:"3 × 4 (measure)", cue:"Compare to Week 1. This is your progress.", sets:3},
        {name:"Romanian Deadlift", target:"3 × 5", cue:"Maintaining. Don't go heavy on deload week.", sets:3},
        {name:"Nordic Hamstring Curl", target:"3 × 5", cue:"Maintain the habit. Injury prevention never stops.", sets:3},
        {name:"McGill Bird Dog", target:"2 × 8/side", cue:"Reduced volume. Quality maintained.", sets:2},
        {name:"Pallof Press", target:"3 × 10/side", cue:"Core stability maintained.", sets:3},
      ]},
    wed:{ title:"Wednesday S&C — Peak Speed Session", focus:"Personal best attempts. Feel the results of 9 weeks.",
      intensity:"78-82%",exercises:[
        {name:"Sprint Test — 5m & 10m & 40m", target:"3 trials each (RECORD)", cue:"COMPARE TO WEEK 1. This is your 9-week progress.", sets:3},
        {name:"Broad Jump (measure)", target:"3 × 4", cue:"Record your distance. Compare to Week 1.", sets:3},
        {name:"Hang Power Clean", target:"3 × 3 @ 78-82%", cue:"Reduced volume. Maximum intent on each rep.", sets:3},
        {name:"Box Jump (test max height)", target:"3 × 4", cue:"Peak week max height. Record it.", sets:3},
        {name:"40m Runs @ 90%", target:"3 × (3 × 40m)", cue:"Reduced conditioning volume. Maintain speed.", sets:9},
      ]},
    fri:{ title:"Friday S&C — Peak Upper Body", focus:"Reduced volume, maintained intensity.",
      intensity:"85-90%",exercises:[
        {name:"Bench Press", target:"3 × 3 @ 85-90%", cue:"Peak week. Low volume, max intent.", sets:3},
        {name:"Bent-Over Row", target:"3 × 5", cue:"Reduced reps. Maintained load.", sets:3},
        {name:"Weighted Pull-Up", target:"3 × 4", cue:"Deload volume. Same weight as peak week.", sets:3},
        {name:"Full Neck/Trap Protocol", target:"Full sequence (maintenance)", cue:"Neck work does not reduce. Ever.", sets:3},
        {name:"McGill Big 3", target:"2 rounds", cue:"Spine care maintained throughout peak.", sets:2},
        {name:"Copenhagen Plank", target:"3 × 25s/side", cue:"Slightly reduced from peak week.", sets:3},
      ]},
  },
];

const MOTTOS = WEEKS.map(w => ({wk:w.wk, focus:w.focus, motto:w.motto, thinker:w.thinker}));

const NUTRITION_TIPS = [
  {icon:"🍌", tip:"Pre-session fuel (6:30am): banana + toast with peanut butter OR overnight oats. Prepare it the night before."},
  {icon:"🥛", tip:"Post-session recovery: 500mL chocolate milk within 30 min. 17g protein + 58g carbs = the cheapest recovery tool in sport."},
  {icon:"💧", tip:"Hydration target: 500mL water before you arrive. Your urine should be pale yellow by midday."},
  {icon:"🍗", tip:"Protein target: 25–40g per meal, 4–5 meals per day. 70kg athlete = 112–154g daily."},
  {icon:"🍚", tip:"Carbohydrate timing: big serve at dinner the night before heavy training days. Top up the fuel tank overnight."},
  {icon:"😴", tip:"Sleep is your most powerful recovery tool. 8–9 hours. Phone down 60 min before bed. Non-negotiable."},
  {icon:"🥚", tip:"Budget meal: 3 eggs + 2 slices toast + banana = 35g protein + 40g carbs. ~$2. Perfect pre-training breakfast."},
  {icon:"🍫", tip:"Recovery window: 30–60 min post-training is critical. Chocolate milk, protein + banana, or Greek yoghurt + fruit."},
];

const RECOVERY_TIPS = [
  {icon:"🧊", tip:"Cold water immersion: 10–15 min at 10–14°C after FIELD sessions only. NOT after gym sessions — it blunts strength gains."},
  {icon:"🔄", tip:"Foam roll protocol: 60 sec each area — quads, hamstrings, glutes, IT band, thoracic spine, calves. Do this 3x per week minimum."},
  {icon:"🌙", tip:"Pre-sleep routine: no screens 60 min before bed. Room temp 16–18°C. Same bedtime every night — this trains your body clock."},
  {icon:"🚶", tip:"Active recovery (Tue/Thu): 15–20 min easy walk or swim. Low heart rate. This clears metabolic waste faster than doing nothing."},
  {icon:"🧘", tip:"Stretch protocol post-training: quads 45s, hamstrings 45s, hip flexors 45s, calves 30s, glutes 45s, lats 30s."},
  {icon:"⚡", tip:"Contrast shower (home CWI): 90 sec warm → 30 sec cold → repeat × 4. Accessible recovery when a cold plunge isn't available."},
  {icon:"📊", tip:"RPE monitoring: if your RPE is consistently 9–10 for two sessions in a row, your body needs a load reduction. Tell your coach."},
  {icon:"💊", tip:"Supplements worth it: Omega-3 fish oil (2–3g daily), Vitamin D if deficient. Everything else — food first."},
];

// ════════════════════════════════════════════════════════════════════════════
// STORAGE
// ════════════════════════════════════════════════════════════════════════════
const LS_USERS  = 'rl_users';
const LS_CURRENT = 'rl_current';
const LS_LOGS   = 'rl_logs';
const LS_WELL   = 'rl_wellbeing';
const LS_TESTS  = 'rl_tests';

const getUsers   = () => JSON.parse(localStorage.getItem(LS_USERS)  || '{}');
const saveUsers  = u  => localStorage.setItem(LS_USERS, JSON.stringify(u));
const getCurrent = () => localStorage.getItem(LS_CURRENT);
const setCurrent = n  => localStorage.setItem(LS_CURRENT, n);
const getLogs    = () => JSON.parse(localStorage.getItem(LS_LOGS)   || '{}');
const saveLogs   = l  => localStorage.setItem(LS_LOGS, JSON.stringify(l));
const getWell    = () => JSON.parse(localStorage.getItem(LS_WELL)   || '{}');
const saveWell   = w  => localStorage.setItem(LS_WELL, JSON.stringify(w));
const getTests   = () => JSON.parse(localStorage.getItem(LS_TESTS)  || '{}');
const saveTests  = t  => localStorage.setItem(LS_TESTS, JSON.stringify(t));

let currentUser = null;
let currentPage = 'dashboard';
let currentWeek = 1;
let currentSession = 'mon';

// ════════════════════════════════════════════════════════════════════════════
// AUTH
// ════════════════════════════════════════════════════════════════════════════
function showReg()   { document.getElementById('login-form-card').style.display='none'; document.getElementById('reg-form-card').style.display='block'; }
function showLogin() { document.getElementById('reg-form-card').style.display='none'; document.getElementById('login-form-card').style.display='block'; }

function doRegister() {
  const name = document.getElementById('reg-name').value.trim();
  const year = document.getElementById('reg-year').value;
  const pos  = document.getElementById('reg-pos').value;
  const pin  = document.getElementById('reg-pin').value.trim();
  if (!name || pin.length !== 4 || !/^\d{4}$/.test(pin)) { showToast('Please enter your name and a 4-digit PIN', true); return; }
  const users = getUsers();
  if (users[name.toLowerCase()]) { showToast('Name already taken — try a different name', true); return; }
  users[name.toLowerCase()] = { name, year, pos, pin, created: Date.now() };
  saveUsers(users);
  setCurrent(name.toLowerCase());
  currentUser = users[name.toLowerCase()];
  loadApp();
}

function doLogin() {
  const name = document.getElementById('login-name').value.trim();
  const pin  = document.getElementById('login-pin').value.trim();
  const users = getUsers();
  const key = name.toLowerCase();
  if (!users[key] || users[key].pin !== pin) { showToast('Name or PIN incorrect', true); return; }
  setCurrent(key);
  currentUser = users[key];
  loadApp();
}

function doLogout() {
  localStorage.removeItem(LS_CURRENT);
  currentUser = null;
  document.getElementById('login').classList.add('active');
  document.getElementById('main').classList.remove('active');
  document.getElementById('login-name').value='';
  document.getElementById('login-pin').value='';
}

// ════════════════════════════════════════════════════════════════════════════
// APP INIT
// ════════════════════════════════════════════════════════════════════════════
function loadApp() {
  const key = getCurrent();
  if (key) {
    const users = getUsers();
    if (users[key]) {
      currentUser = users[key];
      document.getElementById('login').classList.remove('active');
      document.getElementById('main').classList.add('active');
      renderSidebar();
      navigate('dashboard');
      return;
    }
  }
  document.getElementById('login').classList.add('active');
  document.getElementById('main').classList.remove('active');
}

const NAV = [
  { section:'TRAINING', items:[
    { id:'dashboard', icon:'🏠', label:'Dashboard' },
    { id:'workouts', icon:'🏋', label:'Workouts' },
    { id:'testing', icon:'⚡', label:'My Testing' },
  ]},
  { section:'WELLBEING', items:[
    { id:'wellbeing', icon:'❤️', label:'Wellbeing' },
    { id:'nutrition', icon:'🍎', label:'Nutrition' },
    { id:'recovery', icon:'🔄', label:'Recovery' },
  ]},
  { section:'PROGRAM', items:[
    { id:'mottos', icon:'💬', label:'Weekly Focus' },
    { id:'info', icon:'ℹ️', label:'Program Info' },
  ]},
];

function renderSidebar() {
  let html = '';
  NAV.forEach(section => {
    html += `<div class="nav-section">${section.section}</div>`;
    section.items.forEach(item => {
      html += `<div class="nav-item${item.id===currentPage?' active':''}" onclick="navigate('${item.id}')" data-page="${item.id}">
        <span class="icon">${item.icon}</span>${item.label}
      </div>`;
    });
  });
  const userHtml = `<div class="name">${currentUser.name}</div>
    <div class="pos">${currentUser.pos} · ${currentUser.year}</div>
    <div class="logout" onclick="doLogout()">Sign out</div>`;
  document.getElementById('sidebar-nav').innerHTML = html;
  document.getElementById('sidebar-user').innerHTML = userHtml;
  document.getElementById('mobile-nav-content').innerHTML = `
    <div style="padding:16px 18px 0">
      <div style="font-size:11px;color:rgba(255,255,255,0.4);letter-spacing:2px;margin-bottom:4px">SIGNED IN AS</div>
      <div style="font-weight:700;margin-bottom:16px">${currentUser.name} · ${currentUser.pos}</div>
    </div>
    ${html}
    <div style="padding:16px 18px"><button class="btn btn-ghost btn-sm" onclick="doLogout()">Sign Out</button></div>`;
}

function navigate(page) {
  currentPage = page;
  document.querySelectorAll('.nav-item').forEach(el => {
    el.classList.toggle('active', el.dataset.page === page);
  });
  const content = document.getElementById('main-content');
  if (page === 'dashboard') content.innerHTML = renderDashboard();
  else if (page === 'workouts') content.innerHTML = renderWorkouts();
  else if (page === 'testing')  content.innerHTML = renderTesting();
  else if (page === 'wellbeing') content.innerHTML = renderWellbeing();
  else if (page === 'nutrition') content.innerHTML = renderNutrition();
  else if (page === 'recovery')  content.innerHTML = renderRecovery();
  else if (page === 'mottos')    content.innerHTML = renderMottos();
  else if (page === 'info')      content.innerHTML = renderInfo();
  closeMobileMenu({target:{closest:()=>null}});
}

// ════════════════════════════════════════════════════════════════════════════
// DASHBOARD
// ════════════════════════════════════════════════════════════════════════════
function renderDashboard() {
  const logs = getLogs();
  const userKey = currentUser.name.toLowerCase();
  const userLogs = logs[userKey] || {};
  const sessionCount = Object.keys(userLogs).length;
  const dayOfWeek = new Date().getDay(); // 0=Sun,1=Mon,...,5=Fri
  const dayNames = ['Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturday'];
  const today = dayNames[dayOfWeek];
  let nextSession = '';
  if (dayOfWeek === 1) nextSession = 'Monday S&C (7:15am)';
  else if (dayOfWeek === 3) nextSession = 'Wednesday S&C (7:15am)';
  else if (dayOfWeek === 5) nextSession = 'Friday S&C (7:15am)';
  else if (dayOfWeek === 2) nextSession = 'Wednesday S&C tomorrow (7:15am)';
  else if (dayOfWeek === 4) nextSession = 'Friday S&C tomorrow (7:15am)';
  else nextSession = 'Monday S&C on Monday (7:15am)';

  // Find current week (which week they're on based on sessions logged)
  const progressWeek = Math.min(Math.ceil((sessionCount + 1) / 3), 9);
  const wkData = WEEKS[progressWeek-1];
  const motto = wkData.motto;
  const mottoPerson = wkData.thinker;
  const mottoFocus = wkData.focus;

  // Recent logs
  const allEntries = Object.entries(userLogs).sort((a,b)=>b[1].timestamp-a[1].timestamp).slice(0,4);
  const recentHtml = allEntries.length === 0
    ? `<div class="empty-state"><div class="es-icon">📋</div><p>No sessions logged yet.<br>Head to Workouts to start.</p></div>`
    : allEntries.map(([key, log]) => {
        const [wk, sess] = key.split('_');
        const sessLabel = {mon:'Monday S&C',wed:'Wednesday S&C',fri:'Friday S&C'}[sess]||sess;
        const date = new Date(log.timestamp).toLocaleDateString('en-AU',{weekday:'short',day:'numeric',month:'short'});
        return `<div class="session-row">
          <div class="session-dot"></div>
          <div class="session-info">
            <div class="s-name">Week ${wk} — ${sessLabel}</div>
            <div class="s-date">${date}</div>
          </div>
          ${log.avgRpe ? `<div class="session-rpe">RPE ${log.avgRpe}</div>` : ''}
        </div>`;
      }).join('');

  const pct = Math.round((sessionCount / 27) * 100);

  return `<div class="page">
    <div class="dash-hero">
      <div class="greeting">Welcome back,</div>
      <div class="hero-name"><span>${currentUser.name.split(' ')[0]}</span></div>
      <div class="hero-meta">${currentUser.pos} · ${currentUser.year} · ${today}</div>
    </div>

    <div class="grid-4" style="margin-bottom:16px">
      <div class="stat-tile">
        <div class="num">${sessionCount}</div>
        <div class="label">Sessions Logged</div>
      </div>
      <div class="stat-tile" style="border-top-color:var(--steel)">
        <div class="num" style="color:var(--steel)">${progressWeek}</div>
        <div class="label">Current Week</div>
      </div>
      <div class="stat-tile" style="border-top-color:var(--green)">
        <div class="num" style="color:var(--green)">${pct}%</div>
        <div class="label">Term Progress</div>
      </div>
      <div class="stat-tile" style="border-top-color:var(--purple)">
        <div class="num" style="color:#c084fc">${27 - sessionCount}</div>
        <div class="label">Sessions Left</div>
      </div>
    </div>

    <div class="progress-bar" style="margin-bottom:24px">
      <div class="fill" style="width:${pct}%"></div>
    </div>

    <div class="grid-2" style="margin-bottom:16px">
      <div class="next-session-card">
        <div class="nsc-label">⚡ Next Up</div>
        <div class="nsc-title">${nextSession}</div>
        <div class="nsc-meta">Week ${progressWeek} · ${wkData.label}</div>
        <div style="margin-top:12px">
          <button class="btn btn-green btn-sm" onclick="navigate('workouts')">Go to Workout →</button>
        </div>
      </div>
      <div class="motto-card">
        <div class="motto-label">Weekly Focus</div>
        <div class="motto-theme">${mottoFocus}</div>
        <div class="motto-text">"${motto}"</div>
        <div class="motto-author">— ${mottoPerson}</div>
      </div>
    </div>

    <div class="section-title">Recent Sessions</div>
    <div class="card">
      ${recentHtml}
    </div>
  </div>`;
}

// ════════════════════════════════════════════════════════════════════════════
// WORKOUTS
// ════════════════════════════════════════════════════════════════════════════
function renderWorkouts() {
  const logs = getLogs();
  const userKey = currentUser.name.toLowerCase();
  const userLogs = logs[userKey] || {};

  const weekTabsHtml = WEEKS.map((w,i) => {
    const hasAny = ['mon','wed','fri'].some(s => userLogs[`${w.wk}_${s}`]);
    const hasAll = ['mon','wed','fri'].every(s => userLogs[`${w.wk}_${s}`]);
    const classes = ['week-tab',
      i+1===currentWeek?'active':'',
      hasAll?'completed':''].join(' ').trim();
    return `<div class="${classes}" onclick="setWeek(${w.wk})">${w.wk}</div>`;
  }).join('');

  const wk = WEEKS[currentWeek-1];
  const phaseClass = {GPP:'phase-gpp',ACC:'phase-acc',TRANS:'phase-trans',REAL:'phase-real'}[wk.phase];

  const sessionTabsHtml = [
    {key:'mon', label:'Monday — Strength'},
    {key:'wed', label:'Wednesday — Power'},
    {key:'fri', label:'Friday — Athletic Dev'},
  ].map(s => `<div class="session-tab${s.key===currentSession?' active':''}" onclick="setSession('${s.key}')">${s.label}</div>`).join('');

  const sess = currentSession==='mon'?wk.mon : currentSession==='wed'?wk.wed : wk.fri;
  const logKey = `${currentWeek}_${currentSession}`;
  const savedLog = (userLogs[logKey] || {}).exercises || {};
  const savedNotes = (userLogs[logKey] || {}).notes || '';
  const isLogged = !!userLogs[logKey];

  const exercisesHtml = sess.exercises.map((ex, ei) => {
    const setRows = Array.from({length:ex.sets}, (_,si) => {
      const saved = (savedLog[ei] || {})[si] || {};
      return `<div class="set-log-grid" style="grid-template-columns:50px 1fr 1fr 80px">
        <div class="set-label">Set ${si+1}</div>
        <input type="number" placeholder="kg" value="${saved.weight||''}" 
          oninput="saveField(${ei},${si},'weight',this.value)"
          class="log-input" inputmode="decimal">
        <input type="number" placeholder="reps" value="${saved.reps||''}"
          oninput="saveField(${ei},${si},'reps',this.value)"
          class="log-input" inputmode="numeric">
        <select class="rpe-select" onchange="saveField(${ei},${si},'rpe',this.value)">
          <option value="">RPE</option>
          ${[6,7,7.5,8,8.5,9,9.5,10].map(r=>`<option value="${r}"${saved.rpe==r?' selected':''}>${r}</option>`).join('')}
        </select>
      </div>`;
    }).join('');

    return `<div class="exercise-card">
      <div class="exercise-header" onclick="toggleEx(${ei})">
        <div class="ex-name">${ex.name}</div>
        <div class="ex-target">${ex.target}</div>
        <div class="ex-chevron" id="chev-${ei}">▾</div>
      </div>
      <div class="exercise-body" id="ex-body-${ei}">
        <div class="ex-cue">${ex.cue}</div>
        <div class="set-log-grid" style="grid-template-columns:50px 1fr 1fr 80px;margin-bottom:6px">
          <div class="header-cell"></div>
          <div class="header-cell">Weight</div>
          <div class="header-cell">Reps</div>
          <div class="header-cell">RPE</div>
        </div>
        ${setRows}
      </div>
    </div>`;
  }).join('');

  return `<div class="page">
    <div class="page-header">
      <div class="eyebrow">Training Program</div>
      <h1>Workouts</h1>
      <p>9-week progressive program. Log your sets, weights, and RPE every session.</p>
    </div>

    <div class="info-bar">📍 <strong>Week ${currentWeek} of 9</strong> — ${wk.label} &nbsp;·&nbsp; ${wk.theme}</div>

    <div class="week-tabs">${weekTabsHtml}</div>

    <div id="workout-area">
      <div style="display:flex;align-items:center;gap:10px;margin-bottom:12px;flex-wrap:wrap">
        <span class="phase-badge ${phaseClass}">${wk.phase}</span>
        ${isLogged ? '<span style="font-size:12px;color:var(--green);font-weight:700">✓ Session logged</span>' : ''}
      </div>
      <div class="session-tabs">${sessionTabsHtml}</div>

      <div class="card" style="margin-bottom:12px;padding:14px 16px">
        <div style="font-size:12px;color:var(--gray);margin-bottom:2px">${sess.title}</div>
        <div style="font-size:14px;font-weight:600;color:var(--gold)">${sess.focus}</div>
        <div style="font-size:13px;color:rgba(255,255,255,0.5);margin-top:2px">Intensity target: <strong style="color:var(--white)">${sess.intensity}</strong></div>
      </div>

      <div id="exercises-container">${exercisesHtml}</div>

      <div class="session-notes" style="margin-bottom:12px">
        <label>Session Notes</label>
        <textarea id="session-notes" placeholder="How did it feel? Anything to flag? Personal bests?" 
          onchange="saveNotes(this.value)">${savedNotes}</textarea>
      </div>

      <div class="save-session-bar">
        <button class="btn btn-green" onclick="saveSession()">
          ${isLogged ? '✓ UPDATE SESSION LOG' : '✓ MARK SESSION COMPLETE'}
        </button>
      </div>
    </div>
  </div>`;
}

// Temp storage for current session in-progress
let tempLog = {};
function saveField(ei, si, field, val) {
  if (!tempLog[ei]) tempLog[ei] = {};
  if (!tempLog[ei][si]) tempLog[ei][si] = {};
  tempLog[ei][si][field] = val;
}
function saveNotes(val) { /* stored on save */ }

function saveSession() {
  const logs = getLogs();
  const userKey = currentUser.name.toLowerCase();
  if (!logs[userKey]) logs[userKey] = {};
  const logKey = `${currentWeek}_${currentSession}`;
  const notes = document.getElementById('session-notes')?.value || '';

  // Merge tempLog with any existing saved data
  const existing = (logs[userKey][logKey] || {}).exercises || {};
  const merged = {...existing};
  Object.entries(tempLog).forEach(([ei, sets]) => {
    if (!merged[ei]) merged[ei] = {};
    Object.entries(sets).forEach(([si, data]) => {
      merged[ei][si] = {...(merged[ei][si]||{}), ...data};
    });
  });

  // Calculate avg RPE
  let rpeSum=0, rpeCount=0;
  Object.values(merged).forEach(sets => {
    Object.values(sets).forEach(s => { if (s.rpe) { rpeSum+=parseFloat(s.rpe); rpeCount++; }});
  });

  logs[userKey][logKey] = {
    exercises: merged,
    notes,
    timestamp: Date.now(),
    avgRpe: rpeCount > 0 ? Math.round(rpeSum/rpeCount*10)/10 : null,
  };
  saveLogs(logs);
  tempLog = {};
  showToast('Session saved ✓');
  navigate('workouts');
}

function toggleEx(ei) {
  const body = document.getElementById(`ex-body-${ei}`);
  const chev = document.getElementById(`chev-${ei}`);
  body.classList.toggle('open');
  chev.classList.toggle('open');
}
function setWeek(wk) { currentWeek=wk; tempLog={}; navigate('workouts'); }
function setSession(s) { currentSession=s; tempLog={}; navigate('workouts'); }

// ════════════════════════════════════════════════════════════════════════════
// TESTING
// ════════════════════════════════════════════════════════════════════════════
const TESTS_DEF = [
  {id:'5m', name:'5m Sprint', unit:'sec', target:'<1.05 (Fwds) / <0.98 (Backs)', low:true},
  {id:'10m', name:'10m Sprint', unit:'sec', target:'<1.85', low:true},
  {id:'40m', name:'40m Sprint', unit:'sec', target:'<5.6 (Fwds) / <5.2 (Backs)', low:true},
  {id:'cod', name:'5-0-5 COD', unit:'sec', target:'<2.45', low:true},
  {id:'cmj', name:'CMJ Height', unit:'cm', target:'>50cm', low:false},
  {id:'broad', name:'Broad Jump', unit:'cm', target:'>220cm', low:false},
  {id:'squat', name:'Back Squat 1RM', unit:'kg', target:'>1.5× BW', low:false},
  {id:'bench', name:'Bench Press 1RM', unit:'kg', target:'>1.0× BW', low:false},
  {id:'yoyo', name:'Yo-Yo Level', unit:'level', target:'Level 17–19', low:false},
];
const TEST_PERIODS = [{id:'pre', label:'Pre-Term (Wk 1)'},{id:'mid', label:'Mid-Term (Wk 5)'},{id:'end', label:'End-Term (Wk 9)'}];

function renderTesting() {
  const tests = getTests();
  const userKey = currentUser.name.toLowerCase();
  const userTests = tests[userKey] || {};

  const periodsHtml = TEST_PERIODS.map(p => {
    const rows = TESTS_DEF.map(t => {
      const val = (userTests[p.id] || {})[t.id] || '';
      return `<div class="test-row">
        <div>
          <div class="test-name">${t.name}</div>
          <div class="test-target">Target: ${t.target}</div>
        </div>
        <div class="test-input-group">
          <input type="number" class="test-input" value="${val}" inputmode="decimal"
            placeholder="—"
            onchange="saveTest('${p.id}','${t.id}',this.value)">
          <span class="test-unit">${t.unit}</span>
          ${val ? getBadge(t, val) : ''}
        </div>
      </div>`;
    }).join('');
    return `<div style="margin-bottom:24px">
      <div class="section-title">${p.label}</div>
      ${rows}
      <button class="btn btn-ghost btn-sm" style="margin-top:12px" onclick="saveAllTests()">Save Results</button>
    </div>`;
  }).join('');

  // Progress comparison
  const preTests = userTests.pre || {};
  const endTests = userTests.end || {};
  const hasComparison = Object.keys(preTests).length > 0 && Object.keys(endTests).length > 0;
  const compHtml = hasComparison ? `
    <div class="section-title">Progress (Pre vs End)</div>
    <div class="card">${TESTS_DEF.map(t => {
      const pre = preTests[t.id]; const end = endTests[t.id];
      if (!pre || !end) return '';
      const diff = t.low ? pre - end : end - pre;
      const improved = diff > 0;
      return `<div class="test-row">
        <div class="test-name">${t.name}</div>
        <div style="display:flex;gap:12px;align-items:center">
          <span style="font-size:13px;color:var(--gray)">${pre}${t.unit}</span>
          <span style="color:var(--gray)">→</span>
          <span style="font-size:13px;font-weight:700;color:var(--white)">${end}${t.unit}</span>
          <span class="test-badge ${improved?'badge-good':'badge-work'}">${improved?'+':''}${Math.round(Math.abs(diff)*100)/100} ${improved?'✓':'↓'}</span>
        </div>
      </div>`;
    }).join('')}</div>` : '';

  return `<div class="page">
    <div class="page-header">
      <div class="eyebrow">Performance Data</div>
      <h1>My Testing</h1>
      <p>Record your physical test results at the start, middle, and end of term. Track your progress.</p>
    </div>
    <div class="info-bar">💡 Enter your results after each testing session. Your coach will also record these in the squad tracker.</div>
    ${periodsHtml}
    ${compHtml}
  </div>`;
}

function getBadge(t, val) {
  // Simple green/orange for direction indicator
  return `<span class="test-badge badge-ok">${val}</span>`;
}

function saveTest(period, testId, val) {
  const tests = getTests();
  const userKey = currentUser.name.toLowerCase();
  if (!tests[userKey]) tests[userKey] = {};
  if (!tests[userKey][period]) tests[userKey][period] = {};
  tests[userKey][period][testId] = val;
  saveTests(tests);
}
function saveAllTests() { showToast('Test results saved ✓'); }

// ════════════════════════════════════════════════════════════════════════════
// WELLBEING
// ════════════════════════════════════════════════════════════════════════════
const DOMAINS = [
  {id:'sleep', label:'Sleep', icon:'😴'},
  {id:'energy', label:'Energy', icon:'⚡'},
  {id:'mood', label:'Mood', icon:'😊'},
  {id:'soreness', label:'Soreness', icon:'💪'},
  {id:'stress', label:'Stress', icon:'🧠'},
];
let wellTemp = {};

function renderWellbeing() {
  const well = getWell();
  const userKey = currentUser.name.toLowerCase();
  const userWell = well[userKey] || {};
  const weekKey = `wk${currentWeek}`;
  const saved = userWell[weekKey] || {};
  wellTemp = {...saved};

  const today = new Date().toLocaleDateString('en-AU',{weekday:'long',day:'numeric',month:'long'});
  const domainsHtml = DOMAINS.map(d => {
    const cur = saved[d.id] || 0;
    const dots = [1,2,3,4,5].map(n => {
      const c = cur==n ? `selected-${n}` : '';
      return `<div class="rating-dot ${c}" onclick="setWell('${d.id}',${n})" id="dot-${d.id}-${n}">${n}</div>`;
    }).join('');
    return `<div class="wellbeing-domain">
      <div class="domain-name">${d.icon} ${d.label}</div>
      <div class="rating-dots">${dots}</div>
    </div>`;
  }).join('');

  // Check for flag (any domain ≤ 2)
  const flaggedDomains = DOMAINS.filter(d => saved[d.id] <= 2 && saved[d.id] > 0);
  const flagHtml = flaggedDomains.length >= 2 ? `
    <div class="flag-card">
      <div class="flag-title">⚠️ Low Score Alert</div>
      <p>You've scored 2 or below on ${flaggedDomains.map(d=>d.label).join(' and ')}. Please talk to your coach before the next session.</p>
    </div>` : '';

  // History
  const histHtml = Object.entries(userWell).slice(-4).reverse().map(([wk, data]) => {
    const avg = DOMAINS.reduce((s,d)=>s+(data[d.id]||0),0)/DOMAINS.length;
    const bar = Math.round(avg/5*100);
    return `<div style="margin-bottom:12px">
      <div style="display:flex;justify-content:space-between;margin-bottom:4px">
        <span style="font-size:13px">${wk}</span>
        <span style="font-size:12px;color:var(--gold);font-weight:700">${Math.round(avg*10)/10} / 5</span>
      </div>
      <div class="progress-bar"><div class="fill" style="width:${bar}%"></div></div>
    </div>`;
  }).join('');

  return `<div class="page">
    <div class="page-header">
      <div class="eyebrow">Weekly Check-In</div>
      <h1>Wellbeing</h1>
      <p>${today} — Rate 1 (very poor) to 5 (excellent)</p>
    </div>
    <div class="card" style="margin-bottom:16px">
      <div class="card-title" style="margin-bottom:16px">Week ${currentWeek} — How Are You Feeling?</div>
      ${domainsHtml}
      ${flagHtml}
      <div style="margin-top:16px">
        <button class="btn btn-green" onclick="saveWellbeing()">Save Check-In</button>
      </div>
    </div>
    ${histHtml ? `<div class="section-title">Recent History</div><div class="card">${histHtml}</div>` : ''}
  </div>`;
}

function setWell(domain, val) {
  wellTemp[domain] = val;
  DOMAINS.forEach(d => {
    [1,2,3,4,5].forEach(n => {
      const el = document.getElementById(`dot-${d.id}-${n}`);
      if (el) {
        el.className = `rating-dot${d.id===domain&&n===val ? ` selected-${n}` : (wellTemp[d.id]===n ? ` selected-${n}` : '')}`;
      }
    });
  });
}

function saveWellbeing() {
  const well = getWell();
  const userKey = currentUser.name.toLowerCase();
  if (!well[userKey]) well[userKey] = {};
  well[userKey][`wk${currentWeek}`] = {...wellTemp};
  saveWell(well);
  showToast('Wellbeing check-in saved ✓');
  navigate('wellbeing');
}

// ════════════════════════════════════════════════════════════════════════════
// NUTRITION & RECOVERY
// ════════════════════════════════════════════════════════════════════════════
function renderNutrition() {
  const tipsHtml = NUTRITION_TIPS.map(t => `
    <div class="card" style="margin-bottom:10px;padding:14px 16px;display:flex;gap:12px;align-items:flex-start">
      <span style="font-size:24px;flex-shrink:0">${t.icon}</span>
      <span style="font-size:14px;line-height:1.5;color:rgba(255,255,255,0.8)">${t.tip}</span>
    </div>`).join('');

  return `<div class="page">
    <div class="page-header">
      <div class="eyebrow">Fuelling for Performance</div>
      <h1>Nutrition</h1>
      <p>Key principles from your nutrition protocol. Food is your most powerful performance tool.</p>
    </div>
    <div class="info-bar">Your full Nutrition Protocol document has the complete meal plans, macros, and game-day fuelling guide. These are your daily reminders.</div>

    <div class="card" style="margin-bottom:20px;background:linear-gradient(135deg,rgba(26,122,66,0.15) 0%,rgba(13,33,55,0.4) 100%);border-color:rgba(26,122,66,0.2)">
      <div style="font-size:10px;font-weight:700;letter-spacing:2px;color:#4ade80;margin-bottom:8px">TODAY'S MOST IMPORTANT ACTION</div>
      <div style="font-size:16px;font-weight:600;color:var(--white);line-height:1.4">Eat 25–40g of protein within 60 minutes of every training session. Chocolate milk ($0.80) counts.</div>
    </div>

    <div class="section-title">Daily Reminders</div>
    ${tipsHtml}

    <div class="section-title">Macro Quick Reference</div>
    <div class="card">
      ${[
        ['Heavy Training Day (Mon/Wed)','6–8g carbs/kg · 1.8–2.2g protein/kg · ~3,500 kcal (70kg)'],
        ['Moderate Training Day (Fri)','5–6g carbs/kg · 1.6–2.0g protein/kg · ~3,000 kcal (70kg)'],
        ['Active Recovery Day (Tue/Thu)','4–5g carbs/kg · 1.6–2.0g protein/kg · ~2,600 kcal (70kg)'],
        ['Game Day','7–9g carbs/kg · 1.8–2.2g protein/kg — carb-load the night before'],
      ].map(([label,val])=>`<div class="test-row"><div><div class="test-name">${label}</div><div style="font-size:12px;color:var(--gray);margin-top:2px">${val}</div></div></div>`).join('')}
    </div>
  </div>`;
}

function renderRecovery() {
  const tipsHtml = RECOVERY_TIPS.map(t => `
    <div class="card" style="margin-bottom:10px;padding:14px 16px;display:flex;gap:12px;align-items:flex-start">
      <span style="font-size:24px;flex-shrink:0">${t.icon}</span>
      <span style="font-size:14px;line-height:1.5;color:rgba(255,255,255,0.8)">${t.tip}</span>
    </div>`).join('');

  return `<div class="page">
    <div class="page-header">
      <div class="eyebrow">Adapt. Rebuild. Repeat.</div>
      <h1>Recovery</h1>
      <p>Recovery is where you adapt. Training breaks you down. Recovery builds you back up stronger.</p>
    </div>

    <div class="card" style="margin-bottom:20px;background:linear-gradient(135deg,rgba(27,79,138,0.2) 0%,rgba(13,33,55,0.4) 100%);border-color:rgba(27,79,138,0.2)">
      <div style="font-size:10px;font-weight:700;letter-spacing:2px;color:#60a5fa;margin-bottom:8px">THE HIERARCHY — DO THESE IN ORDER</div>
      ${[
        ['1','Sleep 8–9 hours every night','Non-negotiable foundation'],
        ['2','Post-session nutrition within 60 min','Protein + carbs after every session'],
        ['3','Hydrate to pale yellow','1.5× fluid lost through sweat'],
        ['4','10 min easy movement on rest days','Walk, swim, or bike — not rest'],
        ['5','Foam roll 3× per week minimum','10 min — target key muscle groups'],
        ['6','Cold water immersion after field/games','NOT after gym sessions'],
      ].map(([n,t,s])=>`<div style="display:flex;gap:12px;align-items:flex-start;padding:8px 0;border-bottom:1px solid var(--border)">
        <div style="width:24px;height:24px;border-radius:50%;background:var(--steel);display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:700;flex-shrink:0">${n}</div>
        <div><div style="font-size:14px;font-weight:600">${t}</div><div style="font-size:12px;color:var(--gray)">${s}</div></div>
      </div>`).join('')}
    </div>

    <div class="section-title">Recovery Reminders</div>
    ${tipsHtml}
  </div>`;
}

// ════════════════════════════════════════════════════════════════════════════
// MOTTOS (Weekly Focus)
// ════════════════════════════════════════════════════════════════════════════
function renderMottos() {
  const phaseColors = {GPP:'var(--green)',ACC:'var(--steel)',TRANS:'#c084fc',REAL:'var(--orange)'};
  const phaseBgs = {GPP:'rgba(26,122,66,0.1)',ACC:'rgba(27,79,138,0.1)',TRANS:'rgba(90,42,122,0.1)',REAL:'rgba(192,80,32,0.1)'};

  const allHtml = WEEKS.map(w => {
    const isCurrentWk = w.wk === currentWeek;
    const c = phaseColors[w.phase];
    const bg = phaseBgs[w.phase];
    return `<div class="card" style="margin-bottom:10px;${isCurrentWk?`border-color:${c};background:${bg}`:''};cursor:default">
      <div style="display:flex;align-items:flex-start;justify-content:space-between;gap:12px;margin-bottom:8px">
        <div>
          <div style="font-size:10px;font-weight:700;letter-spacing:2px;color:${c};margin-bottom:4px">WEEK ${w.wk} · ${w.focus}</div>
          <div style="font-size:15px;font-style:italic;color:var(--white);line-height:1.4">"${w.motto}"</div>
          <div style="font-size:12px;color:var(--gray);margin-top:4px">— ${w.thinker}</div>
        </div>
        ${isCurrentWk ? `<div style="background:${c};color:#fff;font-size:10px;font-weight:700;letter-spacing:1.5px;padding:4px 8px;border-radius:3px;flex-shrink:0">THIS WEEK</div>` : `<div style="color:var(--gray);font-size:12px;flex-shrink:0">Wk${w.wk}</div>`}
      </div>
      <div style="font-size:12px;color:var(--gray);border-top:1px solid var(--border);padding-top:8px">${w.theme}</div>
    </div>`;
  }).join('');

  return `<div class="page">
    <div class="page-header">
      <div class="eyebrow">Character & Performance</div>
      <h1>Weekly Focus</h1>
      <p>Each week has a character theme and a quote from history's great thinkers and leaders. Carry it through the week.</p>
    </div>
    <div class="info-bar">💬 These themes are drawn from philosophy, sport, and leadership. Read Monday. Carry it all week. Reflect Sunday.</div>
    ${allHtml}
  </div>`;
}

// ════════════════════════════════════════════════════════════════════════════
// PROGRAM INFO
// ════════════════════════════════════════════════════════════════════════════
function renderInfo() {
  return `<div class="page">
    <div class="page-header">
      <div class="eyebrow">Bundaberg SHS</div>
      <h1>Program Info</h1>
      <p>Everything you need to know about the Rugby League Academy.</p>
    </div>

    <div class="card" style="margin-bottom:16px;background:linear-gradient(135deg,rgba(201,162,39,0.1) 0%,rgba(13,33,55,0.5) 100%);border-color:rgba(201,162,39,0.2)">
      <div style="font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:28px;color:var(--gold);margin-bottom:4px">RL ACADEMY</div>
      <div style="font-size:13px;color:var(--gray)">Bundaberg State High School · NRL-Standard Methodology</div>
    </div>

    <div class="section-title">Weekly Schedule</div>
    <div class="card" style="margin-bottom:16px">
      ${[
        ['Monday 7:15am','S&C — Lower Body Strength (Gym)','🏋'],
        ['Monday (class)','RL Skills — Attack & Ball Handling','🏉'],
        ['Monday after school','Field Training — Full Team Session','⚡'],
        ['Wednesday 7:15am','S&C — Power & Speed (Gym)','🏋'],
        ['Wednesday after school','Field Training — Scenarios & Review','⚡'],
        ['Friday 7:15am','S&C — Athletic Development (Gym)','🏋'],
        ['Friday (class)','RL Skills — Defence & Film Analysis','🎬'],
      ].map(([day,sess,icon])=>`<div class="session-row">
        <span style="font-size:18px">${icon}</span>
        <div class="session-info">
          <div class="s-name">${sess}</div>
          <div class="s-date">${day}</div>
        </div>
      </div>`).join('')}
    </div>

    <div class="section-title">Non-Negotiables</div>
    <div class="card" style="margin-bottom:16px">
      ${[
        'Arrive ready before the session starts — equipment on, water bottle full',
        'Head ALWAYS on the safe side in every tackle, every time',
        'Log your session in this app after every gym session',
        'RPE logged immediately after each session — honest score only',
        'Neck and trap work NEVER skipped on Fridays',
        'Recovery meal within 60 minutes of finishing training',
        'Sleep target: 8–9 hours every night — this is training too',
      ].map(t=>`<div style="display:flex;gap:10px;padding:8px 0;border-bottom:1px solid var(--border);font-size:13px">
        <span style="color:var(--gold);font-weight:700;flex-shrink:0">✓</span>${t}
      </div>`).join('')}
    </div>

    <div class="section-title">RPE Scale</div>
    <div class="card" style="margin-bottom:16px">
      ${[['6','Easy — too light, go heavier','badge-work'],['7','Challenging — 3 reps left','badge-ok'],['8','Hard — 1–2 reps left (target)','badge-good'],['9','Very Hard — 1 rep left','badge-ok'],['10','Maximum — testing only','badge-work']].map(([n,d,b])=>`
        <div style="display:flex;align-items:center;gap:12px;padding:7px 0;border-bottom:1px solid var(--border)">
          <span class="test-badge ${b}" style="width:32px;text-align:center">${n}</span>
          <span style="font-size:13px">${d}</span>
        </div>`).join('')}
    </div>

    <div class="section-title">Pathways</div>
    <div class="card">
      ${[
        ['Dolphins NRL','Wide Bay Game Development — Danny Blair'],
        ['QRL Wide Bay','Area Manager — Bryce Holdsworth'],
        ['CQ Capras','Community Care Program'],
        ['QRL RISE Program','13–15 year old pathway'],
        ['Dolphins Cup','U15 & U18 schoolboys competition'],
      ].map(([org,detail])=>`<div style="padding:8px 0;border-bottom:1px solid var(--border)">
        <div style="font-size:14px;font-weight:600;color:var(--gold)">${org}</div>
        <div style="font-size:12px;color:var(--gray)">${detail}</div>
      </div>`).join('')}
    </div>
  </div>`;
}

// ════════════════════════════════════════════════════════════════════════════
// UTILS
// ════════════════════════════════════════════════════════════════════════════
function showToast(msg, error=false) {
  const t = document.getElementById('toast');
  t.textContent = (error ? '✕ ' : '✓ ') + msg;
  t.className = 'toast show' + (error?' error':'');
  setTimeout(()=>t.classList.remove('show'), 3000);
}

function toggleMobileMenu() {
  document.getElementById('mobile-menu').classList.toggle('open');
}
function closeMobileMenu(e) {
  if (!e.target.closest('.mobile-menu-panel')) {
    document.getElementById('mobile-menu').classList.remove('open');
  }
}

// ════════════════════════════════════════════════════════════════════════════
// BOOT
// ════════════════════════════════════════════════════════════════════════════
document.addEventListener('DOMContentLoaded', loadApp);
document.getElementById('login-pin').addEventListener('keyup', e => { if (e.key==='Enter') doLogin(); });
document.getElementById('login-name').addEventListener('keyup', e => { if (e.key==='Enter') document.getElementById('login-pin').focus(); });
</script>
</body>
</html>
