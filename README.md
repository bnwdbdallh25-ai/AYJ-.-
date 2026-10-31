<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>AYJ – للبحوث والخدمات الطلابية</title>
<style>
:root{--navy:#0B1F3A;--navy2:#13305c;--gold:#C9A24B;--bg:#fff;--card:#f6f7fb;--text:#14213d;--mut:#5b6678;--bd:#e3e6ee;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media(prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#0a1424;--card:#111e35;--text:#eef1f7;--mut:#a7b1c4;--bd:#223250}}
*{box-sizing:border-box}html{scroll-padding-top:env(safe-area-inset-top,0px)}
body{margin:0;background:var(--bg);color:var(--text);font-family:Tahoma,"Segoe UI",Arial,sans-serif;line-height:1.7}
header{background:var(--navy);color:#fff;position:sticky;top:env(safe-area-inset-top,0px);z-index:5}
.bar{display:flex;align-items:center;gap:10px;padding:10px 14px;flex-wrap:wrap}
.logo{display:flex;align-items:center;gap:8px;color:#fff;text-decoration:none;font-weight:700}
.logo b{background:var(--gold);color:var(--navy);padding:4px 10px;border-radius:8px;letter-spacing:1px}
nav{display:flex;gap:4px;overflow-x:auto;flex:1;white-space:nowrap}
nav a{color:#dfe5f0;text-decoration:none;padding:6px 10px;border-radius:8px;font-size:14px}
nav a.on,nav a:hover{background:var(--navy2);color:var(--gold)}
.lang{background:none;border:1px solid var(--gold);color:var(--gold);border-radius:8px;padding:5px 10px;cursor:pointer}
main{max-width:980px;margin:0 auto;padding:18px 14px}
.hero{background:linear-gradient(135deg,var(--navy),var(--navy2));color:#fff;border-radius:18px;padding:34px 20px;text-align:center;border-bottom:4px solid var(--gold)}
.hero h1{margin:8px 0;font-size:26px}.hero p{color:#d6dcea;max-width:600px;margin:8px auto 18px}
.btn{display:inline-block;background:var(--gold);color:var(--navy);border:0;border-radius:10px;padding:11px 20px;font-weight:700;text-decoration:none;cursor:pointer;font-size:15px;margin:4px}
.btn.o{background:none;border:1px solid var(--gold);color:var(--gold)}
h2{color:var(--navy);border-inline-start:5px solid var(--gold);padding-inline-start:10px;margin:28px 0 12px}
@media(prefers-color-scheme:dark){:root:not([data-theme="light"]) h2{color:var(--gold)}}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:12px}
.card{background:var(--card);border:1px solid var(--bd);border-radius:14px;padding:14px}
.card h3{margin:0 0 6px;color:var(--text)}.price{color:var(--gold);font-weight:700}
.note{background:var(--card);border:1px dashed var(--gold);border-radius:12px;padding:12px;color:var(--mut)}
label{display:block;margin:10px 0 4px;font-weight:600}
input,select,textarea{width:100%;padding:10px;border:1px solid var(--bd);border-radius:10px;background:var(--bg);color:var(--text);font:inherit}
.ok{background:#e8f6ec;color:#14532d;border-radius:10px;padding:12px;margin-top:12px;word-break:break-all}
.err{background:#fdecec;color:#7f1d1d;border-radius:10px;padding:12px;margin-top:12px}
footer{background:var(--navy);color:#cfd7e6;margin-top:30px;padding:20px 14px;font-size:14px}
footer .in{max-width:980px;margin:auto;display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:12px}
footer a{color:var(--gold)}footer h4{color:#fff;margin:0 0 4px}
.row{display:flex;gap:8px;flex-wrap:wrap;align-items:center}
.ord{border-bottom:1px solid var(--bd);padding:10px 0}
bdi{unicode-bidi:isolate}
</style>
</head>
<body>
<header><div class="bar"><a class="logo" href="#home"><b>AYJ</b><span id="sub"></span></a><button class="lang" id="lg"></button><nav id="nav"></nav></div></header>
<main id="app"></main>
<footer><div class="in" id="ft"></div></footer>
<script>
const WA=[["966581934618","+966 58 193 4618"],["966571033246","+966 57 103 3246"],["201039368299","+20 01039368299"]],MAIL="ayj7481@gmail.com";
const T={ar:{sub:"للبحوث والخدمات الطلابية",lg:"English",home:"الرئيسية",about:"من نحن",services:"الخدمات والأسعار",order:"طلب خدمة",track:"متابعة الطلب",contact:"تواصل معنا",faq:"الأسئلة الشائعة",terms:"الشروط والأحكام",privacy:"سياسة الخصوصية",refund:"سياسة الاسترداد",admin:"الإدارة",
h1:"أهلاً بك في AYJ",intro:"منصة لخدمات الطلاب والباحثين: بحوث، مشاريع، مطويات، سير ذاتية، ودعم أكاديمي بجودة واحترافية ونزاهة أكاديمية.",cta:"اطلب خدمتك الآن",browse:"تصفح الخدمات",
why:"مميزات AYJ",whys:["جودة واحترافية في كل طلب","أسعار واضحة بالريال السعودي","التزام بالنزاهة الأكاديمية","متابعة طلبك برقم فريد"],steps:"خطوات طلب الخدمة",stp:["اختر الخدمة","املأ نموذج الطلب","احتفظ برقم الطلب","تابع حالة طلبك"],
rev:"آراء العملاء",revt:"لا توجد آراء منشورة بعد. سنعرض آراء عملائنا الحقيقية هنا عند توفرها.",direct:"تواصل مباشر",
aboutt:"AYJ للبحوث والخدمات الطلابية منصة تقدم خدمات تعليمية وأكاديمية للطلاب والباحثين: إعداد وتنسيق البحوث، المشاريع، المطويات، السير الذاتية، ودعم البحوث الجامعية مع الالتزام بالنزاهة الأكاديمية.",
price:"السعر",sar:"ريال سعودي",name:"الاسم",phone:"رقم الهاتف",email:"البريد الإلكتروني",svc:"نوع الخدمة",olang:"اللغة المطلوبة",det:"تفاصيل الطلب",notes:"ملاحظات",send:"إرسال الطلب",
saved:"تم حفظ طلبك بنجاح. رقم الطلب (احتفظ به):",needf:"يرجى تعبئة الاسم ورقم الهاتف وتفاصيل الطلب.",nodb:"الحفظ المباشر غير متاح في هذا العرض (يتطلب تسجيل الدخول). لم يُحفظ طلبك. يمكنك إرساله عبر واتساب أو البريد:",wa:"إرسال عبر واتساب",mail:"إرسال عبر البريد",
oid:"رقم الطلب",chk:"استعلام",st:{new:"طلب جديد",review:"قيد المراجعة",progress:"قيد التنفيذ",done:"مكتمل",cancel:"ملغي"},stl:"الحالة:",nof:"لا توجد حالة مسجلة؛ إن كان رقم الطلب صحيحاً فهو قيد الاستلام كطلب جديد.",
ksa:"السعودية",egy:"مصر",files:"رفع الملفات غير متاح حالياً؛ أرسل ملفاتك عبر واتساب أو البريد بعد الحصول على رقم الطلب.",
faqs:[["كيف أطلب خدمة؟","من صفحة «طلب خدمة» عبّأ النموذج وستحصل على رقم طلب."],["كيف أتابع طلبي؟","أدخل رقم الطلب في صفحة «متابعة الطلب»."],["ما العملة؟","جميع الأسعار بالريال السعودي (SAR)."]],
termsT:"تُقدَّم الخدمات للمساعدة والتنظيم والتنسيق مع الالتزام بالنزاهة الأكاديمية. يلتزم العميل بصحة بياناته. الأسعار المعروضة قابلة للتحديد النهائي حسب حجم الطلب.",
privT:"نجمع الاسم والهاتف والبريد وتفاصيل الطلب لتنفيذ الخدمة فقط، ولا نشاركها مع أطراف خارجية. لا يمكن للعملاء الاطلاع على طلبات غيرهم.",
refT:"يُنظر في طلبات الاسترداد حسب حالة التنفيذ؛ تواصل معنا بعد الحصول على رقم الطلب لمراجعة طلبك.",
adm:"لوحة الإدارة",admno:"هذه اللوحة لصاحب المشروع فقط (سجّل الدخول بحسابه في claude.ai).",save:"حفظ",inote:"ملاحظة داخلية",none:"لا توجد طلبات.",prices:"إدارة الخدمات والأسعار",load:"جارٍ التحميل…",done2:"تم الحفظ"},
en:{sub:"Research & Student Services",lg:"العربية",home:"Home",about:"About",services:"Services & Prices",order:"Order a Service",track:"Track Order",contact:"Contact",faq:"FAQ",terms:"Terms",privacy:"Privacy",refund:"Refunds",admin:"Admin",
h1:"Welcome to AYJ",intro:"A platform for students and researchers: research, projects, brochures, CVs and academic support with quality, professionalism and academic integrity.",cta:"Order your service now",browse:"Browse services",
why:"Why AYJ",whys:["Quality and professionalism in every order","Clear prices in Saudi Riyal","Committed to academic integrity","Track your order with a unique ID"],steps:"How to order",stp:["Choose a service","Fill in the order form","Keep your order ID","Track your order"],
rev:"Client reviews",revt:"No reviews published yet. Real client reviews will appear here when available.",direct:"Contact us directly",
aboutt:"AYJ Research & Student Services offers educational and academic services for students and researchers: research preparation and formatting, projects, brochures, CVs, and university research support, with academic integrity.",
price:"Price",sar:"SAR",name:"Name",phone:"Phone",email:"Email",svc:"Service",olang:"Requested language",det:"Order details",notes:"Notes",send:"Submit order",
saved:"Your order was saved. Order ID (keep it):",needf:"Please fill in name, phone and order details.",nodb:"Direct saving is unavailable in this view (sign-in required). Your order was NOT saved. You can send it via WhatsApp or email:",wa:"Send via WhatsApp",mail:"Send via email",
oid:"Order ID",chk:"Check",st:{new:"New order",review:"Under review",progress:"In progress",done:"Completed",cancel:"Cancelled"},stl:"Status:",nof:"No status recorded yet; if the ID is correct, it is awaiting processing as a new order.",
ksa:"Saudi Arabia",egy:"Egypt",files:"File upload is not available yet; send your files via WhatsApp or email after getting your order ID.",
faqs:[["How do I order?","Fill in the form on the Order page and you will get an order ID."],["How do I track my order?","Enter your order ID on the Track page."],["Which currency?","All prices are in Saudi Riyal (SAR)."]],
termsT:"Services provide assistance, organization and formatting, with academic integrity. Clients are responsible for accurate information. Listed prices are finalized by order size.",
privT:"We collect name, phone, email and order details only to deliver the service and never share them externally. Clients cannot see other clients’ orders.",
refT:"Refund requests are reviewed based on the order’s progress; contact us with your order ID.",
adm:"Admin panel",admno:"This panel is for the owner only (sign in with the owner account on claude.ai).",save:"Save",inote:"Internal note",none:"No orders.",prices:"Manage services & prices",load:"Loading…",done2:"Saved"}};
const SV=[{id:"research",ar:"البحوث",en:"Research",da:"إعداد وتنسيق البحوث والمساعدة في جمع المعلومات من المصادر الموثوقة.",de:"Research preparation, formatting and help gathering information from reliable sources.",p:"5 – 10"},
{id:"projects",ar:"المشاريع",en:"Projects",da:"المساعدة في إعداد المشاريع وتنظيمها وتنسيقها.",de:"Help preparing, organizing and formatting projects.",p:"10 – 15"},
{id:"brochures",ar:"المطويات",en:"Brochures",da:"تصميم مطويات تعليمية وإبداعية وجذابة.",de:"Educational, creative and attractive brochure design.",p:"10 – 20"},
{id:"cv",ar:"إعداد السير الذاتية",en:"CV Preparation",da:"تصميم سير ذاتية احترافية ومنظمة.",de:"Professional, well-organized CV design.",p:"10 – 15"},
{id:"univ",ar:"دعم البحوث الجامعية",en:"University Research Support",da:"المساعدة في البحث والتوثيق والتنسيق والمراجعة، مع الالتزام بالنزاهة الأكاديمية.",de:"Help with research, citation, formatting and review, with academic integrity.",p:""}];
let L="ar",svc=SV,draft={},db=null,isOwner=false,msg="";
try{L=localStorage.getItem("ayjL")||"ar"}catch(e){}
const t=k=>T[L][k],$=s=>document.querySelector(s),P=["home","about","services","order","track","contact","faq","terms","privacy","refund"];
const esc=s=>String(s??"").replace(/[&<>"]/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;"}[c]));
const pr=s=>s.p?`${s.p} ${t("sar")}`:(L=="ar"?"يحدد حسب حجم ومتطلبات الخدمة":"Set by scope and requirements");
const route=()=>(location.hash.slice(1)||"home");
function contact(){return `<div class="grid"><div class="card"><h3>${t("ksa")}</h3>${WA.slice(0,2).map(w=>`<div><a href="https://wa.me/${w[0]}" target="_blank" rel="noopener"><bdi dir="ltr">${w[1]}</bdi></a> · WhatsApp</div>`).join("")}</div><div class="card"><h3>${t("egy")}</h3><div><a href="https://wa.me/${WA[2][0]}" target="_blank" rel="noopener"><bdi dir="ltr">${WA[2][1]}</bdi></a> · WhatsApp</div></div><div class="card"><h3>${t("email")}</h3><a href="mailto:${MAIL}">${MAIL}</a></div></div>`}
function cards(){return `<div class="grid">${svc.map(s=>`<div class="card"><h3>${s[L]}</h3><p>${s[L=="ar"?"da":"de"]}</p><div class="price">${pr(s)}</div></div>`).join("")}</div>`}
function view(r){
 if(r=="home")return `<div class="hero"><b style="font-size:34px;color:var(--gold);letter-spacing:3px">AYJ</b><h1>${t("h1")}</h1><p>${t("intro")}</p><a class="btn" href="#order">${t("cta")}</a><a class="btn o" href="#services">${t("browse")}</a></div><h2>${t("services")}</h2>${cards()}<h2>${t("why")}</h2><div class="grid">${t("whys").map(x=>`<div class="card">✔ ${x}</div>`).join("")}</div><h2>${t("steps")}</h2><div class="grid">${t("stp").map((x,i)=>`<div class="card"><b class="price">${i+1}</b> ${x}</div>`).join("")}</div><h2>${t("rev")}</h2><div class="note">${t("revt")}</div><h2>${t("direct")}</h2>${contact()}`;
 if(r=="about")return `<h2>${t("about")}</h2><p>${t("aboutt")}</p>`;
 if(r=="services")return `<h2>${t("services")}</h2>${cards()}`;
 if(r=="contact")return `<h2>${t("contact")}</h2>${contact()}`;
 if(r=="faq")return `<h2>${t("faq")}</h2>${t("faqs").map(f=>`<div class="card" style="margin-bottom:8px"><b>${f[0]}</b><div>${f[1]}</div></div>`).join("")}`;
 if(r=="terms")return `<h2>${t("terms")}</h2><p>${t("termsT")}</p>`;
 if(r=="privacy")return `<h2>${t("privacy")}</h2><p>${t("privT")}</p>`;
 if(r=="refund")return `<h2>${t("refund")}</h2><p>${t("refT")}</p>`;
 if(r=="order")return `<h2>${t("order")}</h2><div class="card"><label>${t("name")}</label><input data-d="name" value="${esc(draft.name)}"><label>${t("phone")}</label><input data-d="phone" type="tel" value="${esc(draft.phone)}"><label>${t("email")}</label><input data-d="email" type="email" value="${esc(draft.email)}"><label>${t("svc")}</label><select data-d="svc">${svc.map(s=>`<option value="${s.id}" ${draft.svc==s.id?"selected":""}>${s[L]}</option>`).join("")}</select><label>${t("olang")}</label><select data-d="ol"><option value="ar" ${draft.ol=="ar"?"selected":""}>العربية</option><option value="en" ${draft.ol=="en"?"selected":""}>English</option></select><label>${t("det")}</label><textarea rows="4" data-d="det">${esc(draft.det)}</textarea><label>${t("notes")}</label><textarea rows="2" data-d="notes">${esc(draft.notes)}</textarea><p class="note">${t("files")}</p><button class="btn" id="go">${t("send")}</button><div id="res">${msg}</div></div>`;
 if(r=="track")return `<h2>${t("track")}</h2><div class="card"><label>${t("oid")}</label><input id="tid" dir="ltr"><button class="btn" id="tk">${t("chk")}</button><div id="tres"></div></div>`;
 if(r=="admin")return `<h2>${t("adm")}</h2><div id="adm" class="card">${t("load")}</div>`;
 return "";}
function render(){
 document.documentElement.lang=L;document.documentElement.dir=L=="ar"?"rtl":"ltr";document.title="AYJ – "+t("sub");
 const r=route();$("#sub").textContent=t("sub");$("#lg").textContent=t("lg");
 $("#nav").innerHTML=P.slice(0,6).concat(isOwner?["admin"]:[]).map(p=>`<a href="#${p}" class="${p==r?"on":""}">${t(p)}</a>`).join("");
 $("#app").innerHTML=view(r);
 $("#ft").innerHTML=`<div><h4>AYJ</h4>${t("sub")}</div><div><h4>${t("contact")}</h4>${WA.map(w=>`<div><a href="https://wa.me/${w[0]}" target="_blank" rel="noopener"><bdi dir="ltr">${w[1]}</bdi></a></div>`).join("")}<a href="mailto:${MAIL}">${MAIL}</a></div><div>${["faq","terms","privacy","refund"].map(p=>`<div><a href="#${p}">${t(p)}</a></div>`).join("")}</div>`;
 document.querySelectorAll("[data-d]").forEach(e=>e.oninput=e.onchange=()=>draft[e.dataset.d]=e.value);
 if(r=="order"){draft.svc=draft.svc||svc[0].id;draft.ol=draft.ol||L;$("#go").onclick=submit}
 if(r=="track")$("#tk").onclick=trackIt;
 if(r=="admin")adminView();
}
async function submit(){
 const d=draft,res=$("#res");
 if(!(d.name||"").trim()||!(d.phone||"").trim()||!(d.det||"").trim()||(d.email&&!/^\S+@\S+\.\S+$/.test(d.email)))return res.innerHTML=`<div class="err">${t("needf")}</div>`;
 const id="AYJ-"+Array.from(crypto.getRandomValues(new Uint8Array(6)),b=>b.toString(36).padStart(2,"0")).join("").toUpperCase().slice(0,10);
 const text=`AYJ – ${svc.find(s=>s.id==d.svc)[L]}\n${d.name} | ${d.phone}\n${d.det}`;
 if(db){try{await db.doc("orders/"+id).set({...d,created:new Date().toISOString(),status:"new"});draft={};res.innerHTML=`<div class="ok">${t("saved")} <b dir="ltr">${id}</b></div>`;return}catch(e){}}
 res.innerHTML=`<div class="err">${t("nodb")}<div class="row"><a class="btn" target="_blank" rel="noopener" href="https://wa.me/${WA[0][0]}?text=${encodeURIComponent(text)}">${t("wa")}</a><a class="btn o" href="mailto:${MAIL}?subject=AYJ&body=${encodeURIComponent(text)}">${t("mail")}</a></div></div>`;
}
async function trackIt(){
 const id=$("#tid").value.trim().toUpperCase(),o=$("#tres");if(!id)return;
 if(!db)return o.innerHTML=`<div class="err">${t("nodb")}</div>`;
 try{const s=await db.doc("track/"+id).get();o.innerHTML=s.exists?`<div class="ok">${t("stl")} <b>${t("st")[s.data().status]||""}</b></div>`:`<div class="note">${t("nof")}</div>`}catch(e){o.innerHTML=`<div class="err">${esc(e.message||e)}</div>`}
}
async function adminView(){
 const a=$("#adm");if(!isOwner||!db)return a.innerHTML=t("admno");
 try{
  const q=await db.collection("orders").get(),tr={};
  (await db.collection("track").get()).docs.forEach(x=>tr[x.id]=x.data());
  const pe=svc.map((s,i)=>`<div class="row"><b style="flex:1">${s[L]}</b><input data-p="${i}" value="${esc(s.p)}" style="width:110px" dir="ltr"></div>`).join("");
  a.innerHTML=`<h3>${t("prices")}</h3>${pe}<button class="btn" id="sp">${t("save")}</button><span id="pm"></span><h3>${t("order")}</h3>`+(q.empty?t("none"):q.docs.map(x=>{const d=x.data(),s=tr[x.id]||{};return `<div class="ord"><b dir="ltr">${x.id}</b> · ${esc(d.name)} · <bdi dir="ltr">${esc(d.phone)}</bdi> ${esc(d.email)}<div>${esc((svc.find(v=>v.id==d.svc)||{})[L])} · ${esc(d.ol)}</div><div>${esc(d.det)}</div><div>${esc(d.notes)}</div><div class="row"><select data-o="${x.id}">${Object.keys(t("st")).map(k=>`<option value="${k}" ${(s.status||d.status)==k?"selected":""}>${t("st")[k]}</option>`).join("")}</select><input data-n="${x.id}" placeholder="${t("inote")}" value="${esc(d.inote||"")}" style="flex:1"><button class="btn" data-s="${x.id}">${t("save")}</button></div></div>`}).join(""));
  $("#sp").onclick=async()=>{svc=svc.map((s,i)=>({...s,p:document.querySelector(`[data-p="${i}"]`).value.trim()}));await db.doc("site/services").set({list:svc});$("#pm").textContent=" "+t("done2")};
  a.querySelectorAll("[data-s]").forEach(b=>b.onclick=async()=>{const id=b.dataset.s,st=document.querySelector(`[data-o="${id}"]`).value;await db.doc("track/"+id).set({status:st});await db.doc("orders/"+id).update({status:st,inote:document.querySelector(`[data-n="${id}"]`).value});b.textContent="✓"});
 }catch(e){a.innerHTML=`<div class="err">${esc(e.message||e)}</div>`}
}
$("#lg").onclick=()=>{L=L=="ar"?"en":"ar";try{localStorage.setItem("ayjL",L)}catch(e){}render()};
addEventListener("hashchange",()=>{render();scrollTo(0,0)});
render();
(async()=>{try{
 const u=await claude.use("user");isOwner=u?await u.isOwner():false;
 db=await claude.use("db");
 if(db){try{const s=await db.doc("site/services").get();if(s.exists&&s.data().list)svc=s.data().list}catch(e){}}
 render();
}catch(e){}})();
</script>
</body>
</html>
