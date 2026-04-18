# shop
shop
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>LUXE — Premium E-Commerce</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
:root{--ink:#0f0d0a;--cream:#faf7f2;--warm:#f5ede0;--gold:#c9963a;--gold-light:#e8c27a;--muted:#8a7f72;--border:#e0d8ce;--card:#fff;--red:#c94040;--green:#3a8a5a}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:'DM Sans',sans-serif;background:var(--cream);color:var(--ink);font-size:15px;line-height:1.6}

/* ANNOUNCE */
.announce{background:var(--ink);color:var(--cream);text-align:center;padding:9px 40px;font-size:0.78rem;letter-spacing:1px;text-transform:uppercase;position:relative}
.announce span{color:var(--gold-light);font-weight:600}
.ann-close{position:absolute;right:14px;top:50%;transform:translateY(-50%);background:none;border:none;color:rgba(255,255,255,.5);cursor:pointer;font-size:1.1rem;line-height:1;padding:4px}

/* HEADER */
header{position:sticky;top:0;z-index:200;background:rgba(250,247,242,.97);backdrop-filter:blur(16px);border-bottom:1px solid var(--border)}
.hdr{max-width:1400px;margin:auto;display:flex;align-items:center;justify-content:space-between;height:64px;padding:0 4%;gap:20px}
.logo{font-family:'Playfair Display',serif;font-size:1.75rem;font-weight:700;letter-spacing:3px;color:var(--ink);text-decoration:none;flex-shrink:0}
.logo span{color:var(--gold)}
nav{display:flex;gap:22px;align-items:center}
nav a{text-decoration:none;color:var(--muted);font-size:0.8rem;font-weight:500;letter-spacing:.4px;text-transform:uppercase;transition:color .2s;white-space:nowrap;padding:4px 0;border-bottom:2px solid transparent}
nav a:hover,nav a.nav-active{color:var(--ink);border-bottom-color:var(--gold)}
.hdr-actions{display:flex;gap:8px;align-items:center;flex-shrink:0}
.icon-btn{background:none;border:none;cursor:pointer;color:var(--ink);font-size:1.2rem;position:relative;padding:8px;border-radius:50%;transition:background .2s;line-height:1}
.icon-btn:hover{background:var(--warm)}
.cart-badge{position:absolute;top:2px;right:2px;background:var(--gold);color:#fff;font-size:.6rem;font-weight:700;width:16px;height:16px;border-radius:50%;display:flex;align-items:center;justify-content:center;line-height:1}
.hamburger{display:none;flex-direction:column;gap:4px;cursor:pointer;padding:8px;background:none;border:none}
.hamburger span{display:block;width:22px;height:2px;background:var(--ink);border-radius:2px;transition:all .3s}
.hamburger.open span:nth-child(1){transform:translateY(6px) rotate(45deg)}
.hamburger.open span:nth-child(2){opacity:0}
.hamburger.open span:nth-child(3){transform:translateY(-6px) rotate(-45deg)}

/* MOBILE NAV */
.mob-nav{display:none;position:fixed;top:64px;left:0;right:0;bottom:0;background:#fff;z-index:190;padding:24px 6%;overflow-y:auto;flex-direction:column;gap:0}
.mob-nav.open{display:flex}
.mob-nav a{font-size:1.1rem;font-weight:500;color:var(--ink);text-decoration:none;padding:14px 0;border-bottom:1px solid var(--border)}

/* HERO */
.hero{max-width:1400px;margin:0 auto;padding:0 4%;display:grid;grid-template-columns:1fr 1fr;gap:50px;align-items:center;min-height:calc(100vh - 64px)}
.hero-txt{padding:60px 0}
.eyebrow{display:inline-block;background:var(--warm);color:var(--gold);font-size:.72rem;font-weight:600;letter-spacing:2px;text-transform:uppercase;padding:5px 14px;border-radius:20px;margin-bottom:20px}
.hero-txt h1{font-family:'Playfair Display',serif;font-size:clamp(2.6rem,4.5vw,4.2rem);line-height:1.08;font-weight:700;margin-bottom:20px}
.hero-txt h1 em{font-style:italic;color:var(--gold)}
.hero-txt p{font-size:1rem;color:var(--muted);max-width:400px;margin-bottom:32px;line-height:1.8}
.hero-btns{display:flex;gap:12px;flex-wrap:wrap}
.btn-pri{display:inline-flex;align-items:center;gap:8px;background:var(--ink);color:var(--cream);padding:13px 30px;border-radius:2px;font-size:.85rem;font-weight:500;letter-spacing:1px;text-transform:uppercase;text-decoration:none;border:2px solid var(--ink);transition:all .25s;cursor:pointer;font-family:'DM Sans',sans-serif}
.btn-pri:hover{background:transparent;color:var(--ink)}
.btn-out{display:inline-flex;align-items:center;gap:8px;background:transparent;color:var(--ink);padding:13px 30px;border-radius:2px;font-size:.85rem;font-weight:500;letter-spacing:1px;text-transform:uppercase;text-decoration:none;border:2px solid var(--ink);transition:all .25s;cursor:pointer;font-family:'DM Sans',sans-serif}
.btn-out:hover{background:var(--ink);color:var(--cream)}
.hero-stats{display:flex;gap:32px;margin-top:40px;padding-top:32px;border-top:1px solid var(--border);flex-wrap:wrap}
.hstat-num{font-family:'Playfair Display',serif;font-size:1.8rem;font-weight:700;color:var(--ink);display:block}
.hstat-lbl{font-size:.72rem;color:var(--muted);text-transform:uppercase;letter-spacing:1px}
.hero-vis{height:560px;display:grid;grid-template-columns:1fr 1fr;grid-template-rows:1fr 1fr;gap:14px}
.hcard{border-radius:6px;overflow:hidden;position:relative;display:flex;align-items:center;justify-content:center}
.hcard:first-child{grid-row:span 2;font-size:7rem}
.hcard:nth-child(2){font-size:4rem}
.hcard:nth-child(3){font-size:4rem}
.hb1{background:linear-gradient(150deg,#ddd0c0,#b09070)}
.hb2{background:linear-gradient(150deg,#c0d0d8,#7090a8)}
.hb3{background:linear-gradient(150deg,#d8d0c0,#a89870)}
.hlabel{position:absolute;bottom:14px;left:14px;background:rgba(255,255,255,.92);padding:6px 12px;border-radius:2px;font-size:.72rem;font-weight:600;letter-spacing:.5px}
.hpill{position:absolute;top:14px;right:14px;background:var(--gold);color:#fff;padding:4px 10px;border-radius:20px;font-size:.7rem;font-weight:700;letter-spacing:.5px;text-transform:uppercase}

/* SECTION */
.section{padding:70px 4%;max-width:1400px;margin:0 auto}
.sec-hdr{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:36px;gap:16px;flex-wrap:wrap}
.sec-title{font-family:'Playfair Display',serif;font-size:clamp(1.7rem,3vw,2.4rem);font-weight:700}
.sec-title em{font-style:italic;color:var(--gold)}
.see-all{font-size:.8rem;text-transform:uppercase;letter-spacing:1px;color:var(--muted);text-decoration:none;font-weight:500;border-bottom:1px solid var(--muted);padding-bottom:2px;transition:color .2s;white-space:nowrap;background:none;border-top:none;border-left:none;border-right:none;cursor:pointer;font-family:'DM Sans',sans-serif}
.see-all:hover{color:var(--ink);border-bottom-color:var(--ink)}

/* CATS */
.cats{display:grid;grid-template-columns:repeat(6,1fr);gap:12px}
.cat-card{border-radius:6px;overflow:hidden;position:relative;cursor:pointer;aspect-ratio:2/3;transition:transform .3s}
.cat-card:hover{transform:translateY(-5px)}
.cat-card:hover .cat-ov{opacity:1}
.cat-bg{width:100%;height:100%;display:flex;align-items:center;justify-content:center;font-size:2.2rem}
.cb1{background:linear-gradient(160deg,#c8bfb4,#8f7f6e)}
.cb2{background:linear-gradient(160deg,#b4c0c8,#6e7f8f)}
.cb3{background:linear-gradient(160deg,#c8c4b4,#8f8a6e)}
.cb4{background:linear-gradient(160deg,#c4b4c8,#8a6e8f)}
.cb5{background:linear-gradient(160deg,#b4c8b8,#6e8f74)}
.cb6{background:linear-gradient(160deg,#c8bcb4,#8f736e)}
.cat-ov{position:absolute;inset:0;background:rgba(15,13,10,.4);opacity:0;transition:opacity .3s}
.cat-lbl{position:absolute;bottom:0;left:0;right:0;padding:14px 12px;background:linear-gradient(to top,rgba(0,0,0,.7),transparent);color:#fff}
.cat-lbl h3{font-family:'Playfair Display',serif;font-size:.9rem}
.cat-lbl p{font-size:.7rem;opacity:.8;margin-top:1px}

/* TOOLBAR */
.toolbar{display:flex;align-items:center;justify-content:space-between;margin-bottom:22px;gap:12px;flex-wrap:wrap}
.filter-bar{display:flex;gap:6px;flex-wrap:wrap;align-items:center}
.fbtn{padding:7px 15px;border:1px solid var(--border);background:#fff;border-radius:20px;font-size:.78rem;cursor:pointer;transition:all .2s;font-family:'DM Sans',sans-serif;white-space:nowrap}
.fbtn:hover,.fbtn.active{background:var(--ink);color:#fff;border-color:var(--ink)}
.tb-right{display:flex;align-items:center;gap:10px}
.sort-sel{padding:7px 14px;border:1px solid var(--border);border-radius:20px;background:#fff;font-family:'DM Sans',sans-serif;font-size:.78rem;cursor:pointer;outline:none;color:var(--ink)}
.view-btns{display:flex;gap:4px}
.vbtn{background:#fff;border:1px solid var(--border);padding:7px 10px;border-radius:6px;cursor:pointer;font-size:.9rem;transition:all .2s;line-height:1}
.vbtn.active{background:var(--ink);color:#fff;border-color:var(--ink)}

/* PRODUCTS */
.pgrid{display:grid;grid-template-columns:repeat(4,1fr);gap:20px}
.pgrid.lv{grid-template-columns:1fr}
.pgrid.lv .pcard{display:flex;flex-direction:row;height:170px}
.pgrid.lv .pimg{width:130px;flex-shrink:0;aspect-ratio:auto;height:100%}
.pgrid.lv .pthumb{height:100%}
.pgrid.lv .pinfo{flex:1;padding:18px 20px;display:flex;flex-direction:column;justify-content:center}
.pgrid.lv .pactions{position:static;opacity:1;transform:none;margin-top:10px}
.pgrid.lv .qadd{width:auto;display:inline-block;padding:8px 18px}

.pcard{background:var(--card);border-radius:6px;overflow:hidden;border:1px solid var(--border);transition:transform .3s,box-shadow .3s;cursor:pointer;animation:fuUp .4s ease both}
@keyframes fuUp{from{opacity:0;transform:translateY(14px)}to{opacity:1;transform:none}}
.pcard:hover{transform:translateY(-4px);box-shadow:0 16px 44px rgba(15,13,10,.12)}
.pcard:hover .pactions{opacity:1;transform:translateY(0)}
.pcard:hover .pthumb{transform:scale(1.06)}
.pimg{position:relative;overflow:hidden;aspect-ratio:3/4}
.pthumb{width:100%;height:100%;display:flex;align-items:center;justify-content:center;font-size:3.6rem;transition:transform .4s}
.p1{background:linear-gradient(135deg,#f0e8dc,#d4c4b0)}
.p2{background:linear-gradient(135deg,#dce8f0,#b0c4d4)}
.p3{background:linear-gradient(135deg,#f0ead8,#d4c8a0)}
.p4{background:linear-gradient(135deg,#e8dcf0,#c4b0d4)}
.p5{background:linear-gradient(135deg,#dcf0e4,#b0d4bc)}
.p6{background:linear-gradient(135deg,#f0dce8,#d4b0c4)}
.p7{background:linear-gradient(135deg,#eef0dc,#d0d4b0)}
.p8{background:linear-gradient(135deg,#f0e4dc,#d4bcb0)}
.p9{background:linear-gradient(135deg,#e0f0dc,#a8d4a0)}
.p10{background:linear-gradient(135deg,#f0e0d8,#d4b8a8)}
.p11{background:linear-gradient(135deg,#d8e4f0,#a0b8d4)}
.p12{background:linear-gradient(135deg,#f0f0dc,#d4d4a0)}
.p13{background:linear-gradient(135deg,#f0dce0,#d4a8b0)}
.p14{background:linear-gradient(135deg,#e0dcf0,#b0a8d4)}
.p15{background:linear-gradient(135deg,#dcf0ec,#a0d4cc)}
.p16{background:linear-gradient(135deg,#f0e8d8,#d4c8a4)}
.pbadge{position:absolute;top:10px;left:10px;padding:4px 9px;border-radius:2px;font-size:.68rem;font-weight:700;letter-spacing:.5px;text-transform:uppercase}
.bn{background:var(--ink);color:#fff}
.bs{background:var(--red);color:#fff}
.bh{background:var(--gold);color:#fff}
.be{background:var(--green);color:#fff}
.pactions{position:absolute;bottom:0;left:0;right:0;padding:10px;opacity:0;transform:translateY(6px);transition:all .3s}
.qadd{width:100%;padding:9px;background:rgba(15,13,10,.88);color:#fff;border:none;border-radius:2px;font-size:.78rem;font-weight:500;letter-spacing:.5px;text-transform:uppercase;cursor:pointer;transition:background .2s;font-family:'DM Sans',sans-serif}
.qadd:hover{background:var(--gold)}
.wbtn{position:absolute;top:10px;right:10px;background:#fff;border:none;width:32px;height:32px;border-radius:50%;display:flex;align-items:center;justify-content:center;cursor:pointer;font-size:.95rem;box-shadow:0 2px 8px rgba(0,0,0,.15);transition:transform .2s}
.wbtn:hover{transform:scale(1.2)}
.pinfo{padding:14px}
.pbrand{font-size:.68rem;text-transform:uppercase;letter-spacing:1px;color:var(--muted);margin-bottom:3px}
.pname{font-family:'Playfair Display',serif;font-size:.95rem;font-weight:400;margin-bottom:7px;line-height:1.4}
.ppricing{display:flex;align-items:center;gap:8px}
.pprice{font-weight:700;font-size:.95rem}
.ppold{color:var(--muted);text-decoration:line-through;font-size:.86rem}
.ppsale{color:var(--red)}
.pstars{display:flex;align-items:center;gap:1px;margin-top:5px;font-size:.72rem}
.sf{color:var(--gold)}
.se{color:#d0c8bc}
.sc{color:var(--muted);margin-left:4px}

/* PAGINATION */
.pager{display:flex;justify-content:center;align-items:center;gap:6px;padding:40px 0 10px}
.pgbtn{width:38px;height:38px;border-radius:4px;border:1px solid var(--border);background:#fff;cursor:pointer;font-size:.85rem;font-family:'DM Sans',sans-serif;transition:all .2s;display:flex;align-items:center;justify-content:center}
.pgbtn:hover{border-color:var(--ink);background:var(--warm)}
.pgbtn.active{background:var(--ink);color:#fff;border-color:var(--ink)}
.pgbtn:disabled{opacity:.35;cursor:default}

/* MARQUEE */
.marq-wrap{background:var(--ink);padding:13px 0;overflow:hidden;white-space:nowrap}
.marq-inner{display:inline-flex;animation:marq 28s linear infinite}
@keyframes marq{from{transform:translateX(0)}to{transform:translateX(-50%)}}
.marq-item{font-size:.75rem;letter-spacing:2px;text-transform:uppercase;color:rgba(255,255,255,.55);padding:0 36px}
.marq-item span{color:var(--gold)}

/* BANNER */
.ban-wrap{padding:0 4% 70px;max-width:1400px;margin:0 auto}
.banner{background:var(--ink);border-radius:6px;overflow:hidden;display:grid;grid-template-columns:1fr 1fr;min-height:270px}
.ban-txt{padding:50px;display:flex;flex-direction:column;justify-content:center;gap:14px}
.ban-txt .eyebrow{font-size:.72rem;text-transform:uppercase;letter-spacing:2px;color:var(--gold);font-weight:600;background:transparent;padding:0}
.ban-txt h2{font-family:'Playfair Display',serif;font-size:clamp(1.6rem,3vw,2.5rem);color:#fff;line-height:1.15}
.ban-txt h2 em{color:var(--gold-light);font-style:italic}
.ban-txt p{color:rgba(255,255,255,.6);font-size:.9rem;max-width:360px}
.btn-gold{display:inline-flex;align-items:center;gap:8px;background:var(--gold);color:#fff;padding:12px 26px;border-radius:2px;font-size:.82rem;font-weight:600;letter-spacing:1px;text-transform:uppercase;text-decoration:none;align-self:flex-start;border:none;cursor:pointer;transition:background .2s;font-family:'DM Sans',sans-serif}
.btn-gold:hover{background:var(--gold-light)}
.ban-vis{display:flex;align-items:center;justify-content:center;background:linear-gradient(135deg,#1a1712,#2a2520);font-size:7rem}

/* TRUST */
.trust{background:var(--warm);border-top:1px solid var(--border);border-bottom:1px solid var(--border);padding:26px 4%}
.trust-in{max-width:1400px;margin:auto;display:grid;grid-template-columns:repeat(4,1fr);gap:20px}
.titem{display:flex;align-items:center;gap:14px}
.ticon{font-size:1.7rem;flex-shrink:0}
.ttxt h4{font-size:.86rem;font-weight:600}
.ttxt p{font-size:.76rem;color:var(--muted)}

/* NEWSLETTER */
.nl{background:var(--ink);padding:70px 4%;text-align:center}
.nl .eyebrow{display:block;margin-bottom:12px;background:transparent;padding:0}
.nl h2{font-family:'Playfair Display',serif;font-size:clamp(1.8rem,3vw,2.4rem);color:#fff;margin-bottom:10px}
.nl p{color:rgba(255,255,255,.55);margin-bottom:28px;font-size:.9rem}
.nl-form{display:flex;max-width:460px;margin:auto;border-radius:3px;overflow:hidden}
.nl-form input{flex:1;padding:14px 18px;border:none;background:#fff;font-family:'DM Sans',sans-serif;font-size:.9rem;outline:none;min-width:0}
.nl-form button{padding:14px 20px;background:var(--gold);color:#fff;border:none;cursor:pointer;font-size:.8rem;font-weight:600;letter-spacing:1px;text-transform:uppercase;white-space:nowrap;transition:background .2s;font-family:'DM Sans',sans-serif}
.nl-form button:hover{background:var(--gold-light)}

/* FOOTER */
footer{background:#0a0807;color:rgba(255,255,255,.6);padding:56px 4% 26px}
.fgrid{max-width:1400px;margin:auto;display:grid;grid-template-columns:2fr 1fr 1fr 1fr 1fr;gap:36px;padding-bottom:40px;border-bottom:1px solid rgba(255,255,255,.08);margin-bottom:24px}
.fbrand .logo{color:#fff;margin-bottom:14px;display:block}
.fbrand p{font-size:.83rem;line-height:1.75;max-width:260px}
.fsoc{display:flex;gap:8px;margin-top:16px}
.sbtn{width:34px;height:34px;border-radius:50%;background:rgba(255,255,255,.1);display:flex;align-items:center;justify-content:center;font-size:.85rem;cursor:pointer;border:none;color:#fff;transition:background .2s}
.sbtn:hover{background:var(--gold)}
.fcol h4{color:#fff;font-size:.76rem;text-transform:uppercase;letter-spacing:1.5px;margin-bottom:14px;font-weight:600}
.fcol a{display:block;color:rgba(255,255,255,.5);text-decoration:none;font-size:.83rem;margin-bottom:8px;transition:color .2s}
.fcol a:hover{color:var(--gold-light)}
.fbot{max-width:1400px;margin:auto;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:12px;font-size:.76rem}
.picons{display:flex;gap:5px}
.pic{background:rgba(255,255,255,.12);padding:4px 8px;border-radius:3px;font-size:.68rem;color:#fff;font-weight:600}

/* CART */
.cart-ov{position:fixed;inset:0;background:rgba(0,0,0,.4);z-index:300;opacity:0;pointer-events:none;transition:opacity .3s}
.cart-ov.open{opacity:1;pointer-events:all}
.cart-dr{position:fixed;top:0;right:-450px;width:440px;height:100vh;background:#fff;z-index:301;display:flex;flex-direction:column;transition:right .35s cubic-bezier(.4,0,.2,1);box-shadow:-8px 0 40px rgba(0,0,0,.15)}
.cart-dr.open{right:0}
.chdr{padding:20px 22px;border-bottom:1px solid var(--border);display:flex;justify-content:space-between;align-items:center}
.chdr h3{font-family:'Playfair Display',serif;font-size:1.2rem}
.chdr-r{display:flex;align-items:center;gap:10px}
.clr-btn{background:none;border:none;font-size:.72rem;color:var(--muted);cursor:pointer;text-transform:uppercase;letter-spacing:.5px;transition:color .2s}
.clr-btn:hover{color:var(--red)}
.clos{background:none;border:none;cursor:pointer;font-size:1.5rem;color:var(--muted);line-height:1;transition:color .2s}
.clos:hover{color:var(--ink)}
.citems{flex:1;overflow-y:auto;padding:14px 22px}
.cempty{text-align:center;padding:60px 20px;color:var(--muted)}
.cempty-ic{font-size:2.8rem;margin-bottom:10px}
.cempty p{font-size:.88rem;line-height:1.6}
.citem{display:flex;gap:12px;padding:14px 0;border-bottom:1px solid var(--border)}
.citem:last-child{border-bottom:none}
.citem-img{width:70px;height:88px;border-radius:4px;display:flex;align-items:center;justify-content:center;font-size:1.9rem;flex-shrink:0}
.citem-inf{flex:1;min-width:0}
.citem-name{font-weight:500;font-size:.86rem;margin-bottom:2px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.citem-price{color:var(--muted);font-size:.8rem;margin-bottom:7px}
.citem-bot{display:flex;align-items:center;justify-content:space-between}
.qty-row{display:flex;align-items:center;gap:7px}
.qbtn{width:24px;height:24px;border-radius:50%;border:1px solid var(--border);background:#fff;cursor:pointer;font-size:.95rem;display:flex;align-items:center;justify-content:center;transition:background .2s;line-height:1}
.qbtn:hover{background:var(--warm)}
.qval{font-size:.86rem;font-weight:600;min-width:18px;text-align:center}
.rem-btn{background:none;border:none;cursor:pointer;color:var(--muted);font-size:.73rem;transition:color .2s}
.rem-btn:hover{color:var(--red)}
.cftr{padding:16px 22px;border-top:1px solid var(--border)}
.csub{display:flex;justify-content:space-between;font-size:.85rem;color:var(--muted);margin-bottom:5px}
.ctot{display:flex;justify-content:space-between;font-weight:700;font-size:1rem;margin-bottom:14px}
.ckbtn{width:100%;padding:14px;background:var(--ink);color:#fff;border:none;cursor:pointer;font-size:.86rem;font-weight:600;letter-spacing:.5px;text-transform:uppercase;border-radius:2px;transition:background .2s;font-family:'DM Sans',sans-serif}
.ckbtn:hover{background:var(--gold)}

/* MODAL */
.modal-ov{position:fixed;inset:0;background:rgba(0,0,0,.55);z-index:400;opacity:0;pointer-events:none;transition:opacity .3s;display:flex;align-items:center;justify-content:center;padding:20px}
.modal-ov.open{opacity:1;pointer-events:all}
.modal{background:#fff;border-radius:8px;width:100%;max-width:800px;max-height:90vh;overflow:hidden;display:grid;grid-template-columns:1fr 1fr;transform:scale(.95);transition:transform .3s}
.modal-ov.open .modal{transform:scale(1)}
.mimg{display:flex;align-items:center;justify-content:center;font-size:7.5rem;min-height:380px}
.mbody{padding:36px;overflow-y:auto;display:flex;flex-direction:column;gap:14px;position:relative}
.mclos{position:absolute;top:14px;right:16px;background:none;border:none;font-size:1.5rem;cursor:pointer;color:var(--muted);transition:color .2s;line-height:1}
.mclos:hover{color:var(--ink)}
.mbrand{font-size:.7rem;text-transform:uppercase;letter-spacing:1.5px;color:var(--gold);font-weight:600}
.mname{font-family:'Playfair Display',serif;font-size:1.6rem;line-height:1.2}
.mprice{font-size:1.3rem;font-weight:700}
.mprice .mold{font-size:.95rem;color:var(--muted);text-decoration:line-through;margin-left:8px;font-weight:400}
.mprice .msale{color:var(--red)}
.mdesc{font-size:.88rem;color:var(--muted);line-height:1.75;border-top:1px solid var(--border);padding-top:14px}
.mqlbl{font-size:.8rem;text-transform:uppercase;letter-spacing:.5px;color:var(--muted)}
.mqrow{display:flex;align-items:center;gap:12px}
.mqbox{display:flex;align-items:center;gap:8px;border:1px solid var(--border);border-radius:2px;padding:4px 10px}
.madd{flex:1;padding:12px;background:var(--ink);color:#fff;border:none;border-radius:2px;font-size:.86rem;font-weight:600;letter-spacing:.5px;text-transform:uppercase;cursor:pointer;transition:background .2s;font-family:'DM Sans',sans-serif}
.madd:hover{background:var(--gold)}
.mtags{display:flex;gap:5px;flex-wrap:wrap}
.mtag{padding:4px 11px;background:var(--warm);border-radius:20px;font-size:.72rem;color:var(--muted)}

/* SEARCH OVERLAY */
.srch-ov{position:fixed;inset:0;background:rgba(250,247,242,.98);z-index:250;display:flex;flex-direction:column;align-items:center;padding:80px 20px 40px;opacity:0;pointer-events:none;transition:opacity .3s}
.srch-ov.open{opacity:1;pointer-events:all}
.srch-clos{position:absolute;top:22px;right:22px;background:none;border:none;font-size:1.5rem;cursor:pointer;color:var(--muted)}
.srch-wrap{width:100%;max-width:620px;margin-bottom:20px;position:relative}
.srch-inp{width:100%;padding:15px 18px 15px 46px;border:2px solid var(--ink);border-radius:4px;font-family:'Playfair Display',serif;font-size:1.3rem;outline:none;background:#fff}
.srch-ico{position:absolute;left:14px;top:50%;transform:translateY(-50%);font-size:1.2rem;color:var(--muted)}
.srch-hint{font-size:.8rem;color:var(--muted);margin-bottom:18px}
.srch-res{width:100%;max-width:620px;display:grid;grid-template-columns:repeat(3,1fr);gap:10px;overflow-y:auto;max-height:50vh}

/* TOAST */
.toast{position:fixed;bottom:28px;left:50%;transform:translateX(-50%) translateY(70px);background:var(--ink);color:#fff;padding:10px 22px;border-radius:4px;font-size:.83rem;font-weight:500;z-index:500;transition:transform .3s;pointer-events:none;white-space:nowrap;max-width:90vw;text-align:center}
.toast.show{transform:translateX(-50%) translateY(0)}

/* BACK TOP */
.btop{position:fixed;bottom:28px;right:28px;width:42px;height:42px;background:var(--ink);color:#fff;border:none;border-radius:50%;cursor:pointer;font-size:1rem;display:flex;align-items:center;justify-content:center;z-index:100;opacity:0;transform:translateY(10px);transition:all .3s;box-shadow:0 4px 14px rgba(0,0,0,.2)}
.btop.vis{opacity:1;transform:none}
.btop:hover{background:var(--gold)}

/* RESPONSIVE */
@media(max-width:1200px){.pgrid{grid-template-columns:repeat(3,1fr)}.cats{grid-template-columns:repeat(3,1fr)}.fgrid{grid-template-columns:1fr 1fr 1fr}}
@media(max-width:1024px){nav{display:none}.hamburger{display:flex}.hero{grid-template-columns:1fr;min-height:auto;padding:48px 4%}.hero-vis{display:none}.hero-txt{padding:0}.pgrid{grid-template-columns:repeat(3,1fr)}.cats{grid-template-columns:repeat(3,1fr)}.banner{grid-template-columns:1fr}.ban-vis{min-height:180px}.trust-in{grid-template-columns:repeat(2,1fr)}.modal{grid-template-columns:1fr;max-width:480px}.mimg{min-height:240px;font-size:5.5rem}}
@media(max-width:768px){.pgrid{grid-template-columns:repeat(2,1fr);gap:12px}.cats{grid-template-columns:repeat(3,1fr);gap:8px}.cart-dr{width:100%;right:-100%}.section{padding:48px 4%}.toolbar{flex-direction:column;align-items:flex-start}.tb-right{width:100%;justify-content:space-between}.fgrid{grid-template-columns:1fr 1fr;gap:24px}.fbot{flex-direction:column;text-align:center}.nl-form{flex-direction:column}.nl-form input,.nl-form button{border-radius:2px}.hero-stats{gap:16px}.pgrid.lv{grid-template-columns:1fr 1fr}.pgrid.lv .pcard{height:auto;flex-direction:column}.pgrid.lv .pimg{width:100%;height:160px}}
@media(max-width:480px){.hdr{height:58px;padding:0 4%}.logo{font-size:1.5rem}.pgrid{grid-template-columns:1fr 1fr;gap:10px}.cats{grid-template-columns:repeat(2,1fr)}.filter-bar{gap:4px}.fbtn{font-size:.73rem;padding:6px 11px}.pager{gap:4px}.pgbtn{width:32px;height:32px;font-size:.78rem}.trust-in{grid-template-columns:1fr}.mob-nav{top:58px}.pgrid.lv{grid-template-columns:1fr}.srch-res{grid-template-columns:repeat(2,1fr)}}
</style>
</head>
<body>

<div class="announce" id="annBar">
  Free shipping on orders over <span>$75</span> &nbsp;·&nbsp; Use code <span>LUXE20</span> for 20% off
  <button class="ann-close" onclick="this.parentElement.remove()">×</button>
</div>

<header>
  <div class="hdr">
    <a href="#" class="logo">LUX<span>E</span></a>
    <nav id="mainNav">
      <a href="#" onclick="setF('all',event)">All</a>
      <a href="#" onclick="setF('fashion',event)">Fashion</a>
      <a href="#" onclick="setF('home',event)">Home</a>
      <a href="#" onclick="setF('beauty',event)">Beauty</a>
      <a href="#" onclick="setF('accessories',event)">Accessories</a>
      <a href="#" onclick="setF('wellness',event)">Wellness</a>
      <a href="#" onclick="setF('tech',event)">Tech</a>
    </nav>
    <div class="hdr-actions">
      <button class="icon-btn" onclick="openSrch()" title="Search (/)">🔍</button>
      <button class="icon-btn" onclick="toggleCart()" title="Cart">🛒<span class="cart-badge" id="cartBadge">0</span></button>
      <button class="hamburger" id="hamburger" onclick="toggleMob()"><span></span><span></span><span></span></button>
    </div>
  </div>
</header>

<div class="mob-nav" id="mobNav">
  <a href="#" onclick="setF('all',event);closeMob()">All Products</a>
  <a href="#" onclick="setF('fashion',event);closeMob()">👗 Fashion</a>
  <a href="#" onclick="setF('home',event);closeMob()">🏠 Home & Living</a>
  <a href="#" onclick="setF('beauty',event);closeMob()">💄 Beauty</a>
  <a href="#" onclick="setF('accessories',event);closeMob()">⌚ Accessories</a>
  <a href="#" onclick="setF('wellness',event);closeMob()">🧘 Wellness</a>
  <a href="#" onclick="setF('tech',event);closeMob()">💻 Tech</a>
</div>

<section style="background:var(--cream)">
  <div class="hero">
    <div class="hero-txt">
      <div class="eyebrow">✦ New Collection 2026</div>
      <h1>Curated <em>Luxury</em><br>For Every<br>Occasion</h1>
      <p>Discover premium fashion, home décor, beauty and lifestyle — thoughtfully curated for the discerning individual.</p>
      <div class="hero-btns">
        <button class="btn-pri" onclick="scrollToP()">Shop Now →</button>
        <button class="btn-out" onclick="setF('sale',null)">View Sale</button>
      </div>
      <div class="hero-stats">
        <div><span class="hstat-num">38+</span><span class="hstat-lbl">Products</span></div>
        <div><span class="hstat-num">7</span><span class="hstat-lbl">Categories</span></div>
        <div><span class="hstat-num">4.9★</span><span class="hstat-lbl">Rating</span></div>
        <div><span class="hstat-num">30</span><span class="hstat-lbl">Day Returns</span></div>
      </div>
    </div>
    <div class="hero-vis">
      <div class="hcard hb1"><div style="font-size:6rem">👗</div><div class="hlabel">SS 2026</div></div>
      <div class="hcard hb2"><div style="font-size:4rem">💄</div><div class="hpill">New</div></div>
      <div class="hcard hb3"><div style="font-size:4rem">🏠</div><div class="hlabel">Home</div></div>
    </div>
  </div>
</section>

<div class="marq-wrap"><div class="marq-inner">
  <span class="marq-item">Free Returns <span>✦</span></span><span class="marq-item">Premium Quality <span>✦</span></span><span class="marq-item">Worldwide Shipping <span>✦</span></span><span class="marq-item">Exclusive Brands <span>✦</span></span><span class="marq-item">Secure Checkout <span>✦</span></span><span class="marq-item">New Arrivals Weekly <span>✦</span></span><span class="marq-item">Free Returns <span>✦</span></span><span class="marq-item">Premium Quality <span>✦</span></span><span class="marq-item">Worldwide Shipping <span>✦</span></span><span class="marq-item">Exclusive Brands <span>✦</span></span><span class="marq-item">Secure Checkout <span>✦</span></span><span class="marq-item">New Arrivals Weekly <span>✦</span></span>
</div></div>

<section class="section">
  <div class="sec-hdr">
    <h2 class="sec-title">Shop by <em>Category</em></h2>
    <button class="see-all" onclick="setF('all',null)">All categories →</button>
  </div>
  <div class="cats">
    <div class="cat-card" onclick="setF('fashion',null)"><div class="cat-bg cb1">👗</div><div class="cat-ov"></div><div class="cat-lbl"><h3>Fashion</h3><p>14 items</p></div></div>
    <div class="cat-card" onclick="setF('home',null)"><div class="cat-bg cb2">🏠</div><div class="cat-ov"></div><div class="cat-lbl"><h3>Home</h3><p>6 items</p></div></div>
    <div class="cat-card" onclick="setF('beauty',null)"><div class="cat-bg cb3">💄</div><div class="cat-ov"></div><div class="cat-lbl"><h3>Beauty</h3><p>5 items</p></div></div>
    <div class="cat-card" onclick="setF('accessories',null)"><div class="cat-bg cb4">⌚</div><div class="cat-ov"></div><div class="cat-lbl"><h3>Accessories</h3><p>4 items</p></div></div>
    <div class="cat-card" onclick="setF('wellness',null)"><div class="cat-bg cb5">🧘</div><div class="cat-ov"></div><div class="cat-lbl"><h3>Wellness</h3><p>5 items</p></div></div>
    <div class="cat-card" onclick="setF('tech',null)"><div class="cat-bg cb6">💻</div><div class="cat-ov"></div><div class="cat-lbl"><h3>Tech</h3><p>4 items</p></div></div>
  </div>
</section>

<section class="section" id="products" style="padding-top:0">
  <div class="sec-hdr">
    <h2 class="sec-title" id="secTitle">All <em>Products</em></h2>
    <span class="see-all" id="resCount">38 items</span>
  </div>
  <div class="toolbar">
    <div class="filter-bar" id="filterBar">
      <button class="fbtn active" data-cat="all" onclick="setF('all',null)">All</button>
      <button class="fbtn" data-cat="fashion" onclick="setF('fashion',null)">Fashion</button>
      <button class="fbtn" data-cat="home" onclick="setF('home',null)">Home</button>
      <button class="fbtn" data-cat="beauty" onclick="setF('beauty',null)">Beauty</button>
      <button class="fbtn" data-cat="accessories" onclick="setF('accessories',null)">Accessories</button>
      <button class="fbtn" data-cat="wellness" onclick="setF('wellness',null)">Wellness</button>
      <button class="fbtn" data-cat="tech" onclick="setF('tech',null)">Tech</button>
      <button class="fbtn" data-cat="sale" onclick="setF('sale',null)">🏷 Sale</button>
    </div>
    <div class="tb-right">
      <select class="sort-sel" id="sortSel" onchange="renderPage()">
        <option value="default">Featured</option>
        <option value="price-asc">Price ↑</option>
        <option value="price-desc">Price ↓</option>
        <option value="rating">Top Rated</option>
        <option value="newest">Newest</option>
      </select>
      <div class="view-btns">
        <button class="vbtn active" id="gvBtn" onclick="setView('grid')" title="Grid view">⊞</button>
        <button class="vbtn" id="lvBtn" onclick="setView('list')" title="List view">☰</button>
      </div>
    </div>
  </div>
  <div class="pgrid" id="pgrid"></div>
  <div class="pager" id="pager"></div>
</section>

<div class="ban-wrap">
  <div class="banner">
    <div class="ban-txt">
      <span class="eyebrow">✦ Limited Time</span>
      <h2>End of Season<br><em>Sale Event</em></h2>
      <p>Up to 50% off on premium fashion, beauty essentials and lifestyle products.</p>
      <button class="btn-gold" onclick="setF('sale',null)">Shop the Sale →</button>
    </div>
    <div class="ban-vis">🎁</div>
  </div>
</div>

<div class="trust">
  <div class="trust-in">
    <div class="titem"><div class="ticon">🚚</div><div class="ttxt"><h4>Free Shipping</h4><p>On orders over $75</p></div></div>
    <div class="titem"><div class="ticon">↩️</div><div class="ttxt"><h4>Easy Returns</h4><p>30-day return policy</p></div></div>
    <div class="titem"><div class="ticon">🔒</div><div class="ttxt"><h4>Secure Payment</h4><p>256-bit SSL encryption</p></div></div>
    <div class="titem"><div class="ticon">🏆</div><div class="ttxt"><h4>Premium Quality</h4><p>Curated luxury brands</p></div></div>
  </div>
</div>

<section class="nl">
  <div class="eyebrow" style="color:var(--gold);font-size:.72rem;letter-spacing:2px;text-transform:uppercase;font-weight:600">✦ Stay in the loop</div>
  <h2>Join the <em style="font-style:italic;color:var(--gold-light)">LUXE</em> Community</h2>
  <p>Exclusive early access, private sales & style guides. No spam, ever.</p>
  <div class="nl-form">
    <input type="email" id="nlEmail" placeholder="Your email address…">
    <button onclick="subscribe()">Subscribe</button>
  </div>
</section>

<footer>
  <div class="fgrid">
    <div class="fbrand">
      <a href="#" class="logo">LUX<span style="color:var(--gold)">E</span></a>
      <p>Premium curated shopping for fashion-forward individuals who appreciate quality, craft, and style.</p>
      <div class="fsoc">
        <button class="sbtn">𝕏</button><button class="sbtn">in</button><button class="sbtn">📷</button><button class="sbtn">📌</button>
      </div>
    </div>
    <div class="fcol"><h4>Shop</h4><a href="#">New Arrivals</a><a href="#">Best Sellers</a><a href="#">Sale</a><a href="#">Gift Cards</a><a href="#">Brands</a></div>
    <div class="fcol"><h4>Help</h4><a href="#">FAQs</a><a href="#">Shipping & Returns</a><a href="#">Track Order</a><a href="#">Size Guide</a><a href="#">Contact</a></div>
    <div class="fcol"><h4>Company</h4><a href="#">About LUXE</a><a href="#">Sustainability</a><a href="#">Careers</a><a href="#">Press</a></div>
    <div class="fcol"><h4>Legal</h4><a href="#">Privacy Policy</a><a href="#">Terms</a><a href="#">Cookies</a><a href="#">Accessibility</a></div>
  </div>
  <div class="fbot">
    <p>© 2026 LUXE. All rights reserved.</p>
    <div class="picons"><span class="pic">VISA</span><span class="pic">MC</span><span class="pic">AMEX</span><span class="pic">PayPal</span><span class="pic">Apple</span></div>
  </div>
</footer>

<!-- CART -->
<div class="cart-ov" id="cartOv" onclick="toggleCart()"></div>
<div class="cart-dr" id="cartDr">
  <div class="chdr"><h3>Shopping Bag</h3><div class="chdr-r"><button class="clr-btn" onclick="clearCart()">Clear all</button><button class="clos" onclick="toggleCart()">×</button></div></div>
  <div class="citems" id="cartItems"></div>
  <div class="cftr" id="cartFtr" style="display:none">
    <div class="csub"><span>Subtotal</span><span id="cSub">$0.00</span></div>
    <div class="ctot"><span>Total</span><span id="cTot">$0.00</span></div>
    <button class="ckbtn" onclick="checkout()">Checkout →</button>
  </div>
</div>

<!-- MODAL -->
<div class="modal-ov" id="modalOv" onclick="closeMod(event)">
  <div class="modal" id="modalBox">
    <div class="mimg" id="mImg"></div>
    <div class="mbody" id="mBody"></div>
  </div>
</div>

<!-- SEARCH -->
<div class="srch-ov" id="srchOv">
  <button class="srch-clos" onclick="closeSrch()">×</button>
  <div class="srch-wrap"><span class="srch-ico">🔍</span><input class="srch-inp" id="srchInp" placeholder="Search products, brands, tags…" oninput="doSrch(this.value)"></div>
  <div class="srch-hint">Try "silk", "candle", "gold", "yoga"…</div>
  <div class="srch-res" id="srchRes"></div>
</div>

<div class="toast" id="toast"></div>
<button class="btop" id="btop" onclick="window.scrollTo({top:0,behavior:'smooth'})">↑</button>

<script>
const P=[
  {id:1, name:'Silk Evening Dress',       brand:'Maison Éclat',  price:289,oldPrice:null,badge:'new', emoji:'👗',bg:'p1', cat:'fashion',    stars:5,rev:124, desc:'Flowing silk evening dress with delicate hand-stitched details. Perfect for formal occasions.',tags:['silk','evening','formal']},
  {id:2, name:'Cashmere Sweater',          brand:'Maison Éclat',  price:320,oldPrice:400, badge:'sale',emoji:'🧥',bg:'p6', cat:'fashion',    stars:5,rev:156, desc:'Ultra-soft Grade-A Mongolian cashmere in a timeless ribbed silhouette.',tags:['cashmere','knitwear','winter']},
  {id:3, name:'Tailored Blazer',           brand:'Atelier Noir',  price:445,oldPrice:560, badge:'sale',emoji:'🥼',bg:'p7', cat:'fashion',    stars:5,rev:88,  desc:'Sharp Italian wool blazer with single-button closure and structured silhouette.',tags:['blazer','tailored','office']},
  {id:4, name:'Linen Wide-Leg Trousers',   brand:'Studio Claire', price:165,oldPrice:null,badge:'new', emoji:'👖',bg:'p3', cat:'fashion',    stars:4,rev:72,  desc:'Breathable summer linen in an elegant wide-leg cut. Effortlessly chic.',tags:['linen','summer','trousers']},
  {id:5, name:'Silk Blouse',               brand:'Maison Éclat',  price:195,oldPrice:240, badge:'sale',emoji:'👚',bg:'p13',cat:'fashion',    stars:4,rev:95,  desc:'Luxurious silk blouse with relaxed draped collar and pearl buttons.',tags:['silk','blouse','work']},
  {id:6, name:'Trench Coat',               brand:'Atelier Noir',  price:590,oldPrice:720, badge:'sale',emoji:'🧤',bg:'p10',cat:'fashion',    stars:5,rev:210, desc:'Classic double-breasted trench in water-resistant cotton gabardine.',tags:['coat','outerwear','classic']},
  {id:7, name:'Wrap Midi Dress',           brand:'Studio Claire', price:215,oldPrice:null,badge:'hot', emoji:'💃',bg:'p6', cat:'fashion',    stars:5,rev:183, desc:'Flattering wrap silhouette in fluid jersey. Adjustable tie waist.',tags:['dress','wrap','versatile']},
  {id:8, name:'High-Waist Jeans',          brand:'Denim & Co.',   price:148,oldPrice:185, badge:'sale',emoji:'🩲',bg:'p2', cat:'fashion',    stars:4,rev:340, desc:'Premium Japanese selvedge denim in a flattering high-waist slim cut.',tags:['denim','jeans','everyday']},
  {id:9, name:'Leather Loafers',           brand:'Aurum Studio',  price:280,oldPrice:null,badge:'new', emoji:'👟',bg:'p9', cat:'fashion',    stars:5,rev:67,  desc:'Hand-crafted Italian leather loafers with cushioned insole and Goodyear welt.',tags:['shoes','leather','loafers']},
  {id:10,name:'Slip Dress',                brand:'Maison Éclat',  price:175,oldPrice:220, badge:'sale',emoji:'👗',bg:'p4', cat:'fashion',    stars:4,rev:112, desc:'Bias-cut satin slip dress. Day-to-night versatility.',tags:['slip','satin','evening']},
  {id:11,name:'Merino Turtleneck',         brand:'Studio Claire', price:135,oldPrice:null,badge:null,  emoji:'🧣',bg:'p11',cat:'fashion',    stars:5,rev:89,  desc:'Ultrafine merino wool turtleneck. Thermoregulating and machine washable.',tags:['merino','knitwear','winter']},
  {id:12,name:'Pleated Midi Skirt',        brand:'Atelier Noir',  price:198,oldPrice:245, badge:'sale',emoji:'🩱',bg:'p5', cat:'fashion',    stars:4,rev:58,  desc:'Elegant pleated midi skirt in flowing viscose.',tags:['skirt','pleated','feminine']},
  {id:13,name:'Structured Tote Bag',       brand:'Aurum Studio',  price:395,oldPrice:null,badge:'new', emoji:'👜',bg:'p8', cat:'fashion',    stars:5,rev:145, desc:'Full-grain leather tote with suede interior and gold hardware.',tags:['bag','leather','tote']},
  {id:14,name:'Ankle Boots',               brand:'Aurum Studio',  price:340,oldPrice:425, badge:'sale',emoji:'👢',bg:'p16',cat:'fashion',    stars:5,rev:203, desc:'Block-heel ankle boots in burnished Italian leather.',tags:['boots','leather','shoes']},
  {id:15,name:'Artisan Candle Set',        brand:'Lumière Home',  price:68, oldPrice:85,  badge:'sale',emoji:'🕯️',bg:'p2', cat:'home',       stars:4,rev:89,  desc:'Set of three hand-poured soy wax candles: amber, cedarwood, bergamot. 45hr burn each.',tags:['candles','fragrance','gift']},
  {id:16,name:'Linen Throw Blanket',       brand:'Casa Luxe',     price:95, oldPrice:null,badge:null,  emoji:'🛋️',bg:'p5', cat:'home',       stars:5,rev:43,  desc:'Stonewashed French linen throw in earthy tones. Pre-washed for softness.',tags:['linen','blanket','bedroom']},
  {id:17,name:'Ceramic Vase Set',          brand:'Casa Luxe',     price:120,oldPrice:150, badge:'sale',emoji:'🏺',bg:'p12',cat:'home',       stars:5,rev:61,  desc:'Set of three handmade ceramic vases in matte earth tones.',tags:['ceramic','vase','decor']},
  {id:18,name:'Linen Bed Set',             brand:'Lumière Home',  price:245,oldPrice:null,badge:'new', emoji:'🛏️',bg:'p7', cat:'home',       stars:5,rev:114, desc:'100% stonewashed French linen duvet cover and pillowcase. OEKO-TEX certified.',tags:['linen','bedding','bedroom']},
  {id:19,name:'Reed Diffuser',             brand:'Lumière Home',  price:58, oldPrice:72,  badge:'sale',emoji:'🌿',bg:'p9', cat:'home',       stars:4,rev:77,  desc:'6-month reed diffuser in Neroli & White Tea. Non-toxic, sustainably made.',tags:['diffuser','fragrance','home']},
  {id:20,name:'Marble Serving Board',      brand:'Casa Luxe',     price:88, oldPrice:null,badge:'hot', emoji:'🪨',bg:'p3', cat:'home',       stars:5,rev:39,  desc:'Hand-finished Carrara marble serving board with walnut handles.',tags:['marble','kitchen','hosting']},
  {id:21,name:'Velvet Blush Palette',      brand:'Éclat Beauty',  price:52, oldPrice:null,badge:'hot', emoji:'💄',bg:'p3', cat:'beauty',     stars:5,rev:210, desc:'12-shade editorial blush and bronzer palette. Highly pigmented and blendable.',tags:['blush','palette','makeup']},
  {id:22,name:'Perfume Édition Rare',      brand:'Olfac Paris',   price:175,oldPrice:null,badge:'new', emoji:'🧴',bg:'p7', cat:'beauty',     stars:4,rev:92,  desc:'Eau de parfum: iris, saffron, rose heart, oud and amber base.',tags:['perfume','fragrance','luxury']},
  {id:23,name:'Gold Face Serum',           brand:'Éclat Beauty',  price:128,oldPrice:160, badge:'sale',emoji:'✨',bg:'p16',cat:'beauty',     stars:5,rev:188, desc:'24K gold and vitamin C brightening serum. Reduces dark spots in 4 weeks.',tags:['serum','skincare','gold']},
  {id:24,name:'Lip Gloss Collection',      brand:'Éclat Beauty',  price:38, oldPrice:null,badge:null,  emoji:'💋',bg:'p6', cat:'beauty',     stars:4,rev:156, desc:'Five non-sticky high-shine lip glosses in nudes and berries.',tags:['lips','gloss','makeup']},
  {id:25,name:'Retinol Night Cream',       brand:'Olfac Paris',   price:95, oldPrice:118, badge:'sale',emoji:'🌙',bg:'p4', cat:'beauty',     stars:5,rev:74,  desc:'Encapsulated retinol and hyaluronic acid night cream. Firms skin overnight.',tags:['retinol','skincare','night']},
  {id:26,name:'Gold Chain Bracelet',       brand:'Aurum Studio',  price:145,oldPrice:190, badge:'sale',emoji:'📿',bg:'p4', cat:'accessories',stars:4,rev:67,  desc:'18K gold-plated chain bracelet. Hypoallergenic and tarnish-resistant.',tags:['gold','bracelet','jewellery']},
  {id:27,name:'Leather Mini Bag',          brand:'Aurum Studio',  price:235,oldPrice:null,badge:'hot', emoji:'👜',bg:'p8', cat:'accessories',stars:5,rev:178, desc:'Pebbled leather mini crossbody with adjustable chain strap.',tags:['bag','leather','crossbody']},
  {id:28,name:'Silk Scarf',                brand:'Maison Éclat',  price:98, oldPrice:null,badge:'new', emoji:'🧣',bg:'p1', cat:'accessories',stars:5,rev:55,  desc:'Hand-rolled 100% twill silk scarf with original botanical print. 90×90cm.',tags:['scarf','silk','print']},
  {id:29,name:'Sunglasses',                brand:'Atelier Noir',  price:185,oldPrice:225, badge:'sale',emoji:'🕶️',bg:'p15',cat:'accessories',stars:4,rev:102, desc:'Oversized acetate frames with polarized UV400 lenses.',tags:['sunglasses','summer','UV']},
  {id:30,name:'Yoga Mat Premium',          brand:'Zen Studio',    price:88, oldPrice:110, badge:'sale',emoji:'🧘',bg:'p5', cat:'wellness',   stars:5,rev:134, desc:'6mm natural rubber yoga mat with alignment guides and microfibre surface.',tags:['yoga','fitness','mat']},
  {id:31,name:'Himalayan Salt Lamp',       brand:'Zen Studio',    price:55, oldPrice:null,badge:null,  emoji:'🪔',bg:'p10',cat:'wellness',   stars:4,rev:87,  desc:'Authentic Himalayan crystal salt lamp with dimmer switch.',tags:['salt','lamp','ambience']},
  {id:32,name:'Essential Oil Set',         brand:'Lumière Home',  price:72, oldPrice:90,  badge:'sale',emoji:'🫙',bg:'p9', cat:'wellness',   stars:5,rev:61,  desc:'6 pure essential oils: Lavender, Eucalyptus, Peppermint, Tea Tree, Lemon & Frankincense.',tags:['oils','aromatherapy','gift']},
  {id:33,name:'Meditation Cushion',        brand:'Zen Studio',    price:65, oldPrice:null,badge:'new', emoji:'🪑',bg:'p12',cat:'wellness',   stars:4,rev:48,  desc:'Buckwheat-filled zafu cushion in organic cotton. Ergonomic for long sessions.',tags:['meditation','cushion','yoga']},
  {id:34,name:'Jade Roller Set',           brand:'Éclat Beauty',  price:45, oldPrice:58,  badge:'sale',emoji:'💚',bg:'p11',cat:'wellness',   stars:5,rev:219, desc:'Genuine jade facial roller and gua sha set. Promotes lymphatic drainage.',tags:['jade','beauty','skincare']},
  {id:35,name:'Wireless Earbuds',          brand:'SoundLuxe',     price:189,oldPrice:240, badge:'sale',emoji:'🎧',bg:'p14',cat:'tech',       stars:5,rev:304, desc:'Hybrid ANC, 28hr battery, IPX5 water resistance and custom EQ app.',tags:['audio','wireless','ANC']},
  {id:36,name:'Smart Watch',               brand:'SoundLuxe',     price:295,oldPrice:null,badge:'hot', emoji:'⌚',bg:'p2', cat:'tech',       stars:5,rev:178, desc:'AMOLED display, 14-day battery, health tracking, GPS and NFC payments.',tags:['watch','fitness','smart']},
  {id:37,name:'Portable Charger',          brand:'SoundLuxe',     price:68, oldPrice:85,  badge:'sale',emoji:'🔋',bg:'p15',cat:'tech',       stars:4,rev:93,  desc:'20,000mAh MagSafe-compatible power bank with 65W USB-C PD.',tags:['charger','power','MagSafe']},
  {id:38,name:'Desk Lamp Wireless',        brand:'Casa Luxe',     price:115,oldPrice:null,badge:'new', emoji:'💡',bg:'p13',cat:'tech',       stars:5,rev:57,  desc:'Dimmable LED desk lamp with USB-C port and wireless charging pad in the base.',tags:['lamp','LED','desk','wireless']},
];

const PER=12;
let cart=[],wl=new Set(),af='all',cp=1,view='grid',mq=1;

function getList(){
  let l=af==='all'?[...P]:af==='sale'?P.filter(x=>x.oldPrice):P.filter(x=>x.cat===af);
  const s=document.getElementById('sortSel').value;
  if(s==='price-asc')l.sort((a,b)=>a.price-b.price);
  if(s==='price-desc')l.sort((a,b)=>b.price-a.price);
  if(s==='rating')l.sort((a,b)=>b.stars-a.stars||b.rev-a.rev);
  if(s==='newest')l.sort((a,b)=>(b.badge==='new'?1:0)-(a.badge==='new'?1:0));
  return l;
}

function setF(cat,e){
  if(e&&e.preventDefault)e.preventDefault();
  af=cat; cp=1;
  document.querySelectorAll('.fbtn').forEach(b=>b.classList.toggle('active',b.dataset.cat===cat));
  document.querySelectorAll('#mainNav a').forEach(a=>a.classList.toggle('nav-active',a.textContent.toLowerCase()===cat));
  const t={all:'All',fashion:'Fashion',home:'Home',beauty:'Beauty',accessories:'Accessories',wellness:'Wellness',tech:'Tech',sale:'On Sale'};
  document.getElementById('secTitle').innerHTML=`${t[cat]||cat} <em>Products</em>`;
  renderPage();
  document.getElementById('products').scrollIntoView({behavior:'smooth',block:'start'});
}

function renderPage(){
  const list=getList(),total=list.length,pages=Math.ceil(total/PER);
  const slice=list.slice((cp-1)*PER,cp*PER);
  document.getElementById('resCount').textContent=`${total} item${total!==1?'s':''}`;
  const g=document.getElementById('pgrid');
  g.className='pgrid'+(view==='list'?' lv':'');
  g.innerHTML=slice.map((p,i)=>card(p,i)).join('');
  renderPager(pages);
}

function card(p,i){
  const sf='★'.repeat(p.stars),se='☆'.repeat(5-p.stars);
  const disc=p.oldPrice?Math.round((1-p.price/p.oldPrice)*100):0;
  const bc={new:'bn',sale:'bs',hot:'bh',eco:'be'};
  return`<div class="pcard" style="animation-delay:${i*.045}s" onclick="openMod(${p.id})">
    <div class="pimg">
      <div class="pthumb ${p.bg}">${p.emoji}</div>
      ${p.badge?`<div class="pbadge ${bc[p.badge]}">${p.badge}${disc?` -${disc}%`:''}</div>`:''}
      <button class="wbtn" onclick="togWl(${p.id},event)">${wl.has(p.id)?'❤️':'🤍'}</button>
      <div class="pactions"><button class="qadd" onclick="addCart(${p.id},event)">+ Add to Bag</button></div>
    </div>
    <div class="pinfo">
      <div class="pbrand">${p.brand}</div>
      <div class="pname">${p.name}</div>
      <div class="ppricing">
        <span class="pprice${p.oldPrice?' ppsale':''}">$${p.price}</span>
        ${p.oldPrice?`<span class="ppold">$${p.oldPrice}</span>`:''}
      </div>
      <div class="pstars"><span class="sf">${sf}</span><span class="se">${se}</span><span class="sc">(${p.rev})</span></div>
    </div>
  </div>`;
}

function renderPager(pages){
  const pg=document.getElementById('pager');
  if(pages<=1){pg.innerHTML='';return;}
  let h=`<button class="pgbtn" onclick="goP(${cp-1})" ${cp===1?'disabled':''}>‹</button>`;
  for(let i=1;i<=pages;i++){
    if(pages>7&&i>2&&i<pages-1&&Math.abs(i-cp)>1){if(i===3||i===pages-2)h+=`<span style="padding:0 4px;color:var(--muted)">…</span>`;continue;}
    h+=`<button class="pgbtn${i===cp?' active':''}" onclick="goP(${i})">${i}</button>`;
  }
  h+=`<button class="pgbtn" onclick="goP(${cp+1})" ${cp===pages?'disabled':''}>›</button>`;
  pg.innerHTML=h;
}

function goP(n){
  const pages=Math.ceil(getList().length/PER);
  if(n<1||n>pages)return;
  cp=n; renderPage();
  document.getElementById('products').scrollIntoView({behavior:'smooth',block:'start'});
}

function setView(v){
  view=v;
  document.getElementById('gvBtn').classList.toggle('active',v==='grid');
  document.getElementById('lvBtn').classList.toggle('active',v==='list');
  renderPage();
}

/* MODAL */
function openMod(id){
  const p=P.find(x=>x.id===id); if(!p)return;
  mq=1;
  const disc=p.oldPrice?Math.round((1-p.price/p.oldPrice)*100):0;
  document.getElementById('mImg').className='mimg '+p.bg;
  document.getElementById('mImg').innerHTML=p.emoji;
  document.getElementById('mBody').innerHTML=`
    <button class="mclos" onclick="closeMod2()">×</button>
    <div class="mbrand">${p.brand}</div>
    <div class="mname">${p.name}</div>
    <div class="mprice">
      <span class="${p.oldPrice?'msale':''}">$${p.price}</span>
      ${p.oldPrice?`<span class="mold">$${p.oldPrice}</span><span style="color:var(--red);font-size:.78rem;margin-left:6px;font-weight:700">-${disc}%</span>`:''}
    </div>
    <div class="mdesc">${p.desc}</div>
    <div class="mqrow">
      <span class="mqlbl">Qty</span>
      <div class="mqbox">
        <button class="qbtn" onclick="chMq(-1)">−</button>
        <span class="qval" id="mqv">1</span>
        <button class="qbtn" onclick="chMq(1)">+</button>
      </div>
    </div>
    <div style="display:flex;gap:10px">
      <button class="madd" onclick="addCartQ(${p.id})">Add to Bag</button>
      <button style="padding:12px 14px;border:2px solid var(--ink);background:none;border-radius:2px;cursor:pointer;font-size:1.1rem" onclick="togWl(${p.id},event)">${wl.has(p.id)?'❤️':'🤍'}</button>
    </div>
    <div class="mtags">${p.tags.map(t=>`<span class="mtag">${t}</span>`).join('')}</div>
  `;
  document.getElementById('modalOv').classList.add('open');
  document.body.style.overflow='hidden';
}
function chMq(d){mq=Math.max(1,mq+d);document.getElementById('mqv').textContent=mq;}
function addCartQ(id){const p=P.find(x=>x.id===id);const ex=cart.find(x=>x.id===id);if(ex)ex.qty+=mq;else cart.push({...p,qty:mq});updCart();toast(`${p.name} × ${mq} added ✦`);closeMod2();}
function closeMod(e){if(e.target===document.getElementById('modalOv'))closeMod2();}
function closeMod2(){document.getElementById('modalOv').classList.remove('open');document.body.style.overflow='';}

/* CART */
function addCart(id,e){if(e)e.stopPropagation();const p=P.find(x=>x.id===id);const ex=cart.find(x=>x.id===id);if(ex)ex.qty++;else cart.push({...p,qty:1});updCart();toast(`${p.name} added ✦`);}
function updCart(){
  const tot=cart.reduce((s,x)=>s+x.price*x.qty,0),cnt=cart.reduce((s,x)=>s+x.qty,0);
  document.getElementById('cartBadge').textContent=cnt;
  const el=document.getElementById('cartItems'),ftr=document.getElementById('cartFtr');
  if(!cart.length){el.innerHTML=`<div class="cempty"><div class="cempty-ic">🛍️</div><p>Your bag is empty.<br>Time to add some luxuries!</p></div>`;ftr.style.display='none';return;}
  ftr.style.display='block';
  document.getElementById('cSub').textContent=`$${tot.toFixed(2)}`;
  document.getElementById('cTot').textContent=`$${tot.toFixed(2)}`;
  el.innerHTML=cart.map(it=>`<div class="citem">
    <div class="citem-img ${it.bg}">${it.emoji}</div>
    <div class="citem-inf">
      <div class="citem-name">${it.name}</div>
      <div class="citem-price">${it.brand} · $${it.price}</div>
      <div class="citem-bot">
        <div class="qty-row"><button class="qbtn" onclick="chQ(${it.id},-1)">−</button><span class="qval">${it.qty}</span><button class="qbtn" onclick="chQ(${it.id},1)">+</button></div>
        <button class="rem-btn" onclick="remItem(${it.id})">Remove</button>
      </div>
    </div>
  </div>`).join('');
}
function chQ(id,d){const it=cart.find(x=>x.id===id);if(!it)return;it.qty+=d;if(it.qty<=0)cart=cart.filter(x=>x.id!==id);updCart();}
function remItem(id){cart=cart.filter(x=>x.id!==id);updCart();}
function clearCart(){cart=[];updCart();toast('Cart cleared');}
function toggleCart(){document.getElementById('cartDr').classList.toggle('open');document.getElementById('cartOv').classList.toggle('open');}
function checkout(){toast('Redirecting to checkout… ✦');setTimeout(toggleCart,1200);}

/* WISHLIST */
function togWl(id,e){if(e)e.stopPropagation();const p=P.find(x=>x.id===id);wl.has(id)?(wl.delete(id),toast('Removed from wishlist')):(wl.add(id),toast(`${p.name} saved ♡`));renderPage();}

/* SEARCH */
function openSrch(){document.getElementById('srchOv').classList.add('open');document.getElementById('srchInp').focus();document.body.style.overflow='hidden';}
function closeSrch(){document.getElementById('srchOv').classList.remove('open');document.body.style.overflow='';document.getElementById('srchInp').value='';document.getElementById('srchRes').innerHTML='';}
function doSrch(q){
  const r=document.getElementById('srchRes');
  if(!q.trim()){r.innerHTML='';return;}
  const m=P.filter(p=>p.name.toLowerCase().includes(q.toLowerCase())||p.brand.toLowerCase().includes(q.toLowerCase())||p.tags.some(t=>t.includes(q.toLowerCase())));
  if(!m.length){r.innerHTML=`<p style="color:var(--muted);grid-column:1/-1">No results for "${q}"</p>`;return;}
  r.innerHTML=m.slice(0,9).map(p=>`
    <div onclick="closeSrch();openMod(${p.id})" style="background:#fff;border:1px solid var(--border);border-radius:6px;overflow:hidden;cursor:pointer;transition:transform .2s" onmouseover="this.style.transform='translateY(-2px)'" onmouseout="this.style.transform=''">
      <div class="${p.bg}" style="height:90px;display:flex;align-items:center;justify-content:center;font-size:2.2rem">${p.emoji}</div>
      <div style="padding:10px">
        <div style="font-size:.68rem;color:var(--muted);text-transform:uppercase">${p.brand}</div>
        <div style="font-size:.85rem;font-weight:500">${p.name}</div>
        <div style="font-weight:700;font-size:.88rem;margin-top:3px;color:${p.oldPrice?'var(--red)':'inherit'}">$${p.price}</div>
      </div>
    </div>`).join('');
}

/* MOBILE NAV */
function toggleMob(){const n=document.getElementById('mobNav'),h=document.getElementById('hamburger');const o=n.classList.toggle('open');h.classList.toggle('open',o);document.body.style.overflow=o?'hidden':'';}
function closeMob(){document.getElementById('mobNav').classList.remove('open');document.getElementById('hamburger').classList.remove('open');document.body.style.overflow='';}

/* MISC */
function subscribe(){const i=document.getElementById('nlEmail');i.value&&i.value.includes('@')?(toast('Welcome to LUXE! Check your inbox ✦'),i.value=''):toast('Please enter a valid email');}
function scrollToP(){document.getElementById('products').scrollIntoView({behavior:'smooth'});}

let tt;
function toast(msg){const t=document.getElementById('toast');t.textContent=msg;t.classList.add('show');clearTimeout(tt);tt=setTimeout(()=>t.classList.remove('show'),2600);}

window.addEventListener('scroll',()=>document.getElementById('btop').classList.toggle('vis',scrollY>500));
document.addEventListener('keydown',e=>{if(e.key==='Escape'){closeSrch();closeMod2();closeMob();}if(e.key==='/'&&!document.getElementById('srchOv').classList.contains('open')){e.preventDefault();openSrch();}});

updCart();renderPage();
</script>
</body>
</html>
