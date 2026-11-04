
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>FIKA Gestion</title>
<style>
*{box-sizing:border-box}
body{margin:0;font-family:Arial,sans-serif;background:#f1f5f8;color:#193044}
header{background:#123b52;color:white;padding:22px}
h1{margin:0;font-size:28px}
header p{margin:6px 0 18px}
nav{display:flex;gap:8px;flex-wrap:wrap}
nav button{background:#ffffff20;color:white;border:1px solid #ffffff55}
button{padding:11px 16px;border:0;border-radius:8px;background:#087e78;color:white;font-weight:bold;cursor:pointer}
button:hover{opacity:.85}
nav button.active{background:white;color:#123b52}
select,input{padding:11px;border:1px solid #ccd8df;border-radius:7px;width:100%;margin-top:5px}
main{max-width:1150px;margin:25px auto;padding:0 15px}
h2{color:#123b52}
.page{display:none}
.page.active{display:block}
.cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(190px,1fr));gap:15px}
.card,.panel{background:white;padding:20px;border-radius:12px;margin-bottom:18px;box-shadow:0 2px 9px #0000000c}
.card strong{display:block;font-size:25px;color:#087e78;margin-top:8px}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(210px,1fr));gap:14px}
label{font-weight:bold;font-size:14px}
.actions{margin-top:15px}
table{width:100%;border-collapse:collapse}
th,td{padding:10px;border-bottom:1px solid #ddd;text-align:left}
.tablewrap{overflow-x:auto}
footer{text-align:center;padding:25px;color:#687987}
</style>
</head>
<body>

<header>
<h1>FIKA GESTION</h1>
<p id="subtitle">Plateforme de gestion de l'association FIKA</p>

<nav>
<button class="active" onclick="showPage('dashboard',this)" data-fr="Tableau de bord" data-rn="Incamake">Tableau de bord</button>
<button onclick="showPage('members',this)" data-fr="Membres" data-rn="Abanywanyi">Membres</button>
<button onclick="showPage('contributions',this)" data-fr="Cotisations" data-rn="Intererano">Cotisations</button>
<button onclick="showPage('credits',this)" data-fr="Crédits" data-rn="Imyenda">Crédits</button>
<button onclick="showPage('repayments',this)" data-fr="Remboursements" data-rn="Kwishura">Remboursements</button>
<button onclick="showPage('reports',this)" data-fr="Rapports" data-rn="Raporo">Rapports</button>
</nav>

<div style="max-width:180px;margin-top:15px">
<select id="language" onchange="changeLanguage()">
<option value="fr">Français</option>
<option value="rn">Kirundi</option>
</select>
</div>
</header>

<main>

<section id="dashboard" class="page active">
<h2>Tableau de bord</h2>
<div class="cards">
<div class="card">Membres<strong id="memberCount">0</strong></div>
<div class="card">Total cotisations<strong id="contributionTotal">0 FBu</strong></div>
<div class="card">Total crédits<strong id="creditTotal">0 FBu</strong></div>
<div class="card">Remboursements<strong id="repaymentTotal">0 FBu</strong></div>
</div>
<div class="panel">
<h3>Bienvenue dans FIKA Gestion</h3>
<p>Gestion des membres, cotisations, crédits et remboursements.</p>
<p><b>Règle de crédit :</b> 5% d'intérêt par mois, maximum 3 mois.</p>
</div>
</section>

<section id="members" class="page">
<h2>Membres</h2>
<div class="panel">
<h3>Ajouter un membre</h3>
<div class="grid">
<label>Nom complet<input id="memberName" placeholder="Nom du membre"></label>
<label>Téléphone<input id="memberPhone" placeholder="+257..."></label>
</div>
<div class="actions"><button onclick="addMember()">Enregistrer le membre</button></div>
</div>
<div class="panel">
<h3>Liste des membres</h3>
<div class="tablewrap"><table>
<thead><tr><th>Nom</th><th>Téléphone</th></tr></thead>
<tbody id="membersTable"></tbody>
</table></div>
</div>
</section>

<section id="contributions" class="page">
<h2>Cotisations</h2>
<div class="panel">
<h3>Enregistrer une cotisation</h3>
<div class="grid">
<label>Membre<select id="contribMember"></select></label>
<label>Montant (FBu)<input type="number" id="contribAmount"></label>
<label>Date de cotisation<input type="date" id="contribDate"></label>
</div>
<div class="actions"><button onclick="addContribution()">Enregistrer</button></div>
</div>
<div class="panel">
<h3>Historique des cotisations</h3>
<div class="tablewrap"><table>
<thead><tr><th>Date</th><th>Membre</th><th>Montant</th></tr></thead>
<tbody id="contribTable"></tbody>
</table></div>
</div>
</section>

<section id="credits" class="page">
<h2>Crédits</h2>
<div class="panel">
<h3>Enregistrer un crédit</h3>
<div class="grid">
<label>Membre<select id="creditMember"></select></label>
<label>Capital (FBu)<input type="number" id="principal"></label>
<label>Date de décaissement<input type="date" id="creditDate"></label>
<label>Durée
<select id="months">
<option value="1">1 mois</option>
<option value="2">2 mois</option>
<option value="3" selected>3 mois</option>
</select></label>
</div>
<p>Intérêt : 5% par mois sur le capital initial.</p>
<div class="actions"><button onclick="addCredit()">Enregistrer le crédit</button></div>
</div>
<div class="panel">
<h3>Liste des crédits</h3>
<div class="tablewrap"><table>
<thead><tr><th>Membre</th><th>Capital</th><th>Intérêt</th><th>Total à payer</th><th>Date</th><th>Échéance</th><th>Solde</th></tr></thead>
<tbody id="creditsTable"></tbody>
</table></div>
</div>
</section>

<section id="repayments" class="page">
<h2>Remboursements</h2>
<div class="panel">
<h3>Enregistrer un remboursement</h3>
<div class="grid">
<label>Crédit<select id="repayCredit"></select></label>
<label>Montant payé (FBu)<input type="number" id="repayAmount"></label>
<label>Date de paiement<input type="date" id="repayDate"></label>
</div>
<div class="actions"><button onclick="addRepayment()">Enregistrer le paiement</button></div>
</div>
<div class="panel">
<h3>Historique des remboursements</h3>
<div class="tablewrap"><table>
<thead><tr><th>Date</th><th>Membre</th><th>Montant</th></tr></thead>
<tbody id="repaymentsTable"></tbody>
</table></div>
</div>
</section>

<section id="reports" class="page">
<h2>Rapports</h2>
<div class="panel">
<h3>Choisir une période</h3>
<div class="grid">
<label>Du<input type="date" id="dateFrom"></label>
<label>Au<input type="date" id="dateTo"></label>
</div>
<div class="actions"><button onclick="makeReport()">Afficher le rapport</button></div>
<h3 id="reportResult"></h3>
</div>
</section>

</main>
<footer>FIKA Gestion © 2026</footer>

<script>
const db={
members:JSON.parse(localStorage.getItem('fika_members')||'[]'),
contributions:JSON.parse(localStorage.getItem('fika_contributions')||'[]'),
credits:JSON.parse(localStorage.getItem('fika_credits')||'[]'),
repayments:JSON.parse(localStorage.getItem('fika_repayments')||'[]')
};

function save(){
Object.keys(db).forEach(k=>{
localStorage.setItem('fika_'+k,JSON.stringify(db[k]));
});
refresh();
}

function showPage(id,btn){
document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
document.getElementById(id).classList.add('active');
document.querySelectorAll('nav button').forEach(b=>b.classList.remove('active'));
btn.classList.add('active');
refresh();
}

function money(n){
return Number(n||0).toLocaleString('fr-FR')+' FBu';
}

function memberName(id){
return db.members.find(m=>m.id==id)?.name||'—';
}

function addMember(){
let name=document.getElementById('memberName').value.trim();
let phone=document.getElementById('memberPhone').value.trim();
if(!name)return alert('Entrez le nom du membre.');
db.members.push({id:Date.now(),name,phone});
document.getElementById('memberName').value='';
document.getElementById('memberPhone').value='';
save();
}

function addContribution(){
let memberId=document.getElementById('contribMember').value;
let amount=Number(document.getElementById('contribAmount').value);
let date=document.getElementById('contribDate').value;
if(!memberId||amount<=0||!date)return alert('Complétez les champs.');
db.contributions.push({id:Date.now(),memberId,amount,date});
document.getElementById('contribAmount').value='';
save();
}

function addCredit(){
let memberId=document.getElementById('creditMember').value;
let principal=Number(document.getElementById('principal').value);
let months=Number(document.getElementById('months').value);
let date=document.getElementById('creditDate').value;
if(!memberId||principal<=0||!date)return alert('Complétez les champs.');
let interest=principal*0.05*months;
let total=principal+interest;
let due=new Date(date+'T12:00:00');
due.setMonth(due.getMonth()+months);
db.credits.push({
id:Date.now(),memberId,principal,months,interest,total,date,
due:due.toISOString().slice(0,10)
});
document.getElementById('principal').value='';
save();
}

function paidFor(creditId){
return db.repayments.filter(r=>r.creditId==creditId)
.reduce((s,r)=>s+r.amount,0);
}

function addRepayment(){
let creditId=document.getElementById('repayCredit').value;
let amount=Number(document.getElementById('repayAmount').value);
let date=document.getElementById('repayDate').value;
if(!creditId||amount<=0||!date)return alert('Complétez les champs.');
let credit=db.credits.find(c=>c.id==creditId);
if(amount>credit.total-paidFor(credit.id))
return alert('Le montant dépasse le solde restant.');
db.repayments.push({id:Date.now(),creditId,amount,date});
document.getElementById('repayAmount').value='';
save();
}

function makeReport(){
let from=document.getElementById('dateFrom').value;
let to=document.getElementById('dateTo').value;
if(!from||!to||from>to)return alert('Vérifiez les dates.');
let c=db.contributions.filter(x=>x.date>=from&&x.date<=to).reduce((s,x)=>s+x.amount,0);
let r=db.repayments.filter(x=>x.date>=from&&x.date<=to).reduce((s,x)=>s+x.amount,0);
document.getElementById('reportResult').textContent=
'Cotisations : '+money(c)+' | Remboursements : '+money(r);
}

function refresh(){
document.getElementById('memberCount').textContent=db.members.length;
document.getElementById('contributionTotal').textContent=money(db.contributions.reduce((s,x)=>s+x.amount,0));
document.getElementById('creditTotal').textContent=money(db.credits.reduce((s,x)=>s+x.total,0));
document.getElementById('repaymentTotal').textContent=money(db.repayments.reduce((s,x)=>s+x.amount,0));

document.getElementById('membersTable').innerHTML=db.members.map(m=>
`<tr><td>${safe(m.name)}</td><td>${safe(m.phone)}</td></tr>`).join('');

['contribMember','creditMember'].forEach(id=>{
document.getElementById(id).innerHTML='<option value="">Choisir un membre</option>'+
db.members.map(m=>`<option value="${m.id}">${safe(m.name)}</option>`).join('');
});

document.getElementById('contribTable').innerHTML=db.contributions.slice().reverse().map(x=>
`<tr><td>${x.date}</td><td>${safe(memberName(x.memberId))}</td><td>${money(x.amount)}</td></tr>`).join('');

document.getElementById('creditsTable').innerHTML=db.credits.slice().reverse().map(x=>
`<tr><td>${safe(memberName(x.memberId))}</td><td>${money(x.principal)}</td><td>${money(x.interest)}</td><td>${money(x.total)}</td><td>${x.date}</td><td>${x.due}</td><td>${money(x.total-paidFor(x.id))}</td></tr>`).join('');

document.getElementById('repayCredit').innerHTML='<option value="">Choisir un crédit</option>'+
db.credits.map(c=>`<option value="${c.id}">${safe(memberName(c.memberId))} - Solde : ${money(c.total-paidFor(c.id))}</option>`).join('');

document.getElementById('repaymentsTable').innerHTML=db.repayments.slice().reverse().map(r=>{
let c=db.credits.find(x=>x.id==r.creditId);
return `<tr><td>${r.date}</td><td>${safe(memberName(c?.memberId))}</td><td>${money(r.amount)}</td></tr>`;
}).join('');
}

function safe(value){
return String(value||'').replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
}

function changeLanguage(){
let lang=document.getElementById('language').value;
document.querySelectorAll('nav button').forEach(b=>{
b.textContent=b.dataset[lang];
});
document.getElementById('subtitle').textContent=
lang==='rn'?'Porogarame yo gucunga ibikorwa vya FIKA':'Plateforme de gestion de l’association FIKA';
}

let today=new Date().toISOString().slice(0,10);
['contribDate','creditDate','repayDate','dateTo'].forEach(id=>{
document.getElementById(id).value=today;
});
refresh();
</script>
</body>
</html>
