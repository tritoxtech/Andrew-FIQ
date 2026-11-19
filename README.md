<!doctype html><html lang="en"><head><meta charset="utf-8"><meta name="viewport" content="width=device-width,initial-scale=1"><title>Andrew FIQ · TritoX QC</title><style>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;700;900&family=DM+Sans:wght@300;400;500;600;700&display=swap');
:root{
  --bg:#080a0f;--surface:#111520;--surface2:#171c2c;--surface3:#1e2438;
  --border:#252d45;--border2:#2e3850;
  --accent:#00d4ff;--accent2:#0085ff;--accent3:#7b2fff;
  --pass:#00e887;--pass-bg:rgba(0,232,135,0.07);
  --fail:#ff4d6a;--fail-bg:rgba(255,77,106,0.07);
  --warn:#ffb347;--warn-bg:rgba(255,179,71,0.07);
  --stop:#ff2d55;--stop-bg:rgba(255,45,85,0.12);
  --text:#dce4f5;--text2:#8a97bb;--muted:#424d6b;
  --sans:'DM Sans',sans-serif;--brand:'Orbitron',sans-serif;
}
*{box-sizing:border-box;margin:0;padding:0;}
body{background:var(--bg);color:var(--text);font-family:var(--sans);min-height:100vh;
  background-image:radial-gradient(ellipse 80% 40% at 50% -10%,rgba(0,133,255,0.08) 0%,transparent 70%),
  radial-gradient(ellipse 40% 30% at 90% 10%,rgba(123,47,255,0.06) 0%,transparent 60%);}
.app{max-width:1200px;margin:0 auto;padding:36px 24px 80px;}
/* Header */
.brand-header{display:flex;align-items:center;justify-content:space-between;margin-bottom:48px;padding-bottom:28px;border-bottom:1px solid var(--border);}
.brand-left{display:flex;align-items:center;gap:16px;}
.back-link{width:42px;height:42px;border-radius:12px;flex-shrink:0;display:flex;align-items:center;justify-content:center;text-decoration:none;background:var(--surface2);border:1px solid var(--border);color:var(--text);font-size:24px;transition:all .2s;}
.back-link:hover{border-color:var(--accent);color:var(--accent);transform:translateX(-2px);}
.brand-logo{width:64px;height:56px;border-radius:0;flex-shrink:0;background:#fff;display:flex;align-items:center;justify-content:center;box-shadow:none;position:relative;overflow:hidden;}
.brand-logo img{width:100%;height:100%;object-fit:contain;display:block;}
.brand-logo::after{content:none;}
.brand-name{font-family:var(--brand);font-size:22px;font-weight:900;letter-spacing:3px;text-transform:uppercase;background:linear-gradient(90deg,var(--accent),var(--accent2),var(--accent3));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
.brand-sub{font-size:12px;color:var(--text2);letter-spacing:1.5px;text-transform:uppercase;margin-top:3px;}
.brand-right{display:flex;align-items:center;gap:16px;}
.resource-links{display:flex;align-items:center;gap:10px;}
.resource-link{height:40px;display:inline-flex;align-items:center;gap:9px;padding:0 15px;border:1px solid var(--border2);border-radius:10px;background:var(--surface2);color:var(--text);font-size:12px;font-weight:700;text-decoration:none;white-space:nowrap;transition:all .2s;}
.resource-link:hover{border-color:var(--accent);background:rgba(0,133,255,.08);transform:translateY(-1px);}
.resource-icon{width:22px;height:22px;border-radius:6px;display:inline-flex;align-items:center;justify-content:center;color:#fff;font-size:13px;font-weight:900;}
.resource-icon.sheet{background:#188038;}
.resource-icon.doc{background:#1a73e8;}
.status-links{display:flex;align-items:center;gap:10px;}
.brand-badge{background:var(--surface2);border:1px solid var(--border);border-radius:20px;padding:5px 14px;font-size:11px;color:var(--text2);letter-spacing:1px;text-transform:uppercase;}

.debug-btn{background:#1e2438;border:1px solid #2e3850;color:#8a97bb;border-radius:6px;padding:4px 10px;font-size:11px;cursor:pointer;transition:all 0.15s;}
.debug-btn:hover{border-color:#00d4ff;color:#00d4ff;}

.live-dot{display:inline-block;width:6px;height:6px;border-radius:50%;background:var(--pass);margin-right:5px;animation:pulse 1.8s ease-in-out infinite;}
@keyframes pulse{0%,100%{opacity:1;transform:scale(1)}50%{opacity:0.5;transform:scale(0.8)}}
@media(max-width:900px){
  .brand-header{align-items:flex-start;flex-direction:column;}
  .brand-right{width:100%;justify-content:space-between;flex-wrap:wrap;}
}
@media(max-width:560px){
  .resource-links{width:100%;}
  .resource-link{flex:1;justify-content:center;padding:0 10px;}
}
/* Upload */
.upload-zone{border:2px dashed var(--border2);border-radius:20px;padding:56px 32px;text-align:center;cursor:pointer;transition:all 0.25s;background:var(--surface);margin-bottom:32px;position:relative;overflow:hidden;}
.upload-zone::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse 60% 50% at 50% 100%,rgba(0,133,255,0.04) 0%,transparent 70%);pointer-events:none;}
.upload-zone:hover,.upload-zone.drag-over{border-color:var(--accent2);background:rgba(0,133,255,0.04);}
.upload-zone input{display:none;}
.upload-icon{font-size:42px;margin-bottom:16px;display:block;}
.upload-zone h2{font-size:18px;font-weight:700;margin-bottom:8px;font-family:var(--brand);letter-spacing:1px;}
.upload-zone p{font-size:13px;color:var(--text2);line-height:1.7;}
.btn-upload{display:inline-block;margin-top:20px;padding:12px 32px;background:linear-gradient(135deg,var(--accent2),var(--accent3));color:#fff;border-radius:10px;font-size:14px;font-weight:700;cursor:pointer;border:none;transition:all 0.2s;font-family:var(--sans);letter-spacing:0.5px;box-shadow:0 4px 20px rgba(0,133,255,0.25);}
.btn-upload:hover{transform:translateY(-1px);}
/* Progress */
.progress-wrap{display:none;margin-bottom:28px;}
.progress-label{font-size:12px;color:var(--text2);margin-bottom:10px;display:flex;align-items:center;gap:8px;}
.progress-track{height:4px;background:var(--surface2);border-radius:4px;overflow:hidden;}
.progress-fill{height:100%;width:0%;background:linear-gradient(90deg,var(--accent2),var(--accent),var(--accent3));border-radius:4px;transition:width 0.3s;}
/* Summary */
.summary-bar{display:flex;gap:14px;margin-bottom:28px;flex-wrap:wrap;}
.summary-card{flex:1;min-width:130px;background:var(--surface);border:1px solid var(--border);border-radius:14px;padding:18px 20px;}
.sc-label{font-size:10px;color:var(--muted);text-transform:uppercase;letter-spacing:1.2px;margin-bottom:8px;font-weight:600;}
.sc-val{font-family:var(--brand);font-size:30px;font-weight:700;}
.sc-total .sc-val{color:var(--text);}
.sc-pass .sc-val{color:var(--pass);}
.sc-fail .sc-val{color:var(--fail);}
.sc-warn .sc-val{color:var(--warn);}
/* Toolbar */
.toolbar{display:flex;gap:8px;margin-bottom:20px;flex-wrap:wrap;align-items:center;}
.filter-btn{padding:7px 18px;border-radius:20px;border:1px solid var(--border);background:var(--surface);color:var(--text2);font-size:13px;cursor:pointer;transition:all 0.15s;font-family:var(--sans);font-weight:500;}
.filter-btn:hover{border-color:var(--accent2);color:var(--text);}
.filter-btn.active{background:linear-gradient(135deg,var(--accent2),var(--accent3));border-color:transparent;color:#fff;}
.search-box{margin-left:auto;padding:8px 16px;border-radius:20px;border:1px solid var(--border);background:var(--surface);color:var(--text);font-size:13px;width:210px;font-family:var(--sans);outline:none;transition:border-color 0.2s;}
.search-box:focus{border-color:var(--accent2);}
.search-box::placeholder{color:var(--muted);}
.btn-action{padding:8px 18px;border-radius:8px;border:1px solid var(--border);background:var(--surface2);color:var(--text2);font-size:13px;cursor:pointer;transition:all 0.15s;font-family:var(--sans);font-weight:500;}
.btn-action:hover{border-color:var(--accent2);color:var(--text);}
.btn-stop{border-color:rgba(255,45,85,0.4);color:var(--stop);}
.btn-stop:hover{border-color:var(--stop);background:var(--stop-bg);}
.btn-danger:hover{border-color:var(--fail);color:var(--fail);}
/* Table */
.results-wrap{display:none;}
.results-table{width:100%;border-collapse:collapse;}
.results-table thead tr{border-bottom:1px solid var(--border);}
.results-table th{text-align:left;padding:10px 14px;font-size:10px;text-transform:uppercase;letter-spacing:1px;color:var(--muted);font-weight:700;white-space:nowrap;}
.row-card{border-bottom:1px solid var(--border);transition:background 0.15s;}
.row-card:hover{background:rgba(255,255,255,0.015);}
/* STOP banner */
.stop-banner{background:var(--stop-bg);border-left:3px solid var(--stop);padding:8px 14px;font-size:12px;font-weight:700;color:var(--stop);letter-spacing:0.5px;}
.row-main{display:grid;grid-template-columns:32px 200px 140px 90px 110px 105px 1fr;align-items:center;gap:0;cursor:pointer;padding:15px 14px;}
.row-expand{color:var(--muted);font-size:10px;transition:transform 0.2s;user-select:none;}
.row-expand.open{transform:rotate(90deg);color:var(--accent);}
.col-name .cname{font-weight:600;font-size:14px;color:var(--text);}
.col-name .fname{font-size:11px;color:var(--muted);margin-top:3px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;max-width:190px;}
.chip{display:inline-block;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700;}
.chip-farmers{background:rgba(255,179,71,0.12);color:var(--warn);border:1px solid rgba(255,179,71,0.2);}
.chip-farmer-bristol{background:rgba(123,47,255,0.12);color:#a78bfa;border:1px solid rgba(123,47,255,0.2);}
.chip-bristol{background:rgba(0,133,255,0.12);color:var(--accent);border:1px solid rgba(0,133,255,0.2);}
.chip-unknown{background:var(--surface2);color:var(--muted);border:1px solid var(--border);}
.status-badge{display:inline-flex;align-items:center;gap:5px;padding:5px 13px;border-radius:20px;font-size:12px;font-weight:700;}
.status-pass{background:var(--pass-bg);color:var(--pass);border:1px solid rgba(0,232,135,0.2);}
.status-fail{background:var(--fail-bg);color:var(--fail);border:1px solid rgba(255,77,106,0.2);}
.status-warn{background:var(--warn-bg);color:var(--warn);border:1px solid rgba(255,179,71,0.2);}
.err-pill{display:inline-block;background:var(--fail-bg);color:var(--fail);border:1px solid rgba(255,77,106,0.2);border-radius:5px;padding:2px 9px;margin:2px 3px 2px 0;font-size:11px;}
.warn-pill{display:inline-block;background:var(--warn-bg);color:var(--warn);border:1px solid rgba(255,179,71,0.2);border-radius:5px;padding:2px 9px;margin:2px 3px 2px 0;font-size:11px;}
.ok-text{color:var(--pass);font-size:12px;font-weight:600;}
/* Details */
.row-details{display:none;padding:4px 14px 22px 46px;gap:10px;}.row-details.open{display:flex;flex-direction:column;}.row-details-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(230px,1fr));gap:10px;}

.detail-group{background:var(--surface2);border:1px solid var(--border);border-radius:12px;padding:16px;}
.detail-group h4{font-size:10px;text-transform:uppercase;letter-spacing:1px;color:var(--muted);margin-bottom:12px;font-weight:700;padding-bottom:8px;border-bottom:1px solid var(--border);}
.check-item{display:flex;align-items:flex-start;gap:8px;margin-bottom:8px;font-size:13px;line-height:1.4;}
.check-item:last-child{margin-bottom:0;}
.ci-icon{flex-shrink:0;margin-top:1px;}
.ci-ok{color:var(--pass);}.ci-fail{color:var(--fail);}.ci-warn{color:var(--warn);}.ci-info{color:var(--accent);}
.ci-label{color:var(--text2);flex:1;}
.ci-val{font-size:12px;font-weight:600;white-space:nowrap;}
.ci-val.bad{color:var(--fail);}.ci-val.ok{color:var(--pass);}.ci-val.neutral{color:var(--text2);}
.vehicle-item{background:var(--surface3);border-radius:8px;padding:11px 13px;margin-bottom:7px;}
.vehicle-item:last-child{margin-bottom:0;}
.v-name{font-weight:600;font-size:13px;margin-bottom:6px;color:var(--text);}
.v-tags{display:flex;flex-wrap:wrap;gap:4px;margin-bottom:5px;}
.v-ok{background:var(--pass-bg);color:var(--pass);padding:2px 9px;border-radius:4px;font-size:11px;font-weight:600;}
.v-fail{background:var(--fail-bg);color:var(--fail);padding:2px 9px;border-radius:4px;font-size:11px;font-weight:600;}
.v-info{background:rgba(0,133,255,0.1);color:var(--accent);padding:2px 9px;border-radius:4px;font-size:11px;font-weight:600;}
.spinner{display:inline-block;width:13px;height:13px;border:2px solid var(--border2);border-top-color:var(--accent);border-radius:50%;animation:spin 0.7s linear infinite;vertical-align:middle;}
@keyframes spin{to{transform:rotate(360deg)}}
.processing-row td{padding:16px 14px;color:var(--text2);font-size:13px;border-bottom:1px solid var(--border);}

/* AgencyZoom Checklist */
.az-panel{background:var(--surface2);border:1px solid var(--border);border-radius:12px;padding:16px;margin-top:4px;}
.az-panel h4{font-size:10px;text-transform:uppercase;letter-spacing:1px;color:var(--accent);margin-bottom:12px;font-weight:700;padding-bottom:8px;border-bottom:1px solid var(--border);display:flex;align-items:center;gap:6px;}
.az-row{display:flex;align-items:center;gap:8px;margin-bottom:7px;font-size:13px;}
.az-row:last-child{margin-bottom:0;}
.az-label{color:var(--text2);flex:1;min-width:120px;font-size:12px;}
.az-val{color:var(--text);font-weight:600;flex:2;font-size:13px;}
.az-copy{background:var(--surface3);border:1px solid var(--border2);color:var(--accent);border-radius:6px;padding:3px 10px;font-size:11px;cursor:pointer;transition:all 0.15s;white-space:nowrap;font-family:var(--sans);}
.az-copy:hover{background:rgba(0,212,255,0.1);border-color:var(--accent);}
.az-copy.copied{background:rgba(0,232,135,0.1);border-color:var(--pass);color:var(--pass);}
.az-manual{color:var(--warn);font-size:11px;font-style:italic;}
/* Home QC group */
.home-group{border-color:rgba(123,47,255,0.3);}
.home-group h4{color:#a78bfa;}


/* Bookmarklet Section */
.footer{margin-top:60px;padding-top:24px;border-top:1px solid var(--border);display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:10px;}
.footer-brand{font-family:var(--brand);font-size:13px;letter-spacing:2px;background:linear-gradient(90deg,var(--accent),var(--accent3));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
.footer-note{font-size:12px;color:var(--muted);}

.card{background:var(--surface);border:1px solid var(--border);border-radius:14px;padding:20px;margin:15px 0}.checks{display:grid;grid-template-columns:repeat(auto-fit,minmax(300px,1fr));gap:7px}.check{padding:10px;border-radius:7px;background:var(--surface2);font-size:13px}.bad{color:var(--fail)}.good{color:var(--pass)}.review{color:var(--warn)}summary{cursor:pointer;font-weight:700}label{font-size:13px;color:var(--text2)}input,select{background:var(--surface2);border:1px solid var(--border2);border-radius:8px;padding:9px;color:var(--text)}.rules{color:var(--text2);line-height:1.7;font-size:13px}button{cursor:pointer}h3{margin-bottom:14px} .check small{display:block;color:var(--text2);margin-top:5px}/* Match the original QC typography; disclosure rows must not inherit bold summary text. */
summary.row-main{font-family:var(--sans);font-size:13px;font-weight:400;line-height:1.4;list-style:none;}
summary.row-main::-webkit-details-marker{display:none;}
.row-main .rules{font-weight:400;}
.row-main .err-pill,.row-main .warn-pill{font-family:var(--sans);font-size:11px;font-weight:400;line-height:1.4;}
.row-details-grid{font-family:var(--sans);font-weight:400;}
.check-item small{font-family:var(--sans);font-weight:400;}
button,input,select{font-family:var(--sans);}
 .summary-label{font-size:10px;text-transform:uppercase;letter-spacing:1px;color:var(--muted);margin-bottom:9px}.summary-num{font-family:var(--brand);font-size:28px;font-weight:700}#progress{font-size:13px;color:var(--text2);margin:15px 0}.toolbar-right{display:flex;gap:8px;flex-wrap:wrap;margin-left:auto}.toolbar input{border-radius:20px;font-size:13px}.row-card details[open]>.row-main .cname{color:var(--text)}
.andrew-helper-setup{margin-top:28px;padding:24px;border:1px solid rgba(0,212,255,.32);border-radius:16px;background:linear-gradient(135deg,rgba(0,212,255,.055),rgba(123,47,255,.055));}
.andrew-helper-setup h3{margin:0 0 12px;color:var(--accent);font-size:14px;letter-spacing:.3px;}
.andrew-helper-setup ol{margin:0 0 16px;padding-left:20px;color:var(--text2);font-size:12px;line-height:1.85;}
.andrew-helper-setup strong{color:var(--text);}
.andrew-helper-btn{height:40px;display:inline-flex;align-items:center;gap:8px;padding:0 17px;border:0;border-radius:9px;background:linear-gradient(135deg,#00cfff,#7b2fff);color:#fff;font-size:12px;font-weight:800;cursor:pointer;font-family:var(--sans);box-shadow:0 8px 24px rgba(0,150,255,.18);}
.andrew-helper-btn:hover{filter:brightness(1.08);transform:translateY(-1px);}
.andrew-helper-card{width:min(1000px,96vw);max-height:88vh;background:var(--surface);border:1px solid var(--border2);border-radius:14px;overflow:hidden;box-shadow:0 24px 80px rgba(0,0,0,.55);}
.andrew-helper-head{display:flex;align-items:center;justify-content:space-between;padding:16px 18px;border-bottom:1px solid var(--border);}
.andrew-helper-actions{display:flex;gap:8px;}
.andrew-helper-code{margin:0;padding:18px;max-height:68vh;overflow:auto;white-space:pre;font:12px/1.5 Consolas,Monaco,monospace;color:#dce4f5;background:#0b0e16;}
#andrewHelperDialog{width:min(1000px,calc(100% - 32px));padding:0;max-height:88vh;overflow:auto;background:var(--surface);color:var(--text);border:1px solid var(--border2);border-radius:14px}
#andrewHelperDialog::backdrop{background:rgba(0,0,0,.72)}
.andrew-helper-head{flex-wrap:wrap;gap:10px}.andrew-helper-actions{flex-wrap:wrap}
.lead-card{border-color:#237949}.lead-card h4{color:#64dc96}</style></head><body><main class="app"><header class="brand-header"><div class="brand-left"><a class="back-link" href="https://tritoxtech.github.io/Qccheck/" aria-label="Back to QC main page" title="Back to QC main page">←</a><div class="brand-logo"><img src="data:image/jpeg;base64,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" alt="TritoX logo"/></div><div><div class="brand-name">TritoX</div><div class="brand-sub">Andrew FIQ · Auto, Home &amp; Renters</div></div></div></header>
<div class="upload-zone" id="zone"><h2>Drop Quote PDFs Here</h2><p>Auto · Home · Renters · Bundles · Multiple PDFs</p><button class="btn-upload" id="select">Select PDF Files</button><input type="file" id="files" accept="application/pdf" multiple></div><details style="margin:16px 0;color:var(--text2);font-size:13px"><summary>Andrew QC criteria</summary><p>Agency: Andrew Castaneda / Andrew Castaneda Agency · Effective date: exactly 14 days after prepared date · Farmers: Signal and Auto/Home (Home or Condo accepted) · BW: Farmers Home · Active comprehensive/collision: $1,000 · Farmers roadside: Standard · BW roadside: Yes · Home: Personal Property Replacement Cost Included; Roof Materials Loss Settlement Replacement Cost.</p><p>PIP (Personal Injury Protection Medical) is not checked. These checks use Andrew’s supplied rules only.</p></details><p id="progress" aria-live="polite"></p><div class="summary-bar" id="summary" aria-live="polite"></div><div class="toolbar"><div class="filters"><button class="filter-btn active" data-filter="all">All</button><button class="filter-btn" data-filter="fail">Flagged</button><button class="filter-btn" data-filter="review">Warnings</button><button class="filter-btn" data-filter="pass">Passed</button></div><div class="toolbar-right"><input id="search" placeholder="🔍 Search customer name..."><button class="btn-action" id="export">↓ Export All</button><button class="btn-action btn-danger" id="exportFlagged">↓ Export Flagged</button><button class="btn-action" id="clear">Clear All</button></div></div><div style="overflow-x:auto"><table class="results-table"><thead><tr><th>Customer</th><th>Type</th><th>Vehicles</th><th>Status</th><th>Flags / Notes</th></tr></thead><tbody id="results"></tbody></table></div><footer class="footer"><span class="footer-brand">TRITOX QC</span><span class="footer-note">PDFs processed locally in your browser</span></footer></main><script>
const results=[];
const esc=s=>String(s??'').replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
const money=s=>s==null?null:Number(String(s).replace(/[$,\s]/g,''));
const dollars=n=>n==null?'Unavailable':n.toLocaleString('en-US',{style:'currency',currency:'USD',minimumFractionDigits:0,maximumFractionDigits:2});
const datePattern=/\b(?:Jan(?:uary)?|Feb(?:ruary)?|Mar(?:ch)?|Apr(?:il)?|May|Jun(?:e)?|Jul(?:y)?|Aug(?:ust)?|Sep(?:t(?:ember)?)?|Oct(?:ober)?|Nov(?:ember)?|Dec(?:ember)?)\s+\d{1,2},?\s+\d{4}\b|\b\d{1,2}\/\d{1,2}\/\d{2,4}\b/i;
const timestamp=s=>{if(!s)return NaN;const m=s.match(/^(\d+)\/(\d+)\/(\d+)$/);return m?Date.UTC(+m[3]+(m[3].length===2?2000:0),+m[1]-1,+m[2]):Date.parse(s+' UTC');};
const clean=s=>s.replace(/\u00a0/g,' ').replace(/[®™]/g,'').split('\n').map(x=>x.trim().replace(/[ \t]+/g,' ')).join('\n');
const heading=/^(?:(Farmers|Bristol West)\s+)?(Auto|Home|Renters)\s+quote\s+(summary|details)\b/im;
function pageText(items){
 const positioned=items.filter(i=>i.str?.trim()).map(i=>({x:i.transform[4],y:i.transform[5],s:i.str.trim()})).sort((a,b)=>b.y-a.y||a.x-b.x);
 // Keep the payment sidebar out of the main Applied discounts list.
 const discountHeaders=positioned.filter(i=>/^Applied discounts$/i.test(i.s));
 const leftHeader=discountHeaders.find(i=>discountHeaders.some(j=>j.x-i.x>150));
 const sidebar=leftHeader&&discountHeaders.find(j=>j.x-leftHeader.x>150);
 const discountItems=sidebar?positioned.filter(i=>!(i.x>=sidebar.x-4&&i.y<=leftHeader.y+3&&i.y>=leftHeader.y-110)):positioned;
 const rows=[];for(const i of discountItems){const row=rows.at(-1);if(row&&Math.abs(row.y-i.y)<=2.5)row.items.push(i);else rows.push({y:i.y,items:[i]});}
 return rows.map(row=>row.items.sort((a,b)=>a.x-b.x).map(i=>i.s).join(' ')).join('\n');
}
// Conservative first-name hints for review; leave unfamiliar or ambiguous names blank.
const husbandNames=new Set('aaron adam alan albert alexander andrew anthony benjamin brian charles christopher dan daniel david donald edward eric ethan frank george gregory henry israel jack james jason jeffrey john jonathan joseph joshua keith kenneth kevin lawrence mark matthew michael nathan nicholas patrick paul peter raymond richard robert rodney ronald samuel scott stephen steven thomas timothy vincent william'.split(' '));
const wifeNames=new Set('abigail alicia amanda amy angela ann anna anne ashley barbara betty carol catherine cheryl christina christine deborah debra diane donna dorothy elizabeth emily emma grace hannah heather helen jacqueline janet jennifer jessica joan julia julie karen kathleen katherine laura linda lisa margaret maria marie martha mary melissa michelle nancy nicole pamela patricia paula rebecca ruth sandra sarah sharon stephanie susan teresa victoria virginia'.split(' '));
function analyze(raw,filename){
 const pages=raw.split('\f').map(clean),whole=pages.join('\n'),checks=[],blocks={};
 const add=(group,label,expected,found,ok)=>checks.push({group,label,expected,found:found??'Unavailable',state:ok==null?'review':ok?'pass':'fail'});
 let current=null;
 for(const page of pages){
  const h=heading.exec(page);
  if(h){current=h[2].toLowerCase();(blocks[current]??={parts:[],carrier:null}).carrier=h[1]||blocks[current]?.carrier;}
  else if(/\b(?:Homeowners|Homeowner|Home)\s+(?:Insurance\s+)?(?:Quote|Proposal)|Roof Materials Loss Settlement/i.test(page)){current='home';blocks.home??={parts:[],carrier:'Farmers'};}
  else if(/\bAuto\s+(?:Insurance\s+)?(?:Quote|Proposal|Discounts)|Personal Injury Protection|\bPIP\s+(?:Medical|deductible)/i.test(page)){current='auto';blocks.auto??={parts:[],carrier:null};}
  if(current)blocks[current].parts.push(page);
 }
 if(!Object.keys(blocks).length){if(/\bComprehensive\b|\bCollision\b/i.test(whole))blocks.auto={parts:pages,carrier:null};}
 const agency=whole.match(/\bAndrew\s+Castaneda(?:\s+Agency)?\b/i)?.[0];
 add('Agency','Agency name','Andrew Castaneda or Andrew Castaneda Agency',agency,!!agency);
 const name=whole.match(/^Prepared\s+for\s*:?\s*\n([^\n]+)/im)?.[1]?.trim()||filename.replace(/\.pdf$/i,'');
 const type=['auto','home','renters'].filter(k=>blocks[k]).map(k=>k[0].toUpperCase()+k.slice(1)).join(' + ')||'Unknown';
 if(type==='Unknown')add('PDF','Quote type','Recognizable Auto or Home quote',null,null);
 let vehicleCount=null;
 const firstDate=t=>datePattern.exec(t)?.[0];
 function effective(t){
  const lines=t.split('\n');
  for(let i=0;i<lines.length;i++)if(/\b(?:Effective dates?|Policy start date|Policy effective date)\b/i.test(lines[i])){const d=firstDate(lines.slice(i,i+4).join('\n'));if(d)return d;}
  return null;
 }
 const prepared=firstDate(whole.match(/(?:Prepared\s+on|Date\s+Prepared|Preparation\s+date|Quote\s+date)[\s\S]{0,65}/i)?.[0]||'');
 const absent=v=>v!=null&&/^(?:Not (?:included|selected|covered|applicable)|None|No|N\/?A|[-–—])(?:\s|$)/i.test(v.trim());
 const line=(t,rx)=>{const m=rx.exec(t);if(!m)return null;const tail=t.slice(m.index+m[0].length).replace(/^[ \t:]+/,'');return tail.split('\n').map(x=>x.trim()).filter(Boolean)[0]||null;};
 for(const [key,b] of Object.entries(blocks)){
  const t=b.parts.join('\n'),group=key[0].toUpperCase()+key.slice(1),start=effective(t)||effective(whole);
  const days=(timestamp(start)-timestamp(prepared))/86400000;
  add('Date',group+' effective date','14 days after prepared date',Number.isFinite(days)?days+' days':null,Number.isFinite(days)?days===14:null);
  if(key==='auto'){
   const carrier=/Bristol\s+West/i.test(b.carrier||t)?'Bristol West':/Farmers\b/i.test(b.carrier||t)?'Farmers':null;
   add('Auto','Carrier','Farmers or Bristol West',carrier,carrier?true:null);
   const sections=[...t.matchAll(/^(?:Applied discounts|Auto Discounts|Discounts\s*\/\s*Preferences)\b[^\n]*\n([\s\S]*?)(?=^Payment plans?\b|^Vehicles\b|^Coverage\b|^Page \d|^Prepared on\b|^\*|\f|(?![\s\S]))/gim)];
   // Each section ends at the next major heading, keeping wrapped discount names together.
   let d=sections.length?sections.map(m=>m[1]).join(' ').replace(/\s+/g,' ').trim():null;
   if(carrier==='Farmers'){
    const signal=d==null?null:/\bSignal\b/i.test(d),home=d==null?null:/\bAuto\s*\/\s*Home\b|\bHome\s+or\s+Condo\b/i.test(d);
    add('Auto Discounts','Signal','Included',signal==null?null:signal?'Included':'Not listed',signal);
    add('Auto Discounts','Auto/Home','Included (Home or Condo accepted)',home==null?null:home?'Included':'Not listed',home);
   }else if(carrier==='Bristol West'){
    const home=d==null?null:/\b(?:Auto\s*\/\s*)?Farmers\s+Home\b/i.test(d);
    add('Auto Discounts','Farmers Home','Included',home==null?null:home?'Included':'Not listed',home);
   }
   const vs=[...t.matchAll(/^((?:19|20)\d{2}\s+[A-Za-z][^\n]*)\n(?=Coverage\b)/gim)];
   vehicleCount=vs.length||null;
   const chunks=vs.length?vs.map((m,i)=>({label:m[1],text:t.slice(m.index,vs[i+1]?.index??t.length)})):[{label:'Auto',text:t}];
   for(const v of chunks){
    for(const label of ['Comprehensive','Collision']){
     const row=new RegExp('^'+label+'\\b(?!\\s+plus)(?:[ \\t]+Deductible)?[ \\t:]*([^\\n]*)(?:\\n|$)','im').exec(v.text);
     if(!row)continue;
     let value=row[1].trim();
     // A deductible may be placed on its own next line; never read another coverage's value.
     if(!value){const next=v.text.slice(row.index+row[0].length).split('\n')[0].trim();if(/^(?:\$?[\d,]+(?:\.\d{2})?|Not included|Not selected|None|No|N\/?A|[-–—])$/i.test(next))value=next;}
     if(!value||absent(value))continue;
     // Summary column headings are not selected coverage rows.
     if(/^(?:Comprehensive|Collision)\b/i.test(value))continue;
     const amt=value.match(/\$?([\d,]+(?:\.\d{2})?)/)?.[1];
     add('Vehicle Coverage',v.label+' '+label,'$1,000 when present',value,amt==null?null:money(amt)===1000);
    }
    const road=line(v.text,/^(?:Towing and road service|Road\s*side assistance|Roadside assistance)\b/im);
    if(carrier)add('Vehicle Coverage',v.label+' roadside assistance',carrier==='Farmers'?'Standard':'Yes',road,road==null?null:carrier==='Farmers'?/^Standard\b/i.test(road):/^Yes\b/i.test(road));
   }
  }else if(key==='home'){
   const pp=line(t,/^Personal Property Replacement Cost\b/im);
   add('Home Coverage','Personal Property Replacement Cost','Included',pp,pp==null?null:/^Included\b/i.test(pp));
   const roofMatch=/^Roof Materials Loss Settlement\b[ \t:]*/im.exec(t);
   const roofRows=roofMatch?t.slice(roofMatch.index+roofMatch[0].length).trimStart().split('\n'):[];
   let roof=roofRows[0]?.trim()||null;
   // In proposal tables, the Included premium column precedes a wrapped Cost.
   if(roof&&/^Replacement(?:\s+Included)?$/i.test(roof)&&/^Cost\b/i.test(roofRows[1]?.trim()||''))roof+=' '+roofRows[1].trim();
   const roofValue=roof?.replace(/\bIncluded\b/gi,'').replace(/\s+/g,' ').trim();
   add('Home Coverage','Roof Materials Loss Settlement','Replacement Cost',roofValue,roofValue==null?null:/^Replacement\s+Cost\b/i.test(roofValue));
  }
 }
 const status=checks.some(c=>c.state==='fail')?'fail':checks.some(c=>c.state==='review')?'review':'pass';
 return {name,filename,type,checks,status,vehicleCount,text:raw};
}

let pdfReader;
async function readPDF(file){
 const base='https://cdn.jsdelivr.net/npm/pdfjs-dist@5.6.205/legacy/build/';
 const lib=await (pdfReader??=import(base+'pdf.min.mjs').catch(e=>{pdfReader=null;throw Error('PDF reader could not load. Connect to the internet and try again.');}));
 lib.GlobalWorkerOptions.workerSrc=base+'pdf.worker.min.mjs';
 const doc=await lib.getDocument({data:await file.arrayBuffer(),isEvalSupported:false}).promise;
 try{const pages=[];for(let n=1;n<=doc.numPages;n++)pages.push(pageText((await (await doc.getPage(n)).getTextContent()).items));return pages.join('\f');}
 finally{await doc.destroy();}
}
async function handle(files){for(const f of [...files].filter(f=>/\.pdf$/i.test(f.name))){document.getElementById('progress').textContent='Checking '+f.name;try{const t=await readPDF(f);results.push(analyze(t,f.name));}catch(e){results.push({filename:f.name,name:f.name,type:'Unknown',status:'review',checks:[{label:'PDF reading',state:'review',expected:'Readable text PDF',found:e.message}],text:''});}render();}document.getElementById('progress').textContent='Finished.';}

let activeFilter='all';
function checkPanel(title,checks){return `<div class="detail-group ${title.startsWith('Home')?'home-group':''}"><h4>${esc(title)}</h4>${checks.map(c=>`<div class="check-item"><span class="ci-icon ${c.state==='pass'?'ci-ok':c.state==='fail'?'ci-fail':'ci-warn'}">${c.state==='pass'?'✓':c.state==='fail'?'✗':'⚠'}</span><span class="ci-label">${esc(c.label)}<small style="display:block;font-size:11px">Required: ${esc(c.expected)}</small></span><span class="ci-val ${c.state==='pass'?'ok':c.state==='fail'?'bad':'neutral'}" style="white-space:normal">${esc(c.found||(c.state==='pass'?'Verified':'Missing'))}</span></div>`).join('')}</div>`;}
function render(){const q=document.getElementById('search').value.toLowerCase();document.getElementById('summary').innerHTML=[['Total',results.length,''],['✓ Passed',results.filter(r=>r.status==='pass').length,'good'],['✗ Flagged',results.filter(r=>r.status==='fail').length,'bad'],['⚠ Warnings',results.filter(r=>r.status==='review').length,'review']].map(([label,n,color])=>`<div class="summary-card"><div class="summary-label">${label}</div><div class="summary-num ${color}">${n}</div></div>`).join('');
const shown=results.filter(r=>(activeFilter==='all'||activeFilter===r.status)&&(!q||(r.name+' '+r.filename).toLowerCase().includes(q)));
document.getElementById('results').innerHTML=shown.map((r,i)=>{const groups=new Map();for(const c of r.checks){let group=c.group||'PDF';if(!groups.has(group))groups.set(group,[]);groups.get(group).push(c);}const flags=r.checks.filter(c=>c.state!=='pass').map(c=>`<span class="${c.state==='fail'?'err-pill':'warn-pill'}">${c.state==='fail'?'⚑':'⚠'} ${esc(c.label)} — must be ${esc(c.expected)}; found: ${esc(c.found||'Missing')}</span>`).join('')||'<span class="ok-text">✓ All checks passed</span>';return `<tr class="row-card"><td colspan="5"><details><summary class="row-main" style="grid-template-columns:205px 145px 78px 110px minmax(260px,1fr)"><div class="col-name"><div class="cname">▸ ${esc(r.name)}</div><div class="fname">${esc(r.filename)}</div></div><div><span class="chip chip-farmers">${esc(r.type)}</span></div><div class="rules">${r.type.includes('Auto')?(r.vehicleCount??'–'):'–'}</div><div><span class="status-badge status-${r.status==='review'?'warn':r.status}">${r.status==='pass'?'✓ PASS':r.status==='fail'?'✗ FLAGGED':'⚠ REVIEW'}</span></div><div>${flags}</div></summary><div style="padding:15px 14px 22px 46px"><div class="row-details-grid">${[...groups].map(([k,v])=>checkPanel(k,v)).join('')}</div><details style="margin-top:15px"><summary class="btn-action" style="display:inline-block">🔍 Debug</summary><pre style="white-space:pre-wrap;margin-top:12px;font-size:12px">${esc(r.text)}</pre></details></div></details></td></tr>`;}).join('')||'<tr><td colspan="5" style="padding:35px;text-align:center;color:var(--muted)">No results match.</td></tr>';}
document.getElementById('select').onclick=()=>document.getElementById('files').click();document.getElementById('files').onchange=e=>{handle(e.target.files);e.target.value='';};const zone=document.getElementById('zone');zone.onclick=e=>{if(e.target.closest('#select,#files'))return;document.getElementById('files').click();};zone.tabIndex=0;zone.setAttribute('role','button');zone.setAttribute('aria-label','Select quote PDF files');zone.onkeydown=e=>{if(e.target===zone&&(e.key==='Enter'||e.key===' ')){e.preventDefault();document.getElementById('files').click();}};zone.ondragover=e=>e.preventDefault();zone.ondrop=e=>{e.preventDefault();handle(e.dataTransfer.files);};document.getElementById('search').oninput=render;document.querySelectorAll('[data-filter]').forEach(b=>b.onclick=()=>{activeFilter=b.dataset.filter;document.querySelectorAll('[data-filter]').forEach(x=>x.classList.toggle('active',x===b));render();});document.getElementById('clear').onclick=()=>{results.length=0;render();};function exportResults(flagged=false){const cell=s=>'"'+String(s??'').replace(/"/g,'""')+'"';const rows=[['Filename','Customer','Type','Status','Check','Required','Found','Check status'],...results.filter(r=>!flagged||r.status==='fail').flatMap(r=>r.checks.map(c=>[r.filename,r.name,r.type,r.status,c.label,c.expected,c.found,c.state]))];const url=URL.createObjectURL(new Blob(['\ufeff'+rows.map(r=>r.map(cell).join(',')).join('\r\n')],{type:'text/csv;charset=utf-8'}));const a=document.createElement('a');a.href=url;a.download=flagged?'Andrew-FIQ-QC-Flagged.csv':'Andrew-FIQ-QC.csv';a.click();setTimeout(()=>URL.revokeObjectURL(url),1000);}
document.getElementById('export').onclick=()=>exportResults();document.getElementById('exportFlagged').onclick=()=>exportResults(true);
render();
</script></body></html>
