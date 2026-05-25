<!DOCTYPE html>  
<html lang="sv">  
<head>  
<meta charset="UTF-8">  
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">  
<meta name="apple-mobile-web-app-capable" content="yes">  
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">  
<meta name="apple-mobile-web-app-title" content="R&amp;B Order">  
<meta name="theme-color" content="#FFFFFF">  
<title>Rose &amp; Born · MTM Order</title>  
<style>  
:root {  
  --bg: #FFFFFF; --bg-warm: #FAFAFA; --bg-subtle: #F5F2EB;  
  --ink: #000000; --ink-soft: #1A1A1A; --muted: #666666; --muted-soft: #999999;  
  --line: #E5E5E5; --line-soft: #F0F0F0;  
  --accent: #7A1F1F; --green: #2D5A3D; --amber: #A8741A; --red: #8A2A1A;  
  --shadow-md: 0 4px 12px rgba(0,0,0,0.06);  
}  
* { box-sizing: border-box; margin: 0; padding: 0; }  
html, body { background: var(--bg-warm); color: var(--ink); }  
body { font-family: -apple-system, BlinkMacSystemFont, "SF Pro Text", system-ui, "Helvetica Neue", Arial, sans-serif; font-size: 14px; line-height: 1.5; -webkit-font-smoothing: antialiased; min-height: 100vh; }  
.topbar { background: var(--ink); color: #F5F2EB; padding: 14px 24px; padding-top: max(14px, env(safe-area-inset-top)); display: flex; align-items: center; justify-content: space-between; position: sticky; top: 0; z-index: 100; }  
.brand { font-family: "Hoefler Text", "Cormorant Garamond", Georgia, serif; font-size: 22px; font-weight: 500; }  
.brand .amp { font-style: italic; opacity: 0.85; }  
.brand .sub { font-family: -apple-system, sans-serif; font-size: 9.5px; font-weight: 500; letter-spacing: 0.32em; text-transform: uppercase; margin-left: 14px; opacity: 0.6; }  
.tb-meta { font-size: 10px; letter-spacing: 0.16em; text-transform: uppercase; opacity: 0.6; }  
.nav { background: var(--bg); border-bottom: 1px solid var(--line); padding: 0 24px; display: flex; gap: 4px; overflow-x: auto; -webkit-overflow-scrolling: touch; }  
.nav button { background: transparent; border: 0; padding: 16px 4px; margin: 0 14px 0 0; font-family: -apple-system, sans-serif; font-size: 11px; font-weight: 500; letter-spacing: 0.22em; text-transform: uppercase; color: var(--muted); cursor: pointer; position: relative; white-space: nowrap; }  
.nav button.active { color: var(--ink); font-weight: 600; }  
.nav button.active::after { content: ''; position: absolute; bottom: -1px; left: 0; right: 0; height: 2px; background: var(--ink); }  
.main { max-width: 900px; margin: 0 auto; padding: 24px 22px 80px; }  
h1.page-title { font-family: "Hoefler Text", Georgia, serif; font-size: 32px; font-weight: 500; letter-spacing: -0.01em; margin-bottom: 4px; }  
.page-sub { font-size: 13px; color: var(--muted); margin-bottom: 28px; }  
h2.section-title { font-family: -apple-system, sans-serif; font-size: 10px; font-weight: 600; letter-spacing: 0.28em; text-transform: uppercase; color: var(--muted); margin: 28px 0 12px; padding-bottom: 8px; border-bottom: 1px solid var(--line); }  
.card { background: var(--bg); border: 1px solid var(--line); padding: 20px; margin-bottom: 14px; cursor: pointer; transition: all 0.15s ease; }  
.card:hover { border-color: var(--ink); box-shadow: var(--shadow-md); transform: translateY(-1px); }  
.card-title { font-family: "Hoefler Text", Georgia, serif; font-size: 22px; font-weight: 500; margin-bottom: 4px; }  
.card-meta { font-size: 12px; color: var(--muted); display: flex; flex-wrap: wrap; gap: 12px; margin-top: 6px; }  
.btn { font-family: -apple-system, sans-serif; font-size: 11px; font-weight: 600; letter-spacing: 0.18em; text-transform: uppercase; padding: 12px 22px; border: 1px solid var(--ink); background: var(--bg); color: var(--ink); cursor: pointer; transition: all 0.15s ease; border-radius: 0; text-decoration: none; display: inline-block; }  
.btn:hover { background: var(--ink); color: var(--bg); }  
.btn.primary { background: var(--ink); color: var(--bg); }  
.btn.primary:hover { background: var(--accent); border-color: var(--accent); }  
.btn.ghost { border-color: transparent; color: var(--muted); }  
.btn.ghost:hover { background: transparent; color: var(--ink); }  
.btn.small { padding: 8px 14px; font-size: 10px; letter-spacing: 0.14em; }  
.btn.danger { color: var(--red); border-color: var(--red); }  
.btn.danger:hover { background: var(--red); color: var(--bg); }  
.btn-row { display: flex; gap: 10px; flex-wrap: wrap; margin-bottom: 24px; }  
.form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px 22px; }  
@media (max-width: 640px) { .form-grid { grid-template-columns: 1fr; } }  
.field { display: flex; flex-direction: column; gap: 6px; }  
.field.full { grid-column: 1 / -1; }  
.field label { font-family: -apple-system, sans-serif; font-size: 10px; font-weight: 600; letter-spacing: 0.22em; text-transform: uppercase; color: var(--muted); }  
.field input, .field select, .field textarea { font-family: -apple-system, sans-serif; font-size: 15px; color: var(--ink); background: var(--bg); border: 0; border-bottom: 1px solid var(--line); padding: 8px 0 10px; -webkit-appearance: none; appearance: none; transition: border-color 0.15s; }  
.field textarea { border: 1px solid var(--line); padding: 10px 12px; font-size: 14px; line-height: 1.5; resize: vertical; min-height: 80px; font-family: -apple-system, sans-serif; }  
.field input:focus, .field select:focus, .field textarea:focus { outline: none; border-bottom-color: var(--ink); border-color: var(--ink); }  
.plagg-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(180px, 1fr)); gap: 10px; }  
.plagg-card { border: 1px solid var(--line); background: var(--bg); padding: 14px 16px; cursor: pointer; transition: all 0.12s; text-align: left; font-family: -apple-system, sans-serif; font-size: 13px; color: var(--ink); min-height: 56px; display: flex; align-items: center; }  
.plagg-card:hover { border-color: var(--ink); background: var(--bg-subtle); }  
.plagg-card.selected { border-color: var(--ink); background: var(--ink); color: var(--bg); font-weight: 500; }  
.empty { text-align: center; padding: 60px 20px; color: var(--muted); }  
.empty .e-icon { font-family: "Hoefler Text", Georgia, serif; font-size: 36px; font-style: italic; color: var(--muted-soft); margin-bottom: 14px; }  
.empty .e-title { font-family: "Hoefler Text", Georgia, serif; font-size: 20px; color: var(--ink); margin-bottom: 8px; }  
.empty .e-msg { font-size: 13px; margin-bottom: 20px; }  
.pill { display: inline-block; font-size: 10px; letter-spacing: 0.12em; text-transform: uppercase; font-weight: 600; padding: 3px 8px; background: var(--bg-subtle); color: var(--ink-soft); }  
.pill.green { background: rgba(45,90,61,0.1); color: var(--green); }  
.pill.amber { background: rgba(168,116,26,0.1); color: var(--amber); }  
.order-summary { background: var(--bg-subtle); padding: 16px 18px; margin-bottom: 24px; font-size: 13px; }  
.order-summary .os-row { display: flex; justify-content: space-between; padding: 4px 0; }  
.order-summary .os-row .k { color: var(--muted); }  
.order-summary .os-row .v { font-weight: 500; }  
.modal-overlay { position: fixed; inset: 0; background: rgba(0,0,0,0.5); z-index: 200; display: none; align-items: center; justify-content: center; padding: 20px; }  
.modal-overlay.show { display: flex; }  
.modal { background: var(--bg); max-width: 540px; width: 100%; padding: 28px; max-height: 90vh; overflow-y: auto; }  
.modal h3 { font-family: "Hoefler Text", Georgia, serif; font-size: 24px; font-weight: 500; margin-bottom: 18px; }  
.modal .modal-actions { margin-top: 24px; display: flex; gap: 10px; justify-content: flex-end; }  
.toast { position: fixed; bottom: 30px; left: 50%; transform: translateX(-50%); background: var(--ink); color: var(--bg); padding: 12px 22px; font-size: 12px; letter-spacing: 0.08em; z-index: 300; opacity: 0; pointer-events: none; transition: opacity 0.25s; }  
.toast.show { opacity: 1; }  
.plagg-rad { border: 1px solid var(--line); padding: 22px; margin-bottom: 16px; background: var(--bg); }  
.plagg-rad-head { display: flex; justify-content: space-between; align-items: baseline; margin-bottom: 16px; gap: 14px; }  
.plagg-rad-head .pr-title { font-family: "Hoefler Text", Georgia, serif; font-size: 20px; font-weight: 500; }  
.plagg-rad-head .pr-num { font-size: 10px; font-weight: 600; letter-spacing: 0.22em; text-transform: uppercase; color: var(--accent); }  
.add-plagg-btn { width: 100%; padding: 18px; border: 2px dashed var(--line); background: transparent; cursor: pointer; font-family: -apple-system, sans-serif; font-size: 12px; font-weight: 600; letter-spacing: 0.18em; text-transform: uppercase; color: var(--muted); transition: all 0.15s; }  
.add-plagg-btn:hover { border-color: var(--ink); color: var(--ink); border-style: solid; background: var(--bg-subtle); }  
.size-info { background: var(--bg-subtle); padding: 10px 14px; font-size: 12px; color: var(--muted); margin-bottom: 16px; border-left: 3px solid var(--accent); }  
.vast-toggle { display: flex; align-items: center; gap: 10px; padding: 12px 0; font-size: 13px; color: var(--muted); }  
.vast-toggle input { width: 18px; height: 18px; cursor: pointer; }  
.pdf-view { background: var(--bg); padding: 40px; max-width: 720px; margin: 0 auto; border: 1px solid var(--line); box-shadow: var(--shadow-md); }  
.pdf-header { text-align: center; border-bottom: 1px solid var(--ink); padding-bottom: 20px; margin-bottom: 24px; }  
.pdf-header h1 { font-family: "Hoefler Text", Georgia, serif; font-size: 28px; font-weight: 500; letter-spacing: 0.04em; text-transform: uppercase; margin-bottom: 4px; }  
.pdf-header .pdf-sub { font-size: 10px; letter-spacing: 0.28em; text-transform: uppercase; color: var(--muted); }  
.pdf-section { margin-bottom: 24px; page-break-inside: avoid; }  
.pdf-section h2 { font-family: "Hoefler Text", Georgia, serif; font-size: 14px; font-weight: 600; background: var(--ink-soft); color: var(--bg); padding: 5px 10px; letter-spacing: 0.02em; }  
.pdf-section .pdf-row { display: grid; grid-template-columns: 180px 1fr; padding: 5px 10px; font-size: 12px; border-bottom: 1px solid var(--line-soft); }  
.pdf-section .pdf-row .k { font-weight: 600; font-size: 11px; }  
.pdf-section .pdf-row .v { font-size: 12px; white-space: pre-wrap; }  
@media print { .topbar, .nav, .btn-row, .toast, .modal-overlay { display: none !important; } body { background: white; } .main { padding: 0; } .pdf-view { border: 0; box-shadow: none; padding: 0; max-width: 100%; } .pdf-section { page-break-inside: avoid; } }  
  
/* Login screen */  
.login-screen {  
  position: fixed; inset: 0; z-index: 1000;  
  background: var(--ink); color: #F5F2EB;  
  display: flex; flex-direction: column; align-items: center; justify-content: center;  
  padding: 40px 24px;  
}  
.login-screen.hidden { display: none; }  
.login-brand-rose {  
  display: block;  
  width: 110px; height: auto;  
  margin: 0 auto 28px;  
  opacity: 0.95;  
}  
.login-brand-wordmark {  
  display: block;  
  width: 240px; height: auto;  
  margin: 0 auto 10px;  
  opacity: 0.95;  
}  
.login-sub {  
  font-size: 10px; letter-spacing: 0.32em; text-transform: uppercase;  
  opacity: 0.5; margin-bottom: 48px;  
}  
.login-box { width: 100%; max-width: 320px; }  
.login-label {  
  font-size: 10px; font-weight: 600; letter-spacing: 0.22em;  
  text-transform: uppercase; opacity: 0.6; margin-bottom: 10px;  
}  
.login-input {  
  width: 100%; font-family: -apple-system, sans-serif; font-size: 18px;  
  color: #F5F2EB; background: transparent;  
  border: 0; border-bottom: 1px solid rgba(245,242,235,0.3);  
  padding: 10px 0; outline: none; letter-spacing: 0.1em;  
}  
.login-input:focus { border-bottom-color: #F5F2EB; }  
.login-btn {  
  margin-top: 28px; width: 100%; padding: 14px 22px;  
  font-family: -apple-system, sans-serif; font-size: 11px; font-weight: 600;  
  letter-spacing: 0.22em; text-transform: uppercase;  
  background: #F5F2EB; color: var(--ink); border: 0; cursor: pointer;  
  transition: background 0.15s;  
}  
.login-btn:hover { background: #FFFFFF; }  
.login-error {  
  margin-top: 14px; font-size: 12px; color: #E89A7A;  
  opacity: 0; transition: opacity 0.2s; min-height: 18px;  
}  
.login-error.show { opacity: 1; }  
</style>  
</head>  
<body>  
<div class="login-screen" id="login-screen">  
  <img class="login-brand-rose" src="data:image/png;base64,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" alt="Rose">  
  <img class="login-brand-wordmark" src="data:image/png;base64,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" alt="Rose & Born">  
  <div class="login-sub">MTM Order Management</div>  
  <div class="login-box">  
    <div class="login-label">Password</div>  
    <input type="password" class="login-input" id="login-input" autocomplete="off" autofocus>  
    <button class="login-btn" id="login-btn">Enter</button>  
    <div class="login-error" id="login-error">Wrong password</div>  
  </div>  
</div>  
<header class="topbar">  
  <div>  
    <span class="brand">Rose <span class="amp">&amp;</span> Born</span>  
    <span class="brand sub">MTM Order</span>  
  </div>  
  <div class="tb-meta">v1.8</div>  
</header>  
<nav class="nav">  
  <button data-view="customers" class="active">Customers</button>  
  <button data-view="new-order">New Order</button>  
  <button data-view="orders">All Orders</button>  
</nav>  
<main class="main" id="main"></main>  
<div class="toast" id="toast"></div>  
<div class="modal-overlay" id="modal-overlay"><div class="modal" id="modal"></div></div>  
<script>  
// ============================================================  
// LOGIN  
// ============================================================  
const AUTH_KEY = 'rb_auth_v1';  
const PASSWORD = '1989';  
  
function isAuthed() {  
  try { return localStorage.getItem(AUTH_KEY) === 'ok'; } catch(_) { return false; }  
}  
function setAuthed() {  
  try { localStorage.setItem(AUTH_KEY, 'ok'); } catch(_) {}  
}  
  
function setupLogin() {  
  const screen = document.getElementById('login-screen');  
  const input = document.getElementById('login-input');  
  const btn = document.getElementById('login-btn');  
  const err = document.getElementById('login-error');  
  
  function tryLogin() {  
    if (input.value === PASSWORD) {  
      setAuthed();  
      screen.classList.add('hidden');  
      // Starta appen nu när auth är klar  
      initApp();  
    } else {  
      err.classList.add('show');  
      input.value = '';  
      input.focus();  
      setTimeout(() => err.classList.remove('show'), 2000);  
    }  
  }  
  
  btn.addEventListener('click', tryLogin);  
  input.addEventListener('keydown', e => {  
    if (e.key === 'Enter') tryLogin();  
    err.classList.remove('show');  
  });  
  
  if (isAuthed()) {  
    screen.classList.add('hidden');  
    return true;  
  }  
  setTimeout(() => input.focus(), 100);  
  return false;  
}  
  
// initApp() körs efter login (eller direkt om redan inloggad)  
function initApp() {  
  loadStore();  
  render();  
}  
  
// ============================================================  
// STORAGE  
// ============================================================  
const STORAGE_KEY = 'rb_order_data_v3';  
let store = { customers: [], orders: [] };  
  
function loadStore() {  
  try { const d = localStorage.getItem(STORAGE_KEY); if (d) store = JSON.parse(d); } catch(_) {}  
  if (!store.customers) store.customers = [];  
  if (!store.orders) store.orders = [];  
  // Seed demo data om store är helt tomt (förstagångsöppning)  
  if (store.customers.length === 0 && store.orders.length === 0) {  
    seedChrisHart();  
    saveStore();  
  }  
}  
function saveStore() { try { localStorage.setItem(STORAGE_KEY, JSON.stringify(store)); } catch(e) { toast('localStorage full'); } }  
function uid() { return Date.now().toString(36) + Math.random().toString(36).substr(2, 5); }  
function fmtDate(iso) { if (!iso) return ''; return new Date(iso).toLocaleDateString('sv-SE'); }  
function todayISO() { return new Date().toISOString().split('T')[0]; }  
  
// ============================================================  
// SEED — Chris Hart med 14 ordrar från GoCreate (trunkshow feb-maj 2026)  
// ============================================================  
function seedChrisHart() {  
  const customer = {  
    id: uid(),  
    name: 'Chris Hart',  
    email: 'hartc@unitedtalent.com',  
    phone: '+1 310 497 9200',  
    notes: 'UTA. Trunkshow customer.',  
    createdAt: '2026-02-02'  
  };  
  store.customers.push(customer);  
  const cid = customer.id;  
  
  // Helper: skapa plagg-rad med givna fält  
  function p(type, size, fabric, lining, button, designByPart, fittoolsByPart, remark) {  
    const def = PLAGG_TYPES.find(x => x.key === type);  
    const rad = { id: uid(), type, size: size || '', fabric: fabric || '', lining: lining || '',  
      button: button || '', design: {}, fittools: {}, remark: remark || '',  
      includeVest: false, vestDesign: '', vestFitTools: '' };  
    def.parts.forEach(part => {  
      rad.design[part] = (designByPart && designByPart[part]) || '';  
      rad.fittools[part] = (fittoolsByPart && fittoolsByPart[part]) || '';  
    });  
    return rad;  
  }  
  
  function ord(date, plaggArr, notes) {  
    return { id: uid(), customerId: cid, status: 'confirmed', plagg: plaggArr,  
      deliveryDate: '', occasion: 'Work', notes: notes || '',  
      createdAt: date, updatedAt: date };  
  }  
  
  // --- SHIRT 3 (denim) ---  
  const shirtFitTools = 'Let out collar +1.00\nLet out ½ chest front +1.00\nLet out ½ back +1.00\nTake in ½ waist -0.50\nTake in ½ hip -2.00\nLengthen front +1.00\nLengthen length +1.00\nLet out forearm +1.00\nLengthen sleeve R +1.00\nLengthen sleeve L +1.00\nLet out cuff R +0.50\nLet out cuff L +0.50';  
  
  const shirtBrand = 'BrandingOptions:\nSize label: No\n1.1 Inside back yoke: New R&B Shirt label*\n1.2 Inside back yoke: No\n4. Button placket: No';  
  
  const shirt1Design = 'Collar style: button-down (4 cm)\nCollar stays: none\nSkinning: soft\nFront closure: narrow placket\nSleeve style: long sleeves\nBack yoke: 1 piece\nCuff style: single, rounded 1 button (7 cm)\nSleeve vent: middle button\nButton attachment: lily (by hand)\nBack darts: standard\nEdge stitching: 3 mm from edge\nChest pockets: none\nBack style: 1 centre box pleat\nHem shape: curved\nElbow patches: same as fabric\nPocket square: same as fabric\nPre-washed: no\nPackaging: standard\nYarn thickness: thick\n\nContrast: all best match / no contrast\n\nMonogram: H.H., navy blue, ornamental, top of sleeve vent\n\n' + shirtBrand;  
  
  const shirt2Design = 'Collar style: semi-cutaway (4 cm)\nCollar stays: removable\nSkinning: soft\nFront closure: plain\nSleeve style: long sleeves\nBack yoke: 2 pieces\nCuff style: single, slanted-corner 1 button (7 cm)\nSleeve vent: low button\nButton attachment: lily (by hand)\nBack darts: standard\nEdge stitching: 1 mm from edge\nChest pockets: none\nBack style: plain\nHem shape: curved\nElbow patches: none\nPocket square: none\nPre-washed: no\nPackaging: standard\nYarn thickness: standard\n\nContrast: all best match / no contrast\n\nMonogram: H.H., navy blue, ornamental, top of sleeve vent\n\n' + shirtBrand;  
  
  const shirt3Design = 'Collar style: semi-cutaway (4 cm)\nCollar stays: removable\nSkinning: soft\nFront closure: plain\nSleeve style: long sleeves\nBack yoke: 2 pieces\nCuff style: Neapolitan with 2 buttons (7 cm)\nSleeve vent: low button\nButton attachment: lily (by hand)\nBack darts: standard\nEdge stitching: 3 mm from edge\nChest pockets: none\nBack style: plain\nHem shape: curved\nElbow patches: none\nPocket square: none\nPre-washed: no\nPackaging: standard\nYarn thickness: standard\n\nContrast: all best match / no contrast\n\nMonogram: H.H., navy blue, ornamental, top of sleeve vent\n\n' + shirtBrand;  
  
  // --- JACKET standalone (caramel cashmere) ---  
  const jacketDesign1 = 'Canvassing: none (unconstructed)\nClosure & lapel: 2.5 buttons with notch lapel\nLapel width: wide\nLower gorge: regular\nLapel buttonhole: long milanese\nShoulder type: unconstructed\nChest pocket: rounded welt\nSide pockets: rounded patch\nDouble patch: none\nTicket pocket: none\nPocket flap height: no pocket flap\nCuff finishing: 4 kissing buttons with open cuff\n1st sleeve buttonhole left: standard\nVents: 2 side vents\nLining style: half-lined\nInside facing: jet facing\nSleeve lining: same as body lining\nPick stitching (AMF): extensive, 6 mm from edge\nTuxedo (lapel & jets): none\nThroat tab: none\nElbow patches: none\nHidden lining pocket: none\n\nContrast: under collar best match, inside jets same as fabric, inside pick stitching best match with lining, all BH best match\n\nMonogram: C.H., best match with fabric, ornamental, lining left\n\nBranding:\nSize label: No\nHangerloop: R&B Hangerloop new\n3.1 Inside below left pocket: Rose & Born Main label new\n3.2 Inside below left pocket: No\n5. Inside bottom left: Fabric Supplier Label';  
  
  const jacketFitTools = 'Collar pleat -0.50\nSlope shoulder R -1.00\nSlope shoulder L -0.50\nLet out ½ shoulder +0.50\nRaise vent(s) +1.50\nLower chest pocket -1.00\nLower closing button -2.00\nLengthen length +1.00\nRaise armhole +0.50\nLengthen sleeve R +1.00\nLengthen sleeve L +1.00\nChest dart: standard\nForward shoulders: no\nNeck dart: no';  
  
  // --- SUIT 2-piece (midnight blue) ---  
  const suitJacketDesign = 'Canvassing: none (unconstructed)\nClosure & lapel: double-breasted 6 buttons with peak lapel\nLapel width: wide straight\nLower gorge: low\nLapel buttonhole: long milanese\nShoulder type: unconstructed\nChest pocket: rounded welt\nSide pockets: straight jet\nDouble patch: none\nTicket pocket: none\nPocket flap height: no pocket flap\nCuff finishing: 4 kissing buttons with open cuff\n1st sleeve buttonhole left: standard\nVents: 2 side vents\nLining style: half-lined\nInside facing: jet facing\nSleeve lining: same as body lining\nPick stitching (AMF): extensive, 2 mm from edge\nTuxedo (lapel & jets): none\nThroat tab: none\nElbow patches: none\nHidden lining pocket: none\n\nContrast: under collar best match, inside jets same as lining, inside pick stitching best match with lining, all BH best match\n\nMonogram: C.H., mid brown, ornamental, lining left\n\nBranding:\nSize label: No\nHangerloop: R&B Hangerloop new\n3.1 Inside: Rose & Born Main label new\n3.2 Inside: No\n5. Inside bottom left: Fabric Supplier Label';  
  
  const suitTrousersDesign = 'Waistband: plain\nWaistband detailing: high waistband double button (metal color buckle)\nTuxedo waistband: same as fabric\nFront style: single pleat\nClosure: zip fly\nSide pockets: slanted\nCargo pockets: none\nBack pocket(s): welt without button\nHem finish: turn up (5 cm)\nPocket lining: TPC004 dark blue\nPick stitching (AMF): none\nTuxedo side stripe: none\nCoin pocket: yes\nPleat direction: outwards\nPleat depth: standard\nPintuck: no\nSuspender buttons: no\nBuckle loop: no\nCrotch piece: standard\nLeg lining: half-lined front\n\nContrast: pick stitching none, BH best match\n\nBranding:\nSize label: No\n1.1 Pocket lining right back: R&B Hangerloop new';  
  
  const trousersFitTools = 'Raise total rise +1.00\nLet out crotch +1.00\nTake in ½ waist -1.00\nTake in ½ back seam -0.50\nTake in ½ thigh -1.00\nTake in ½ knee -1.00\nTake in ½ hem -0.50\nShorten leg R -1.50\nShorten leg L -1.50\nProminent seat: without\nFlat seat: without';  
  
  // --- TROUSERS standalone (taupe stretch wool-silk hopsack) ---  
  const trousers1Design = 'Waistband: buckle & strap (metal colour)\nWaistband detailing: extended\nTuxedo waistband: same as fabric\nFront style: single pleat\nClosure: zip fly\nSide pockets: slanted\nCargo pockets: none\nBack pocket(s): 1 jet with button (right)\nHem finish: turn up (5 cm)\nPocket lining: TPC003 off-white with anti-slip\nPick stitching (AMF): 2 mm from edge\nTuxedo side stripe: none\nCoin pocket: yes\nPleat direction: outwards\nPleat depth: standard\nPintuck: no\nSuspender buttons: no\nBuckle loop: no\nCrotch piece: standard\nLeg lining: half-lined front\n\nContrast: pick stitching best match, BH best match\n\nBranding:\nSize label: No\n1.1 Pocket lining right back: R&B Hangerloop new*\n1.3 Pocket lining left front: Fabric Supplier Label';  
  
  // --- TROUSERS standalone (bone sharkskin) ---  
  const trousers2Design = 'Waistband: button & tab\nWaistband detailing: extended\nTuxedo waistband: same as fabric\nFront style: single pleat\nClosure: zip fly\nSide pockets: slanted\nCargo pockets: none\nBack pocket(s): jet with button\nHem finish: turn up (4 cm)\nPocket lining: TPC003 off-white\nPick stitching (AMF): 2 mm from edge\nTuxedo side stripe: none\nCoin pocket: yes\nPleat direction: outwards\nPleat depth: standard\nPintuck: no\nSuspender buttons: no\nBuckle loop: no\nCrotch piece: standard\nLeg lining: half-lined front\n\nContrast: pick stitching best match, BH best match\n\nBranding:\nSize label: No\n1.1 Pocket lining right back: R&B Hangerloop new*';  
  
  // --- INFORMAL JACKET (forest green tech) ---  
  const ijDesign = 'Closure: zip closure with snap buttons\nLapel buttonhole: no buttonhole\nChest pocket: none\nSide pockets: bellow\nCuff finishing: cuff with pleats with 1 button\nVent: 2 side vents (overlapping)\nWaist detailing: none\nLining style: no lining\nInside facing: lower patch\nSleeve lining: none\nPick stitching (AMF): extensive, 2 mm pick stitching (AMF)\n\nContrast: edge stitching best match, lapel BH no buttonhole, all other BH best match\n\nBranding:\nSize label: No\n1.1 Inside facing left: No\n1.2 Inside facing left: Rose & Born Main label new*\n3. Inside pocket right: Fabric Supplier Label';  
  
  const ijFitTools = 'Collar pleat -0.50\nSlope shoulder R -1.00\nSlope shoulder L -0.50\nLet out ½ shoulder +0.50\nLet out ½ back +0.50\nLet out ½ chest front +0.50\nLower closing button -2.00\nLet out ½ waist +0.50\nShorten length -1.00\nRaise armhole +0.50\nLet out upper arm & armhole +0.50\nLengthen sleeve R +1.00\nLengthen sleeve L +1.00';  
  
  // --- JEANS / 5-pocket ---  
  const jeansDesign = 'Closing button: RB006 regular gun metal\nWaistband: classic (single belt loop)\nBuckle loop: no\nClosure: button fly\nRivets: RB006 regular gun metal\nPocket lining: POC002 off-white\nFront pockets: curved\nCoin pocket: extended\nBack pockets: standard\nHem finish: standard\nWash effect: plain\nBack patch: none\nContrast topstitching: best match\n\nMeasurements:\nTotal rise 1.00, Front rise 0.00, Back rise 0.00, ½ waist 45.00, ½ thigh 28.20, ½ knee 21.70, ½ Foot 18.60, Inseam R 85.40, Inseam L 85.40\nLaundry shrinkage compensation: No\n\nBranding:\nSize label: No\n2. Inside waistband left front: New Rose & Born Luxury Denim\n4. Inside waistband left back: No';  
  
  // --- KNITWEAR helper (alla samma struktur) ---  
  function knit(button, knitType, neckline, sleeveStyle, brandLabel, detailing) {  
    let d = 'Knit type: ' + knitType + '\nNeckline / Closure: ' + neckline + '\nSilhouette: traditional cut\nArmhole style: classic\n';  
    if (detailing) d += 'Detailing collar/hem/cuff: ' + detailing + '\n';  
    d += 'Sleeve style: ' + sleeveStyle + '\nChest pocket: none\nSide pockets: none\nContrast option: no contrast\nContrast color: no contrast\n\nBranding:\nSize label: No\n1. Inside back: ' + brandLabel;  
    return d;  
  }  
  
  // --- SHOES ---  
  const runnerDesign = 'Sole: off-white/midnight rubber\nLining: midnight leather\nContrast back piece: no contrast\nContrast tongue: no contrast\nShoe trees: no\nExtra pair of laces: no\nBelt: no\n\nMain material: SDE26 Suede midnight blue\nSecondary material: MES08 Mesh navy\n\nBranding:\nSize label: No\n1. Heel of insole: No';  
  
  const formalDesign = 'Model: plain toe loafer\nShoe trees: no\nSole: leather with rubber grip\nBelt: no\nMonogram text: Chris\n\nLeather: SDE06 Suede taupe\n\nBranding:\nSize label: No\n1. Heel of insole: No\n3. Inside belt: No';  
  
  // === ORDRAR (sorterade på datum) ===  
  
  // 25 May 2026 - trunkshow  
  // 3 shirts + 1 jacket + 1 suit (suit har 2 plagg-rader i en order eller delas? – från PDF är de 5 olika order-IDn)  
  // PDF visar 5 separata GoCreate-ordrar. Jag samlar in dem som EN order per tillfälle med flera plagg-rader.  
  const may25Plagg = [  
    p('shirt', 'Slim 2.0 / handmade / 41',  
      'SH00169 l.blue 120/2 washed cotton denim twill', '',  
      'RB031 white thick mother of pearl look with round edge',  
      { 'Shirt': shirt1Design }, { 'Shirt': shirtFitTools }),  
    p('shirt', 'Slim 2.0 / handmade / 41',  
      'SH00358 white fine cotton pinpoint', '',  
      'RB031 white thick mother of pearl look with round edge',  
      { 'Shirt': shirt2Design }, { 'Shirt': shirtFitTools }),  
    p('shirt', 'Slim 2.0 / handmade / 41',  
      'SH00454 white cotton poplin with d.blue bold stripes', '',  
      'RB031 white thick mother of pearl look with round edge',  
      { 'Shirt': shirt3Design }, { 'Shirt': shirtFitTools }),  
    p('jacket', 'Slim 2.0 / unconstructed / 52',  
      'ASF026 (LP - CAAM) soft caramel stretch cashmere plain weave', '8134 camel',  
      'RB050 d.brown horn',  
      { 'Jacket': jacketDesign1 }, { 'Jacket': jacketFitTools }),  
    (() => {  
      const r = p('suit', 'Jacket: Slim 2.0 / unconstructed / 52 · Trousers: T40 / traditional with pleated waistband / 52',  
        '6087 (LP - SU) midnight blue wool-silk-linen tropical', '7494 midnight blue',  
        'RB050 d.brown horn',  
        { 'Jacket': suitJacketDesign, 'Trousers': suitTrousersDesign },  
        { 'Jacket': jacketFitTools, 'Trousers': trousersFitTools });  
      return r;  
    })()  
  ];  
  store.orders.push(ord('2026-05-25', may25Plagg, 'Trunkshow 25 May 2026'));  
  
  // 18 March 2026 - trunkshow (delivery ~13-14-21-28 Apr)  
  const mar18Plagg = [  
    p('knitwear', 'K40 / traditional / 52', 'K10255 m.blue cotton-silk', '',  
      '39. l.blue thin mother of pearl look with medium rim',  
      { 'Knitwear': knit('39. l.blue', 'single yarn solid', 'polo', 'short sleeves', '8. Rose & Born Main shirt label') }, {}),  
    p('knitwear', 'K40 / traditional / 52', 'K10268 taupe cotton-silk', '',  
      '7. white thin mother of pearl with medium rim',  
      { 'Knitwear': knit('7. white', 'single yarn solid', 'polo', 'short sleeves', '8. Rose & Born Main shirt label') }, {}, 'Payment: Cash'),  
    p('shoes', 'Standard / Ago (NEW/Runner) / Left-44.5 Right-45.5',  
      'SDE26 Suede midnight blue', 'midnight leather', '',  
      { 'Shoes': 'Item: Runner\n' + runnerDesign }, {}),  
    p('trousers', 'T40 / traditional / 52',  
      'ASF007 (LP - LM) taupe stretch wool-silk hopsack', '',  
      '58. taupe semi-shiny mother of pearl',  
      { 'Trousers': trousers1Design }, { 'Trousers': trousersFitTools }),  
    p('knitwear', 'K40 / traditional / 52', 'K10168 LP S160 off-white ultra-fine merino', '', '',  
      { 'Knitwear': knit('', 'double yarn solid', 'crew neck (3.0 cm)', 'short sleeves', '8. Rose & Born Main shirt label', 'standard rib') }, {}),  
    p('jeans', 'Slim / 5 pocket the sartorial / 34/34',  
      'COL008 light sand twill stretch', '',  
      'RB006 regular gun metal',  
      { 'Jeans': jeansDesign }, {}),  
    p('knitwear', 'K40 / traditional / 52', 'K10198 ZB green mélange extra-fine merino', '',  
      '28. jade green galalith',  
      { 'Knitwear': knit('28. jade green galalith', 'single yarn solid', 'polo', 'short sleeves', '8. Rose & Born Main shirt label') }, {}),  
    p('informal_jacket', 'SJ40 / unconstructed / 52',  
      'OLM004 forest green stretch water-repellent technical fabric', '6383 forest green',  
      '7. grey horn',  
      { 'Informal Jacket': ijDesign }, { 'Informal Jacket': ijFitTools }),  
    p('shoes', 'Standard / blake / Left-44 Right-44',  
      'SDE06 Suede taupe', '', '',  
      { 'Shoes': 'Item: Formal round\n' + formalDesign }, {}, 'Payment: Factuur'),  
    p('knitwear', 'K40 / traditional / 52', 'K10151 white cotton-silk', '',  
      '4. white thin mother of pearl',  
      { 'Knitwear': knit('4. white', 'single yarn solid', 'polo', 'short sleeves', 'New R&B KNIT Label') }, {}),  
    p('trousers', 'T40 / traditional with pleated waistband / 52',  
      '6058 (LP - LW) bone mélange linen-wool-silk sharkskin', '',  
      '59. taupe shiny mother of pearl',  
      { 'Trousers': trousers2Design }, { 'Trousers': trousersFitTools })  
  ];  
  store.orders.push(ord('2026-03-18', mar18Plagg, 'Trunkshow 18 March 2026'));  
  
  // 02 February 2026 - trunkshow  
  const feb02Plagg = [  
    p('knitwear', 'K40 / traditional / 52', 'K10170 LP S160 taupe ultra-fine merino', '',  
      '48. taupe mother of pearl look with medium rim',  
      { 'Knitwear': knit('48. taupe', 'double yarn solid', 'polo', 'long sleeves', 'New R&B KNIT Label') }, {}, 'Payment: Factuur'),  
    p('knitwear', 'K40 / traditional / 52', 'K10167 LP S160 l.grey ultra-fine merino', '',  
      '7. white thin mother of pearl with medium rim',  
      { 'Knitwear': knit('7. white', 'double yarn solid', 'polo', 'long sleeves', '8. Rose & Born Main shirt label') }, {}),  
    p('knitwear', 'K40 / traditional / 52', 'K10164 LP S160 black ultra-fine merino', '',  
      '45. black thin mother of pearl look with medium rim',  
      { 'Knitwear': knit('45. black', 'double yarn solid', 'polo', 'long sleeves', '8. Rose & Born Main shirt label') }, {}),  
    p('knitwear', 'K40 / traditional / 52', 'K10168 LP S160 off-white ultra-fine merino', '',  
      '7. white thin mother of pearl with medium rim',  
      { 'Knitwear': knit('7. white', 'double yarn solid', 'polo', 'long sleeves', '8. Rose & Born Main shirt label') }, {})  
  ];  
  store.orders.push(ord('2026-02-02', feb02Plagg, 'Trunkshow 2 February 2026'));  
  
  // ============================================================  
  // ADAM JIWAN  
  // ============================================================  
  const adam = {  
    id: uid(),  
    name: 'Adam Jiwan',  
    email: '',  
    phone: '+1 917 460 6582',  
    notes: 'Trunkshow customer. Mobile only.',  
    createdAt: '2026-01-29'  
  };  
  store.customers.push(adam);  
  const aid = adam.id;  
  
  function ordA(date, plaggArr, notes) {  
    return { id: uid(), customerId: aid, status: 'confirmed', plagg: plaggArr,  
      deliveryDate: '', occasion: 'Work', notes: notes || '',  
      createdAt: date, updatedAt: date };  
  }  
  
  // --- KNIT-mall för Adam (med Shorten sleeve -2.50 om long sleeves) ---  
  function adamKnitDesign(button, knitType, neckline, sleeveStyle, brandLabel, contrastOpt, contrastCol, detailing, silhouetteIncluded) {  
    let d = '';  
    if (button) d += 'Button: ' + button + '\n';  
    d += 'Knit type: ' + knitType + '\nNeckline / Closure: ' + neckline + '\n';  
    if (silhouetteIncluded !== false) d += 'Silhouette: traditional cut\n';  
    d += 'Armhole style: classic\n';  
    if (detailing) d += 'Detailing collar/hem/cuff: ' + detailing + '\n';  
    d += 'Sleeve style: ' + sleeveStyle + '\nChest pocket: none\nSide pockets: none\n';  
    d += 'Contrast option: ' + (contrastOpt || 'no contrast') + '\n';  
    d += 'Contrast color: ' + (contrastCol || 'no contrast') + '\n';  
    d += '\nBranding:\nSize label: No\n1. Inside back: ' + brandLabel;  
    return d;  
  }  
  
  // === ADAM JIWAN ORDRAR ===  
  
  // --- 5 May 2026 ---  
  const may05Plagg = [  
    p('knitwear', 'K40 / traditional / 52', 'K10074 l.blue cashmere-silk', '',  
      '6. white thin mother of pearl with wide rim',  
      { 'Knitwear': adamKnitDesign('6. white thin mother of pearl with wide rim', 'single yarn solid', 'polo', 'long sleeves', '8. Rose & Born Main shirt label') },  
      { 'Knitwear': 'Shorten sleeve -2.50' })  
  ];  
  store.orders.push(ordA('2026-05-05', may05Plagg, 'Trunkshow 5 May 2026. Payment: Factuur'));  
  
  // --- 30 Apr 2026 ---  
  const apr30Plagg = [  
    p('knitwear', 'K40 / traditional / 52', 'K10264 white cotton-silk', '',  
      '6. white thin mother of pearl with wide rim',  
      { 'Knitwear': adamKnitDesign('6. white thin mother of pearl with wide rim', 'double yarn solid', 'polo', 'long sleeves', '8. Rose & Born Main shirt label') },  
      { 'Knitwear': 'Shorten sleeve -2.50' }),  
    p('knitwear', 'K40 / traditional / 52', 'K10256 denim blue mélange cotton-silk', '',  
      'none (without buttons)',  
      { 'Knitwear': adamKnitDesign('none (without buttons)', 'single yarn solid', 'polo without buttons', 'long sleeves', '8. Rose & Born Main shirt label') },  
      { 'Knitwear': 'Shorten sleeve -2.50' })  
  ];  
  store.orders.push(ordA('2026-04-30', apr30Plagg, 'Trunkshow 30 April 2026'));  
  
  // --- 4 Apr 2026 — Jacket (LPN719059) ---  
  const jacketDesignApr = 'Canvassing: none (unconstructed)\nClosure & lapel: 2 buttons with notch lapel\nLapel width: wide\nLower gorge: regular\nLapel buttonhole: handmade\nShoulder type: unconstructed\nChest pocket: rounded welt\nSide pockets: straight flap\nDouble patch: none\nTicket pocket: none\nPocket flap height: standard (5 cm)\nCuff finishing: 4 kissing buttons with open cuff\n1st sleeve buttonhole left: standard\nVents: 2 side vents\nLining style: fully-lined\nInside facing: jet facing\nSleeve lining: same as body lining\nPick stitching (AMF): extensive, 2 mm from edge\nTuxedo (lapel & jets): none\nThroat tab: 51. off-white alcantara\nElbow patches: none\nHidden lining pocket: none\n\nContrast: under collar best match, inside jets same as fabric, inside pick stitching best match with lining, pick stitching (AMF) OFF WHITE, all BH best match\n\nMonogram: A.J., off white, ornamental, lining left\n\nBranding:\nSize label: No\nHangerloop: R&B Hangerloop new\n3.1 Inside: Rose & Born Main label new\n3.2 Inside: No\n5. Inside bottom left: Fabric Supplier Label';  
  
  const adamJacketFitTools = 'Slope shoulder R -0.50\nSlope shoulder L -1.00\nTake in ½ shoulder -0.50\nTake in ½ back -0.50\nTake in ½ chest front -0.50\nRaise vent(s) +1.50\nLower chest pocket -1.00\nTake in ½ waist -1.50\nLower closing button -2.00\nRaise armhole +1.00\nTake in ½ cuff -0.50\nShorten sleeve R -2.00\nShorten sleeve L -1.50\nArms backwards +0.50\nChest dart: standard\nForward shoulders: no\nNeck dart: no';  
  
  const apr04Plagg = [  
    p('jacket', 'Slim 2.0 / unconstructed handmade / 50',  
      'LPN719059', '7770 bright blue',  
      'RB057 dark blue horn with flame',  
      { 'Jacket': jacketDesignApr }, { 'Jacket': adamJacketFitTools })  
  ];  
  store.orders.push(ordA('2026-04-04', apr04Plagg, 'Trunkshow 4 April 2026'));  
  
  // --- 30 Mar 2026 — jeans + knit + jacket DB ---  
  const adamJeansBase = 'Closing button: RB006 regular gun metal\nWaistband: classic (single belt loop)\nBuckle loop: no\nClosure: button fly\nRivets: RB006 regular gun metal\nFront pockets: curved\nBack pockets: standard\nHem finish: standard\nBack patch: none\n\nMeasurements:\nTotal rise 0.00, Front rise 0.00, Back rise 0.50, ½ waist 43.00, ½ thigh 26.80, ½ knee 20.70, ½ Foot 18.00, Inseam R 74.40, Inseam L 74.40\nLaundry shrinkage compensation: No\n\nBranding:\nSize label: No\n2. Inside waistband left front: New Rose & Born Luxury Denim\n4. Inside waistband left back: No';  
  
  const jeansWAS004Design = 'Pocket lining: RB P001 off-white with black Rose & Born logo\nCoin pocket: standard\nWash effect: worn\nContrast topstitching: tobacco\n\n' + adamJeansBase;  
  
  const jacketDesignMar30 = 'Canvassing: none (unconstructed)\nClosure & lapel: double-breasted 6 buttons with peak lapel\nLapel width: wide straight\nLower gorge: regular\nLapel buttonhole: handmade\nShoulder type: unconstructed\nChest pocket: rounded welt\nSide pockets: straight jet\nDouble patch: none\nTicket pocket: none\nPocket flap height: no pocket flap\nCuff finishing: 4 kissing buttons with open cuff\n1st sleeve buttonhole left: standard\nVents: 2 side vents\nLining style: half-lined\nInside facing: jet facing\nSleeve lining: same as body lining\nPick stitching (AMF): extensive, 2 mm from edge\nTuxedo (lapel & jets): none\nThroat tab: none\nElbow patches: none\nHidden lining pocket: none\n\nContrast: under collar best match, inside jets same as lining, inside pick stitching best match with lining, all BH best match\n\nMonogram: A.J., best match with fabric, ornamental, lining left\n\nBranding:\nSize label: No\nHangerloop: R&B Hangerloop new*\n3.1 Inside: Rose & Born Main label new*\n3.2 Inside: NEW Rose & Born Handmade\n5. Inside bottom left: Fabric Supplier Label';  
  
  const mar30Plagg = [  
    p('jeans', 'Slim / 5 pocket the traditional / 32/30',  
      'WAS004 mid blue stretch', '',  
      'RB006 regular gun metal',  
      { 'Jeans': jeansWAS004Design }, {}, 'Payment: Factuur'),  
    p('knitwear', 'K40 / traditional / 52', 'K10083 silver grey cashmere-silk', '', '',  
      { 'Knitwear': adamKnitDesign('', 'double yarn solid', 'half zip', 'long sleeves', '8. Rose & Born Main shirt label', 'line edges', 'K10076 d.blue cashmere-silk', 'standard rib', false) },  
      { 'Knitwear': 'Shorten sleeve -2.50' }, 'Payment: Factuur'),  
    p('jacket', 'Slim 2.0 / unconstructed handmade / 50',  
      'DR85111', '109 Bemberg silver',  
      'RB049 blond faux horn with flame',  
      { 'Jacket': jacketDesignMar30 }, { 'Jacket': adamJacketFitTools })  
  ];  
  store.orders.push(ordA('2026-03-30', mar30Plagg, 'Trunkshow 30 March 2026'));  
  
  // --- 14 Mar 2026 — knit + jeans (samma data som 30 Mar men separat tillfälle) ---  
  const mar14Plagg = [  
    p('knitwear', 'K40 / traditional / 52', 'K10083 silver grey cashmere-silk', '', '',  
      { 'Knitwear': adamKnitDesign('', 'double yarn solid', 'half zip', 'long sleeves', '8. Rose & Born Main shirt label', 'line edges', 'K10076 d.blue cashmere-silk', 'standard rib', false) },  
      { 'Knitwear': 'Shorten sleeve -2.50' }),  
    p('jeans', 'Slim / 5 pocket the traditional / 32/30',  
      'WAS004 mid blue stretch', '',  
      'RB006 regular gun metal',  
      { 'Jeans': jeansWAS004Design }, {}, 'Payment: Factuur')  
  ];  
  store.orders.push(ordA('2026-03-14', mar14Plagg, 'Trunkshow 14 March 2026'));  
  
  // --- 3 Feb / 29 Jan 2026 — 2 jeans + IJ + 3 knit ---  
  const jeansCOL001Design = 'Pocket lining: POC002 off-white\nCoin pocket: extended\nWash effect: plain\nContrast topstitching: best match\n\n' + adamJeansBase;  
  const jeansWAS003Design = 'Pocket lining: POC002 off-white\nCoin pocket: extended\nWash effect: plain\nContrast topstitching: tobacco\n\n' + adamJeansBase;  
  
  const ijIvoryDesign = 'Closure: 4 buttons\nLapel buttonhole: standard\nChest pocket: 2x safari without buttons and buttonholes\nSide pockets: safari without buttons and buttonholes\nCuff finishing: cuff with pleats with 1 button\nVent: 2 side vents (overlapping)\nWaist detailing: internal elastic cord\nLining style: shoulder-lined\nInside facing: jet\nSleeve lining: same as body\nPick stitching (AMF): 7mm top stitching\n\nContrast: edge stitching best match, all BH best match\n\nMonogram: A.J., mid brown, ornamental, inside facing left\n\nBranding:\nSize label: No\n1.2 Inside facing left: Rose & Born Main label new\n3. Inside pocket right: Fabric Supplier Label';  
  
  const ijIvoryFitTools = 'Stooped posture +1.00\nLet out ½ shoulder +0.50\nLet out ½ back +0.50\nLet out ½ chest front +0.50\nLet out ½ centre front +0.50\nShorten length -2.00\nRaise armhole +1.00\nShorten sleeve R -1.00\nShorten sleeve L -1.00\nLower internal elastic cord -1.50';  
  
  const feb03Plagg = [  
    p('jeans', 'Slim / 5 pocket the traditional / 32/30',  
      'COL001 off white twill stretch', '',  
      'RB006 regular gun metal',  
      { 'Jeans': jeansCOL001Design }, {}, 'Payment: Factuur'),  
    p('jeans', 'Slim / 5 pocket the traditional / 32/30',  
      'WAS003 dark blue stretch', '',  
      'RB006 regular gun metal',  
      { 'Jeans': jeansWAS003Design }, {}, 'Payment: Factuur'),  
    p('informal_jacket', 'SJ40 / unconstructed / 50',  
      '9143 ivory-cream wool-alpaca blend herringbone', '8202 light beige',  
      '6. chestnut brown horn with waves',  
      { 'Informal Jacket': ijIvoryDesign }, { 'Informal Jacket': ijIvoryFitTools }),  
    p('knitwear', 'K40 / traditional / 50', 'K10074 l.blue cashmere-silk', '',  
      'none (without buttons)',  
      { 'Knitwear': adamKnitDesign('none (without buttons)', 'double yarn solid', 'half zip', 'long sleeves', '8. Rose & Born Main shirt label', 'line edges', 'K10076 d.blue cashmere-silk', 'standard rib') },  
      {}),  
    p('knitwear', 'K40 / traditional / 50', 'K10040 l.heathered grey cashmere', '',  
      'none (without buttons)',  
      { 'Knitwear': adamKnitDesign('none (without buttons)', 'half english rib', 'polo without buttons', 'long sleeves', '8. Rose & Born Main shirt label', 'no contrast', 'no contrast') + '\nArmhole style: raglan (override)' },  
      {}),  
    p('knitwear', 'K40 / traditional / 50', 'K10031 l.blue cashmere', '',  
      'none (without buttons)',  
      { 'Knitwear': adamKnitDesign('none (without buttons)', 'half english rib', 'polo without buttons', 'long sleeves', '8. Rose & Born Main shirt label', 'no contrast', 'no contrast') + '\nArmhole style: raglan (override)' },  
      {}, 'Payment: Factuur')  
  ];  
  store.orders.push(ordA('2026-02-03', feb03Plagg, 'Trunkshow 3 February 2026'));  
  
  // ============================================================  
  // RICH R  
  // ============================================================  
  const rich = {  
    id: uid(),  
    name: 'Rich R',  
    email: '',  
    phone: '+1 815 922 9015',  
    notes: 'Trunkshow customer.',  
    createdAt: '2026-04-29'  
  };  
  store.customers.push(rich);  
  const rid = rich.id;  
  
  function ordR(date, plaggArr, notes) {  
    return { id: uid(), customerId: rid, status: 'confirmed', plagg: plaggArr,  
      deliveryDate: '', occasion: 'Work', notes: notes || '',  
      createdAt: date, updatedAt: date };  
  }  
  
  const richJacketFitTools = 'Collar pleat -0.50\nSlope shoulder R -0.50\nLet out ½ shoulder +0.50\nLet out ½ back +1.00\nLet out ½ waist +0.50\nLower closing button -1.00\nShorten sleeve R -2.00\nShorten sleeve L -2.00\nArms backwards +0.50\nLet out ½ cuff only (NEW) +1.00\nChest dart: standard\nForward shoulders: no\nNeck dart: no';  
  
  const richTrousersFitTools = 'Raise total rise +1.50\nRaise front rise +2.00\nLet out crotch +1.00\nShorten leg R -7.00\nShorten leg L -7.00\nProminent seat: without\nFlat seat: without';  
  
  const richShirtFitTools = 'Let out ½ chest front +1.50\nTake in ½ hip -1.50\nLengthen front +1.00\nLengthen length +1.00\nLet out forearm +1.00\nShorten sleeve R -2.00\nShorten sleeve L -2.00\nLet out cuff R +1.00\nLet out cuff L +1.00';  
  
  // --- 25 May 2026: Trousers (tuxedo-style, DR028 black panama) ---  
  const richTuxTrousersDesign = 'Waistband: plain\nWaistband detailing: high waistband double button (metal color buckle)\nTuxedo waistband: black satin\nFront style: single pleat\nClosure: zip fly\nSide pockets: slanted\nCargo pockets: none\nBack pocket(s): welt without button\nHem finish: plain with slanted bottom\nPocket lining: TPC001 black\nPick stitching (AMF): none\nTuxedo side stripe: black satin top stitched\nCoin pocket: no\nPleat direction: outwards\nPleat depth: standard\nPintuck: no\nSuspender buttons: yes\nBuckle loop: no\nCrotch piece: standard\nLeg lining: half-lined front\n\nContrast: pick stitching none, BH best match\n\nBranding:\nSize label: No\n1.1 Pocket lining right back: R&B Hangerloop new';  
  
  const may25R = [  
    p('trousers', 'T40 / traditional with pleated waistband / 54',  
      'DR028 black S130 wool panama', '',  
      '31. black galalith',  
      { 'Trousers': richTuxTrousersDesign }, { 'Trousers': richTrousersFitTools })  
  ];  
  store.orders.push(ordR('2026-05-25', may25R, 'Trunkshow 25 May 2026. Tuxedo trousers.'));  
  
  // --- 22 May 2026: Jacket (DR028, tuxedo-style 1-button shawl) ---  
  const richTuxJacketDesign = 'Canvassing: light\nClosure & lapel: 1 button with shawl lapel\nLower gorge: regular\nLapel width: wide\nLapel buttonhole: no buttonhole\nShoulder type: unconstructed\nChest pocket: rounded welt\nSide pockets: straight jet\nDouble patch: none\nTicket pocket: none\nPocket flap height: no pocket flap\nCuff finishing: 4 kissing buttons with open cuff\n1st sleeve buttonhole left: standard\nVents: 2 side vents\nLining style: fully-lined\nInside facing: jet facing\nSleeve lining: same as body lining\nPick stitching (AMF): extensive, 2 mm from edge\nTuxedo (lapel & jets): black satin\nThroat tab: none\nElbow patches: none\nHidden lining pocket: none\n\nContrast: under collar best match, inside jets 2300 black, inside pick stitching best match with lining, pick stitching (AMF) best match, lapel BH no buttonhole, all other BH best match\n\nMonogram: R.R., silver, ornamental, lining left\n\nBranding:\nSize label: No\nHangerloop: R&B Hangerloop new\n3.1 Inside: Rose & Born Main label new\n3.2 Inside: No\n5. Inside bottom left: No';  
  
  const may22R = [  
    p('jacket', 'Slim 2.0 / traditional full canvas / 54',  
      'DR028 black S130 wool panama', '2300 black',  
      'T1. black satin',  
      { 'Jacket': richTuxJacketDesign }, { 'Jacket': richJacketFitTools })  
  ];  
  store.orders.push(ordR('2026-05-22', may22R, 'Trunkshow 22 May 2026. Tuxedo jacket (1-button shawl, black satin facing).'));  
  
  // --- 30 Apr 2026: trousers + 2 shirts + jacket ---  
  const richTrousers30Design = 'Waistband: plain\nWaistband detailing: high waistband double button (brass color buckle)\nTuxedo waistband: same as fabric\nFront style: single pleat\nClosure: zip fly\nSide pockets: slanted\nCargo pockets: none\nBack pocket(s): welt without button\nHem finish: turn up (5 cm)\nPocket lining: TPC009 sand mélange\nPick stitching (AMF): 2 mm from edge\nTuxedo side stripe: none\nCoin pocket: yes\nPleat direction: outwards\nPleat depth: standard\nPintuck: no\nSuspender buttons: no\nBuckle loop: no\nCrotch piece: standard\nLeg lining: half-lined front\n\nContrast: pick stitching best match, BH best match\n\nBranding:\nSize label: No\n1.1 Pocket lining right back: R&B Hangerloop new';  
  
  const richShirt1Design = 'Collar style: one-piece cutaway (4 cm)\nCollar stays: none\nSkinning: soft\nFront closure: plain\nSleeve style: long sleeves\nBack yoke: 2 pieces\nCuff style: single, rounded 1 button (7 cm)\nSleeve vent: middle button\nButton attachment: lily (by hand)\nBack darts: standard\nEdge stitching: 3 mm from edge\nChest pockets: none\nBack style: plain\nHem shape: curved\nElbow patches: none\nPocket square: none\nPre-washed: no\nPackaging: standard\nYarn thickness: standard\n\nContrast: all best match / no contrast / no piping\n\nBranding:\nSize label: No\n1.1 Inside back yoke: New R&B Shirt label\n1.2 Inside back yoke: No\n4. Button placket: No';  
  
  // Shirt 2: TUXEDO shirt — double cuff + black studs  
  const richShirt2Design = 'Collar style: semi-cutaway (4 cm)\nCollar stays: removable\nSkinning: standard\nFront closure: plain (with black studs)\nSleeve style: long sleeves\nBack yoke: 2 pieces\nCuff style: double, square with cufflink openings (7 cm)\nSleeve vent: hidden button\nBack darts: standard\nButton attachment: lily (by hand)\nEdge stitching: 1 mm from edge\nChest pockets: none\nBack style: plain\nHem shape: curved\nElbow patches: none\nPocket square: same as fabric\nPre-washed: no\nPackaging: standard\nYarn thickness: standard\n\nContrast: all best match / no contrast / no piping\n\nBranding:\nSize label: No\n1.1 Inside back yoke: New R&B Shirt label\n1.2 Inside back yoke: No\n4. Button placket: Fabric Supplier Label';  
  
  const richJacket30Design = 'Canvassing: light\nClosure & lapel: 1 button with peak lapel\nLower gorge: regular\nLapel width: wide\nLapel buttonhole: handmade\nShoulder type: unconstructed\nChest pocket: rounded welt\nSide pockets: straight jet\nDouble patch: none\nTicket pocket: none\nPocket flap height: no pocket flap\nCuff finishing: 4 kissing buttons with open cuff\n1st sleeve buttonhole left: standard\nVents: 2 side vents\nLining style: fully-lined\nInside facing: jet facing\nSleeve lining: same as body lining\nPick stitching (AMF): standard, 2 mm from edge\nTuxedo (lapel & jets): none\nThroat tab: none\nElbow patches: none\nHidden lining pocket: none\n\nContrast: under collar best match, inside jets same as lining, inside pick stitching best match with lining, pick stitching (AMF) best match, all BH best match\n\nMonogram: R.R., white, ornamental, lining left\n\nBranding:\nSize label: No\nHangerloop: R&B Hangerloop new\n3.1 Inside: Rose & Born Main label new\n3.2 Inside: No\n5. Inside bottom left: No';  
  
  // Note: Jacket 30 Apr har egen fittools-set (utan "Let out ½ waist", utan "Let out ½ cuff only")  
  const richJacket30FitTools = 'Collar pleat -0.50\nSlope shoulder R -0.50\nLet out ½ shoulder +0.50\nLet out ½ back +1.00\nLower closing button -1.00\nShorten sleeve R -2.00\nShorten sleeve L -2.00\nArms backwards +0.50\nChest dart: standard\nForward shoulders: no\nNeck dart: no';  
  
  const apr30R = [  
    p('trousers', 'T40 / traditional with pleated waistband / 54',  
      'C203/1', '',  
      'RB055 (102) blond and d.brown tortoise horn',  
      { 'Trousers': richTrousers30Design }, { 'Trousers': richTrousersFitTools }, 'Payment: Factuur'),  
    p('shirt', 'Slim 2.0 / traditional / 42',  
      'SH00253 white linen', '',  
      'RB031 white thick mother of pearl look with round edge',  
      { 'Shirt': richShirt1Design }, { 'Shirt': richShirtFitTools }),  
    p('shirt', 'Slim 2.0 / traditional / 42',  
      'SH00436 white 100/2 natural stretch cotton dobby', '',  
      'RB031 white thick mother of pearl look with round edge',  
      { 'Shirt': richShirt2Design }, { 'Shirt': richShirtFitTools }, 'Tuxedo shirt (double cuff + black studs)'),  
    p('jacket', 'Slim 2.0 / traditional full canvas / 54',  
      'EVE012 off-white bamboo', '1098 Bemberg white',  
      'fabric-covered button',  
      { 'Jacket': richJacket30Design }, { 'Jacket': richJacket30FitTools }, 'Payment: Factuur')  
  ];  
  store.orders.push(ordR('2026-04-30', apr30R, 'Trunkshow 30 April 2026'));  
  
  // --- 29 Apr 2026: 3-piece suit (DR028, tuxedo-rigged jacket + trousers + waistcoat) ---  
  const richSuitJacketDesign = 'Canvassing: light\nClosure & lapel: 1 button with shawl lapel\nLower gorge: regular\nLapel width: wide\nLapel buttonhole: handmade\nShoulder type: unconstructed\nChest pocket: rounded welt\nSide pockets: straight jet\nDouble patch: none\nTicket pocket: none\nPocket flap height: no pocket flap\nCuff finishing: 4 kissing buttons with open cuff\n1st sleeve buttonhole left: standard\nVents: 2 side vents\nLining style: fully-lined\nInside facing: jet facing\nSleeve lining: same as body lining\nPick stitching (AMF): extensive, 2 mm from edge\nTuxedo (lapel & jets): none\nThroat tab: none\nElbow patches: none\nHidden lining pocket: none\n\nContrast: under collar best match, inside jets same as lining, inside pick stitching best match with lining, pick stitching (AMF) best match, all BH best match\n\nMonogram: R.R., silver, ornamental, lining left\n\nBranding:\nSize label: No\nHangerloop: R&B Hangerloop new\n3.1 Inside: Rose & Born Main label new\n3.2 Inside: NEW Rose & Born Handmade\n5. Inside bottom left: Fabric Supplier Label';  
  
  const richSuitTrousersDesign = 'Waistband: plain\nWaistband detailing: high waistband (metal color buckle)\nTuxedo waistband: black satin\nFront style: single pleat\nClosure: zip fly\nSide pockets: slanted\nCargo pockets: none\nBack pocket(s): welt without button\nHem finish: plain with slanted bottom\nPocket lining: TPC001 black\nPick stitching (AMF): none\nTuxedo side stripe: none\nCoin pocket: yes\nPleat direction: outwards\nPleat depth: standard\nPintuck: no\nSuspender buttons: no\nBuckle loop: no\nCrotch piece: standard\nLeg lining: half-lined front\n\nContrast: pick stitching none, BH best match\n\nBranding:\nSize label: No\n1.1 Pocket lining right back: R&B Hangerloop new';  
  
  const richWaistcoatDesign = 'Button: T1. black satin\nClosure: 4 buttons with horseshoe front\nSide pockets: jet\nBack style: lining with buckle (metal colour)\nPick stitching (AMF): 2 mm from edge\nTuxedo (jets): black satin\nChest pockets: none\n\nContrast: pick stitching best match, BH best match\n\nBranding:\nSize label: No\n1. Inside lining right: Rose & Born Main label new';  
  
  const richWaistcoatFitTools = 'Slope shoulder R -0.50\nShorten length -1.00';  
  
  // Bygg suit-rad och slå på vest manuellt  
  const suitRad = p('suit', 'Jacket: Slim 2.0 / traditional full canvas / 54 · Trousers: T40 / traditional with pleated waistband / 54 · Waistcoat: Slim 2.0 / traditional / 54',  
    'DR028 black S130 wool panama', '2300 black',  
    'T1. black satin',  
    { 'Jacket': richSuitJacketDesign, 'Trousers': richSuitTrousersDesign },  
    { 'Jacket': richJacketFitTools, 'Trousers': richTrousersFitTools });  
  suitRad.includeVest = true;  
  suitRad.vestDesign = richWaistcoatDesign;  
  suitRad.vestFitTools = richWaistcoatFitTools;  
  
  const apr29R = [suitRad];  
  store.orders.push(ordR('2026-04-29', apr29R, 'Trunkshow 29 April 2026. 3-piece tuxedo (DR028 black panama).'));  
  
  // ============================================================  
  // ALEX ROBBINS  
  // ============================================================  
  const alex = {  
    id: uid(),  
    name: 'Alex Robbins',  
    email: 'alexrobbins34@gmail.com',  
    phone: '+1 781 307 7360',  
    notes: 'Trunkshow customer (Edwin Nenzell, original sales associate 2023).',  
    createdAt: '2023-03-22'  
  };  
  store.customers.push(alex);  
  const alxid = alex.id;  
  
  // --- 22 Mar 2023: 2-piece suit (E0011 black wool, tuxedo-rigged trousers) ---  
  const alexJacketDesign = 'Design fields not specified in source (GoCreate defaults).\n\nMonogram: A.M.R., mid grey, ornamental, lining left (1 line)\n\nBranding:\nSize label: No\nHangerloop: X Old Hangerloop Rose & Born\n3.1 Inside: X Old Rose & Born Main label\n3.2 Inside: NEW Rose & Born Made to Measure\n5. Inside bottom left: No';  
  
  const alexJacketFitTools = 'Collar pleat -0.50\nSlope shoulder R -0.50\nSlope shoulder L -0.50\nLet out ½ chest front +1.00\nRaise vent(s) +1.00\nTake in ½ waist -1.50\nLower closing button -0.50\nShorten length -1.50\nLet out upper arm & armhole +0.50\nLet out ½ cuff +0.50\nShorten sleeve R -2.50\nShorten sleeve L -2.50';  
  
  const alexTrousersDesign = 'Waistband: plain\nWaistband detailing: extended\nFront style: flat front\nClosure: zip fly with double hook & eye\nSide pockets: jet\nCargo pockets: none\nBack pocket(s): jet with button\nHem finish: plain\nPocket lining: TPC001 black\nPick stitching (AMF): none\nTuxedo side stripe: black satin top stitched\nCoin pocket: yes\nPleat direction: no pleats\nPleat depth: no pleats\nSuspender buttons: no\nBuckle loop: no\nCrotch piece: standard\nLeg lining: half-lined front\n\nContrast: pick stitching none, BH best match\n\nBranding:\nSize label: No\nInside waistband left: X OLD Rose & Born trouser label';  
  
  const alexTrousersFitTools = 'Lower front rise -1.00\nTake in ½ waist -1.50\nTake in ½ seat -0.50\nLet out ½ thigh +1.00\nLet out ½ knee +0.50\nTake in ½ hem -1.50\nShorten leg R -7.00\nShorten leg L -7.00\nProminent seat: without\nFlat seat: without';  
  
  const alexSuitRad = {  
    id: uid(),  
    type: 'suit',  
    size: 'Jacket: Slim 2.0 / unconstructed / 52 · Trousers: T40 / traditional with pleated waistband / 52',  
    fabric: 'E0011 black S100 wool plain weave',  
    lining: '2300 black',  
    button: '',  
    design: { 'Jacket': alexJacketDesign, 'Trousers': alexTrousersDesign },  
    fittools: { 'Jacket': alexJacketFitTools, 'Trousers': alexTrousersFitTools },  
    remark: '',  
    includeVest: false, vestDesign: '', vestFitTools: ''  
  };  
  
  store.orders.push({  
    id: uid(), customerId: alxid, status: 'confirmed',  
    plagg: [alexSuitRad],  
    deliveryDate: '', occasion: 'Work',  
    notes: 'Trunkshow 22 March 2023 (Edwin Nenzell). 2-piece suit with tuxedo-style side stripe. Payment: Factuur.',  
    createdAt: '2023-03-22', updatedAt: '2023-03-22'  
  });  
}  
  
// (loadStore flyttat till efter PLAGG_TYPES-deklarationen)  
  
// ============================================================  
// PLAGG-TYPER — definitions för hur många design/ändringar-rutor per plagg  
// ============================================================  
const PLAGG_TYPES = [  
  { key: 'suit',            label: 'Suit',             parts: ['Jacket', 'Trousers'], allowVest: true },  
  { key: 'tuxedo',          label: 'Tuxedo',           parts: ['Jacket', 'Trousers'], allowVest: true },  
  { key: 'informal_suit',   label: 'Informal Suit',    parts: ['Jacket', 'Trousers'], allowVest: false },  
  { key: 'jacket',          label: 'Jacket',           parts: ['Jacket'],             allowVest: false },  
  { key: 'informal_jacket', label: 'Informal Jacket',  parts: ['Informal Jacket'],    allowVest: false },  
  { key: 'trousers',        label: 'Trousers',         parts: ['Trousers'],           allowVest: false },  
  { key: 'vest',            label: 'Vest',             parts: ['Vest'],               allowVest: false },  
  { key: 'shirt',           label: 'Shirt',            parts: ['Shirt'],              allowVest: false },  
  { key: 'coat',            label: 'Coat',             parts: ['Coat'],               allowVest: false },  
  { key: 'jeans',           label: 'Jeans / Chinos',   parts: ['Jeans'],              allowVest: false },  
  { key: 'knitwear',        label: 'Knitwear',         parts: ['Knitwear'],           allowVest: false },  
  { key: 'shoes',           label: 'Shoes',            parts: ['Shoes'],              allowVest: false },  
  { key: 'bermuda',         label: 'Bermuda Shorts',   parts: ['Bermuda'],            allowVest: false }  
];  
  
function getPlaggDef(key) { return PLAGG_TYPES.find(p => p.key === key); }  
  
// loadStore() flyttat till initApp() som triggas av login  
  
// ============================================================  
// VIEW ROUTING  
// ============================================================  
let currentView = 'customers';  
let currentCustomerId = null;  
let currentOrderId = null;  
  
function setView(view, opts) {  
  opts = opts || {};  
  currentView = view;  
  if (opts.customerId !== undefined) currentCustomerId = opts.customerId;  
  if (opts.orderId !== undefined) currentOrderId = opts.orderId;  
  document.querySelectorAll('.nav button').forEach(b => b.classList.toggle('active', b.dataset.view === view));  
  render();  
}  
document.querySelectorAll('.nav button').forEach(b => {  
  b.addEventListener('click', () => {  
    currentCustomerId = null; currentOrderId = null;  
    setView(b.dataset.view);  
  });  
});  
  
// ============================================================  
// DOM HELPERS  
// ============================================================  
function el(tag, attrs, children) {  
  attrs = attrs || {}; children = children || [];  
  const e = document.createElement(tag);  
  for (const k in attrs) {  
    if (k === 'class') e.className = attrs[k];  
    else if (k === 'html') e.innerHTML = attrs[k];  
    else if (k.startsWith('on')) e.addEventListener(k.substring(2).toLowerCase(), attrs[k]);  
    else e.setAttribute(k, attrs[k]);  
  }  
  (Array.isArray(children) ? children : [children]).forEach(c => {  
    if (c == null) return;  
    if (typeof c === 'string' || typeof c === 'number') e.appendChild(document.createTextNode(String(c)));  
    else e.appendChild(c);  
  });  
  return e;  
}  
function field(label, inputEl, fullWidth) {  
  return el('div', { class: 'field' + (fullWidth ? ' full' : '') }, [el('label', {}, label), inputEl]);  
}  
function textInput(value, onInput, placeholder) {  
  return el('input', { type: 'text', value: value || '', placeholder: placeholder || '', oninput: e => onInput(e.target.value) });  
}  
function textareaInput(value, onInput, placeholder, minHeight) {  
  const t = el('textarea', { placeholder: placeholder || '', oninput: e => onInput(e.target.value) }, value || '');  
  if (minHeight) t.style.minHeight = minHeight;  
  return t;  
}  
function select(value, options, onChange) {  
  const sel = el('select', { onchange: e => onChange(e.target.value) });  
  sel.appendChild(el('option', { value: '' }, '— Välj —'));  
  options.forEach(opt => {  
    const v = typeof opt === 'string' ? opt : opt.value;  
    const t = typeof opt === 'string' ? opt : opt.label;  
    const o = el('option', { value: v }, t);  
    if (v === value) o.selected = true;  
    sel.appendChild(o);  
  });  
  return sel;  
}  
function toast(msg) {  
  const t = document.getElementById('toast');  
  t.textContent = msg; t.classList.add('show');  
  setTimeout(() => t.classList.remove('show'), 1800);  
}  
function modal(title, body, actions) {  
  const overlay = document.getElementById('modal-overlay');  
  const m = document.getElementById('modal');  
  m.innerHTML = '';  
  m.appendChild(el('h3', {}, title));  
  m.appendChild(body);  
  if (actions) m.appendChild(actions);  
  overlay.classList.add('show');  
  overlay.onclick = e => { if (e.target === overlay) overlay.classList.remove('show'); };  
}  
function closeModal() { document.getElementById('modal-overlay').classList.remove('show'); }  
  
// ============================================================  
// CUSTOMERS  
// ============================================================  
function renderCustomers() {  
  const main = document.getElementById('main');  
  main.innerHTML = '';  
  if (currentCustomerId) { renderCustomerDetail(currentCustomerId); return; }  
  main.appendChild(el('h1', { class: 'page-title' }, 'Customers'));  
  main.appendChild(el('p', { class: 'page-sub' }, store.customers.length + ' customer' + (store.customers.length === 1 ? '' : 's')));  
  main.appendChild(el('div', { class: 'btn-row' }, [  
    el('button', { class: 'btn primary', onclick: () => openCustomerForm() }, '+ New Customer')  
  ]));  
  if (store.customers.length === 0) {  
    main.appendChild(el('div', { class: 'empty' }, [  
      el('div', { class: 'e-icon' }, '·'),  
      el('div', { class: 'e-title' }, 'No customers yet'),  
      el('div', { class: 'e-msg' }, 'Add a customer to get started.'),  
      el('button', { class: 'btn primary', onclick: () => openCustomerForm() }, '+ First customer')  
    ]));  
    return;  
  }  
  
  // Sökruta — sparas i window så den överlever rerender  
  if (window._customerSearch == null) window._customerSearch = '';  
  const searchBox = el('div', { style: 'margin-bottom: 18px; position: relative;' });  
  const searchInput = el('input', {  
    type: 'search', value: window._customerSearch, placeholder: 'Search customer (name, email, phone)...',  
    autocomplete: 'off',  
    style: 'width:100%; padding:14px 16px 14px 44px; font-size:15px; border:1px solid var(--line); border-radius:0; background:var(--bg); font-family:-apple-system,sans-serif;',  
    oninput: e => { window._customerSearch = e.target.value; renderCustomerResults(); }  
  });  
  // Förstoringsglas-ikon  
  searchBox.appendChild(el('div', { style: 'position:absolute; left:14px; top:50%; transform:translateY(-50%); color:var(--muted-soft); font-size:18px; pointer-events:none;', html: '⌕' }));  
  searchBox.appendChild(searchInput);  
  if (window._customerSearch) {  
    searchBox.appendChild(el('button', {  
      style: 'position:absolute; right:10px; top:50%; transform:translateY(-50%); background:transparent; border:0; color:var(--muted); cursor:pointer; padding:6px 10px; font-size:18px;',  
      onclick: () => { window._customerSearch = ''; renderCustomers(); }  
    }, '×'));  
  }  
  main.appendChild(searchBox);  
  
  const resultsContainer = el('div', { id: 'customer-results' });  
  main.appendChild(resultsContainer);  
  renderCustomerResults();  
  
  // Auto-fokus om sök är aktivt  
  if (window._customerSearch) setTimeout(() => searchInput.focus(), 0);  
}  
  
function customerMatchScore(c, q) {  
  if (!q) return 0;  
  const ql = q.toLowerCase().trim();  
  const name = (c.name || '').toLowerCase();  
  const email = (c.email || '').toLowerCase();  
  const phone = (c.phone || '').toLowerCase().replace(/[\s\-+()]/g, '');  
  const qPhone = ql.replace(/[\s\-+()]/g, '');  
  // Högre score = bättre match  
  if (name.startsWith(ql)) return 100;  
  if (name.split(/\s+/).some(part => part.startsWith(ql))) return 90;  
  if (name.includes(ql)) return 70;  
  if (email.startsWith(ql)) return 60;  
  if (email.includes(ql)) return 50;  
  if (qPhone && phone.includes(qPhone)) return 40;  
  return 0;  
}  
  
function renderCustomerResults() {  
  const container = document.getElementById('customer-results');  
  if (!container) return;  
  container.innerHTML = '';  
  const q = window._customerSearch || '';  
  
  let list;  
  if (q.trim()) {  
    list = store.customers  
      .map(c => ({ c, score: customerMatchScore(c, q) }))  
      .filter(x => x.score > 0)  
      .sort((a, b) => b.score - a.score)  
      .map(x => x.c);  
  } else {  
    list = [...store.customers].sort((a, b) => {  
      const lastA = store.orders.filter(o => o.customerId === a.id).sort((x,y) => (y.updatedAt||'').localeCompare(x.updatedAt||''))[0];  
      const lastB = store.orders.filter(o => o.customerId === b.id).sort((x,y) => (y.updatedAt||'').localeCompare(x.updatedAt||''))[0];  
      if (lastA && lastB) return (lastB.updatedAt||'').localeCompare(lastA.updatedAt||'');  
      if (lastA) return -1; if (lastB) return 1;  
      return a.name.localeCompare(b.name);  
    });  
  }  
  
  if (list.length === 0) {  
    container.appendChild(el('div', { class: 'empty' }, [  
      el('div', { class: 'e-msg' }, q ? 'No customer matches "' + q + '"' : 'No customers')  
    ]));  
    return;  
  }  
  
  if (q.trim()) {  
    container.appendChild(el('p', { style: 'font-size:11px; color:var(--muted); margin-bottom:12px; letter-spacing:0.1em; text-transform:uppercase;' },  
      list.length + ' match' + (list.length === 1 ? '' : 'es')));  
  }  
  
  // Visa max 50 åt gången för prestanda  
  const visible = list.slice(0, 50);  
  visible.forEach(c => {  
    const orderCount = store.orders.filter(o => o.customerId === c.id).length;  
    const lastOrder = store.orders.filter(o => o.customerId === c.id).sort((a,b) => (b.updatedAt||'').localeCompare(a.updatedAt||''))[0];  
    container.appendChild(el('div', { class: 'card', onclick: () => setView('customers', { customerId: c.id }) }, [  
      el('div', { class: 'card-title' }, c.name),  
      el('div', { class: 'card-meta' }, [  
        el('span', {}, orderCount + ' orders'),  
        c.email ? el('span', {}, c.email) : null,  
        c.phone ? el('span', {}, c.phone) : null,  
        lastOrder ? el('span', {}, 'Last: ' + fmtDate(lastOrder.updatedAt)) : null  
      ].filter(Boolean))  
    ]));  
  });  
  if (list.length > 50) {  
    container.appendChild(el('p', { style: 'font-size:12px; color:var(--muted); padding:14px; text-align:center;' },  
      'Showing 50 of ' + list.length + '. Search more specifically to find others.'));  
  }  
}  
  
function renderCustomerDetail(customerId) {  
  const main = document.getElementById('main');  
  const c = store.customers.find(x => x.id === customerId);  
  if (!c) { setView('customers'); return; }  
  main.innerHTML = '';  
  main.appendChild(el('div', { class: 'btn-row' }, [  
    el('button', { class: 'btn ghost', onclick: () => { currentCustomerId = null; render(); } }, '← Customers')  
  ]));  
  main.appendChild(el('h1', { class: 'page-title' }, c.name));  
  const subParts = [];  
  if (c.email) subParts.push(c.email);  
  if (c.phone) subParts.push(c.phone);  
  main.appendChild(el('p', { class: 'page-sub' }, subParts.join(' · ') || 'No contact info'));  
  main.appendChild(el('div', { class: 'btn-row' }, [  
    el('button', { class: 'btn primary', onclick: () => { currentOrderId = null; currentCustomerId = c.id; setView('new-order'); } }, '+ New Order'),  
    el('button', { class: 'btn', onclick: () => openCustomerForm(c) }, 'Edit Profile'),  
    el('button', { class: 'btn danger small', onclick: () => confirmDeleteCustomer(c) }, 'Delete')  
  ]));  
  if (c.notes) {  
    main.appendChild(el('h2', { class: 'section-title' }, 'Notes'));  
    main.appendChild(el('div', { class: 'order-summary', html: c.notes.replace(/\n/g, '<br>') }));  
  }  
  main.appendChild(el('h2', { class: 'section-title' }, 'Order history'));  
  const customerOrders = store.orders.filter(o => o.customerId === c.id).sort((a,b) => (b.updatedAt||'').localeCompare(a.updatedAt||''));  
  if (customerOrders.length === 0) {  
    main.appendChild(el('div', { class: 'empty' }, [el('div', { class: 'e-msg' }, 'No orders yet')]));  
  } else {  
    customerOrders.forEach(o => {  
      const plaggLabels = (o.plagg || []).map(p => (getPlaggDef(p.type) || {}).label || p.type).join(', ');  
      main.appendChild(el('div', { class: 'card', onclick: () => setView('new-order', { orderId: o.id }) }, [  
        el('div', { class: 'card-title' }, plaggLabels || '(no garments)'),  
        el('div', { class: 'card-meta' }, [  
          el('span', {}, fmtDate(o.createdAt)),  
          el('span', { class: 'pill ' + (o.status === 'draft' ? 'amber' : 'green') }, o.status === 'draft' ? 'Draft' : 'Ready')  
        ])  
      ]));  
    });  
  }  
}  
  
function openCustomerForm(existing) {  
  const c = existing ? JSON.parse(JSON.stringify(existing)) : {  
    id: uid(), name: '', email: '', phone: '', notes: '', createdAt: todayISO()  
  };  
  const body = el('div');  
  const grid = el('div', { class: 'form-grid' });  
  grid.appendChild(field('Name', textInput(c.name, v => c.name = v, 'Hugo F'), true));  
  grid.appendChild(field('Email', textInput(c.email, v => c.email = v, 'hugo@example.com')));  
  grid.appendChild(field('Phone', textInput(c.phone, v => c.phone = v, '+46 ...')));  
  grid.appendChild(field('Notes', textareaInput(c.notes, v => c.notes = v, 'Free text about the customer...'), true));  
  body.appendChild(grid);  
  const actions = el('div', { class: 'modal-actions' }, [  
    el('button', { class: 'btn ghost', onclick: closeModal }, 'Cancel'),  
    el('button', { class: 'btn primary', onclick: () => {  
      if (!c.name.trim()) { toast('Name required'); return; }  
      const idx = store.customers.findIndex(x => x.id === c.id);  
      if (idx >= 0) store.customers[idx] = c; else store.customers.push(c);  
      saveStore();  
      toast(existing ? 'Profile updated' : 'Customer added');  
      closeModal();  
      currentCustomerId = c.id;  
      render();  
    }}, 'Save')  
  ]);  
  modal(existing ? 'Edit Customer' : 'New Customer', body, actions);  
}  
  
function confirmDeleteCustomer(c) {  
  const orderCount = store.orders.filter(o => o.customerId === c.id).length;  
  const msg = el('div', {}, [  
    el('p', {}, 'Delete ' + c.name + '?'),  
    orderCount > 0 ? el('p', { style:'color:var(--red); margin-top:8px;' }, 'This will also delete ' + orderCount + ' orders.') : null  
  ].filter(Boolean));  
  const actions = el('div', { class: 'modal-actions' }, [  
    el('button', { class: 'btn ghost', onclick: closeModal }, 'Cancel'),  
    el('button', { class: 'btn danger', onclick: () => {  
      store.customers = store.customers.filter(x => x.id !== c.id);  
      store.orders = store.orders.filter(o => o.customerId !== c.id);  
      saveStore(); closeModal();  
      currentCustomerId = null;  
      setView('customers');  
      toast('Deleted');  
    }}, 'Delete')  
  ]);  
  modal('Confirm Delete', msg, actions);  
}  
  
// ============================================================  
// ORDER — kund + storlek + N plagg-rader  
// ============================================================  
function newPlaggRad(type) {  
  const def = getPlaggDef(type);  
  if (!def) return null;  
  const rad = {  
    id: uid(),  
    type: type,  
    size: '',  
    fabric: '', lining: '', button: '',  
    design: {},  
    fittools: {},  
    remark: '',  
    includeVest: false,  
    vestDesign: '',  
    vestFitTools: ''  
  };  
  def.parts.forEach(p => { rad.design[p] = ''; rad.fittools[p] = ''; });  
  return rad;  
}  
  
function renderNewOrder() {  
  const main = document.getElementById('main');  
  main.innerHTML = '';  
  
  let order;  
  if (currentOrderId) {  
    order = store.orders.find(o => o.id === currentOrderId);  
    if (!order) { setView('orders'); return; }  
    // Migrera gamla ordrar utan plagg-array  
    if (!order.plagg) order.plagg = [];  
  } else {  
    order = {  
      id: uid(),  
      customerId: currentCustomerId || (store.customers[0] && store.customers[0].id) || '',  
      status: 'draft',  
      plagg: [],  
      deliveryDate: '', occasion: 'Work', notes: '',  
      createdAt: todayISO(), updatedAt: todayISO()  
    };  
  }  
  
  const isExisting = !!store.orders.find(o => o.id === order.id);  
  function save(silent) {  
    order.updatedAt = todayISO();  
    const idx = store.orders.findIndex(o => o.id === order.id);  
    if (idx >= 0) store.orders[idx] = order; else store.orders.push(order);  
    currentOrderId = order.id;  
    saveStore();  
    if (!silent) toast('Saved');  
  }  
  function rerender() {  
    const sy = window.scrollY;  
    save(true);  
    renderNewOrder();  
    window.scrollTo(0, sy);  
  }  
  
  // Header  
  main.appendChild(el('div', { class: 'btn-row' }, [  
    el('button', { class: 'btn ghost', onclick: () => {  
      if (order.customerId) { currentCustomerId = order.customerId; currentOrderId = null; setView('customers', { customerId: order.customerId }); }  
      else setView('orders');  
    }}, '← Back')  
  ]));  
  
  main.appendChild(el('h1', { class: 'page-title' }, isExisting ? 'Edit Order' : 'Ny order'));  
  const customer = store.customers.find(c => c.id === order.customerId);  
  main.appendChild(el('p', { class: 'page-sub' }, customer ? customer.name + ' · ' + (isExisting ? 'draft' : 'new') : 'No customer selected'));  
  
  const headActions = el('div', { class: 'btn-row' });  
  headActions.appendChild(el('button', { class: 'btn primary', onclick: () => save() }, 'Save'));  
  headActions.appendChild(el('button', { class: 'btn', onclick: () => { save(true); openOrderPDF(order.id); } }, 'PDF / Print'));  
  if (isExisting) {  
    headActions.appendChild(el('button', { class: 'btn', onclick: () => duplicateOrder(order) }, 'Duplicate'));  
    headActions.appendChild(el('button', { class: 'btn danger small', onclick: () => confirmDeleteOrder(order) }, 'Delete'));  
  }  
  main.appendChild(headActions);  
  
  // ====== KUND ======  
  main.appendChild(el('h2', { class: 'section-title' }, '1. Customer'));  
  if (store.customers.length === 0) {  
    main.appendChild(el('p', { style: 'font-size:13px; color:var(--muted); padding:14px 0;' }, 'No customers yet — add one under Customers first.'));  
    return;  
  }  
  
  if (order.customerId) {  
    // Kund vald — visa info + Byt-knapp  
    const selectedC = store.customers.find(c => c.id === order.customerId);  
    if (selectedC) {  
      const infoParts = [];  
      if (selectedC.email) infoParts.push(selectedC.email);  
      if (selectedC.phone) infoParts.push(selectedC.phone);  
      main.appendChild(el('div', { class: 'order-summary', style: 'display:flex; align-items:center; justify-content:space-between; gap:14px;' }, [  
        el('div', {}, [  
          el('div', { style: 'font-family:Hoefler Text,Georgia,serif; font-size:20px; font-weight:500; margin-bottom:4px;' }, selectedC.name),  
          el('div', { style: 'font-size:12px; color:var(--muted);' }, infoParts.join(' · ') || 'No contact info')  
        ]),  
        el('button', { class: 'btn ghost small', onclick: () => {  
          order.customerId = '';  
          window._orderCustomerSearch = '';  
          rerender();  
        }}, 'Change Customer')  
      ]));  
    }  
  } else {  
    // Ingen kund vald — visa sökruta  
    if (window._orderCustomerSearch == null) window._orderCustomerSearch = '';  
    const searchWrap = el('div', { style: 'position:relative; margin-bottom: 16px;' });  
    const searchInput = el('input', {  
      type: 'search', value: window._orderCustomerSearch,  
      placeholder: 'Search customer (name, email, phone)...', autocomplete: 'off',  
      style: 'width:100%; padding:14px 16px 14px 44px; font-size:15px; border:1px solid var(--line); border-radius:0; background:var(--bg); font-family:-apple-system,sans-serif;',  
      oninput: e => {  
        window._orderCustomerSearch = e.target.value;  
        const sy = window.scrollY;  
        renderNewOrder();  
        window.scrollTo(0, sy);  
        setTimeout(() => {  
          const newInput = document.querySelector('input[type="search"]');  
          if (newInput) {  
            newInput.focus();  
            newInput.setSelectionRange(newInput.value.length, newInput.value.length);  
          }  
        }, 0);  
      }  
    });  
    searchWrap.appendChild(el('div', { style: 'position:absolute; left:14px; top:50%; transform:translateY(-50%); color:var(--muted-soft); font-size:18px; pointer-events:none;', html: '⌕' }));  
    searchWrap.appendChild(searchInput);  
    main.appendChild(searchWrap);  
  
    const q = window._orderCustomerSearch || '';  
    let list;  
    if (q.trim()) {  
      list = store.customers  
        .map(c => ({ c, score: customerMatchScore(c, q) }))  
        .filter(x => x.score > 0)  
        .sort((a, b) => b.score - a.score)  
        .map(x => x.c)  
        .slice(0, 20);  
    } else {  
      // Visa senast aktiva 10 när ingen sökning  
      list = [...store.customers].sort((a, b) => {  
        const lastA = store.orders.filter(o => o.customerId === a.id).sort((x,y) => (y.updatedAt||'').localeCompare(x.updatedAt||''))[0];  
        const lastB = store.orders.filter(o => o.customerId === b.id).sort((x,y) => (y.updatedAt||'').localeCompare(x.updatedAt||''))[0];  
        if (lastA && lastB) return (lastB.updatedAt||'').localeCompare(lastA.updatedAt||'');  
        if (lastA) return -1; if (lastB) return 1;  
        return a.name.localeCompare(b.name);  
      }).slice(0, 10);  
    }  
  
    if (q.trim() && list.length === 0) {  
      main.appendChild(el('p', { style: 'font-size:13px; color:var(--muted); padding:14px;' }, 'No customer matches "' + q + '"'));  
    } else {  
      if (!q.trim()) {  
        main.appendChild(el('p', { style: 'font-size:10px; color:var(--muted); letter-spacing:0.18em; text-transform:uppercase; font-weight:600; margin-bottom:10px;' }, 'Recent customers'));  
      }  
      const listWrap = el('div');  
      list.forEach(c => {  
        const infoParts = [];  
        if (c.email) infoParts.push(c.email);  
        if (c.phone) infoParts.push(c.phone);  
        listWrap.appendChild(el('div', {  
          style: 'padding:12px 16px; border:1px solid var(--line); margin-bottom:6px; cursor:pointer; transition:all 0.12s; background:var(--bg);',  
          onmouseover: e => { e.currentTarget.style.borderColor = 'var(--ink)'; e.currentTarget.style.background = 'var(--bg-subtle)'; },  
          onmouseout: e => { e.currentTarget.style.borderColor = 'var(--line)'; e.currentTarget.style.background = 'var(--bg)'; },  
          onclick: () => {  
            order.customerId = c.id;  
            window._orderCustomerSearch = '';  
            rerender();  
          }  
        }, [  
          el('div', { style: 'font-weight:500; font-size:14px;' }, c.name),  
          infoParts.length ? el('div', { style: 'font-size:11px; color:var(--muted); margin-top:2px;' }, infoParts.join(' · ')) : null  
        ].filter(Boolean)));  
      });  
      main.appendChild(listWrap);  
    }  
    return; // Kan inte gå vidare utan kund  
  }  
  
  // ====== PLAGG-RADER ======  
  main.appendChild(el('h2', { class: 'section-title' }, '2. Garments'));  
  
  if (order.plagg.length === 0) {  
    main.appendChild(el('p', { style: 'font-size:13px; color:var(--muted); padding:8px 0 16px;' }, 'No garments yet — choose a garment type below to add.'));  
  }  
  
  order.plagg.forEach((rad, idx) => {  
    renderPlaggRad(main, order, rad, idx, rerender);  
  });  
  
  // ADD PLAGG  
  main.appendChild(el('div', { style: 'margin-top: 20px;' }, [  
    el('div', { style: 'font-size:10px; font-weight:600; letter-spacing:0.22em; text-transform:uppercase; color:var(--muted); margin-bottom:10px;' }, order.plagg.length > 0 ? 'Add garment' : 'Choose garment'),  
    (() => {  
      const grid = el('div', { class: 'plagg-grid' });  
      PLAGG_TYPES.forEach(p => {  
        grid.appendChild(el('button', {  
          class: 'plagg-card', type: 'button',  
          onclick: () => {  
            const ny = newPlaggRad(p.key);  
            if (ny) { order.plagg.push(ny); rerender(); }  
          }  
        }, '+ ' + p.label));  
      });  
      return grid;  
    })()  
  ]));  
  
  // ====== LEVERANS / REMARK ======  
  main.appendChild(el('h2', { class: 'section-title' }, '3. Delivery & Notes'));  
  const grid = el('div', { class: 'form-grid' });  
  grid.appendChild(field('Expected Delivery', el('input', { type: 'date', value: order.deliveryDate || '', oninput: e => order.deliveryDate = e.target.value })));  
  grid.appendChild(field('Occasion', select(order.occasion, ['Work', 'Wedding', 'Casual', 'Other'], v => order.occasion = v)));  
  grid.appendChild(field('Order notes', textareaInput(order.notes, v => order.notes = v, ''), true));  
  main.appendChild(grid);  
  
  // FOOTER  
  main.appendChild(el('div', { class: 'btn-row', style: 'margin-top: 30px;' }, [  
    el('button', { class: 'btn primary', onclick: () => save() }, 'Save'),  
    el('button', { class: 'btn', onclick: () => { order.status = 'confirmed'; save(); toast('Ready for GoCreate'); }}, 'Mark as Ready'),  
    el('button', { class: 'btn', onclick: () => { save(true); openOrderPDF(order.id); } }, 'PDF / Print')  
  ]));  
}  
  
function renderPlaggRad(main, order, rad, idx, rerender) {  
  const def = getPlaggDef(rad.type);  
  if (!def) return;  
  const wrap = el('div', { class: 'plagg-rad' });  
  wrap.appendChild(el('div', { class: 'plagg-rad-head' }, [  
    el('div', {}, [  
      el('div', { class: 'pr-num' }, 'Garment ' + (idx + 1)),  
      el('div', { class: 'pr-title' }, def.label)  
    ]),  
    el('button', { class: 'btn danger small', onclick: () => {  
      if (confirm('Remove this garment?')) {  
        order.plagg.splice(idx, 1);  
        rerender();  
      }  
    }}, 'Remove')  
  ]));  
  
  // Storlek  
  wrap.appendChild(el('div', { style: 'margin-bottom: 18px;' }, [  
    field('Base Size', textInput(rad.size || '', v => rad.size = v, ''), true)  
  ]));  
  
  // Tyg / Foder / Knapp  
  const tygGrid = el('div', { class: 'form-grid' });  
  tygGrid.appendChild(field('Fabric', textInput(rad.fabric, v => rad.fabric = v, '')));  
  tygGrid.appendChild(field('Lining', textInput(rad.lining, v => rad.lining = v, '')));  
  tygGrid.appendChild(field('Button', textInput(rad.button, v => rad.button = v, ''), true));  
  wrap.appendChild(tygGrid);  
  
  // Design + FitTools — en uppsättning per "part"  
  def.parts.forEach(part => {  
    wrap.appendChild(el('div', { style: 'margin-top: 22px; padding-top: 18px; border-top: 1px solid var(--line-soft);' }, [  
      el('div', { style: 'font-family:Hoefler Text,Georgia,serif; font-size:17px; color:var(--accent); margin-bottom: 14px;' }, part),  
      (() => {  
        const g = el('div', { class: 'form-grid' });  
        g.appendChild(field('Design (' + part + ')', textareaInput(rad.design[part] || '', v => rad.design[part] = v, '', '100px'), true));  
        g.appendChild(field('Adjustments / FitTools (' + part + ')', textareaInput(rad.fittools[part] || '', v => rad.fittools[part] = v, '', '100px'), true));  
        return g;  
      })()  
    ]));  
  });  
  
  // Väst-tillval (bara för kostym/smoking)  
  if (def.allowVest) {  
    wrap.appendChild(el('div', { style: 'margin-top: 22px; padding-top: 18px; border-top: 1px solid var(--line-soft);' }, [  
      el('label', { class: 'vast-toggle' }, [  
        el('input', { type: 'checkbox', checked: rad.includeVest ? 'checked' : null, onchange: e => { rad.includeVest = e.target.checked; rerender(); }}),  
        el('span', {}, 'Include vest in this ' + def.label.toLowerCase())  
      ])  
    ]));  
    if (rad.includeVest) {  
      wrap.appendChild(el('div', { style: 'margin-top: 12px;' }, [  
        el('div', { style: 'font-family:Hoefler Text,Georgia,serif; font-size:17px; color:var(--accent); margin-bottom: 14px;' }, 'Vest'),  
        (() => {  
          const g = el('div', { class: 'form-grid' });  
          g.appendChild(field('Design (Vest)', textareaInput(rad.vestDesign || '', v => rad.vestDesign = v, '', '100px'), true));  
          g.appendChild(field('Adjustments / FitTools (Vest)', textareaInput(rad.vestFitTools || '', v => rad.vestFitTools = v, '', '100px'), true));  
          return g;  
        })()  
      ]));  
    }  
  }  
  
  // Per-plagg remark  
  wrap.appendChild(el('div', { style: 'margin-top: 22px; padding-top: 18px; border-top: 1px solid var(--line-soft);' }, [  
    field('Remark for this garment (optional)', textareaInput(rad.remark || '', v => rad.remark = v, '', '60px'), true)  
  ]));  
  
  main.appendChild(wrap);  
}  
  
function duplicateOrder(orig) {  
  const copy = JSON.parse(JSON.stringify(orig));  
  copy.id = uid(); copy.status = 'draft';  
  copy.createdAt = todayISO(); copy.updatedAt = todayISO();  
  if (copy.plagg) copy.plagg.forEach(p => p.id = uid());  
  store.orders.push(copy); saveStore();  
  currentOrderId = copy.id; setView('new-order');  
  toast('Duplicated');  
}  
  
function confirmDeleteOrder(o) {  
  const msg = el('p', {}, 'Delete this order?');  
  const actions = el('div', { class: 'modal-actions' }, [  
    el('button', { class: 'btn ghost', onclick: closeModal }, 'Cancel'),  
    el('button', { class: 'btn danger', onclick: () => {  
      store.orders = store.orders.filter(x => x.id !== o.id);  
      saveStore(); closeModal();  
      const custId = o.customerId; currentOrderId = null;  
      if (custId) { currentCustomerId = custId; setView('customers', { customerId: custId }); }  
      else setView('orders');  
      toast('Order deleted');  
    }}, 'Delete')  
  ]);  
  modal('Confirm Delete', msg, actions);  
}  
  
// ============================================================  
// ALL ORDERS  
// ============================================================  
function renderAllOrders() {  
  const main = document.getElementById('main');  
  main.innerHTML = '';  
  main.appendChild(el('h1', { class: 'page-title' }, 'All Orders'));  
  main.appendChild(el('p', { class: 'page-sub' }, store.orders.length + ' order' + (store.orders.length === 1 ? '' : 's')));  
  main.appendChild(el('div', { class: 'btn-row' }, [  
    el('button', { class: 'btn primary', onclick: () => { currentOrderId = null; currentCustomerId = null; setView('new-order'); } }, '+ New Order')  
  ]));  
  if (store.orders.length === 0) {  
    main.appendChild(el('div', { class: 'empty' }, [el('div', { class: 'e-icon' }, '·'), el('div', { class: 'e-title' }, 'No orders yet')]));  
    return;  
  }  
  const sorted = [...store.orders].sort((a,b) => (b.updatedAt||'').localeCompare(a.updatedAt||''));  
  sorted.forEach(o => {  
    const c = store.customers.find(x => x.id === o.customerId);  
    const plaggLabels = (o.plagg || []).map(p => (getPlaggDef(p.type) || {}).label || p.type).join(', ');  
    main.appendChild(el('div', { class: 'card', onclick: () => setView('new-order', { orderId: o.id }) }, [  
      el('div', { class: 'card-title' }, (plaggLabels || '(empty)') + (c ? ' · ' + c.name : '')),  
      el('div', { class: 'card-meta' }, [  
        el('span', { class: 'pill ' + (o.status === 'draft' ? 'amber' : 'green') }, o.status === 'draft' ? 'Draft' : 'Ready'),  
        el('span', {}, fmtDate(o.updatedAt))  
      ])  
    ]));  
  });  
}  
  
// ============================================================  
// PDF  
// ============================================================  
function openOrderPDF(orderId) {  
  const order = store.orders.find(o => o.id === orderId);  
  if (!order) return;  
  const customer = store.customers.find(c => c.id === order.customerId);  
  const main = document.getElementById('main');  
  main.innerHTML = '';  
  main.appendChild(el('div', { class: 'btn-row' }, [  
    el('button', { class: 'btn ghost', onclick: () => { currentOrderId = orderId; setView('new-order'); } }, '← Back'),  
    el('button', { class: 'btn primary', onclick: () => window.print() }, 'Skriv ut / PDF')  
  ]));  
  const pdf = el('div', { class: 'pdf-view' });  
  pdf.appendChild(el('div', { class: 'pdf-header' }, [  
    el('h1', {}, 'Rose & Born · MTM Order'),  
    el('div', { class: 'pdf-sub' }, fmtDate(order.updatedAt))  
  ]));  
  pdf.appendChild(pdfSection('Customer', [  
    ['Name', customer ? customer.name : '—'],  
    ['E-mail', customer ? (customer.email || '—') : '—'],  
    ['Phone', customer ? (customer.phone || '—') : '—']  
  ]));  
  pdf.appendChild(pdfSection('Order info', [  
    ['Delivery', order.deliveryDate || '—'],  
    ['Occasion', order.occasion || '—'],  
    ['Remark', order.notes || '—']  
  ]));  
  (order.plagg || []).forEach((rad, idx) => {  
    const def = getPlaggDef(rad.type);  
    if (!def) return;  
    const baseRows = [  
      ['Size', rad.size || '—'],  
      ['Fabric', rad.fabric || '—'],  
      ['Lining', rad.lining || '—'],  
      ['Button', rad.button || '—']  
    ];  
    pdf.appendChild(pdfSection('Garment ' + (idx + 1) + ' — ' + def.label, baseRows));  
    def.parts.forEach(part => {  
      const designStr = rad.design[part] || '—';  
      const fitStr = rad.fittools[part] || '—';  
      pdf.appendChild(pdfSection(def.label + ' · ' + part, [  
        ['Design', designStr],  
        ['FitTools', fitStr]  
      ]));  
    });  
    if (def.allowVest && rad.includeVest) {  
      pdf.appendChild(pdfSection(def.label + ' · Vest', [  
        ['Design', rad.vestDesign || '—'],  
        ['FitTools', rad.vestFitTools || '—']  
      ]));  
    }  
    if (rad.remark) pdf.appendChild(pdfSection(def.label + ' · Remark', [['Remark', rad.remark]]));  
  });  
  pdf.appendChild(el('div', { style: 'margin-top: 40px; font-size: 11px; color: var(--muted);' },  
    'Date: ' + fmtDate(order.updatedAt) + '                                     Signature: ________________________________'));  
  main.appendChild(pdf);  
}  
  
function pdfSection(title, rows) {  
  const sec = el('div', { class: 'pdf-section' });  
  sec.appendChild(el('h2', {}, title));  
  rows.forEach(r => {  
    const row = el('div', { class: 'pdf-row' });  
    row.appendChild(el('div', { class: 'k' }, r[0]));  
    row.appendChild(el('div', { class: 'v' }, r[1] || '—'));  
    sec.appendChild(row);  
  });  
  return sec;  
}  
  
// ============================================================  
// DISPATCH  
// ============================================================  
function render() {  
  if (currentView === 'customers') renderCustomers();  
  else if (currentView === 'new-order') renderNewOrder();  
  else if (currentView === 'orders') renderAllOrders();  
}  
  
// Bootstrap: visa login, kör appen efter inloggning (eller direkt om redan auth)  
if (setupLogin()) {  
  initApp();  
}  
</script>  
</body>  
</html>  
