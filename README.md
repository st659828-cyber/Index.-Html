# Index.-Html
Winter arc tracker for free
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Winter Arc Tracker</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,600;9..144,700&family=Inter:wght@400;500;600&display=swap">
<style>
:root{--bg:#eaf1f7;--panel:#fbfdff;--ink:#0d1b2a;--mut:#5a6d82;--line:#cbd9e6;--acc:#2b6f9e;--ice:#bfe3f5;--ok:#1f8f6a;--chip:#e2edf6;--dot:#0d1b2a;
box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#08121d;--panel:#0f1e2e;--ink:#e8f2fa;--mut:#8ba3ba;--line:#22374c;--acc:#6db8e6;--ice:#1d4a66;--ok:#4cc9a0;--chip:#16293b;--dot:#e8f2fa}}
:root[data-theme="dark"]{--bg:#08121d;--panel:#0f1e2e;--ink:#e8f2fa;--mut:#8ba3ba;--line:#22374c;--acc:#6db8e6;--ice:#1d4a66;--ok:#4cc9a0;--chip:#16293b;--dot:#e8f2fa}
*,*::before,*::after{box-sizing:inherit}
html,body{margin:0}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
body{background:var(--bg);color:var(--ink);font:15px/1.5 Inter,system-ui,-apple-system,"Segoe UI",sans-serif}
h1,h2{font-family:Fraunces,Georgia,"Times New Roman",serif;margin:0;letter-spacing:-.01em}
button,input,textarea{font:inherit;color:inherit}
button:focus-visible,input:focus-visible,textarea:focus-visible{outline:2px solid var(--acc);outline-offset:2px}
.wrap{max-width:1180px;margin:0 auto;padding:20px 16px 48px}
header{display:flex;flex-wrap:wrap;gap:16px;align-items:flex-end;justify-content:space-between;padding:12px 0 22px;border-bottom:2px solid var(--ink)}
h1{font-size:clamp(30px,6vw,52px);line-height:1.02}
.sub{color:var(--mut);margin:6px 0 0}
.who{display:flex;gap:10px;align-items:center;flex-wrap:wrap}
.who input{background:transparent;border:0;border-bottom:1.5px solid var(--line);padding:6px 2px;width:150px;border-radius:0}
.mon{display:flex;align-items:center;gap:6px;background:var(--panel);border:1px solid var(--line);border-radius:999px;padding:3px}
.mon button{border:0;background:transparent;width:34px;height:34px;border-radius:50%;cursor:pointer;font-size:18px}
.mon button:hover{background:var(--chip)}
.mon strong{min-width:130px;text-align:center;font-family:Fraunces,Georgia,serif;font-size:17px}
.stats{display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));gap:12px;margin:22px 0}
.stat{background:var(--panel);border:1px solid var(--line);border-radius:12px;padding:14px 16px}
.stat b{display:block;font:700 30px/1.1 Fraunces,Georgia,serif}
.stat span{color:var(--mut);font-size:13px}
.bar{height:6px;border-radius:9px;background:var(--chip);margin-top:10px;overflow:hidden}
.bar i{display:block;height:100%;background:var(--acc);border-radius:9px;transition:width .3s}
section{background:var(--panel);border:1px solid var(--line);border-radius:12px;padding:18px;margin-bottom:18px}
section>h2{font-size:22px;margin-bottom:4px}
.hint{color:var(--mut);margin:0 0 14px;font-size:14px}
.scroll{overflow-x:auto;padding-bottom:6px}
table{border-collapse:collapse;table-layout:fixed}
th,td{border:1px solid var(--line);padding:0;text-align:center}
thead th{height:34px;font-size:13px;color:var(--mut);font-weight:600}
th.today{background:var(--ice);color:var(--ink)}
.hn{width:190px;text-align:left;padding:0 6px 0 10px;font-weight:500;font-size:14px;background:var(--panel);position:sticky;left:0;z-index:1}
.hn div{display:flex;align-items:center;justify-content:space-between;gap:6px}
.hn .t{overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.x{border:0;background:transparent;color:var(--mut);cursor:pointer;font-size:16px;padding:4px 6px;border-radius:6px}
.x:hover{color:#c0392b;background:var(--chip)}
td.c{width:42px;height:42px}
td.c button{width:100%;height:100%;border:0;background:transparent;cursor:pointer;font-size:18px;font-weight:700;color:transparent;transition:background .15s}
td.c button:hover{background:var(--chip)}
td.c button.on{background:var(--acc);color:#fff}
td.c.today{background:color-mix(in srgb,var(--ice) 45%,transparent)}
.add{display:flex;gap:8px;margin-top:14px;flex-wrap:wrap}
.add input{flex:1;min-width:180px;background:var(--bg);border:1px solid var(--line);border-radius:8px;padding:9px 12px}
.btn{background:var(--ink);color:var(--bg);border:0;border-radius:8px;padding:9px 16px;cursor:pointer;font-weight:600}
.btn.ghost{background:transparent;color:var(--mut);border:1px solid var(--line)}
.empty{padding:22px;text-align:center;color:var(--mut)}
.sl{position:relative;display:inline-block}
.sl svg{position:absolute;left:0;top:0;pointer-events:none}
.sl th.hl{width:72px;font-size:12px;color:var(--mut);font-weight:600}
.sl td.s{width:42px;height:40px;cursor:pointer;padding:0}
.sl td.s:hover{background:var(--chip)}
.sl td.s span{display:block;width:14px;height:14px;border-radius:50%;background:var(--dot);margin:auto}
.notes{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:14px}
.notes label{display:block;font:600 16px Fraunces,Georgia,serif;margin-bottom:6px}
.notes textarea{width:100%;min-height:140px;resize:vertical;background:var(--bg);border:1px solid var(--line);border-radius:8px;padding:10px 12px;line-height:1.5}
.foot{display:flex;justify-content:space-between;flex-wrap:wrap;gap:10px;color:var(--mut);font-size:13px;margin-top:6px}
@media (prefers-reduced-motion:reduce){*{transition:none!important}}
@media (max-width:560px){.hn{width:130px}.who input{width:110px}.wrap{padding:12px 12px 40px}}
</style>
</head>
<body>
<div class="wrap">
<header>
  <div>
    <h1>Winter Arc Tracker</h1>
    <p class="sub">Pick your habits, check them off daily, and watch the month fill in.</p>
  </div>
  <div class="who">
    <input id="name" placeholder="Your name" aria-label="Your name">
    <div class="mon"><button id="prev" aria-label="Previous month">‹</button><strong id="mlabel"></strong><button id="next" aria-label="Next month">›</button></div>
  </div>
</header>

<div class="stats" id="stats"></div>

<section>
  <h2>Habits</h2>
  <p class="hint">Click a day to mark a habit done. Today is highlighted.</p>
  <div class="scroll" id="habits"></div>
  <form class="add" id="addf" onsubmit="return false">
    <input id="newh" placeholder="Add a habit, e.g. Wake up at 6 AM" maxlength="60" aria-label="New habit">
    <button class="btn" id="addb" type="button">Add habit</button>
  </form>
</section>

<section>
  <h2>Sleep</h2>
  <p class="hint">Click the row that matches your hours for each day. Click again to clear it.</p>
  <div class="scroll"><div class="sl" id="sleep"></div></div>
</section>

<section>
  <div class="notes">
    <div><label for="target">This month’s target</label><textarea id="target" placeholder="What does a win look like by month end?"></textarea></div>
    <div><label for="wins">My wins this month</label><textarea id="wins" placeholder="Log what went well."></textarea></div>
    <div><label for="areas">Areas to work on</label><textarea id="areas" placeholder="What needs more attention?"></textarea></div>
  </div>
</section>

<div class="foot"><span>Saved in this browser only.</span><button class="btn ghost" id="reset">Clear this month</button></div>
</div>

<script>
var $=function(s){return document.querySelector(s)};
var S=null;
try{S=JSON.parse(localStorage.getItem("winterarc")||"null")}catch(e){}
S=S||{name:"",habits:[],months:{}};
function save(){try{localStorage.setItem("winterarc",JSON.stringify(S))}catch(e){}}
var now=new Date(), cur=new Date(now.getFullYear(),now.getMonth(),1);
var MN=["January","February","March","April","May","June","July","August","September","October","November","December"];
function key(){return cur.getFullYear()+"-"+(cur.getMonth()+1)}
function M(){var k=key();if(!S.months[k])S.months[k]={checks:{},sleep:{},target:"",wins:"",areas:""};return S.months[k]}
function dim(){return new Date(cur.getFullYear(),cur.getMonth()+1,0).getDate()}
function todayD(){return(now.getFullYear()==cur.getFullYear()&&now.getMonth()==cur.getMonth())?now.getDate():0}
function elapsed(){var t=cur.getFullYear()*12+cur.getMonth(),n=now.getFullYear()*12+now.getMonth();return t<n?dim():t==n?now.getDate():0}
function esc(s){return String(s).replace(/[&<>"]/g,function(c){return{"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;"}[c]})}

function render(){
  var m=M(),n=dim(),td=todayD(),el=elapsed(),H=S.habits;
  $("#name").value=S.name;
  $("#mlabel").textContent=MN[cur.getMonth()]+" "+cur.getFullYear();
  ["target","wins","areas"].forEach(function(f){var e=$("#"+f);if(document.activeElement!==e)e.value=m[f]||""});

  // stats
  var done=0,possible=H.length*el,best=0,run=0,perfect=0;
  for(var d=1;d<=el;d++){
    var all=H.length>0,c=0;
    H.forEach(function(h){if((m.checks[h.id]||[]).indexOf(d)>-1){c++}else all=false});
    done+=c;
    if(all){run++;perfect++;if(run>best)best=run}else run=0;
  }
  var pct=possible?Math.round(done/possible*100):0;
  var sv=Object.keys(m.sleep).map(function(k){return m.sleep[k]});
  var avg=sv.length?(sv.reduce(function(a,b){return a+b},0)/sv.length).toFixed(1):"–";
  $("#stats").innerHTML=
   '<div class="stat"><b>'+pct+'%</b><span>Habits completed so far</span><div class="bar"><i style="width:'+pct+'%"></i></div></div>'+
   '<div class="stat"><b>'+best+(best==1?" day":" days")+'</b><span>Longest streak with every habit done</span></div>'+
   '<div class="stat"><b>'+perfect+'</b><span>Perfect days</span></div>'+
   '<div class="stat"><b>'+avg+(sv.length?" hrs":"")+'</b><span>Average sleep ('+sv.length+' logged)</span></div>';

  // habits grid
  if(!H.length){$("#habits").innerHTML='<div class="empty">No habits yet. Add your first one below to start your arc.</div>'}
  else{
    var h='<table><thead><tr><th class="hn">Habit</th>';
    for(var d=1;d<=n;d++)h+='<th'+(d==td?' class="today"':'')+'>'+d+'</th>';
    h+='</tr></thead><tbody>';
    H.forEach(function(hb){
      var ch=m.checks[hb.id]||[];
      h+='<tr><td class="hn"><div><span class="t" title="'+esc(hb.t)+'">'+esc(hb.t)+'</span><button class="x" data-del="'+hb.id+'" aria-label="Remove '+esc(hb.t)+'">×</button></div></td>';
      for(var d=1;d<=n;d++){
        var on=ch.indexOf(d)>-1;
        h+='<td class="c'+(d==td?' today':'')+'"><button data-h="'+hb.id+'" data-d="'+d+'" class="'+(on?'on':'')+'" aria-pressed="'+on+'" aria-label="'+esc(hb.t)+', day '+d+'">✓</button></td>';
      }
      h+='</tr>';
    });
    $("#habits").innerHTML=h+'</tbody></table>';
  }

  // sleep grid
  var s='<table><thead><tr><th class="hl"></th>';
  for(var d=1;d<=n;d++)s+='<th'+(d==td?' class="today"':'')+'>'+d+'</th>';
  s+='</tr></thead><tbody>';
  for(var hr=10;hr>=4;hr--){
    s+='<tr><th class="hl">'+hr+' hrs</th>';
    for(var d=1;d<=n;d++)s+='<td class="s" data-sh="'+hr+'" data-sd="'+d+'">'+(m.sleep[d]==hr?'<span></span>':'')+'</td>';
    s+='</tr>';
  }
  s+='</tbody></table>';
  s+='<svg id="sv"></svg>';
  $("#sleep").innerHTML=s;
  drawLine();
}
function drawLine(){
  var box=$("#sleep"),sv=$("#sv"),o=box.getBoundingClientRect(),n=dim(),m=M(),pts=[];
  for(var d=1;d<=n;d++){if(!m.sleep[d])continue;var c=box.querySelector('td[data-sh="'+m.sleep[d]+'"][data-sd="'+d+'"]');if(!c)continue;var r=c.getBoundingClientRect();pts.push((r.left-o.left+r.width/2).toFixed(1)+","+(r.top-o.top+r.height/2).toFixed(1))}
  sv.setAttribute("width",o.width);sv.setAttribute("height",o.height);
  sv.innerHTML='<polyline fill="none" stroke="var(--acc)" stroke-width="2" points="'+pts.join(" ")+'"/>';
}
window.addEventListener("resize",drawLine);
if(document.fonts&&document.fonts.ready)document.fonts.ready.then(drawLine);

document.addEventListener("click",function(e){
  var t=e.target.closest("[data-h],[data-del],[data-sh]");if(!t)return;
  var m=M();
  if(t.dataset.h){
    var id=t.dataset.h,d=+t.dataset.d,a=m.checks[id]||(m.checks[id]=[]),i=a.indexOf(d);
    if(i>-1)a.splice(i,1);else a.push(d);
  }else if(t.dataset.del){
    var id2=t.dataset.del;
    if(!confirm("Remove this habit and its history?"))return;
    S.habits=S.habits.filter(function(h){return h.id!=id2});
    for(var k in S.months)delete S.months[k].checks[id2];
  }else{
    var d2=+t.dataset.sd,h2=+t.dataset.sh;
    if(m.sleep[d2]==h2)delete m.sleep[d2];else m.sleep[d2]=h2;
  }
  save();render();
});
function addHabit(){
  var v=$("#newh").value.trim();if(!v)return;
  S.habits.push({id:"h"+Date.now(),t:v});$("#newh").value="";save();render();
}
$("#addb").onclick=addHabit;
$("#newh").addEventListener("keydown",function(e){if(e.key==="Enter"){e.preventDefault();addHabit()}});
$("#name").addEventListener("input",function(e){S.name=e.target.value;save()});
["target","wins","areas"].forEach(function(f){$("#"+f).addEventListener("input",function(e){M()[f]=e.target.value;save()})});
$("#prev").onclick=function(){cur=new Date(cur.getFullYear(),cur.getMonth()-1,1);render()};
$("#next").onclick=function(){cur=new Date(cur.getFullYear(),cur.getMonth()+1,1);render()};
$("#reset").onclick=function(){if(confirm("Clear all check-ins, sleep and notes for this month?")){delete S.months[key()];save();render()}};
render();
</script>
</body>
</html>
