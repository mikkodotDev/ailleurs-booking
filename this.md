<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ailleurs — Curated Journeys for the Curious</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400;1,600&family=Josefin+Sans:wght@300;400;600&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --cream:#f5f0e8;--cream2:#ede6d6;--cream3:#e2d9c5;
  --sand:#c9b99a;--gold:#b8913a;--gold2:#d4a843;--gold-lt:#e8c96e;
  --ink:#1c1510;--ink2:#3a2e24;--ink3:#6b5a48;--ink4:#9c8878;
  --white:#fdfaf4;
  --serif:'Cormorant Garamond',Georgia,serif;
  --sans:'Josefin Sans',sans-serif;
}
html{font-size:16px;scroll-behavior:smooth}
body{background:var(--cream);color:var(--ink);font-family:var(--sans);font-weight:300;line-height:1.6;overflow-x:hidden}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:200;display:flex;align-items:center;justify-content:space-between;padding:1.4rem 3.5rem;transition:background .4s,backdrop-filter .4s}
nav.scrolled{background:rgba(245,240,232,0.94);backdrop-filter:blur(10px);border-bottom:1px solid rgba(201,185,154,0.4)}
.nav-logo{font-family:var(--serif);font-size:1.6rem;font-weight:600;letter-spacing:.12em;color:var(--white);text-transform:uppercase;transition:color .4s}
nav.scrolled .nav-logo{color:var(--ink)}
.nav-links{display:flex;gap:2.5rem;list-style:none}
.nav-links a{font-family:var(--sans);font-size:.68rem;letter-spacing:.22em;text-transform:uppercase;color:rgba(255,255,255,.8);text-decoration:none;transition:color .2s;font-weight:400}
nav.scrolled .nav-links a{color:var(--ink3)}
.nav-links a:hover,.nav.scrolled .nav-links a:hover{color:var(--gold2)}
.nav-book{font-family:var(--sans);font-size:.65rem;letter-spacing:.2em;text-transform:uppercase;font-weight:600;padding:.6rem 1.4rem;border:1px solid rgba(255,255,255,.5);color:var(--white);background:transparent;cursor:pointer;transition:all .25s}
nav.scrolled .nav-book{border-color:var(--gold);color:var(--gold)}
.nav-book:hover{background:var(--gold);border-color:var(--gold);color:var(--ink)}

/* HERO */
.hero{height:100vh;min-height:700px;position:relative;display:flex;align-items:flex-end;overflow:hidden}
.hero-bg{position:absolute;inset:0;background:linear-gradient(to bottom,rgba(28,21,16,.25) 0%,rgba(28,21,16,.05) 35%,rgba(28,21,16,.7) 100%),linear-gradient(135deg,#2c4a3e 0%,#3d6b5a 18%,#7a9e7e 38%,#c4a882 58%,#8b6914 78%,#5c3d11 100%);background-size:cover}
.hero-bg::after{content:'';position:absolute;inset:0;background-image:url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Ccircle cx='30' cy='30' r='1' fill='%23ffffff' fill-opacity='0.025'/%3E%3C/svg%3E")}
.hero-mountains{position:absolute;bottom:0;left:0;right:0;height:55%;pointer-events:none}
.hero-mountains svg{width:100%;height:100%}
.hero-content{position:relative;z-index:2;padding:0 3.5rem 5.5rem;max-width:800px;animation:heroIn 1.2s cubic-bezier(.16,1,.3,1) both}
@keyframes heroIn{from{opacity:0;transform:translateY(28px)}to{opacity:1;transform:translateY(0)}}
.hero-label{font-family:var(--sans);font-size:.65rem;letter-spacing:.35em;text-transform:uppercase;color:var(--gold2);margin-bottom:1.2rem;display:flex;align-items:center;gap:.8rem;animation:heroIn 1.2s .1s cubic-bezier(.16,1,.3,1) both}
.hero-label::before{content:'';display:inline-block;width:36px;height:1px;background:var(--gold2)}
.hero-title{font-family:var(--serif);font-size:clamp(3.2rem,8vw,7rem);font-weight:300;line-height:.95;letter-spacing:-.01em;color:var(--white);margin-bottom:1.4rem;animation:heroIn 1.2s .2s cubic-bezier(.16,1,.3,1) both}
.hero-title em{font-style:italic;color:var(--gold-lt)}
.hero-sub{font-family:var(--sans);font-size:.82rem;letter-spacing:.1em;color:rgba(245,240,232,.7);max-width:420px;line-height:1.9;margin-bottom:2.4rem;animation:heroIn 1.2s .3s cubic-bezier(.16,1,.3,1) both}
.hero-actions{display:flex;gap:1rem;align-items:center;flex-wrap:wrap;animation:heroIn 1.2s .4s cubic-bezier(.16,1,.3,1) both}
.btn-gold{font-family:var(--sans);font-size:.68rem;letter-spacing:.22em;text-transform:uppercase;font-weight:600;padding:.95rem 2.2rem;background:var(--gold);color:var(--ink);border:none;cursor:pointer;transition:all .25s;position:relative;overflow:hidden}
.btn-gold::after{content:'';position:absolute;inset:0;background:linear-gradient(90deg,transparent,rgba(255,255,255,.25),transparent);transform:translateX(-100%);transition:transform .5s}
.btn-gold:hover::after{transform:translateX(100%)}
.btn-gold:hover{background:var(--gold2);box-shadow:0 8px 30px rgba(184,145,58,.4)}
.btn-ghost-w{font-family:var(--sans);font-size:.65rem;letter-spacing:.2em;text-transform:uppercase;padding:.9rem 1.8rem;border:1px solid rgba(255,255,255,.4);color:var(--white);background:transparent;cursor:pointer;transition:all .2s}
.btn-ghost-w:hover{background:rgba(255,255,255,.1);border-color:rgba(255,255,255,.7)}
.hero-scroll{position:absolute;bottom:2.5rem;right:3.5rem;z-index:2;display:flex;flex-direction:column;align-items:center;gap:.5rem;animation:heroIn 1.2s .6s cubic-bezier(.16,1,.3,1) both}
.hero-scroll-label{font-family:var(--sans);font-size:.55rem;letter-spacing:.3em;text-transform:uppercase;color:rgba(255,255,255,.5);writing-mode:vertical-rl}
.hero-scroll-line{width:1px;height:60px;background:linear-gradient(to bottom,rgba(255,255,255,.5),transparent);animation:scrollPulse 2s ease-in-out infinite}
@keyframes scrollPulse{0%,100%{opacity:.5}50%{opacity:1}}

/* SEARCH */
.search-bar{background:var(--white);margin:0 3.5rem;margin-top:-3rem;position:relative;z-index:10;box-shadow:0 20px 60px rgba(28,21,16,.15);display:flex;align-items:stretch}
.search-field{flex:1;padding:1.4rem 1.8rem;border-right:1px solid var(--cream3);display:flex;flex-direction:column;gap:.25rem;cursor:pointer}
.search-field:last-of-type{border-right:none}
.sf-label{font-family:var(--sans);font-size:.58rem;letter-spacing:.2em;text-transform:uppercase;color:var(--ink4);font-weight:600}
.sf-val{font-family:var(--serif);font-size:1.05rem;color:var(--ink);font-weight:500}
.search-btn{font-family:var(--sans);font-size:.65rem;letter-spacing:.22em;text-transform:uppercase;font-weight:600;padding:0 2.5rem;background:var(--gold);color:var(--ink);border:none;cursor:pointer;transition:background .2s;white-space:nowrap}
.search-btn:hover{background:var(--gold2)}

/* STATS */
.stats-strip{display:flex;justify-content:center;gap:5rem;padding:3.5rem 2rem;border-bottom:1px solid var(--cream3);flex-wrap:wrap}
.stat-num{font-family:var(--serif);font-size:2.6rem;font-weight:300;color:var(--gold);line-height:1;margin-bottom:.3rem}
.stat-label{font-family:var(--sans);font-size:.6rem;letter-spacing:.18em;text-transform:uppercase;color:var(--ink4)}

/* SECTIONS */
.sec{padding:6rem 3.5rem}
.s-label{font-family:var(--sans);font-size:.6rem;letter-spacing:.3em;text-transform:uppercase;color:var(--gold);margin-bottom:.7rem;display:flex;align-items:center;gap:.7rem}
.s-label::after{content:'';flex:1;max-width:60px;height:1px;background:var(--gold);opacity:.5}
.s-title{font-family:var(--serif);font-size:clamp(2.2rem,4vw,3.4rem);font-weight:300;line-height:1.1;letter-spacing:-.01em;color:var(--ink)}
.s-title em{font-style:italic;color:var(--gold)}
.s-sub{font-family:var(--sans);font-size:.78rem;letter-spacing:.06em;color:var(--ink3);max-width:500px;line-height:1.85;margin-top:.8rem}

/* DESTINATIONS */
.dest-header{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:3rem;gap:2rem;flex-wrap:wrap}
.filter-tabs{display:flex;border:1px solid var(--cream3);overflow:hidden}
.ftab{font-family:var(--sans);font-size:.62rem;letter-spacing:.15em;text-transform:uppercase;padding:.55rem 1.1rem;background:transparent;border:none;border-right:1px solid var(--cream3);cursor:pointer;color:var(--ink3);transition:all .2s;font-weight:400}
.ftab:last-child{border-right:none}
.ftab:hover{background:var(--cream2);color:var(--ink)}
.ftab.active{background:var(--gold);color:var(--ink)}

/* CARD GRID */
.cards-grid{display:grid;grid-template-columns:repeat(12,1fr);gap:1.2rem}
.dc{position:relative;overflow:hidden;cursor:pointer;background:var(--ink2)}
.dc:nth-child(1){grid-column:1/6;aspect-ratio:4/5}
.dc:nth-child(2){grid-column:6/9;aspect-ratio:3/5}
.dc:nth-child(3){grid-column:9/13;aspect-ratio:4/5}
.dc:nth-child(4){grid-column:1/5;grid-row:2;aspect-ratio:16/9}
.dc:nth-child(5){grid-column:5/9;grid-row:2;aspect-ratio:16/9}
.dc:nth-child(6){grid-column:9/13;grid-row:2;aspect-ratio:16/9}
.dc-img{position:absolute;inset:0;background-size:cover;background-position:center;transition:transform .7s cubic-bezier(.25,.46,.45,.94)}
.dc:hover .dc-img{transform:scale(1.07)}
.dc::after{content:'';position:absolute;inset:0;background:linear-gradient(to top,rgba(28,21,16,.9) 0%,rgba(28,21,16,.3) 40%,rgba(28,21,16,.05) 100%);transition:opacity .4s}
.dc:hover::after{background:linear-gradient(to top,rgba(28,21,16,.95) 0%,rgba(28,21,16,.45) 55%,rgba(28,21,16,.1) 100%)}
.dc-content{position:absolute;bottom:0;left:0;right:0;padding:1.6rem;z-index:2;transform:translateY(0);transition:transform .4s cubic-bezier(.25,.46,.45,.94)}
.dc:hover .dc-content{transform:translateY(-6px)}
.dc-region{font-family:var(--sans);font-size:.55rem;letter-spacing:.25em;text-transform:uppercase;color:var(--gold2);margin-bottom:.35rem;display:flex;align-items:center;gap:.4rem}
.dc-region::before{content:'';display:inline-block;width:14px;height:1px;background:var(--gold2)}
.dc-rating{font-family:var(--sans);font-size:.6rem;color:var(--gold2);margin-bottom:.35rem;letter-spacing:.05em}
.dc-name{font-family:var(--serif);font-size:1.6rem;font-weight:300;color:var(--white);line-height:1.15;margin-bottom:.5rem;letter-spacing:-.01em}
.dc-meta{display:flex;align-items:center;justify-content:space-between}
.dc-price{font-family:var(--serif);font-size:.9rem;color:rgba(245,240,232,.7)}
.dc-price strong{font-size:1.3rem;font-weight:500;color:var(--white)}
.dc-tag{font-family:var(--sans);font-size:.55rem;letter-spacing:.12em;text-transform:uppercase;padding:.25rem .65rem;border:1px solid rgba(184,145,58,.5);color:var(--gold2)}
.dc-btn{position:absolute;top:1.2rem;right:1.2rem;z-index:3;font-family:var(--sans);font-size:.58rem;letter-spacing:.15em;text-transform:uppercase;padding:.45rem .9rem;background:rgba(245,240,232,.9);color:var(--ink);border:none;cursor:pointer;opacity:0;transform:translateY(-6px);transition:opacity .3s,transform .3s;font-weight:600}
.dc:hover .dc-btn{opacity:1;transform:translateY(0)}
.dc-btn:hover{background:var(--gold)}
.dc-fav{position:absolute;top:1.2rem;left:1.2rem;z-index:3;width:32px;height:32px;background:rgba(28,21,16,.5);border:1px solid rgba(245,240,232,.2);display:flex;align-items:center;justify-content:center;cursor:pointer;font-size:.75rem;opacity:0;transform:scale(.8);transition:all .25s;color:var(--white)}
.dc:hover .dc-fav{opacity:1;transform:scale(1)}
.dc-fav:hover{background:rgba(184,145,58,.6)}

/* FEATURED */
.featured{background:var(--ink);color:var(--white);padding:6rem 3.5rem;position:relative;overflow:hidden}
.feat-bg{position:absolute;inset:0;background:linear-gradient(135deg,#1c1510,#2c1f14 40%,#3d2a1a 60%,#1c1510)}
.feat-glow{position:absolute;inset:0;background:radial-gradient(circle at 20% 50%,rgba(184,145,58,.07),transparent 50%),radial-gradient(circle at 80% 20%,rgba(184,145,58,.05),transparent 40%)}
.feat-inner{position:relative;z-index:2;display:grid;grid-template-columns:1fr 1fr;gap:6rem;align-items:center;max-width:1200px;margin:0 auto}
.feat-label{font-family:var(--sans);font-size:.6rem;letter-spacing:.3em;text-transform:uppercase;color:var(--gold2);margin-bottom:1rem;display:flex;align-items:center;gap:.7rem}
.feat-label::before{content:'';width:30px;height:1px;background:var(--gold2)}
.feat-title{font-family:var(--serif);font-size:clamp(2.4rem,4vw,3.8rem);font-weight:300;line-height:1.1;color:var(--white);margin-bottom:1.2rem}
.feat-title em{font-style:italic;color:var(--gold-lt)}
.feat-desc{font-family:var(--sans);font-size:.8rem;color:rgba(245,240,232,.6);line-height:1.9;margin-bottom:2rem;letter-spacing:.04em}
.feat-details{display:flex;gap:2rem;margin-bottom:2.4rem;flex-wrap:wrap}
.feat-detail{padding-left:1rem;border-left:1px solid rgba(184,145,58,.3)}
.fdl{font-family:var(--sans);font-size:.55rem;letter-spacing:.2em;text-transform:uppercase;color:var(--ink4)}
.fdv{font-family:var(--serif);font-size:1rem;color:var(--white);font-weight:300}
.feat-price-row{display:flex;align-items:baseline;gap:1rem;margin-bottom:1.6rem}
.feat-from{font-family:var(--sans);font-size:.62rem;letter-spacing:.15em;text-transform:uppercase;color:var(--ink4)}
.feat-price{font-family:var(--serif);font-size:2.8rem;font-weight:300;color:var(--gold-lt);line-height:1}
.feat-price sup{font-size:1.2rem;vertical-align:top;margin-top:.5rem;display:inline-block}
.feat-pp{font-family:var(--sans);font-size:.62rem;color:var(--ink4);letter-spacing:.08em;align-self:flex-end;padding-bottom:.3rem}
.feat-btns{display:flex;gap:1rem;flex-wrap:wrap}
.btn-ghost-gold{font-family:var(--sans);font-size:.65rem;letter-spacing:.18em;text-transform:uppercase;background:transparent;border:1px solid rgba(201,185,154,.25);color:rgba(245,240,232,.6);padding:.9rem 1.6rem;cursor:pointer;transition:all .2s}
.btn-ghost-gold:hover{border-color:rgba(201,185,154,.6);color:rgba(245,240,232,.9)}

/* Collage */
.feat-visuals{position:relative;height:520px}
.fv-main{position:absolute;top:0;left:0;width:75%;height:80%;background:linear-gradient(135deg,#4a7c59,#2d5a3d 30%,#1a3a27 60%,#8b6914);overflow:hidden}
.fv-main::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse at 30% 70%,rgba(74,124,89,.6),transparent 60%),radial-gradient(ellipse at 70% 30%,rgba(139,105,20,.4),transparent 50%)}
.fv-a1{position:absolute;bottom:0;right:0;width:48%;height:50%;background:linear-gradient(135deg,#c4a882,#8b6914 50%,#5c3d11);border:3px solid var(--ink)}
.fv-a2{position:absolute;top:45%;left:58%;width:30%;height:28%;background:linear-gradient(135deg,#2c4a3e,#7a9e7e);border:3px solid var(--ink)}
.fv-caption{position:absolute;bottom:1rem;left:1rem;font-family:var(--serif);font-style:italic;font-size:.85rem;color:rgba(245,240,232,.45);z-index:2}
.feat-badge{position:absolute;top:-1.2rem;right:25%;width:80px;height:80px;border-radius:50%;background:var(--gold);display:flex;flex-direction:column;align-items:center;justify-content:center;z-index:5;border:3px solid var(--ink)}
.fb-top{font-family:var(--sans);font-size:.45rem;letter-spacing:.15em;text-transform:uppercase;color:var(--ink);font-weight:600}
.fb-num{font-family:var(--serif);font-size:1.4rem;font-weight:600;color:var(--ink);line-height:1}
.fb-bot{font-family:var(--sans);font-size:.42rem;letter-spacing:.1em;text-transform:uppercase;color:var(--ink2)}

/* EXPERIENCES */
.exp-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:1.5rem}
.exp-card{background:var(--white);overflow:hidden;transition:transform .3s,box-shadow .3s;cursor:pointer}
.exp-card:hover{transform:translateY(-4px);box-shadow:0 16px 48px rgba(28,21,16,.12)}
.exp-img{height:180px;position:relative;overflow:hidden}
.exp-img-bg{position:absolute;inset:0;background-size:cover;background-position:center;transition:transform .5s}
.exp-card:hover .exp-img-bg{transform:scale(1.06)}
.exp-etag{position:absolute;top:.8rem;left:.8rem;font-family:var(--sans);font-size:.55rem;letter-spacing:.15em;text-transform:uppercase;padding:.25rem .6rem;background:var(--gold);color:var(--ink);font-weight:600;z-index:2}
.exp-body{padding:1.4rem}
.exp-name{font-family:var(--serif);font-size:1.15rem;font-weight:500;color:var(--ink);margin-bottom:.4rem;line-height:1.25}
.exp-loc{font-family:var(--sans);font-size:.62rem;letter-spacing:.1em;color:var(--ink4);text-transform:uppercase;margin-bottom:.7rem}
.exp-desc{font-size:.78rem;color:var(--ink3);line-height:1.7;margin-bottom:1rem;letter-spacing:.02em}
.exp-footer{display:flex;align-items:center;justify-content:space-between;border-top:1px solid var(--cream3);padding-top:.9rem}
.exp-price{font-family:var(--serif);font-size:1.2rem;font-weight:500;color:var(--gold)}
.exp-dur{font-family:var(--sans);font-size:.58rem;letter-spacing:.1em;color:var(--ink4);text-transform:uppercase}
.exp-btn{font-family:var(--sans);font-size:.58rem;letter-spacing:.15em;text-transform:uppercase;font-weight:600;padding:.45rem .9rem;background:transparent;border:1px solid var(--cream3);color:var(--ink3);cursor:pointer;transition:all .2s}
.exp-btn:hover{border-color:var(--gold);color:var(--gold)}

/* TESTIMONIAL */
.testi-strip{background:var(--gold);padding:4.5rem 3.5rem;text-align:center;position:relative;overflow:hidden}
.testi-strip::before{content:'"';position:absolute;font-family:var(--serif);font-size:28rem;font-weight:300;color:rgba(28,21,16,.06);top:-5rem;left:50%;transform:translateX(-50%);line-height:1;pointer-events:none}
.tq{font-family:var(--serif);font-style:italic;font-size:clamp(1.4rem,3vw,2.2rem);font-weight:300;color:var(--ink);line-height:1.45;max-width:820px;margin:0 auto 1.6rem;position:relative;z-index:1}
.ta{font-family:var(--sans);font-size:.65rem;letter-spacing:.22em;text-transform:uppercase;color:rgba(28,21,16,.6);position:relative;z-index:1}

/* WHY US */
.why-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:2.5rem;max-width:1100px;margin:2.5rem auto 0}
.why-card{text-align:center}
.why-icon{font-size:2rem;margin-bottom:1rem;display:block}
.why-title{font-family:var(--serif);font-size:1.15rem;font-weight:500;color:var(--ink);margin-bottom:.5rem}
.why-desc{font-family:var(--sans);font-size:.75rem;color:var(--ink3);line-height:1.75;letter-spacing:.03em}

/* BOOKING CTA */
.booking-cta{background:var(--ink);padding:7rem 3.5rem;position:relative;overflow:hidden}
.bk-pat{position:absolute;inset:0;background-image:linear-gradient(rgba(201,185,154,.04) 1px,transparent 1px),linear-gradient(90deg,rgba(201,185,154,.04) 1px,transparent 1px);background-size:80px 80px}
.bk-glow{position:absolute;width:800px;height:400px;border-radius:50%;background:radial-gradient(ellipse,rgba(184,145,58,.08),transparent 70%);top:50%;left:50%;transform:translate(-50%,-50%)}
.bk-inner{position:relative;z-index:2;display:grid;grid-template-columns:1fr auto;gap:4rem;align-items:center;max-width:1100px;margin:0 auto}
.bk-label{font-family:var(--sans);font-size:.6rem;letter-spacing:.3em;text-transform:uppercase;color:var(--gold);margin-bottom:1rem;display:flex;align-items:center;gap:.6rem}
.bk-label::before{content:'';width:24px;height:1px;background:var(--gold)}
.bk-title{font-family:var(--serif);font-size:clamp(2.2rem,4vw,3.8rem);font-weight:300;color:var(--white);line-height:1.1;margin-bottom:1rem}
.bk-title em{font-style:italic;color:var(--gold-lt)}
.bk-sub{font-family:var(--sans);font-size:.78rem;color:rgba(245,240,232,.5);line-height:1.8;letter-spacing:.04em;max-width:480px}
.bk-form{min-width:340px;background:rgba(245,240,232,.05);border:1px solid rgba(201,185,154,.15);padding:2.2rem;display:flex;flex-direction:column;gap:1rem}
.bk-form-title{font-family:var(--serif);font-size:1.1rem;color:var(--white);font-weight:300;margin-bottom:.5rem;padding-bottom:1rem;border-bottom:1px solid rgba(201,185,154,.15)}
.ff{display:flex;flex-direction:column;gap:.35rem}
.fl{font-family:var(--sans);font-size:.55rem;letter-spacing:.2em;text-transform:uppercase;color:var(--ink4);font-weight:600}
.fi{padding:.75rem .9rem;background:rgba(245,240,232,.05);border:1px solid rgba(201,185,154,.2);color:var(--white);font-family:var(--serif);font-size:.95rem;outline:none;transition:border-color .2s;width:100%;appearance:none;-webkit-appearance:none}
.fi:focus{border-color:rgba(184,145,58,.5)}
.fi::placeholder{color:rgba(245,240,232,.3);font-style:italic}
.fi option{background:var(--ink2)}
.fr{display:grid;grid-template-columns:1fr 1fr;gap:.8rem}
.fs{font-family:var(--sans);font-size:.68rem;letter-spacing:.22em;text-transform:uppercase;font-weight:600;padding:1rem;background:var(--gold);color:var(--ink);border:none;cursor:pointer;transition:all .25s;margin-top:.5rem}
.fs:hover{background:var(--gold2);box-shadow:0 8px 28px rgba(184,145,58,.3)}
.ffine{font-family:var(--sans);font-size:.55rem;letter-spacing:.08em;color:rgba(245,240,232,.3);text-align:center}

/* FOOTER */
footer{background:var(--ink);padding:4rem 3.5rem 0}
.ft{display:grid;grid-template-columns:1.8fr 1fr 1fr 1fr;gap:4rem;padding-bottom:3rem;border-bottom:1px solid rgba(201,185,154,.1);margin-bottom:0}
.fb-name{font-family:var(--serif);font-size:1.8rem;font-weight:300;letter-spacing:.12em;color:var(--gold2);text-transform:uppercase;margin-bottom:.8rem}
.fb-tl{font-family:var(--serif);font-style:italic;font-size:.9rem;color:var(--ink4);line-height:1.6;margin-bottom:1.5rem}
.social-row{display:flex;gap:.8rem}
.sbtn{width:34px;height:34px;border:1px solid rgba(201,185,154,.2);display:flex;align-items:center;justify-content:center;font-size:.75rem;cursor:pointer;color:var(--ink4);transition:all .2s;background:transparent}
.sbtn:hover{border-color:var(--gold);color:var(--gold)}
.fc-title{font-family:var(--sans);font-size:.58rem;letter-spacing:.25em;text-transform:uppercase;color:var(--gold);margin-bottom:1.2rem;font-weight:600}
.fl-list{list-style:none;display:flex;flex-direction:column;gap:.7rem}
.fl-list a{font-family:var(--sans);font-size:.78rem;color:var(--ink4);text-decoration:none;letter-spacing:.04em;transition:color .15s;font-weight:300}
.fl-list a:hover{color:var(--gold2)}
.fb{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:1rem;padding:1.5rem 0}
.fcopy{font-family:var(--sans);font-size:.6rem;letter-spacing:.1em;color:rgba(156,136,120,.5)}

/* RESPONSIVE */
@media(max-width:1100px){
  .cards-grid{grid-template-columns:repeat(6,1fr)}
  .dc:nth-child(1){grid-column:1/4;grid-row:1}
  .dc:nth-child(2){grid-column:4/7;grid-row:1}
  .dc:nth-child(3){grid-column:1/4;grid-row:2}
  .dc:nth-child(4){grid-column:4/7;grid-row:2}
  .dc:nth-child(5){grid-column:1/4;grid-row:3}
  .dc:nth-child(6){grid-column:4/7;grid-row:3}
  .dc{aspect-ratio:4/3!important}
  .feat-inner{grid-template-columns:1fr;gap:3rem}
  .feat-visuals{height:320px}
  .bk-inner{grid-template-columns:1fr}
  .bk-form{min-width:auto}
  .exp-grid{grid-template-columns:1fr 1fr}
  .why-grid{grid-template-columns:1fr 1fr}
  .ft{grid-template-columns:1fr 1fr;gap:2rem}
}
@media(max-width:700px){
  nav{padding:1rem 1.5rem}
  .nav-links{display:none}
  .sec{padding:4rem 1.5rem}
  .search-bar{margin:0 1.5rem;flex-direction:column}
  .search-field{border-right:none;border-bottom:1px solid var(--cream3)}
  .search-btn{padding:1rem}
  .cards-grid{grid-template-columns:1fr}
  .dc{grid-column:1/-1!important;grid-row:auto!important;aspect-ratio:4/3!important}
  .exp-grid{grid-template-columns:1fr}
  .why-grid{grid-template-columns:1fr 1fr}
  .ft{grid-template-columns:1fr}
  .booking-cta{padding:4rem 1.5rem}
  .testi-strip{padding:3rem 1.5rem}
  .fr{grid-template-columns:1fr}
  .hero-content{padding:0 1.5rem 4rem}
  .hero-scroll{display:none}
  .feat-visuals{height:220px}
  footer{padding:3rem 1.5rem 0}
}
</style>
</head>
<body>

<!-- NAV -->
<nav id="mainNav">
  <div class="nav-logo">Ailleurs</div>
  <ul class="nav-links">
    <li><a href="#destinations">Destinations</a></li>
    <li><a href="#journeys">Journeys</a></li>
    <li><a href="#experiences">Experiences</a></li>
    <li><a href="#about">About</a></li>
  </ul>
  <button class="nav-book">Plan your journey</button>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-mountains">
    <svg viewBox="0 0 1440 200" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M0,200 L0,140 L120,80 L240,120 L360,60 L480,100 L540,40 L600,80 L720,20 L800,70 L900,30 L1000,90 L1100,50 L1200,100 L1320,60 L1440,110 L1440,200 Z" fill="rgba(28,21,16,0.5)"/>
      <path d="M0,200 L0,160 L180,110 L300,140 L420,90 L560,120 L680,70 L760,100 L880,60 L960,90 L1080,70 L1200,120 L1360,80 L1440,130 L1440,200 Z" fill="rgba(28,21,16,0.35)"/>
    </svg>
  </div>
  <div class="hero-content">
    <div class="hero-label">Curated travel · Est. 2012</div>
    <h1 class="hero-title">Go <em>somewhere</em><br>that changes you</h1>
    <p class="hero-sub">Handcrafted journeys to 140 destinations across six continents. We don't book trips — we architect experiences that last a lifetime.</p>
    <div class="hero-actions">
      <button class="btn-gold">Explore destinations</button>
      <button class="btn-ghost-w">View our stories</button>
    </div>
  </div>
  <div class="hero-scroll">
    <div class="hero-scroll-label">Scroll</div>
    <div class="hero-scroll-line"></div>
  </div>
</section>

<!-- SEARCH -->
<div class="search-bar">
  <div class="search-field"><div class="sf-label">Destination</div><div class="sf-val">Where do you want to go?</div></div>
  <div class="search-field"><div class="sf-label">Travel Dates</div><div class="sf-val">Select dates</div></div>
  <div class="search-field"><div class="sf-label">Travellers</div><div class="sf-val">2 adults</div></div>
  <div class="search-field" style="border-right:none"><div class="sf-label">Journey Style</div><div class="sf-val">Any style</div></div>
  <button class="search-btn">Search Journeys</button>
</div>

<!-- STATS -->
<div class="stats-strip">
  <div class="stat-item"><div class="stat-num">140+</div><div class="stat-label">Destinations</div></div>
  <div class="stat-item"><div class="stat-num">28k</div><div class="stat-label">Journeys crafted</div></div>
  <div class="stat-item"><div class="stat-num">4.9</div><div class="stat-label">Average rating</div></div>
  <div class="stat-item"><div class="stat-num">12</div><div class="stat-label">Years of expertise</div></div>
</div>

<!-- DESTINATION CARDS -->
<section class="sec" id="destinations">
  <div class="dest-header">
    <div>
      <div class="s-label">Explore</div>
      <h2 class="s-title">Where will you go <em>next?</em></h2>
    </div>
    <div class="filter-tabs">
      <button class="ftab active">All</button>
      <button class="ftab">Asia</button>
      <button class="ftab">Europe</button>
      <button class="ftab">Africa</button>
      <button class="ftab">Americas</button>
    </div>
  </div>

  <div class="cards-grid">
    <!-- Kyoto -->
    <div class="dc">
      <div class="dc-img" style="background:linear-gradient(160deg,#3d5a4a,#2a3d30 25%,#1a2820 50%,#4a3520 75%,#8b6535)"></div>
      <button class="dc-fav">♡</button><button class="dc-btn">Quick view</button>
      <div class="dc-content">
        <div class="dc-region">Japan · Asia</div>
        <div class="dc-rating">★★★★★ &nbsp;4.9</div>
        <div class="dc-name">Kyoto &<br>Nara</div>
        <div class="dc-meta"><div class="dc-price">from <strong>$3,240</strong></div><div class="dc-tag">10 days</div></div>
      </div>
    </div>
    <!-- Amalfi -->
    <div class="dc">
      <div class="dc-img" style="background:linear-gradient(170deg,#1a4a6b,#2266a0 30%,#4a8fbf 50%,#c4a882 75%,#8b6535)"></div>
      <button class="dc-fav">♡</button><button class="dc-btn">Quick view</button>
      <div class="dc-content">
        <div class="dc-region">Italy · Europe</div>
        <div class="dc-rating">★★★★★ &nbsp;4.8</div>
        <div class="dc-name">Amalfi<br>Coast</div>
        <div class="dc-meta"><div class="dc-price">from <strong>$2,890</strong></div><div class="dc-tag">7 days</div></div>
      </div>
    </div>
    <!-- Patagonia -->
    <div class="dc">
      <div class="dc-img" style="background:linear-gradient(145deg,#2c3e50,#3d5a6b 20%,#6b8fa0 40%,#a0b8c4 60%,#c8d8e0 80%,#1a2830)"></div>
      <button class="dc-fav">♡</button><button class="dc-btn">Quick view</button>
      <div class="dc-content">
        <div class="dc-region">Chile · Americas</div>
        <div class="dc-rating">★★★★★ &nbsp;4.9</div>
        <div class="dc-name">Patagonia &<br>Torres del Paine</div>
        <div class="dc-meta"><div class="dc-price">from <strong>$4,120</strong></div><div class="dc-tag">14 days</div></div>
      </div>
    </div>
    <!-- Morocco -->
    <div class="dc">
      <div class="dc-img" style="background:linear-gradient(150deg,#8b4513,#c4681a 25%,#e8a040 50%,#d4824a 75%,#5c2a0a)"></div>
      <button class="dc-fav">♡</button><button class="dc-btn">Quick view</button>
      <div class="dc-content">
        <div class="dc-region">Morocco · Africa</div>
        <div class="dc-rating">★★★★☆ &nbsp;4.7</div>
        <div class="dc-name">Marrakech &<br>the Sahara</div>
        <div class="dc-meta"><div class="dc-price">from <strong>$2,450</strong></div><div class="dc-tag">9 days</div></div>
      </div>
    </div>
    <!-- Santorini -->
    <div class="dc">
      <div class="dc-img" style="background:linear-gradient(160deg,#1a3a6b,#2a5aa0 20%,#4a80c8 40%,#f5f0e8 65%,#e8d5b0 80%,#c4a882)"></div>
      <button class="dc-fav">♡</button><button class="dc-btn">Quick view</button>
      <div class="dc-content">
        <div class="dc-region">Greece · Europe</div>
        <div class="dc-rating">★★★★★ &nbsp;4.9</div>
        <div class="dc-name">Santorini &<br>Mykonos</div>
        <div class="dc-meta"><div class="dc-price">from <strong>$3,680</strong></div><div class="dc-tag">8 days</div></div>
      </div>
    </div>
    <!-- Bali -->
    <div class="dc">
      <div class="dc-img" style="background:linear-gradient(155deg,#1a4a2a,#2d7a40 20%,#4aad5a 40%,#80c870 60%,#3d6b20 80%,#1a3010)"></div>
      <button class="dc-fav">♡</button><button class="dc-btn">Quick view</button>
      <div class="dc-content">
        <div class="dc-region">Indonesia · Asia</div>
        <div class="dc-rating">★★★★★ &nbsp;4.8</div>
        <div class="dc-name">Bali &<br>Ubud</div>
        <div class="dc-meta"><div class="dc-price">from <strong>$1,980</strong></div><div class="dc-tag">11 days</div></div>
      </div>
    </div>
  </div>
</section>

<!-- FEATURED JOURNEY -->
<section class="featured" id="journeys">
  <div class="feat-bg"></div><div class="feat-glow"></div>
  <div class="feat-inner">
    <div>
      <div class="feat-label">Journey of the season</div>
      <h2 class="feat-title">The Silk Road<br><em>Reimagined</em></h2>
      <p class="feat-desc">Seventeen days through Uzbekistan, Georgia, and Armenia — traversing ancient trade routes that once connected East and West. Walled cities at dusk. Caravanserais turned boutique hotels. Markets unchanged for eight centuries.</p>
      <div class="feat-details">
        <div class="feat-detail"><div class="fdl">Duration</div><div class="fdv">17 days</div></div>
        <div class="feat-detail"><div class="fdl">Highlights</div><div class="fdv">Samarkand · Tbilisi · Yerevan</div></div>
        <div class="feat-detail"><div class="fdl">Group size</div><div class="fdv">Max 10 travellers</div></div>
        <div class="feat-detail"><div class="fdl">Departs</div><div class="fdv">Sept – Nov 2026</div></div>
      </div>
      <div class="feat-price-row">
        <span class="feat-from">From</span>
        <div class="feat-price"><sup>$</sup>6,490</div>
        <span class="feat-pp">per person</span>
      </div>
      <div class="feat-btns">
        <button class="btn-gold">Reserve your place</button>
        <button class="btn-ghost-gold">View full itinerary</button>
      </div>
    </div>
    <div class="feat-visuals">
      <div class="fv-main"><div class="fv-caption">Registan Square, Samarkand</div></div>
      <div class="fv-a1"></div>
      <div class="fv-a2"></div>
      <div class="feat-badge">
        <div class="fb-top">Only</div>
        <div class="fb-num">4</div>
        <div class="fb-bot">spots left</div>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCES -->
<section class="sec" id="experiences" style="background:var(--cream2)">
  <div style="margin-bottom:3rem">
    <div class="s-label">Curated experiences</div>
    <h2 class="s-title">Beyond the <em>itinerary</em></h2>
    <p class="s-sub">Each journey includes handpicked experiences you won't find on any booking platform.</p>
  </div>
  <div class="exp-grid">
    <div class="exp-card">
      <div class="exp-img"><div class="exp-img-bg" style="background:linear-gradient(135deg,#4a2c1a,#8b5a2a 50%,#c4a060)"></div><div class="exp-etag">Culinary</div></div>
      <div class="exp-body">
        <div class="exp-name">Private Truffle Hunt, Périgord</div>
        <div class="exp-loc">📍 Dordogne, France</div>
        <div class="exp-desc">Hunt black truffles at dawn with a local family and their trained dogs. Cook your findings with a Michelin-starred chef that evening.</div>
        <div class="exp-footer"><div><div class="exp-price">$420</div><div class="exp-dur">Full day</div></div><button class="exp-btn">Book now</button></div>
      </div>
    </div>
    <div class="exp-card">
      <div class="exp-img"><div class="exp-img-bg" style="background:linear-gradient(135deg,#1a3a6b,#2a5aa0 40%,#7ab0d8)"></div><div class="exp-etag">Adventure</div></div>
      <div class="exp-body">
        <div class="exp-name">Dawn Glacier Trek, Chamonix</div>
        <div class="exp-loc">📍 Mont Blanc, France</div>
        <div class="exp-desc">A guided sunrise trek across Mer de Glace — the largest glacier in the Alps — with a private mountain guide and champagne at the summit.</div>
        <div class="exp-footer"><div><div class="exp-price">$380</div><div class="exp-dur">8 hours</div></div><button class="exp-btn">Book now</button></div>
      </div>
    </div>
    <div class="exp-card">
      <div class="exp-img"><div class="exp-img-bg" style="background:linear-gradient(135deg,#2d5a3d,#4a8a5a 40%,#80b870)"></div><div class="exp-etag">Cultural</div></div>
      <div class="exp-body">
        <div class="exp-name">Tea Ceremony & Zen Garden</div>
        <div class="exp-loc">📍 Kyoto, Japan</div>
        <div class="exp-desc">An intimate tea ceremony in a private Meiji-era garden, led by a 4th-generation tea master. Includes calligraphy and meditation.</div>
        <div class="exp-footer"><div><div class="exp-price">$290</div><div class="exp-dur">Half day</div></div><button class="exp-btn">Book now</button></div>
      </div>
    </div>
    <div class="exp-card">
      <div class="exp-img"><div class="exp-img-bg" style="background:linear-gradient(135deg,#1a1a3a,#2a2a6a 30%,#4040a0 60%,#c0a040)"></div><div class="exp-etag">Exclusive</div></div>
      <div class="exp-body">
        <div class="exp-name">Private Colosseum at Midnight</div>
        <div class="exp-loc">📍 Rome, Italy</div>
        <div class="exp-desc">Exclusive after-hours access to the Colosseum. Walk the arena floor by torchlight with a Roman historian. Strictly 8 guests maximum.</div>
        <div class="exp-footer"><div><div class="exp-price">$680</div><div class="exp-dur">3 hours</div></div><button class="exp-btn">Book now</button></div>
      </div>
    </div>
  </div>
</section>

<!-- TESTIMONIAL -->
<div class="testi-strip">
  <p class="tq">"Ailleurs didn't give us a holiday. They gave us a story we'll spend the rest of our lives telling."</p>
  <div class="ta">— Margot & Luca Ferretti, Milan · Silk Road Journey, 2025</div>
</div>

<!-- WHY US -->
<section class="sec" id="about" style="text-align:center">
  <div class="s-label" style="justify-content:center">Why Ailleurs</div>
  <h2 class="s-title">Travel crafted to a <em>different standard</em></h2>
  <div class="why-grid">
    <div class="why-card"><span class="why-icon">🧭</span><div class="why-title">Expert curation</div><div class="why-desc">Every route, hotel, and guide is personally vetted by our team of former explorers and local specialists.</div></div>
    <div class="why-card"><span class="why-icon">✦</span><div class="why-title">Truly bespoke</div><div class="why-desc">No two journeys are identical. We build yours around you — your pace, your passions, your idea of perfect.</div></div>
    <div class="why-card"><span class="why-icon">🤝</span><div class="why-title">On-ground support</div><div class="why-desc">A dedicated journey manager is available 24/7 — before, during, and after your trip.</div></div>
    <div class="why-card"><span class="why-icon">🌿</span><div class="why-title">Responsible travel</div><div class="why-desc">Carbon-offset journeys, community-first accommodations, and 3% of revenue funds conservation.</div></div>
  </div>
</section>

<!-- BOOKING CTA -->
<section class="booking-cta">
  <div class="bk-pat"></div><div class="bk-glow"></div>
  <div class="bk-inner">
    <div>
      <div class="bk-label">Start planning</div>
      <h2 class="bk-title">Your next chapter<br>begins <em>here</em></h2>
      <p class="bk-sub">Tell us where you dream of going and our journey architects will craft a bespoke itinerary within 48 hours. No commitment, no cost — just possibility.</p>
    </div>
    <div class="bk-form">
      <div class="bk-form-title">Request a bespoke journey</div>
      <div class="ff"><label class="fl">Your name</label><input class="fi" type="text" placeholder="Full name"></div>
      <div class="ff"><label class="fl">Email</label><input class="fi" type="email" placeholder="your@email.com"></div>
      <div class="fr">
        <div class="ff"><label class="fl">Destination</label>
          <select class="fi"><option value="">Any dream</option><option>Japan</option><option>Italy</option><option>Patagonia</option><option>Morocco</option><option>Greece</option><option>Bali</option><option>Silk Road</option></select>
        </div>
        <div class="ff"><label class="fl">Budget pp</label>
          <select class="fi"><option>$2k – $5k</option><option>$5k – $10k</option><option>$10k – $20k</option><option>$20k+</option></select>
        </div>
      </div>
      <div class="ff"><label class="fl">When are you thinking?</label><input class="fi" type="text" placeholder="e.g. Spring 2027, flexible"></div>
      <button class="fs">Request my itinerary →</button>
      <div class="ffine">We respond within 48 hours · No booking required</div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="ft">
    <div>
      <div class="fb-name">Ailleurs</div>
      <div class="fb-tl"><em>Ailleurs</em> is French for "elsewhere" — the feeling of being exactly where you were meant to be.</div>
      <div class="social-row">
        <button class="sbtn">in</button>
        <button class="sbtn">ig</button>
        <button class="sbtn">𝕏</button>
        <button class="sbtn">pt</button>
      </div>
    </div>
    <div>
      <div class="fc-title">Destinations</div>
      <ul class="fl-list">
        <li><a href="#">Asia & Pacific</a></li>
        <li><a href="#">Europe</a></li>
        <li><a href="#">Africa & Middle East</a></li>
        <li><a href="#">The Americas</a></li>
        <li><a href="#">Polar expeditions</a></li>
      </ul>
    </div>
    <div>
      <div class="fc-title">Journeys</div>
      <ul class="fl-list">
        <li><a href="#">Honeymoons</a></li>
        <li><a href="#">Family adventures</a></li>
        <li><a href="#">Solo travel</a></li>
        <li><a href="#">Small group tours</a></li>
        <li><a href="#">Private charters</a></li>
      </ul>
    </div>
    <div>
      <div class="fc-title">Company</div>
      <ul class="fl-list">
        <li><a href="#">Our story</a></li>
        <li><a href="#">Travel guides</a></li>
        <li><a href="#">Responsible travel</a></li>
        <li><a href="#">Press</a></li>
        <li><a href="#">Careers</a></li>
      </ul>
    </div>
  </div>
  <div class="fb">
    <div class="fcopy">© 2026 Ailleurs Travel Ltd. All rights reserved.</div>
    <div class="fcopy">ATOL protected · ABTA member · BCorp certified</div>
  </div>
</footer>

<script>
const nav = document.getElementById('mainNav');
window.addEventListener('scroll', () => {
  nav.classList.toggle('scrolled', window.scrollY > 60);
});
document.querySelectorAll('.ftab').forEach(t => {
  t.addEventListener('click', function() {
    document.querySelectorAll('.ftab').forEach(x => x.classList.remove('active'));
    this.classList.add('active');
  });
});
</script>
</body>
</html>