<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#080d16">
  <title>EBC — Exército Brasileiro de Combate</title>
  <style>
    :root {
      --bg: #080d16;
      --panel: #101927;
      --panel-light: #142235;
      --line: rgba(255,255,255,.09);
      --text: #f2f5f9;
      --muted: #91a0b5;
      --blue: #2876df;
      --blue-light: #55a1ff;
      --green: #42cf91;
      --gold: #d3ae63;
      --red: #f06c6c;
      --sidebar: 250px;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0;
      color: var(--text);
      background:
        radial-gradient(ellipse at 75% -20%, rgba(32,100,190,.18), transparent 40%),
        var(--bg);
      min-height: 100vh;
    }
    button, input, textarea, select { font: inherit; }
    button, a { -webkit-tap-highlight-color: transparent; }
    button { cursor: pointer; }
    a { color: inherit; text-decoration: none; }

    .layout { min-height: 100vh; }
    .sidebar {
      width: var(--sidebar);
      position: fixed;
      inset: 0 auto 0 0;
      z-index: 20;
      background: rgba(9,15,25,.96);
      border-right: 1px solid var(--line);
      padding: 22px 15px;
      display: flex;
      flex-direction: column;
      transition: transform .25s ease;
      backdrop-filter: blur(14px);
    }
    .brand {
      display: flex;
      gap: 12px;
      align-items: center;
      padding: 5px 8px 22px;
      border-bottom: 1px solid var(--line);
      margin-bottom: 18px;
    }
    .brand-mark {
      width: 43px;
      height: 43px;
      border-radius: 13px;
      background: linear-gradient(145deg, #286ed0, #122d56);
      display: grid;
      place-items: center;
      font-size: 15px;
      font-weight: 900;
      letter-spacing: .5px;
      box-shadow: 0 8px 22px rgba(40,118,223,.22);
    }
    .brand-name { font-weight: 800; font-size: 13px; letter-spacing: .7px; }
    .brand-sub { color: var(--muted); font-size: 10px; margin-top: 4px; letter-spacing: .9px; }
    .nav-label {
      color: #64748b;
      font-size: 10px;
      font-weight: 800;
      letter-spacing: 1.5px;
      padding: 8px 11px;
      text-transform: uppercase;
    }
    .nav-list { display: grid; gap: 4px; }
    .nav-link {
      width: 100%;
      display: flex;
      align-items: center;
      gap: 12px;
      border: 0;
      padding: 10px 11px;
      border-radius: 9px;
      background: transparent;
      color: #aab6c7;
      text-align: left;
      font-size: 13px;
      transition: .2s ease;
    }
    .nav-link:hover, .nav-link.active {
      background: rgba(55,126,220,.15);
      color: white;
    }
    .nav-link.active { box-shadow: inset 2px 0 var(--blue-light); }
    .nav-icon { width: 18px; text-align: center; font-size: 15px; }
    .sidebar-bottom { margin-top: auto; }
    .motto {
      background: linear-gradient(140deg, rgba(35,91,163,.22), rgba(17,29,46,.6));
      border: 1px solid var(--line);
      border-radius: 12px;
      padding: 14px;
      color: #d9e3f0;
      font-size: 11px;
      line-height: 1.7;
    }
    .motto strong { color: var(--gold); letter-spacing: 1px; }

    .main { margin-left: var(--sidebar); min-height: 100vh; }
    .topbar {
      height: 70px;
      position: sticky;
      top: 0;
      z-index: 10;
      display: flex;
      align-items: center;
      justify-content: space-between;
