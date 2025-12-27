<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>⚠️ SYSTEM LOCK ⚠️</title>
<style>
html,body{
  margin:0;height:100%;
  background:#000;color:#f00;
  font-family:monospace;overflow:hidden;
  display:flex;align-items:center;justify-content:center;text-align:center
}
.wrap{display:flex;align-items:center;justify-content:center;height:100%}
.box{max-width:92%;padding:20px;border:2px solid #f00}
.big{font-size:28px;font-weight:bold}
.btn{margin-top:14px;padding:10px 14px;border:1px solid #f00;color:#f00;background:#000}
.glitch{animation:flicker .15s infinite}
@keyframes flicker{0%{opacity:1}50%{opacity:.6}100%{opacity:1}}
@keyframes shake{
  0%{transform:translate(0,0)}
  25%{transform:translate(2px,-2px)}
  50%{transform:translate(-2px,2px)}
  75%{transform:translate(2px,2px)}
  100%{transform:translate(0,0)}
}
.shake{animation:shake .15s infinite}
#gui{
  position:fixed;top:0;left:0;width:100%;
  padding:10px;background:#000;border-bottom:2px solid red;
  text-align:center;z-index:9999;font-size:18px;font-weight:bold
}
.blink{animation:blink .5s infinite}
@keyframes blink{0%{opacity:1}50%{opacity:0}100%{opacity:1}}
</style>
</head>
<body>

<div id="gui"><span class="blink">⚠️ SYSTEM LOCKED ⚠️</span></div>

<div class="wrap">
  <div class="box">
    <div class="glitch big">⚠️ ANDA DI HACK BY TEAM Haxx0r ⚠️</div>
    <div class="glitch">😹 You idiot hahahahah 😹</div>
    <div class="glitch" style="margin-top:10px">DATA MU KU SITA</div>
    <button class="btn" id="fakeExit">KLIK INI BUAT KELUAR</button>
  </div>
</div>

<script>
// ===== AUTO FULLSCREEN (ILUSI) =====
let unlocked=false;
function fs(){document.documentElement.requestFullscreen?.().catch(()=>{});}
fs(); setTimeout(fs,800);

document.addEventListener("fullscreenchange",()=>{
  if(!document.fullscreenElement && !unlocked){
    setTimeout(fs,200);
  }
});
document.addEventListener("click", fs);
document.addEventListener("visibilitychange",()=>{
  if(document.hidden && !unlocked) location.reload();
});
window.onbeforeunload=()=>{ if(!unlocked) return "ANDA TIDAK BISA KELUAR"; };
history.pushState(null,'',location.href);
window.onpopstate=()=>{ if(!unlocked) history.pushState(null,'',location.href); };

// ===== TOMBOL KELUAR PALSU =====
document.getElementById('fakeExit').onclick=()=>{
  document.body.innerHTML=`
  <div class="wrap">
    <div class="box shake">
      <div class="glitch big">😹 GOBLOK 😹</div>
      <div class="glitch" style="margin-top:10px">
        MANA ADA NGEHACK KAYAK GITU 😹
      </div>
      <div class="glitch" style="margin-top:10px">
        ANDA BENERAN DI DALAM DUNIA KEGELAPAN<br>ANDA TIDAK BISA KELUAR
      </div>
      <div class="glitch" style="margin-top:10px">DATA MU KU SITA</div>
    </div>
  </div>`;
  history.pushState(null,'',location.href);
  setTimeout(()=>location.reload(),6000);
};
</script>

</body>
</html>
