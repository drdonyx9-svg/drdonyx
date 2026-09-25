<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#050505">
<title>DrDonyx | Official</title>

<style>
*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

:root{
    --bg:#030303;
    --card:rgba(255,255,255,.055);
    --border:rgba(255,255,255,.1);
    --text:#fff;
    --muted:#999;
}

body{
    font-family:Arial, sans-serif;
    background:
        radial-gradient(circle at 50% -10%,#252525 0,#0b0b0b 35%,#030303 70%);
    color:var(--text);
    min-height:100vh;
    overflow-x:hidden;
}

button,input,select{
    font:inherit;
}

/* BACKGROUND */
.bg{
    position:fixed;
    inset:0;
    pointer-events:none;
    overflow:hidden;
    z-index:-1;
}

.orb{
    position:absolute;
    width:350px;
    height:350px;
    border-radius:50%;
    background:rgba(255,255,255,.035);
    filter:blur(80px);
}

.orb.one{
    top:-160px;
    left:-120px;
}

.orb.two{
    right:-160px;
    bottom:-120px;
}

/* APP */
.app{
    width:min(100%,1100px);
    margin:auto;
    padding:25px 18px 60px;
}

/* HERO */
.hero{
    position:relative;
    min-height:390px;
    border:1px solid var(--border);
    border-radius:32px;
    overflow:hidden;
    background:
        linear-gradient(180deg,rgba(255,255,255,.08),rgba(255,255,255,.025));
    backdrop-filter:blur(25px);
    box-shadow:0 30px 100px rgba(0,0,0,.55);
    display:flex;
    align-items:center;
    justify-content:center;
    text-align:center;
    padding:35px 20px;
}

.hero::before{
    content:"";
    position:absolute;
    inset:0;
    background:
        linear-gradient(135deg,transparent 40%,rgba(255,255,255,.035));
    pointer-events:none;
}

/* LOGO */
.logo-box{
    position:relative;
    width:150px;
    height:150px;
    margin:auto auto 22px;
    border-radius:38px;
    background:#050505;
    border:1px solid rgba(255,255,255,.16);
    display:flex;
    align-items:center;
    justify-content:center;
    box-shadow:
        0 20px 60px rgba(0,0,0,.7),
        inset 0 0 35px rgba(255,255,255,.025);
}

.logo-box::before{
    content:"";
    position:absolute;
    inset:9px;
    border:1px solid rgba(255,255,255,.08);
    border-radius:30px;
}

.logo{
    color:#fff;
    font-size:25px;
    font-weight:900;
    letter-spacing:-1.8px;
    position:relative;
    z-index:2;
}

.logo span{
    color:#777;
}

.profile-name{
    font-size:clamp(32px,7vw,58px);
    font-weight:900;
    letter-spacing:-3px;
}

.verified{
    display:inline-flex;
    align-items:center;
    justify-content:center;
    width:22px;
    height:22px;
    border-radius:50%;
    background:#fff;
    color:#000;
    font-size:13px;
    margin-right:7px;
    vertical-align:middle;
}

.bio{
    color:#aaa;
    margin-top:10px;
    font-size:15px;
}

.location{
    color:#777;
    margin-top:9px;
    font-size:13px;
}

.stats{
    display:flex;
    justify-content:center;
    gap:10px;
    margin-top:25px;
    flex-wrap:wrap;
}

.stat{
    min-width:120px;
    padding:12px 17px;
    border:1px solid var(--border);
    border-radius:17px;
    background:rgba(255,255,255,.035);
}

.stat b{
    display:block;
    font-size:19px;
}

.stat span{
    color:#777;
    font-size:11px;
}

/* SECTION */
.section-title{
    display:flex;
    align-items:center;
    justify-content:space-between;
    margin:30px 4px 15px;
}

.section-title h2{
    font-size:20px;
}

.section-title span{
    color:#666;
    font-size:12px;
}

/* ACCOUNTS */
.accounts{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:14px;
}

.account{
    position:relative;
    text-decoration:none;
    color:white;
    min-height:110px;
    padding:20px;
    border-radius:24px;
    border:1px solid var(--border);
    background:var(--card);
    backdrop-filter:blur(20px);
    display:flex;
    align-items:center;
    gap:16px;
    transition:.25s ease;
    overflow:hidden;
}

.account::after{
    content:"";
    position:absolute;
    width:120px;
    height:120px;
    right:-60px;
    top:-60px;
    border-radius:50%;
    background:rgba(255,255,255,.04);
}

.account:hover{
    transform:translateY(-4px);
    border-color:rgba(255,255,255,.25);
    background:rgba(255,255,255,.08);
}

.icon{
    width:58px;
    height:58px;
    flex-shrink:0;
    border-radius:18px;
    background:#0a0a0a;
    border:1px solid rgba(255,255,255,.12);
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:25px;
}

.account-info{
    min-width:0;
}

.account-info strong{
    display:block;
    font-size:16px;
    margin-bottom:5px;
}

.account-info small{
    color:#777;
    font-size:12px;
}

.arrow{
    margin-right:auto;
    color:#777;
    font-size:20px;
}

.empty{
    grid-column:1/-1;
    padding:50px 20px;
    text-align:center;
    border:1px dashed #222;
    border-radius:25px;
    color:#666;
}

/* ADMIN TRIGGER */
.admin-trigger{
    position:fixed;
    bottom:12px;
    left:12px;
    width:6px;
    height:6px;
    opacity:.01;
    border:0;
    background:#fff;
}

/* MODAL */
.modal{
    position:fixed;
    inset:0;
    z-index:100;
    background:rgba(0,0,0,.78);
    backdrop-filter:blur(15px);
    display:none;
    align-items:center;
    justify-content:center;
    padding:18px;
}

.modal.active{
    display:flex;
}

.modal-card{
    width:min(100%,520px);
    max-height:90vh;
    overflow:auto;
    border:1px solid #252525;
    border-radius:28px;
    background:#0b0b0b;
    box-shadow:0 30px 100px #000;
    padding:25px;
}

.modal-head{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:22px;
}

.close{
    width:38px;
    height:38px;
    border-radius:12px;
    border:1px solid #222;
    background:#111;
    color:#fff;
    cursor:pointer;
}

.input-group{
    margin-bottom:14px;
}

.input-group label{
    display:block;
    color:#aaa;
    font-size:12px;
    margin-bottom:7px;
}

.input-group input,
.input-group select{
    width:100%;
    padding:14px;
    border-radius:15px;
    border:1px solid #252525;
    outline:none;
    background:#111;
    color:#fff;
}

.input-group input:focus,
.input-group select:focus{
    border-color:#555;
}

.primary{
    width:100%;
    border:0;
    padding:15px;
    border-radius:16px;
    background:#fff;
    color:#000;
    font-weight:bold;
    cursor:pointer;
    margin-top:5px;
}

.primary:hover{
    background:#ddd;
}

/* ADMIN LIST */
.admin-list{
    margin-top:25px;
    display:grid;
    gap:10px;
}

.admin-item{
    display:flex;
    align-items:center;
    gap:10px;
    padding:13px;
    border-radius:17px;
    border:1px solid #202020;
    background:#101010;
}

.admin-item-info{
    flex:1;
    min-width:0;
}

.admin-item-info b{
    display:block;
}

.admin-item-info small{
    color:#666;
    display:block;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
}

.admin-btn{
    border:1px solid #292929;
    background:#151515;
    color:#fff;
    width:38px;
    height:38px;
    border-radius:12px;
    cursor:pointer;
}

.admin-btn.delete{
    color:#ff7777;
}

/* TOAST */
.toast{
    position:fixed;
    left:50%;
    bottom:25px;
    transform:translate(-50%,30px);
    opacity:0;
    pointer-events:none;
    background:#fff;
    color:#000;
    padding:12px 20px;
    border-radius:14px;
    font-size:13px;
    transition:.3s;
    z-index:300;
}

.toast.show{
    opacity:1;
    transform:translate(-50%,0);
}

/* FOOTER */
footer{
    text-align:center;
    margin-top:35px;
    color:#444;
    font-size:11px;
}

/* MOBILE */
@media(max-width:650px){
    .app{
        padding:12px 10px 45px;
    }

    .hero{
        min-height:365px;
        border-radius:26px;
    }

    .logo-box{
        width:125px;
        height:125px;
        border-radius:32px;
    }

    .logo{
        font-size:21px;
    }

    .profile-name{
        font-size:39px;
        letter-spacing:-2.5px;
    }

    .accounts{
        grid-template-columns:1fr;
    }

    .account{
        min-height:95px;
        padding:16px;
    }

    .icon{
        width:52px;
        height:52px;
    }

    .stat{
        min-width:105px;
    }
}
</style>
</head>

<body>

<div class="bg">
    <div class="orb one"></div>
    <div class="orb two"></div>
</div>

<main class="app">

    <section class="hero">
        <div>

            <div class="logo-box">
                <div class="logo">
                    Dr<span>Donyx</span>
                </div>
            </div>

            <h1 class="profile-name">
                DrDonyx
                <span class="verified">✓</span>
            </h1>

            <p class="bio">
                🎮 Content Creator • 💻 Digital Creator
            </p>

            <p class="location">
                🇮🇶 Iraq
            </p>

            <div class="stats">
                <div class="stat">
                    <b id="accountCount">0</b>
                    <span>Accounts</span>
                </div>

                <div class="stat">
                    <b>DrDonyx</b>
                    <span>Creator</span>
                </div>
            </div>

        </div>
    </section>

    <div class="section-title">
        <h2>حساباتي</h2>
        <span id="accountText">0 حساب</span>
    </div>

    <section class="accounts" id="accounts"></section>

    <footer>
        © 2026 DrDonyx — All Rights Reserved
    </footer>

</main>

<!-- مخفي تماماً -->
<button class="admin-trigger" id="adminTrigger"></button>

<!-- LOGIN -->
<div class="modal" id="loginModal">
    <div class="modal-card">

        <div class="modal-head">
            <h2>🔐 Admin Access</h2>
            <button class="close" onclick="closeModal('loginModal')">×</button>
        </div>

        <div class="input-group">
            <label>Admin Password</label>
            <input
                type="password"
                id="adminPassword"
                placeholder="Enter password"
                autocomplete="off"
            >
        </div>

        <button class="primary" onclick="loginAdmin()">
            دخول لوحة التحكم
        </button>

    </div>
</div>

<!-- ADMIN -->
<div class="modal" id="adminModal">
    <div class="modal-card">

        <div class="modal-head">
            <h2>⚙️ Admin Panel</h2>
            <button class="close" onclick="closeModal('adminModal')">×</button>
        </div>

        <div class="input-group">
            <label>اسم الحساب</label>
            <input
                id="accountName"
                type="text"
                placeholder="مثلاً: YouTube"
            >
        </div>

        <div class="input-group">
            <label>اسم المستخدم</label>
            <input
                id="accountUser"
                type="text"
                placeholder="@DrDonyx"
            >
        </div>

        <div class="input-group">
            <label>المنصة</label>
            <select id="platform">
                <option value="YouTube">YouTube</option>
                <option value="TikTok">TikTok</option>
                <option value="Discord">Discord</option>
                <option value="Instagram">Instagram</option>
                <option value="X">X</option>
                <option value="Facebook">Facebook</option>
                <option value="Twitch">Twitch</option>
                <option value="Website">Website</option>
                <option value="Other">Other</option>
            </select>
        </div>

        <div class="input-group">
            <label>رابط الحساب</label>
            <input
                id="accountUrl"
                type="url"
                placeholder="https://..."
            >
        </div>

        <button class="primary" id="saveBtn" onclick="saveAccount()">
            ＋ إضافة الحساب
        </button>

        <div class="admin-list" id="adminList"></div>

    </div>
</div>

<div class="toast" id="toast"></div>

<script>

/* ================================
   SETTINGS
================================ */

const ADMIN_PASSWORD = "DrDonyx.HassanAli";

const STORAGE_KEY = "drdonyx_accounts";

let accounts = JSON.parse(
    localStorage.getItem(STORAGE_KEY) || "[]"
);

let editIndex = -1;


/* ================================
   ICONS
================================ */

const icons = {
    YouTube:"▶",
    TikTok:"♪",
    Discord:"☁",
    Instagram:"◎",
    X:"𝕏",
    Facebook:"f",
    Twitch:"◈",
    Website:"⌘",
    Other:"●"
};


/* ================================
   SHOW ACCOUNTS
================================ */

function renderAccounts(){

    const container = document.getElementById("accounts");

    const count = accounts.length;

    document.getElementById("accountCount").textContent = count;

    document.getElementById("accountText").textContent =
        count === 1 ? "حساب واحد" : `${count} حساب`;

    if(count === 0){

        container.innerHTML = `
            <div class="empty">
                <div style="font-size:35px;margin-bottom:10px">🔗</div>
                <div>لا توجد حسابات مضافة حالياً</div>
                <small style="display:block;margin-top:7px;color:#444">
                    افتح لوحة Admin لإضافة حساباتك
                </small>
            </div>
        `;

        return;
    }

    container.innerHTML = accounts.map((account,index)=>{

        return `
            <a
                class="account"
                href="${escapeAttr(account.url)}"
                target="_blank"
                rel="noopener noreferrer"
            >

                <div class="icon">
                    ${icons[account.platform] || icons.Other}
                </div>

                <div class="account-info">
                    <strong>${escapeHTML(account.name)}</strong>
                    <small>
                        ${escapeHTML(account.user || account.platform)}
                    </small>
                </div>

                <div class="arrow">←</div>

            </a>
        `;

    }).join("");
}


/* ================================
   ADMIN LIST
================================ */

function renderAdminList(){

    const list = document.getElementById("adminList");

    if(accounts.length === 0){

        list.innerHTML = `
            <div style="text-align:center;color:#555;padding:20px">
                لا توجد حسابات
            </div>
        `;

        return;
    }

    list.innerHTML = accounts.map((account,index)=>{

        return `
            <div class="admin-item">

                <div class="icon" style="width:42px;height:42px;border-radius:13px">
                    ${icons[account.platform] || icons.Other}
                </div>

                <div class="admin-item-info">
                    <b>${escapeHTML(account.name)}</b>
                    <small>${escapeHTML(account.url)}</small>
                </div>

                <button
                    class="admin-btn"
                    onclick="editAccount(${index})"
                >
                    ✎
                </button>

                <button
                    class="admin-btn delete"
                    onclick="deleteAccount(${index})"
                >
                    🗑
                </button>

            </div>
        `;

    }).join("");
}


/* ================================
   SAVE
================================ */

function saveAccount(){

    const name =
        document.getElementById("accountName").value.trim();

    const user =
        document.getElementById("accountUser").value.trim();

    const platform =
        document.getElementById("platform").value;

    const url =
        document.getElementById("accountUrl").value.trim();

    if(!name || !url){

        showToast("⚠️ اكتب اسم الحساب والرابط");

        return;
    }

    if(!/^https?:\/\//i.test(url)){

        showToast("⚠️ الرابط لازم يبدأ بـ https://");

        return;
    }

    const data = {
        name,
        user,
        platform,
        url
    };

    if(editIndex === -1){

        accounts.push(data);

        showToast("✅ تمت إضافة الحساب");

    }else{

        accounts[editIndex] = data;

        showToast("✅ تم تعديل الحساب");

        editIndex = -1;

        document.getElementById("saveBtn").textContent =
            "＋ إضافة الحساب";
    }

    localStorage.setItem(
        STORAGE_KEY,
        JSON.stringify(accounts)
    );

    clearForm();

    renderAccounts();
    renderAdminList();
}


/* ================================
   EDIT
================================ */

function editAccount(index){

    const account = accounts[index];

    document.getElementById("accountName").value =
        account.name;

    document.getElementById("accountUser").value =
        account.user || "";

    document.getElementById("platform").value =
        account.platform;

    document.getElementById("accountUrl").value =
        account.url;

    editIndex = index;

    document.getElementById("saveBtn").textContent =
        "💾 حفظ التعديل";

    document.querySelector("#adminModal .modal-card")
        .scrollTop = 0;
}


/* ================================
   DELETE
================================ */

function deleteAccount(index){

    const account = accounts[index];

    if(!confirm(`حذف حساب ${account.name}؟`)){
        return;
    }

    accounts.splice(index,1);

    localStorage.setItem(
        STORAGE_KEY,
        JSON.stringify(accounts)
    );

    renderAccounts();
    renderAdminList();

    showToast("🗑️ تم حذف الحساب");
}


/* ================================
   CLEAR
================================ */

function clearForm(){

    document.getElementById("accountName").value = "";
    document.getElementById("accountUser").value = "";
    document.getElementById("accountUrl").value = "";

    document.getElementById("platform").value =
        "YouTube";

    editIndex = -1;

    document.getElementById("saveBtn").textContent =
        "＋ إضافة الحساب";
}


/* ================================
   ADMIN LOGIN
================================ */

function loginAdmin(){

    const password =
        document.getElementById("adminPassword").value;

    if(password === ADMIN_PASSWORD){

        document.getElementById("adminPassword").value = "";

        closeModal("loginModal");

        document.getElementById("adminModal")
            .classList.add("active");

        renderAdminList();

        showToast("✅ تم تسجيل الدخول");

    }else{

        showToast("❌ كلمة المرور غير صحيحة");

    }
}


/* ================================
   HIDDEN ADMIN
   اضغط DrDonyx خمس مرات بسرعة
================================ */

let clicks = 0;
let clickTimer;

document.querySelector(".logo-box").addEventListener("click",()=>{

    clicks++;

    clearTimeout(clickTimer);

    clickTimer = setTimeout(()=>{
        clicks = 0;
    },1200);

    if(clicks >= 5){

        clicks = 0;

        document.getElementById("loginModal")
            .classList.add("active");

        setTimeout(()=>{
            document.getElementById("adminPassword").focus();
        },100);

    }

});


/* ================================
   MODALS
================================ */

function closeModal(id){

    document.getElementById(id)
        .classList.remove("active");

    if(id === "adminModal"){
        clearForm();
    }

}


/* إغلاق عند الضغط خارج النافذة */

document.querySelectorAll(".modal").forEach(modal=>{

    modal.addEventListener("click",(e)=>{

        if(e.target === modal){
            modal.classList.remove("active");
        }

    });

});


/* ENTER PASSWORD */

document.getElementById("adminPassword")
    .addEventListener("keydown",(e)=>{

        if(e.key === "Enter"){
            loginAdmin();
        }

    });


/* ================================
   TOAST
================================ */

let toastTimer;

function showToast(message){

    const toast =
        document.getElementById("toast");

    toast.textContent = message;

    toast.classList.add("show");

    clearTimeout(toastTimer);

    toastTimer = setTimeout(()=>{
        toast.classList.remove("show");
    },2200);

}


/* ================================
   SECURITY HELPERS
================================ */

function escapeHTML(value){

    return String(value)
        .replaceAll("&","&amp;")
        .replaceAll("<","&lt;")
        .replaceAll(">","&gt;")
        .replaceAll('"',"&quot;")
        .replaceAll("'","&#039;");
}

function escapeAttr(value){

    return escapeHTML(value);
}


/* ================================
   START
================================ */

renderAccounts();

</script>

</body>
</html>
