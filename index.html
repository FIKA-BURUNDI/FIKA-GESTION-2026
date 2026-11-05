
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>FIKA Gestion V2</title>
<style>
:root {
  --navy:#10243a; --blue:#1769aa; --teal:#078b82;
  --gold:#e6a23c; --bg:#f2f6fa; --red:#c0392b;
  --text:#203447; --line:#dce5ed;
}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--text);font:16px Arial,sans-serif}
header{background:linear-gradient(120deg,var(--navy),var(--blue));color:white;padding:24px}
header h1{margin:0;font-size:30px}
header p{margin:7px 0 0}
nav{display:flex;flex-wrap:wrap;gap:8px;background:white;padding:12px;position:sticky;top:0;z-index:5;border-bottom:1px solid var(--line)}
nav button{border:0;border-radius:8px;padding:12px 15px;background:#eaf1f7;color:var(--navy);font-weight:bold;cursor:pointer}
nav button.active{background:var(--blue);color:white}
main{max-width:1250px;margin:24px auto;padding:0 15px}
.page{display:none}.page.active{display:block}
h2{color:var(--navy);font-size:26px}
h3{color:var(--navy)}
.card{background:white;padding:20px;border:1px solid var(--line);border-radius:13px;margin-bottom:17px;box-shadow:0 2px 8px #10243a0b}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(190px,1fr));gap:14px}
.metric{font-size:25px;font-weight:bold;color:var(--blue);margin-top:8px}
.muted{font-size:14px;color:#65788a}
label{display:block;font-weight:bold;margin:10px 0 5px}
input,select{width:100%;padding:11px;border:1px solid #cbd8e3;border-radius:8px;font-size:16px}
input[type=file]{padding:8px}
.formgrid{display:grid;grid-template-columns:repeat(auto-fit,minmax(190px,1fr));gap:10px}
button.primary{background:var(--blue);color:white;border:0;padding:12px 18px;border-radius:8px;font-weight:bold;cursor:pointer;margin-top:13px}
button.secondary{background:white;border:1px solid var(--line);padding:9px 12px;border-radius:8px;cursor:pointer}
button.danger{background:var(--red);color:white;border:0;padding:8px 10px;border-radius:7px;cursor:pointer}
.tablewrap{overflow-x:auto}
table{width:100%;border-collapse:collapse;min-width:620px}
th,td{text-align:left;padding:11px;border-bottom:1px solid var(--line)}
th{background:#edf3f8;color:var(--navy)}
.avatar{width:90px;height:90px;border-radius:50%;object-fit:cover;background:#e7edf3}
.profile{display:flex;align-items:center;gap:18px;flex-wrap:wrap}
.notice{padding:13px;background:#fff5df;border-left:4px solid var(--gold);border-radius:6px;margin:14px 0}
.tag{display:inline-block;background:#e7f4f1;color:#08756e;border-radius:20px;padding:4px 9px;font-size:13px}
.actions{display:flex;gap:7px;flex-wrap:wrap}
@media(max-width:600px){header h1{font-size:24px}nav button{flex:1 1 40%}h2{font-size:22px}}
@media print{nav,button,form,.no-print{display:none!important}body{background:white}.page{display:none!important}#reports{display:block!important}}
</style>
</head>
<body>

<header>
  <h1>FIKA Gestion</h1>
  <p>Gestion des membres – Cotisations – Crédits – Remboursements – Réunions – Rapports</p>
</header>

<nav id="navigation">
  <button class="active" data-page="dashboard">Tableau de bord</button>
  <button data-page="members">Membres</button>
  <button data-page="contributions">Cotisations</button>
  <button data-page="credits">Crédits</button>
  <button data-page="repayments">Remboursements</button>
  <button data-page="meetings">Réunions</button>
  <button data-page="reports">Rapports</button>
</nav>

<main>

<section id="dashboard" class="page active">
  <h2>Tableau de bord</h2>
  <div class="grid" id="dashboardCards"></div>
  <div class="card">
    <h3>Règles de fonctionnement FIKA</h3>
    <p>Activité : lundi à samedi. Dimanche : repos.</p>
    <p>Cotisation manquée : amende de 5 000 FBu.</p>
    <p>Crédit : intérêt simple de 5 % par mois. Un mois = 26 jours ouvrables. Durée maximale : 3 mois.</p>
    <p>Remboursement manqué : amende de 10 % de l'échéance quotidienne, ajoutée au solde du crédit.</p>
    <p>Arrondissement quotidien par excès au multiple de 500 FBu.</p>
    <p>Réunion mensuelle : premier jour du mois, ou le 2 si le premier est dimanche. Retard : 5 000 FBu. Absence : 50 000 FBu.</p>
  </div>
  <div class="notice">
    Attention : cette version stocke les données dans le navigateur de cet appareil. Elle ne synchronise pas encore les comptes des dirigeants.
    N'enregistrez pas de véritables cartes d'identité ou passeports avant la mise en place d'un stockage sécurisé.
  </div>
</section>

<section id="members" class="page">
  <h2>Gestion des membres</h2>
  <div class="card">
    <h3>Ajouter un membre</h3>
    <form id="memberForm">
      <input type="hidden" id="memberId">
      <div class="formgrid">
        <div><label>Nom complet</label><input id="memberName" required></div>
        <div><label>Téléphone</label><input id="memberPhone"></div>
        <div><label>Adresse</label><input id="memberAddress"></div>
        <div><label>Photo du membre</label><input type="file" id="memberPhoto" accept="image/*"></div>
        <div><label>Référence carte d'identité / passeport</label><input id="memberDocument" placeholder="Référence uniquement"></div>
      </div>
      <button class="primary">Enregistrer le membre</button>
      <button type="button" class="secondary" onclick="clearMemberForm()">Annuler</button>
    </form>
  </div>
  <div class="card">
    <h3>Liste des membres</h3>
    <div class="tablewrap"><table>
      <thead><tr><th>Nom</th><th>Téléphone</th><th>Cotisations</th><th>Solde crédit</th><th>Actions</th></tr></thead>
      <tbody id="membersTable"></tbody>
    </table></div>
  </div>
  <div id="memberProfile"></div>
</section>

<section id="contributions" class="page">
  <h2>Cotisations</h2>
  <div class="card">
    <h3>Enregistrer une cotisation</h3>
    <form id="contributionForm">
      <div class="formgrid">
        <div><label>Membre</label><select id="contributionMember" required></select></div>
        <div><label>Date</label><input type="date" id="contributionDate" required></div>
        <div><label>Montant versé (FBu)</label><input type="number" id="contributionAmount" min="0" required></div>
        <div><label>Amende (FBu)</label><input type="number" id="contributionFine" min="0" value="0"></div>
      </div>
      <button class="primary">Enregistrer</button>
    </form>
  </div>
  <div class="card">
    <h3>Suivi des cotisations</h3>
    <div class="formgrid">
      <div><label>Mois</label><input type="month" id="contributionMonth"></div>
      <div><label>Jusqu'au jour</label><input type="date" id="contributionUntil"></div>
    </div>
    <p id="contributionTotals"></p>
    <div class="tablewrap"><table>
      <thead><tr><th>Date</th><th>Membre</th><th>Montant</th><th>Amende</th></tr></thead>
      <tbody id="contributionTable"></tbody>
    </table></div>
  </div>
</section>

<section id="credits" class="page">
  <h2>Gestion des crédits</h2>
  <div class="card">
    <h3>Accorder un crédit</h3>
    <form id="creditForm">
      <div class="formgrid">
        <div><label>Membre</label><select id="creditMember" required></select></div>
        <div><label>Date du crédit</label><input type="date" id="creditDate" required></div>
        <div><label>Capital (FBu)</label><input type="number" id="creditPrincipal" min="1" required></div>
        <div><label>Durée</label>
          <select id="creditMonths">
            <option value="1">1 mois – 26 jours</option>
            <option value="2">2 mois – 52 jours</option>
            <option value="3">3 mois – 78 jours</option>
          </select>
        </div>
      </div>
      <button class="primary">Créer le crédit</button>
    </form>
  </div>
  <div class="card">
    <h3>Liste des crédits</h3>
    <div class="tablewrap"><table>
      <thead><tr><th>Membre</th><th>Capital</th><th>Intérêt</th><th>Échéance quotidienne</th><th>Durée</th><th>Solde</th></tr></thead>
      <tbody id="creditsTable"></tbody>
    </table></div>
  </div>
</section>

<section id="repayments" class="page">
  <h2>Remboursements</h2>
  <div class="card">
    <h3>Enregistrer un remboursement</h3>
    <form id="repaymentForm">
      <div class="formgrid">
        <div><label>Crédit</label><select id="repaymentCredit" required></select></div>
        <div><label>Date du paiement</label><input type="date" id="repaymentDate" required></div>
        <div><label>Montant versé (FBu)</label><input type="number" id="repaymentAmount" min="1" required></div>
      </div>
      <button class="primary">Enregistrer le paiement</button>
    </form>
    <p class="muted">Les amendes des échéances quotidiennes manquées sont ajoutées au solde. Le paiement est ensuite déduit du solde total.</p>
  </div>
  <div class="card">
    <h3>Historique des remboursements</h3>
    <div class="tablewrap"><table>
      <thead><tr><th>Date</th><th>Membre</th><th>Montant versé</th><th>Amende ajoutée</th><th>Solde restant</th></tr></thead>
      <tbody id="repaymentsTable"></tbody>
    </table></div>
  </div>
</section>

<section id="meetings" class="page">
  <h2>Réunions mensuelles</h2>
  <div class="card">
    <h3>Enregistrer la présence</h3>
    <form id="meetingForm">
      <div class="formgrid">
        <div><label>Membre</label><select id="meetingMember" required></select></div>
        <div><label>Date de réunion</label><input type="date" id="meetingDate" required></div>
        <div><label>Statut</label>
          <select id="meetingStatus">
            <option value="present">Présent</option>
            <option value="late">En retard – 5 000 FBu</option>
            <option value="absent">Absent – 50 000 FBu</option>
          </select>
        </div>
      </div>
      <button class="primary">Enregistrer</button>
    </form>
  </div>
  <div class="card">
    <h3>Historique des réunions</h3>
    <div class="tablewrap"><table>
      <thead><tr><th>Date</th><th>Membre</th><th>Statut</th><th>Amende</th></tr></thead>
      <tbody id="meetingsTable"></tbody>
    </table></div>
  </div>
</section>

<section id="reports" class="page">
  <h2>Rapports</h2>
  <div class="card">
    <div class="formgrid">
      <div><label>Membre</label><select id="reportMember"><option value="all">Tous les membres</option></select></div>
      <div><label>Du</label><input type="date" id="reportFrom"></div>
      <div><label>Au</label><input type="date" id="reportTo"></div>
    </div>
    <button class="primary" onclick="renderReport()">Afficher le rapport</button>
    <button class="secondary" onclick="window.print()">Imprimer / PDF</button>
    <div id="reportOutput"></div>
  </div>
</section>
</main>

<script>
const STORAGE_KEY = "FIKA_GESTION_V2";
let db = JSON.parse(localStorage.getItem(STORAGE_KEY) ||
'{"members":[],"contributions":[],"credits":[],"repayments":[],"meetings":[]}');

const $ = id => document.getElementById(id);
const money = n => (Number(n)||0).toLocaleString("fr-FR") + " FBu";
const esc = s => String(s ?? "").replace(/[&<>"']/g, c => ({
  "&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"
}[c]));
const uid = () => Date.now().toString(36)+Math.random().toString(36).slice(2,8);
const member = id => db.members.find(m => m.id === id);
const credit = id => db.credits.find(c => c.id === id);

function save(){
  localStorage.setItem(STORAGE_KEY, JSON.stringify(db));
  renderAll();
}
function addDays(date, number){
  let d = new Date(date+"T12:00:00");
  d.setDate(d.getDate()+number);
  return d.toISOString().slice(0,10);
}
function workingDates(start, number){
  let result=[], date=start;
  while(result.length<number){
    let day=new Date(date+"T12:00:00").getDay();
    if(day!==0) result.push(date);
    date=addDays(date,1);
  }
  return result;
}
function roundUp500(amount){return Math.ceil(amount/500)*500;}
function balance(c){
  return Math.max(0,c.totalDue+(c.fines||0)-(c.paid||0));
}
function showPage(id){
  document.querySelectorAll(".page").forEach(p=>p.classList.toggle("active",p.id===id));
  document.querySelectorAll("nav button").forEach(b=>b.classList.toggle("active",b.dataset.page===id));
}
$("navigation").addEventListener("click",e=>{
  let b=e.target.closest("button[data-page]");
  if(b) showPage(b.dataset.page);
});

/* MEMBRES */
let photoData="";
$("memberPhoto").addEventListener("change",e=>{
  let file=e.target.files[0];
  if(!file)return;
  if(file.size>500000){alert("Photo trop volumineuse. Choisissez une photo de moins de 500 Ko.");return;}
  let reader=new FileReader();
  reader.onload=()=>photoData=reader.result;
  reader.readAsDataURL(file);
});
function clearMemberForm(){
  $("memberForm").reset();
  $("memberId").value="";
  photoData="";
}
$("memberForm").addEventListener("submit",e=>{
  e.preventDefault();
  let id=$("memberId").value || uid();
  let old=member(id);
  db.members=db.members.filter(m=>m.id!==id);
  db.members.push({
    id,
    name:$("memberName").value.trim(),
    phone:$("memberPhone").value.trim(),
    address:$("memberAddress").value.trim(),
    document:$("memberDocument").value.trim(),
    photo:photoData || old?.photo || ""
  });
  clearMemberForm();
  save();
});
function editMember(id){
  let m=member(id); if(!m)return;
  $("memberId").value=m.id;
  $("memberName").value=m.name;
  $("memberPhone").value=m.phone;
  $("memberAddress").value=m.address;
  $("memberDocument").value=m.document||"";
  photoData=m.photo||"";
  showPage("members");
}
function showProfile(id){
  let m=member(id);if(!m)return;
  let cs=db.contributions.filter(x=>x.memberId===id);
  let ls=db.credits.filter(x=>x.memberId===id);
  let rs=db.repayments.filter(x=>x.memberId===id);
  let totalCon=cs.reduce((s,x)=>s+x.amount,0);
  let totalCredit=ls.reduce((s,x)=>s+x.principal,0);
  let totalPaid=rs.reduce((s,x)=>s+x.amount,0);
  let totalBalance=ls.reduce((s,x)=>s+balance(x),0);
  $("memberProfile").innerHTML=`
    <div class="card">
      <div class="profile">
        <img class="avatar" src="${m.photo||""}" onerror="this.style.display='none'">
        <div><h3>${esc(m.name)}</h3><p>${esc(m.phone)} · ${esc(m.address)}</p>
        <span class="tag">Fiche individuelle</span></div>
      </div>
      <div class="grid">
        <div><p class="muted">Cotisations versées</p><div class="metric">${money(totalCon)}</div></div>
        <div><p class="muted">Crédits accordés</p><div class="metric">${money(totalCredit)}</div></div>
        <div><p class="muted">Remboursements effectués</p><div class="metric">${money(totalPaid)}</div></div>
        <div><p class="muted">Solde des crédits</p><div class="metric">${money(totalBalance)}</div></div>
      </div>
      <p>Document / référence : ${esc(m.document||"Non renseigné")}</p>
      <h3>Crédits du membre</h3>
      ${ls.map(c=>`<p>Crédit du ${c.date} – ${money(c.principal)} – ${c.months} mois – solde ${money(balance(c))}</p>`).join("")||"Aucun crédit"}
      <h3>Historique des cotisations</h3>
      ${cs.map(x=>`<p>${x.date} : ${money(x.amount)} – amende ${money(x.fine)}</p>`).join("")||"Aucune cotisation"}
      <h3>Historique des remboursements</h3>
      ${rs.map(x=>`<p>${x.date} : ${money(x.amount)} – amende ajoutée ${money(x.fine)}</p>`).join("")||"Aucun remboursement"}
    </div>`;
}

/* MENUS MEMBRES */
function fillMembers(selectId, all=false){
  let el=$(selectId), previous=el.value;
  el.innerHTML=(all?'<option value="all">Tous les membres</option>':'<option value="">Choisir un membre</option>')+
    db.members.map(m=>`<option value="${m.id}">${esc(m.name)}</option>`).join("");
  if([...el.options].some(o=>o.value===previous))el.value=previous;
}
function renderMembers(){
  $("membersTable").innerHTML=db.members.map(m=>{
    let con=db.contributions.filter(x=>x.memberId===m.id).reduce((s,x)=>s+x.amount,0);
    let bal=db.credits.filter(x=>x.memberId===m.id).reduce((s,x)=>s+balance(x),0);
    return `<tr><td>${esc(m.name)}</td><td>${esc(m.phone)}</td><td>${money(con)}</td><td>${money(bal)}</td>
    <td><div class="actions">
    <button class="secondary" onclick="showProfile('${m.id}')">Fiche</button>
    <button class="secondary" onclick="editMember('${m.id}')">Modifier</button>
    </div></td></tr>`;
  }).join("");
}

/* COTISATIONS */
$("contributionForm").addEventListener("submit",e=>{
  e.preventDefault();
  db.contributions.push({
    id:uid(),memberId:$("contributionMember").value,
    date:$("contributionDate").value,
    amount:+$("contributionAmount").value,
    fine:+$("contributionFine").value||0
  });
  save();e.target.reset();
});
function renderContributions(){
  let month=$("contributionMonth").value, until=$("contributionUntil").value;
  let rows=db.contributions.filter(x=>
    (!month||x.date.startsWith(month)) && (!until||x.date<=until)
  );
  $("contributionTable").innerHTML=rows.map(x=>`
    <tr><td>${x.date}</td><td>${esc(member(x.memberId)?.name||"")}</td>
    <td>${money(x.amount)}</td><td>${money(x.fine)}</td></tr>`).join("");
  $("contributionTotals").textContent=
    "Total cotisations : "+money(rows.reduce((s,x)=>s+x.amount,0))+
    " | Total amendes : "+money(rows.reduce((s,x)=>s+x.fine,0));
}
$("contributionMonth").addEventListener("change",renderContributions);
$("contributionUntil").addEventListener("change",renderContributions);

/* CREDITS */
$("creditForm").addEventListener("submit",e=>{
  e.preventDefault();
  let principal=+$("creditPrincipal").value;
  let months=+$("creditMonths").value;
  let days=26*months;
  let totalDue=Math.round(principal*(1+0.05*months));
  let daily=roundUp500(totalDue/days);
  let dates=workingDates($("creditDate").value,days);
  let schedule=dates.map((date,i)=>({
    date,
    amount:i===days-1?Math.max(0,totalDue-daily*(days-1)):daily,
    fineApplied:false,
    fine:0
  }));
  db.credits.push({
    id:uid(),memberId:$("creditMember").value,
    date:$("creditDate").value,principal,months,days,totalDue,daily,
    schedule,paid:0,fines:0
  });
  save();e.target.reset();
});
function renderCredits(){
  $("creditsTable").innerHTML=db.credits.map(c=>`
    <tr><td>${esc(member(c.memberId)?.name||"")}</td>
    <td>${money(c.principal)}</td><td>${money(c.totalDue-c.principal)}</td>
    <td>${money(c.daily)}</td><td>${c.months} mois / ${c.days} jours</td>
    <td>${money(balance(c))}</td></tr>`).join("");
  $("repaymentCredit").innerHTML='<option value="">Choisir un crédit</option>'+
    db.credits.filter(c=>balance(c)>0).map(c=>
      `<option value="${c.id}">${esc(member(c.memberId)?.name||"")} – solde ${money(balance(c))}</option>`
    ).join("");
}

/* REMBOURSEMENTS ET AMENDES */
$("repaymentForm").addEventListener("submit",e=>{
  e.preventDefault();
  let c=credit($("repaymentCredit").value);
  if(!c)return;
  let date=$("repaymentDate").value;
  let newFine=0;

  // Chaque échéance passée et non réglée reçoit une amende de 10 % une seule fois.
  c.schedule.forEach(item=>{
    if(item.date<date && !item.fineApplied){
      item.fine=Math.ceil(item.amount*0.10);
      item.fineApplied=true;
      c.fines+=item.fine;
      newFine+=item.fine;
    }
  });

  let amount=+$("repaymentAmount").value;
  c.paid+=amount;
  db.repayments.push({
    id:uid(),creditId:c.id,memberId:c.memberId,date,amount,
    fine:newFine,balance:balance(c)
  });
  save();e.target.reset();
});
function renderRepayments(){
  $("repaymentsTable").innerHTML=db.repayments.map(x=>`
    <tr><td>${x.date}</td><td>${esc(member(x.memberId)?.name||"")}</td>
    <td>${money(x.amount)}</td><td>${money(x.fine)}</td><td>${money(x.balance)}</td></tr>`
  ).join("");
}

/* REUNIONS */
$("meetingForm").addEventListener("submit",e=>{
  e.preventDefault();
  let status=$("meetingStatus").value;
  let fine=status==="late"?5000:status==="absent"?50000:0;
  db.meetings.push({
    id:uid(),memberId:$("meetingMember").value,
    date:$("meetingDate").value,status,fine
  });
  save();e.target.reset();
});
function renderMeetings(){
  $("meetingsTable").innerHTML=db.meetings.map(x=>`
    <tr><td>${x.date}</td><td>${esc(member(x.memberId)?.name||"")}</td>
    <td>${x.status==="late"?"En retard":x.status==="absent"?"Absent":"Présent"}</td>
    <td>${money(x.fine)}</td></tr>`).join("");
}

/* TABLEAU DE BORD */
function renderDashboard(){
  let con=db.contributions.reduce((s,x)=>s+x.amount,0);
  let credits=db.credits.reduce((s,x)=>s+x.principal,0);
  let rep=db.repayments.reduce((s,x)=>s+x.amount,0);
  let bal=db.credits.reduce((s,x)=>s+balance(x),0);
  let fines=db.contributions.reduce((s,x)=>s+x.fine,0)+
    db.credits.reduce((s,x)=>s+x.fines,0)+
    db.meetings.reduce((s,x)=>s+x.fine,0);
  let values=[
    ["Membres",db.members.length],
    ["Cotisations cumulées",money(con)],
    ["Crédits accordés",money(credits)],
    ["Remboursements",money(rep)],
    ["Solde des crédits",money(bal)],
    ["Amendes enregistrées",money(fines)]
  ];
  $("dashboardCards").innerHTML=values.map(x=>`
    <div class="card"><div class="muted">${x[0]}</div><div class="metric">${x[1]}</div></div>`
  ).join("");
}

/* RAPPORTS */
function renderReport(){
  let id=$("reportMember").value||"all";
  let from=$("reportFrom").value,to=$("reportTo").value;
  let filter=x=>(id==="all"||x.memberId===id)&&(!from||x.date>=from)&&(!to||x.date<=to);
  let cs=db.contributions.filter(filter);
  let rs=db.repayments.filter(filter);
  let ms=db.meetings.filter(filter);
  let ls=db.credits.filter(x=>(id==="all"||x.memberId===id)&&(!from||x.date>=from)&&(!to||x.date<=to));
  let totalCon=cs.reduce((s,x)=>s+x.amount,0);
  let totalConFine=cs.reduce((s,x)=>s+x.fine,0);
  let totalCredit=ls.reduce((s,x)=>s+x.principal,0);
  let totalRep=rs.reduce((s,x)=>s+x.amount,0);
  let meetingFine=ms.reduce((s,x)=>s+x.fine,0);
  let creditBalance=ls.reduce((s,x)=>s+balance(x),0);
  $("reportOutput").innerHTML=`
    <h3>Rapport : ${id==="all"?"Tous les membres":esc(member(id)?.name||"")}</h3>
    <div class="grid">
      <div><b>Cotisations</b><p>${money(totalCon)}</p></div>
      <div><b>Amendes cotisations</b><p>${money(totalConFine)}</p></div>
      <div><b>Crédits accordés</b><p>${money(totalCredit)}</p></div>
      <div><b>Remboursements</b><p>${money(totalRep)}</p></div>
      <div><b>Solde des crédits</b><p>${money(creditBalance)}</p></div>
      <div><b>Amendes réunions</b><p>${money(meetingFine)}</p></div>
    </div>`;
}

/* ACTUALISATION GENERALE */
function renderAll(){
  fillMembers("contributionMember");
  fillMembers("creditMember");
  fillMembers("meetingMember");
  fillMembers("reportMember",true);
  renderMembers();
  renderContributions();
  renderCredits();
  renderRepayments();
  renderMeetings();
  renderDashboard();
  renderReport();
}

/* DATES PAR DEFAUT */
let today=new Date().toISOString().slice(0,10);
["contributionDate","creditDate","repaymentDate","meetingDate"].forEach(id=>$(id).value=today);
$("contributionMonth").value=today.slice(0,7);
$("contributionUntil").value=today;

renderAll();
</script>
</body>
</html>
