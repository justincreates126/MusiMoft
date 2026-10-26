<!DOCTYPE html>
<html lang="en"><head><meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<meta name="theme-color" content="#121212">
<title>MusiMoft</title>
<style>
:root{color-scheme:dark;--bg:#121212;--pan:#1a1a1a;--pan2:#2a2a2a;--tx:#fff;--mu:#b3b3b3;--g:#1ed760;--cur:"Snell Roundhand","Apple Chancery","Segoe Script","Brush Script MT","Lucida Handwriting",cursive}
*{box-sizing:border-box;margin:0;-webkit-tap-highlight-color:transparent}
[hidden]{display:none!important}
html,body{height:100%}
body{background:var(--bg);color:var(--tx);font:16px/1.3 "Helvetica Neue",Helvetica,Arial,sans-serif}
svg{width:24px;height:24px;fill:none;stroke:currentColor;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;flex:none;display:block}
svg.f{fill:currentColor;stroke:none}
main{height:100%;overflow:auto;padding:calc(env(safe-area-inset-top,0px) + 14px) 16px 200px}
.hd{font-family:var(--cur);font-weight:700}
h1.hd{font-size:36px;color:var(--g);line-height:1.1}
h2.hd{font-size:28px;color:#fff;margin:26px 0 12px}
button{font:inherit;color:inherit}
.top{display:flex;align-items:center;gap:12px;margin-bottom:14px}
.me{width:38px;height:38px;border-radius:50%;background:#f472b6;color:#000;font-weight:800;display:flex;align-items:center;justify-content:center;font-size:18px;flex:none}
.chips{display:flex;gap:8px;overflow-x:auto;scrollbar-width:none}
.chip{border:0;border-radius:99px;padding:8px 16px;background:var(--pan2);color:#fff;font-size:14px;font-weight:600;white-space:nowrap}
.chip.on{background:var(--g);color:#000}
.ib{border:0;background:none;color:#fff;padding:6px}
.sb{display:flex;align-items:center;gap:14px;background:#fff;color:#000;border-radius:8px;padding:0 14px;height:48px}
.sb input{flex:1;border:0;outline:0;background:none;font:inherit;font-weight:700;color:#000;min-width:0}
.sb input::placeholder{color:#111}
input.t{width:100%;padding:12px;border-radius:8px;border:0;background:var(--pan2);color:#fff;font:inherit}
.grid{display:grid;grid-template-columns:1fr 1fr;gap:8px}
.tile{display:flex;align-items:center;gap:10px;background:var(--pan2);border-radius:4px;overflow:hidden;height:56px;font-weight:700;font-size:14px;cursor:pointer}
.tile .cv,.tile .mos{width:56px;height:56px;flex:none;border-radius:0}
.tile span{padding-right:6px;overflow:hidden;display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical}
.cv{background:var(--pan2) center/cover;display:flex;align-items:center;justify-content:center;color:#fff9;font-size:22px;border-radius:4px}
.mos{display:grid;grid-template-columns:1fr 1fr;border-radius:4px;overflow:hidden;background:var(--pan2)}
.mos i{background:center/cover}
.hs{display:flex;gap:14px;overflow-x:auto;scrollbar-width:none;margin:0 -16px;padding:0 16px}
.card{width:150px;flex:none;cursor:pointer}
.card .cv,.card .mos{width:150px;height:150px}
.card .t{margin-top:8px;font-weight:700}
.row{display:flex;align-items:center;gap:12px;padding:7px 0}
.row .cv,.row .mos{width:52px;height:52px;flex:none}
.row .m{flex:1;min-width:0;cursor:pointer}
.t{white-space:nowrap;overflow:hidden;text-overflow:ellipsis;font-weight:600}
.a{color:var(--mu);font-size:14px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.row.cur .t{color:var(--g)}
.tag{font-size:10px;padding:1px 5px;border-radius:3px;background:var(--pan2);color:var(--mu);margin-right:6px;font-weight:700;vertical-align:1px}
.tag.f{color:var(--g)}
.empty{color:var(--mu);padding:26px 6px;text-align:center}
.bt{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-top:6px}
.bc{position:relative;height:100px;border-radius:6px;overflow:hidden;padding:12px;font-weight:700;font-size:18px;cursor:pointer;border:0;text-align:left;color:#fff}
.bc:after{content:"♪";position:absolute;right:-8px;bottom:-6px;width:58px;height:58px;background:#0003;transform:rotate(25deg);border-radius:4px;display:flex;align-items:center;justify-content:center;font-size:26px;color:#fff8}
.hero{margin:-14px -16px 8px;padding:calc(env(safe-area-inset-top,0px) + 12px) 16px 14px}
.hero .cv,.hero .mos{width:190px;height:190px;margin:8px auto 14px;box-shadow:0 8px 30px #0008;font-size:60px}
.bar{display:flex;align-items:center;gap:18px;margin:8px 0}
.pbig{width:56px;height:56px;border-radius:50%;border:0;background:var(--g);color:#000;margin-left:auto;display:flex;align-items:center;justify-content:center}
.pbig svg{width:28px;height:28px}
#mini{position:fixed;left:8px;right:8px;bottom:calc(66px + env(safe-area-inset-bottom,0px));border-radius:8px;overflow:hidden;z-index:3;background:#2b4a14}
#mini .mi{display:flex;align-items:center;gap:10px;padding:8px 8px 6px;cursor:pointer}
#mini .cv{width:48px;height:48px;flex:none}
#mini .m{flex:1;min-width:0}
#mini .mp{height:2px;background:#fff4;margin:0 8px 4px;border-radius:2px}
#mini .mp i{display:block;height:100%;width:0;background:#fff;border-radius:2px}
#mini svg{width:28px;height:28px}
#nav{position:fixed;left:0;right:0;bottom:0;display:flex;background:linear-gradient(#12121200,#121212e6 28%,#121212);padding:14px 0 calc(8px + env(safe-area-inset-bottom,0px));z-index:2}
#nav button{flex:1;border:0;background:none;color:var(--mu);font-size:11px;font-weight:600;display:flex;flex-direction:column;align-items:center;gap:4px}
#nav button.on{color:#fff}
#nav .on svg{stroke-width:3}
#nav .on svg.fi{fill:currentColor}
#full{position:fixed;inset:0;background:linear-gradient(#1c5a30,#121212 72%);z-index:6;padding:calc(env(safe-area-inset-top,0px) + 12px) 24px calc(22px + env(safe-area-inset-bottom,0px));display:flex;flex-direction:column}
#full .fh{display:flex;justify-content:space-between;align-items:center;font-size:13px;font-weight:700}
#fart{width:100%;aspect-ratio:1;max-height:42vh;margin:auto;border-radius:8px;box-shadow:0 10px 40px #0009;font-size:90px}
#ft{font-size:22px;font-weight:800;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
#pr{width:100%;accent-color:#fff;margin-top:14px}
.tm{display:flex;justify-content:space-between;color:var(--mu);font-size:12px}
.ct{display:flex;justify-content:space-between;align-items:center;margin-top:8px}
.ct button{border:0;background:none;color:#fff;padding:8px}
.ct button.on{color:var(--g)}
.ct svg{width:28px;height:28px}
#fpp{background:#fff;color:#000;border-radius:50%;width:66px;height:66px;display:flex;align-items:center;justify-content:center}
#fpp svg{width:30px;height:30px}
.sheet{position:fixed;inset:0;background:#000b;display:flex;align-items:flex-end;z-index:8}
.sheet>div{background:var(--pan2);width:100%;max-height:70%;overflow:auto;border-radius:14px 14px 0 0;padding:16px 16px calc(16px + env(safe-area-inset-bottom,0px))}
.sheet button.it{display:block;width:100%;text-align:left;padding:14px 4px;border:0;border-bottom:1px solid #fff1;background:none;color:#fff;font:inherit}
#toast{position:fixed;left:50%;bottom:160px;transform:translateX(-50%);background:#fff;color:#000;font-weight:600;padding:10px 16px;border-radius:8px;opacity:0;transition:opacity .2s;pointer-events:none;z-index:9;max-width:90%;text-align:center}
#toast.on{opacity:1}
</style></head><body>
<main id="main"></main>
<div id="mini" hidden></div>
<nav id="nav"></nav>
<div id="full" hidden></div>
<div id="toast"></div>
<script>
const $=s=>document.querySelector(s);
const esc=s=>String(s??'').replace(/[&<>"]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]));
const I={
home:'<path d="M4 10.5 12 3l8 7.5V21h-5.5v-6h-5v6H4z"/>',
search:'<circle cx="11" cy="11" r="7"/><path d="M16.5 16.5 21 21"/>',
lib:'<path d="M4 4v16M9 4v16M14.5 5l4.5 15"/>',
star:'<path d="M12 3l2.7 5.6 6.1.9-4.4 4.3 1 6.1L12 17l-5.4 2.9 1-6.1L3.2 9.5l6.1-.9z"/>',
plus:'<path d="M12 4v16M4 12h16"/>',
heart:'<path d="M12 20s-8-5-8-11a4.5 4.5 0 0 1 8-2.5A4.5 4.5 0 0 1 20 9c0 6-8 11-8 11z"/>',
play:'<path d="M7 4v16l13-8z"/>',
pause:'<path d="M6 4h4v16H6zM14 4h4v16h-4z"/>',
prev:'<path d="M6 5v14M20 5v14L9 12z"/>',
next:'<path d="M18 5v14M4 5v14l11-7z"/>',
shuf:'<path d="M3 17h3c5 0 7-10 12-10h3M18 4l3 3-3 3M3 7h3c2 0 3.5 1.6 4.5 3.5M13.5 13.5C14.5 15.4 16 17 18 17h3M18 14l3 3-3 3"/>',
rep:'<path d="M4 11V9a3 3 0 0 1 3-3h13M17 3l3 3-3 3M20 13v2a3 3 0 0 1-3 3H4M7 21l-3-3 3-3"/>',
down:'<path d="M5 9l7 7 7-7"/>',
back:'<path d="M15 5l-7 7 7 7"/>',
trash:'<path d="M5 7h14M10 7V4h4v3M7 7l1 13h8l1-13"/>',
x:'<path d="M6 6l12 12M18 6 6 18"/>'};
const ic=(n,c='')=>`<svg viewBox="0 0 24 24" class="${c}">${I[n]}</svg>`;
const likeIc=l=>l?'<svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10" fill="#1ed760" stroke="none"/><path d="M7.5 12.5l3 3 6-6.5" stroke="#000" stroke-width="2.4"/></svg>':'<svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><path d="M12 7.5v9M7.5 12h9"/></svg>';
let S={pl:[],jk:'',recent:[],liked:[]};
try{S=Object.assign(S,JSON.parse(localStorage.getItem('mm')||'{}'))}catch(e){}
const save=()=>{try{localStorage.setItem('mm',JSON.stringify(S))}catch(e){}};
const au=new Audio();
let queue=[],qi=-1,shuf=false,rep=0,view='home',openPl=null,results=[],lastQ='',miss=0,flt='all';
const uid=()=>Math.random().toString(36).slice(2,9);
const fmt=x=>isFinite(x)?Math.floor(x/60)+':'+String(Math.floor(x%60)).padStart(2,'0'):'0:00';
const hue=s=>{let h=0;for(const c of String(s))h=(h*31+c.charCodeAt(0))%360;return h};
const cg=p=>p.id==='liked'?'background:linear-gradient(135deg,#4b2be0,#a8b8f0)':`background:linear-gradient(135deg,hsl(${hue(p.id)} 55% 38%),hsl(${(hue(p.id)+50)%360} 50% 22%))`;
const bgi=t=>t.art?`background-image:url('${esc(t.art)}')`:'';
const isLiked=t=>S.liked.some(x=>x.id===t.id);
const getPl=id=>id==='liked'?{id:'liked',name:'Liked Songs',tracks:S.liked}:S.pl.find(x=>x.id===id);
function coverHTML(p){
  if(p.id==='liked')return `<div class="cv" style="${cg(p)}">${ic('heart','f')}</div>`;
  const a=p.tracks.filter(t=>t.art).slice(0,4);
  if(a.length>=4)return `<div class="mos">${a.map(t=>`<i style="${bgi(t)}"></i>`).join('')}</div>`;
  return `<div class="cv" style="${a[0]?bgi(a[0]):cg(p)}">${a[0]?'':'♪'}</div>`;
}
function toast(m){const t=$('#toast');t.textContent=m;t.classList.add('on');clearTimeout(toast.h);toast.h=setTimeout(()=>t.classList.remove('on'),2600)}

/* ---------- sources ---------- */
const gj=async(u,ms=7000)=>{const c=new AbortController();const t=setTimeout(()=>c.abort(),ms);try{const r=await fetch(u,{signal:c.signal});if(!r.ok)throw new Error(r.status);return await r.json()}finally{clearTimeout(t)}};
const AH=['https://discoveryprovider.audius.co','https://discoveryprovider2.audius.co','https://discoveryprovider3.audius.co'];
async function sAudius(q){
  let hosts=AH.slice();
  if(aHost.h)hosts.unshift(aHost.h);
  for(const h of hosts){
    try{
      const j=await gj(`${h}/v1/tracks/search?query=${encodeURIComponent(q)}&limit=15&app_name=MusiMoft`,5000);
      aHost.h=h;
      return(j.data||[]).map(t=>({id:'a'+t.id,title:t.title,artist:t.user.name,art:t.artwork&&t.artwork['150x150'],src:`${h}/v1/tracks/${t.id}/stream?app_name=MusiMoft`,full:1}));
    }catch(e){}
  }
  throw new Error('audius');
}
const aHost={};
async function sJam(q){
  if(!S.jk)return[];
  const j=await gj(`https://api.jamendo.com/v3.0/tracks/?client_id=${encodeURIComponent(S.jk)}&format=json&limit=15&audioformat=mp32&search=${encodeURIComponent(q)}`);
  return(j.results||[]).map(t=>({id:'j'+t.id,title:t.name,artist:t.artist_name,art:t.image,src:t.audio,full:1}));
}
async function sItunes(q){
  const j=await gj(`https://itunes.apple.com/search?term=${encodeURIComponent(q)}&media=music&entity=song&limit=15`);
  return(j.results||[]).filter(t=>t.previewUrl).map(t=>({id:'i'+t.trackId,title:t.trackName,artist:t.artistName,art:t.artworkUrl100,src:t.previewUrl,full:0}));
}
async function searchAll(q,onPart){
  const names=['Audius','Jamendo','Apple previews'];
  const out=[];let fails=[];
  await Promise.all([sAudius,sJam,sItunes].map((f,i)=>f(q).then(r=>{out.push(...r);onPart(out.slice())}).catch(()=>fails.push(names[i]))));
  return{out,fails};
}
async function resolve(t){
  const q=(t.title+' '+t.artist).trim();
  for(const f of [sAudius,sJam,sItunes]){
    try{const r=await f(q);if(r.length){Object.assign(t,{src:r[0].src,art:r[0].art,full:r[0].full});save();return}}catch(e){}
  }
}

/* ---------- shell ---------- */
$('#nav').innerHTML=[['home','Home','home','fi'],['search','Search','search',''],['lib','Your Library','lib',''],['prem','Premium','star','fi'],['create','Create','plus','']].map(a=>`<button data-v="${a[0]}">${ic(a[2],a[3])}${a[1]}</button>`).join('');
$('#mini').innerHTML=`<div class="mi"><div class="cv" id="mart"></div><div class="m"><div class="t" id="mt"></div><div class="a" id="ma" style="color:#fffb"></div></div><button class="ib" id="mlk" aria-label="Like"></button><button class="ib" id="mpp" aria-label="Play or pause"></button></div><div class="mp"><i id="mpb"></i></div>`;
$('#full').innerHTML=`<div class="fh"><button class="ib" id="fx" aria-label="Close">${ic('down')}</button><span>Now playing</span><span style="width:36px"></span></div><div class="cv" id="fart"></div>
<div><div style="display:flex;align-items:center;gap:12px"><div style="flex:1;min-width:0"><div id="ft"></div><div class="a" id="fa" style="font-size:16px"></div></div><button class="ib" id="flk" aria-label="Like"></button></div>
<input type="range" id="pr" min="0" max="100" value="0" step="0.1" aria-label="Seek"><div class="tm"><span id="tc">0:00</span><span id="td">0:00</span></div>
<div class="ct"><button id="sh" aria-label="Shuffle">${ic('shuf')}</button><button id="pv" aria-label="Previous">${ic('prev','f')}</button><button id="fpp" aria-label="Play or pause"></button><button id="nx" aria-label="Next">${ic('next','f')}</button><button id="rp" aria-label="Repeat">${ic('rep')}</button></div></div>`;
const setPP=p=>$('#mpp').innerHTML=$('#fpp').innerHTML=ic(p?'pause':'play','f');
setPP(false);

/* ---------- player ---------- */
function setArt(id,u){$(id).style.backgroundImage=u?`url("${u}")`:'';$(id).textContent=u?'':'♪'}
function updLike(){const t=queue[qi];const l=t&&isLiked(t);$('#mlk').innerHTML=likeIc(l);$('#flk').innerHTML=likeIc(l)}
function toggleLike(){
  const t=queue[qi];if(!t)return;
  if(isLiked(t))S.liked=S.liked.filter(x=>x.id!==t.id);else S.liked.unshift({...t});
  save();updLike();toast(isLiked(t)?'Added to Liked Songs':'Removed from Liked Songs');
}
$('#mlk').onclick=toggleLike;$('#flk').onclick=toggleLike;
async function load(){
  const t=queue[qi];if(!t)return;
  show(t);
  if(!t.src){$('#ma').textContent=$('#fa').textContent='Finding a match…';await resolve(t)}
  if(!t.src){toast('No match for “'+t.title+'”');if(++miss<queue.length)return next(true);miss=0;return}
  miss=0;
  au.src=t.src;
  try{await au.play()}catch(e){}
  S.recent=[{...t},...S.recent.filter(x=>x.id!==t.id)].slice(0,12);save();
  show(t);
  if(view==='home')render();
}
function show(t){
  $('#mini').hidden=false;
  $('#mini').style.background=`hsl(${hue(t.id)} 45% 20%)`;
  $('#mt').textContent=$('#ft').textContent=t.title;
  $('#ma').textContent=$('#fa').textContent=t.artist+(t.src&&!t.full?' · 30s preview':'');
  setArt('#mart',t.art);setArt('#fart',t.art);updLike();
  if('mediaSession' in navigator)navigator.mediaSession.metadata=new MediaMetadata({title:t.title,artist:t.artist,artwork:t.art?[{src:t.art}]:[]});
}
function play(list,i){queue=list.slice();qi=i;miss=0;load()}
function next(auto){
  if(!queue.length)return;
  if(rep===2&&auto===true&&au.src){au.currentTime=0;au.play();return}
  if(shuf)qi=Math.floor(Math.random()*queue.length);
  else if(++qi>=queue.length){if(rep||auto!==true)qi=0;else{qi=queue.length-1;return}}
  load();
}
function prev(){if(au.currentTime>3){au.currentTime=0;return}qi=Math.max(0,qi-1);load()}
const tog=()=>{if(!au.src)return;au.paused?au.play():au.pause()};
$('#mpp').onclick=tog;$('#fpp').onclick=tog;
$('#nx').onclick=()=>next();$('#pv').onclick=prev;
$('#sh').onclick=()=>{shuf=!shuf;$('#sh').classList.toggle('on',shuf);if(openPl)render()};
$('#rp').onclick=()=>{rep=(rep+1)%3;$('#rp').classList.toggle('on',rep>0);$('#rp').innerHTML=ic('rep')+(rep===2?'<b style="position:absolute;font-size:10px;margin:-6px 0 0 -4px">1</b>':'')};
au.onplay=()=>setPP(true);
au.onpause=()=>setPP(false);
au.onended=()=>next(true);
au.onerror=()=>{if(au.src){toast('That track won’t play. Skipping.');if(++miss<queue.length)next(true)}};
au.ontimeupdate=()=>{const p=au.duration?au.currentTime/au.duration*100:0;$('#pr').value=p;$('#mpb').style.width=p+'%';$('#tc').textContent=fmt(au.currentTime);$('#td').textContent=fmt(au.duration)};
$('#pr').oninput=e=>{if(au.duration)au.currentTime=e.target.value/100*au.duration};
$('#mini').onclick=e=>{if(!e.target.closest('button'))$('#full').hidden=false};
$('#fx').onclick=()=>$('#full').hidden=true;
if('mediaSession' in navigator){
  navigator.mediaSession.setActionHandler('nexttrack',()=>next());
  navigator.mediaSession.setActionHandler('previoustrack',prev);
}

/* ---------- UI ---------- */
const lst=c=>c==='r'?results:c==='h'?S.recent:c==='l'?S.liked:(getPl(openPl)||{tracks:[]}).tracks;
function rowHTML(t,i,ctx,extra){
  const cur=queue[qi]&&queue[qi].id===t.id?' cur':'';
  const tag=t.src?`<span class="tag ${t.full?'f':''}">${t.full?'FULL':'30S'}</span>`:'';
  return `<div class="row${cur}"><div class="cv" style="${bgi(t)}">${t.art?'':'♪'}</div><div class="m" data-p="${ctx}:${i}"><div class="t">${esc(t.title)}</div><div class="a">${tag}${esc(t.artist)}</div></div>${extra}</div>`;
}
const addBtn=(c,i)=>`<button class="ib" style="color:var(--mu)" data-a="${c}:${i}" aria-label="Add to playlist">${ic('plus')}</button>`;
const plRow=p=>`<div class="row" data-o="${p.id}"><div style="display:contents">${coverHTML(p)}</div><div class="m"><div class="t">${esc(p.name)}</div><div class="a">Playlist · ${p.tracks.length} songs</div></div></div>`;
const topbar=(t)=>`<div class="top"><div class="me">J</div>${t}</div>`;
const chips=()=>`<div class="chips">${[['all','All'],['pl','Playlists'],['rc','Recent']].map(a=>`<button class="chip ${flt===a[0]?'on':''}" data-f="${a[0]}">${a[1]}</button>`).join('')}</div>`;
const allPl=()=>[{id:'liked',name:'Liked Songs',tracks:S.liked},...S.pl];
const GEN=[['Hip-Hop','#8d67ab'],['Pop','#e8115b'],['Israeli','#1e3264'],['Persian','#148a08'],['Rock','#e13300'],['Chill','#477d95'],['Workout','#dc148c'],['Party','#8c1932']];
async function doSearch(q){
  lastQ=q;results=[];render();
  if(!q)return;
  $('#res').innerHTML='<div class="empty">Searching…</div>';
  const {out,fails}=await searchAll(q,p=>{if(q===lastQ&&view==='search'){results=p;$('#res').innerHTML=p.map((t,i)=>rowHTML(t,i,'r',addBtn('r',i))).join('')}});
  if(q!==lastQ)return;results=out;
  if(!out.length&&view==='search'){$('#res').innerHTML=`<div class="empty">No results. ${fails.length?'Couldn’t reach: '+fails.join(', ')+'. If you opened this inside another app’s preview, open the file in Safari or Chrome instead.':'Try another spelling.'}</div>`}
  else if(fails.length)toast('Some sources didn’t respond: '+fails.join(', '));
}
function render(){
  document.querySelectorAll('#nav button').forEach(b=>b.classList.toggle('on',b.dataset.v===view));
  const m=$('#main');
  if(view==='home'){
    const h=new Date().getHours();
    const showPl=flt!=='rc',showRc=flt!=='pl';
    m.innerHTML=topbar(chips())+
    (showPl?`<div class="grid">${allPl().slice(0,8).map(p=>`<div class="tile" data-o="${p.id}">${coverHTML(p)}<span>${esc(p.name)}</span></div>`).join('')}</div>
    ${S.pl.length?`<h2 class="hd">Your playlists</h2><div class="hs">${S.pl.map(p=>`<div class="card" data-o="${p.id}">${coverHTML(p)}<div class="t">${esc(p.name)}</div><div class="a">${p.tracks.length} songs</div></div>`).join('')}</div>`:''}`:'')+
    (showRc?`<h2 class="hd">Jump back in</h2>${S.recent.length?`<div class="hs">${S.recent.map((t,i)=>`<div class="card" data-p="h:${i}"><div class="cv" style="${bgi(t)}">${t.art?'':'♪'}</div><div class="t">${esc(t.title)}</div><div class="a">${esc(t.artist)}</div></div>`).join('')}</div>`:'<div class="empty">Songs you play show up here.<br>Tap Search to find something.</div>'}`:'');
  }else if(view==='search'){
    m.innerHTML=topbar('<h1 class="hd">Search</h1>')+`<form id="sf" class="sb">${ic('search')}<input id="q" type="search" placeholder="What do you want to listen to?" value="${esc(lastQ)}"></form>
    ${lastQ?`<div id="res" style="margin-top:12px">${results.map((t,i)=>rowHTML(t,i,'r',addBtn('r',i))).join('')}</div>`:`<h2 class="hd" style="margin-top:22px">Browse all</h2><div class="bt">${GEN.map(g=>`<button class="bc" style="background:${g[1]}" data-g="${g[0]}">${g[0]}</button>`).join('')}</div>`}`;
    $('#sf').onsubmit=e=>{e.preventDefault();$('#q').blur();doSearch($('#q').value.trim())};
    $('#q').oninput=e=>{if(!e.target.value&&lastQ){lastQ='';results=[];render();$('#q').focus()}};
  }else if(view==='prem'){
    m.innerHTML=topbar('<h1 class="hd">Premium</h1>')+`<div style="background:linear-gradient(135deg,#1ed760,#0b5a2a);color:#000;border-radius:10px;padding:20px"><div class="hd" style="font-size:30px">MusiMoft Premium</div><p style="font-weight:700;margin-top:8px">Free, always.</p></div>
    <div class="row" style="margin-top:14px"><div class="m"><div class="t">No ads</div><div class="a">Nothing interrupts your music.</div></div></div>
    <div class="row"><div class="m"><div class="t">Unlimited skips</div><div class="a">Skip as much as you want.</div></div></div>
    <div class="row"><div class="m"><div class="t">Full songs from Audius and Jamendo</div><div class="a">Plus 30-second previews of almost anything.</div></div></div>
    <h2 class="hd">Jamendo (optional)</h2><p class="a" style="margin-bottom:8px;white-space:normal">Paste a free client ID from developer.jamendo.com to include Jamendo music.</p>
    <input class="t" type="password" id="jk" placeholder="Jamendo client ID" value="${esc(S.jk)}">`;
    $('#jk').onchange=e=>{S.jk=e.target.value.trim();save();toast('Saved')};
  }else if(view==='lib'&&openPl){
    const p=getPl(openPl);
    if(!p){openPl=null;return render()}
    m.innerHTML=`<div class="hero" style="${cg(p).replace('135deg','180deg').replace(/(\d+)% 22%\)/,'$1% 12%)')}"><button class="ib" id="bk" style="float:left" aria-label="Back">${ic('back')}</button><div style="clear:both;display:contents">${coverHTML(p)}</div><h1 class="hd" style="color:#fff;font-size:34px">${esc(p.name)}</h1><div class="a">${p.tracks.length} songs</div></div>
    <div class="bar"><button class="ib" id="ps" style="color:${shuf?'var(--g)':'#fff'}" aria-label="Shuffle">${ic('shuf')}</button>${p.id==='liked'?'':`<button class="ib" style="color:var(--mu)" id="pd" aria-label="Delete playlist">${ic('trash')}</button>`}<button class="pbig" id="pa" aria-label="Play">${ic('play','f')}</button></div>
    ${p.tracks.length?p.tracks.map((t,i)=>rowHTML(t,i,'p',`<button class="ib" style="color:var(--mu)" data-x="${i}" aria-label="Remove">${ic('x')}</button>`)).join(''):'<div class="empty">Nothing here yet.<br>Add songs from Search with the plus button.</div>'}`;
    $('#bk').onclick=()=>{openPl=null;render()};
    $('#pa').onclick=()=>{if(p.tracks.length)play(p.tracks,shuf?Math.floor(Math.random()*p.tracks.length):0)};
    $('#ps').onclick=()=>{shuf=!shuf;$('#sh').classList.toggle('on',shuf);render()};
    if($('#pd'))$('#pd').onclick=()=>{if(confirm('Delete “'+p.name+'”?')){S.pl=S.pl.filter(x=>x!==p);save();openPl=null;render()}};
  }else{
    m.innerHTML=topbar('<h1 class="hd">Your Library</h1><button class="ib" id="np" style="margin-left:auto" aria-label="New playlist">'+ic('plus')+'</button>')+
    `<div class="chips" style="margin-bottom:10px"><button class="chip" id="im">Import Spotify CSV</button></div>
    ${allPl().map(plRow).join('')}
    <input type="file" id="fi" accept=".csv,text/csv" multiple hidden>
    <p class="a" style="margin-top:18px;white-space:normal">To bring in Spotify playlists, export each one as CSV at exportify.net, then tap Import Spotify CSV. MusiMoft keeps the name and order and finds each song when it plays. Some songs may only play as 30s previews.</p>`;
    $('#np').onclick=newPl;
    $('#im').onclick=()=>$('#fi').click();
    $('#fi').onchange=async e=>{for(const f of e.target.files)importCSV(f.name.replace(/\.csv$/i,''),await f.text());render()};
  }
}
function newPl(){const n=prompt('Playlist name');if(n&&n.trim()){S.pl.push({id:uid(),name:n.trim(),tracks:[]});save();view='lib';openPl=null;render()}}
$('#main').onclick=e=>{
  const f=e.target.closest('[data-f]');if(f){flt=f.dataset.f;return render()}
  const g=e.target.closest('[data-g]');if(g)return doSearch(g.dataset.g);
  const o=e.target.closest('[data-o]');if(o){view='lib';openPl=o.dataset.o;return render()}
  const p=e.target.closest('[data-p]');
  if(p){const[c,i]=p.dataset.p.split(':');return play(lst(c),+i)}
  const a=e.target.closest('[data-a]');
  if(a){const[c,i]=a.dataset.a.split(':');return addTo(lst(c)[+i])}
  const x=e.target.closest('button[data-x]');
  if(x){getPl(openPl).tracks.splice(+x.dataset.x,1);save();render()}
};
document.querySelectorAll('#nav button').forEach(b=>b.onclick=()=>{
  if(b.dataset.v==='create')return createSheet();
  view=b.dataset.v;openPl=null;render();
});
function createSheet(){
  const s=document.createElement('div');s.className='sheet';
  s.innerHTML='<div><button class="it" data-c="n">New playlist</button><button class="it" data-c="i">Import Spotify CSV</button></div>';
  s.onclick=e=>{const b=e.target.closest('button');if(!b){if(e.target===s)s.remove();return}s.remove();if(b.dataset.c==='n')newPl();else{view='lib';openPl=null;render();$('#fi').click()}};
  document.body.appendChild(s);
}
function addTo(t){
  const s=document.createElement('div');s.className='sheet';
  s.innerHTML=`<div><b>Add to playlist</b>${S.pl.map(p=>`<button class="it" data-id="${p.id}">${esc(p.name)}</button>`).join('')}<button class="it" data-id="new" style="color:var(--g)">New playlist</button></div>`;
  s.onclick=e=>{
    const b=e.target.closest('button');
    if(!b){if(e.target===s)s.remove();return}
    let p;
    if(b.dataset.id==='new'){const n=prompt('Playlist name');if(!n||!n.trim())return;p={id:uid(),name:n.trim(),tracks:[]};S.pl.push(p)}
    else p=S.pl.find(x=>x.id===b.dataset.id);
    p.tracks.push({...t});save();s.remove();toast('Added to '+p.name);
  };
  document.body.appendChild(s);
}

/* ---------- Spotify CSV import ---------- */
function parseCSV(s){
  const rows=[];let r=[],f='',q=false;
  for(let i=0;i<s.length;i++){
    const c=s[i];
    if(q){if(c==='"'){if(s[i+1]==='"'){f+='"';i++}else q=false}else f+=c}
    else if(c==='"')q=true;
    else if(c===','){r.push(f);f=''}
    else if(c==='\n'||c==='\r'){if(c==='\r'&&s[i+1]==='\n')i++;r.push(f);f='';if(r.length>1||r[0])rows.push(r);r=[]}
    else f+=c;
  }
  if(f||r.length){r.push(f);rows.push(r)}
  return rows;
}
function importCSV(name,text){
  const rows=parseCSV(text.replace(/^\uFEFF/,''));
  if(rows.length<2)return toast('That file looks empty');
  const h=rows[0].map(x=>x.toLowerCase());
  const ti=h.findIndex(x=>x.includes('track name')),ai=h.findIndex(x=>x.includes('artist'));
  if(ti<0)return toast('Use a CSV exported from Exportify');
  const tracks=rows.slice(1).filter(r=>r[ti]).map(r=>({id:uid(),title:r[ti],artist:(ai>=0?r[ai]:'').split(/[;,]/)[0].trim()}));
  S.pl.push({id:uid(),name,tracks});save();toast('Imported '+tracks.length+' songs into “'+name+'”');
}
render();
</script></body></html>
