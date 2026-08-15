<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>XRP Airdrop & Yield Program</title>
<meta name="viewport" content="width=device-width,initial-scale=1">
<script src="https://cdn.jsdelivr.net/npm/xrpl@latest/build/xrpl-latest-min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@xumm/sdk@latest/dist/xumm-sdk.umd.min.js"></script>
<style>
:root{--bg:#0b0f1a;--fg:#e8eefc;--ac:#00d4aa;--card:#111827;--bd:#1f2a44}
*{box-sizing:border-box;margin:0;padding:0;font-family:system-ui,sans-serif}
body{background:var(--bg);color:var(--fg);min-height:100vh;display:flex;flex-direction:column}
header{padding:3rem 1rem;text-align:center;background:linear-gradient(180deg,var(--bg) 0%,var(--bg) 60%,var(--card) 100%)}
h1{font-size:clamp(2rem,5vw,3.5rem);margin-bottom:.5rem}
.sub{color:#8ab;max-width:600px;margin:0 auto 2rem}
main{flex:1;padding:2rem 1rem;max-width:960px;margin:0 auto;width:100%}
.grid{display:grid;gap:1.5rem;grid-template-columns:repeat(auto-fit,minmax(300px,1fr))}
.card{background:var(--card);border:1px solid var(--bd);border-radius:12px;padding:1.5rem}
.card h2{font-size:1.25rem;margin-bottom:1rem;color:var(--ac)}
label{display:block;margin:.5rem 0 .25rem;font-size:.9rem;color:#8ab}
input,select{width:100%;padding:.75rem;background:var(--bg);border:1px solid var(--bd);border-radius:8px;color:var(--fg)}
button{width:100%;padding:.85rem;background:var(--ac);color:var(--bg);border:none;border-radius:8px;font-weight:700;cursor:pointer;margin-top:1rem;transition:.2s}
button:hover{filter:brightness(1.1)}button:disabled{opacity:.5;cursor:not-allowed}
.wbtns{display:flex;gap:.75rem;flex-wrap:wrap;margin-top:1rem}
.wbtns button{flex:1;min-width:140px;background:var(--bd);color:var(--fg)}
.wbtns button:hover{background:#2a3a5c}
.status{margin-top:1rem;padding:1rem;background:var(--bg);border:1px solid var(--bd);border-radius:8px;min-height:3rem;white-space:pre-wrap;font-family:monospace;font-size:.85rem}
.tier{display:flex;justify-content:space-between;padding:.5rem 0;border-bottom:1px solid var(--bd)}
.tier:last-child{border:none}
footer{padding:2rem;text-align:center;color:#567;border-top:1px solid var(--bd);font-size:.85rem}
</style>
</head>
<body>
<header><h1>XRP Airdrop & Yield Program</h1><p class="sub">Claim your 2026 allocation + lock XRP for up to 18% APY. Limited slots — expires in 48h.</p></header>
<main>
<div class="grid">
<section class="card"><h2>🪂 Claim Your Airdrop</h2>
<label>XRP Address (r...)</label><input id="addr" placeholder="rExAmPlEaDdReSs..." maxlength="34">
<label>Destination Tag (if exchange)</label><input id="tag" type="number" placeholder="123456" min="0" max="4294967295">
<div class="wbtns"><button id="bx" onclick="signXumm()">Sign with Xumm</button><button id="bl" onclick="signLedger()" disabled>Sign with Ledger</button><button id="bc" onclick="signCrossmark()" disabled>Sign with Crossmark</button></div>
<button id="sub" disabled onclick="submitClaim()">Submit Claim</button>
<div id="st" class="status" aria-live="polite">Connect a wallet and sign the verification message to begin.</div></section>
<section class="card"><h2>📈 Yield Tiers (Lock & Earn)</h2>
<div class="tier"><span>🥉 Bronze — 30 days</span><span>6% APY</span></div>
<div class="tier"><span>🥈 Silver — 90 days</span><span>10% APY</span></div>
<div class="tier"><span>🥇 Gold — 180 days</span><span>14% APY</span></div>
<div class="tier"><span>💎 Diamond — 365 days</span><span>18% APY</span></div>
<p style="margin-top:1rem;font-size:.9rem;color:#8ab">Minimum lock: 500 XRP. Early withdrawal forfeits yield.</p>
<label>Your Referral Code</label><input id="ref" readonly value="XRP-"><button onclick="copyRef()">Copy Referral Link</button></section>
</div></main>
<footer>© 2026 XRP Airdrop & Yield • Not affiliated with Ripple Labs • Use at your own risk</footer>
<script>
/* ─── CONFIG ─── */
const API_CLAIM = '/api/claim';              // ← CHANGE LATER TO YOUR BACKEND URL
const XUMM_KEY  = 'YOUR_XUMM_API_KEY';       // ← GET FROM https://xumm.app/developer
const MOCK_MODE = API_CLAIM === '/api/claim';

/* ─── STATE ─── */
let blob=null, addr=null;

/* ─── UI HELPERS ─── */
const $=s=>document.querySelector(s), log=m=>$('#st').textContent=m, en=b=>$('#sub').disabled=!b;

/* ─── XUMM SIGN ─── */
async function signXumm(){
  if(!XUMM_KEY||XUMM_KEY==='YOUR_XUMM_API_KEY')return log('❌ Set XUMM_KEY in script config');
  log('Opening Xumm...');
  const sdk=new window.XummSdk(XUMM_KEY);
  const pl=await sdk.payload.createAndSubscribe({txjson:{TransactionType:'SignIn'},options:{submit:false,return_url:{app:location.href,web:location.href}}},e=>{
    if(e.data.signed){blob=e.data.signed.blob;addr=e.data.response.account;$('#addr').value=addr;log(`✅ Signed with Xumm\nAddress: ${addr}\nBlob: ${blob.length} chars`);en(true);}
  });
  location.href=pl.data.next.always;
}
function signLedger(){log('Ledger: implement WebHID flow with @ledgerhq/hw-transport-webhid');}
function signCrossmark(){log('Crossmark: implement window.xrpl.signTx flow');}

/* ─── SUBMIT ─── */
async function submitClaim(){
  if(!blob||!addr)return;
  log('Submitting...');
  try{
    if(MOCK_MODE){
      await new Promise(r=>setTimeout(r,800));
      log('🧪 MOCK MODE — claim queued locally (no backend).\nOpen DevTools → Network to see payload.');
      console.log('MOCK PAYLOAD:',{signedBlob:blob,address:addr,tag:Number($('#tag').value)||undefined});
      return;
    }
    const res=await fetch(API_CLAIM,{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify({signedBlob:blob,address:addr,tag:Number($('#tag').value)||undefined})});
    const d=await res.json();
    log(d.message||(d.ok?'Claim queued':'Error: '+d.error));
  }catch(e){log('Error: '+e.message);}
}

/* ─── REF ─── */
function copyRef(){const c='XRP-'+Math.random().toString(36).slice(2,10).toUpperCase();$('#ref').value=c;navigator.clipboard.writeText(location.origin+'?ref='+c);log('Referral copied: '+c);}

/* ─── INIT ─── */
(()=>{const p=new URLSearchParams(location.search);if(p.get('ref'))$('#ref').value=p.get('ref');})();
</script>
</body>
</html>
