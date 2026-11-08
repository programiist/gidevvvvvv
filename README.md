<html lang="ru">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>GIDEV — сайты и Telegram-боты под ключ</title>
<meta name="description" content="Разрабатываю сайты и Telegram-ботов под ключ. Консультация, дизайн, запуск и поддержка. Заказ — напрямую в личных сообщениях.">
<meta name="theme-color" content="#ffffff">
<link rel="icon" href="logo.svg" type="image/svg+xml">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@400;500;600;700&family=Barlow:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#111;
    --paper:#fff;
    --soft:#f3f1ee;
    --muted:#6c6a67;
    --hair:rgba(17,17,17,.14);
    --ease:cubic-bezier(.22,.8,.24,1);
    --pad:clamp(20px,5vw,56px);
    --head:'Barlow Condensed','Arial Narrow',Arial,sans-serif;
    --body:'Barlow',system-ui,-apple-system,'Segoe UI',Roboto,Arial,sans-serif;
  }
  *{box-sizing:border-box;margin:0;padding:0}
  html{scroll-behavior:smooth;-webkit-text-size-adjust:100%;scroll-padding-top:80px}
  body{font-family:var(--body);background:var(--paper);color:var(--ink);line-height:1.6;overflow-x:hidden;-webkit-font-smoothing:antialiased}
  a{color:inherit;text-decoration:none}
  svg{display:block}
  .wrap{width:100%;max-width:1200px;margin:0 auto;padding:0 var(--pad)}
  section{padding:clamp(64px,9vw,120px) 0}
  .soft{background:var(--soft)}

  /* ===== типографика ===== */
  h1,h2,h3,.up{font-family:var(--head);text-transform:uppercase;letter-spacing:.03em;font-weight:500}
  h1{font-size:clamp(2.8rem,7.4vw,5.6rem);line-height:.98;font-weight:500}
  h2{font-size:clamp(2.2rem,5vw,3.6rem);line-height:1.02}
  h3{font-size:1.5rem;line-height:1.1;font-weight:600}
  .kicker{display:flex;align-items:center;gap:14px;font-family:var(--head);text-transform:uppercase;letter-spacing:.2em;font-size:.95rem;color:var(--muted);margin-bottom:18px}
  .kicker::before{content:"";width:40px;height:2px;background:var(--ink)}
  .lead{color:var(--muted);font-size:clamp(1rem,1.6vw,1.12rem);max-width:520px}
  .head{display:grid;grid-template-columns:1fr 1fr;gap:24px 56px;align-items:end;margin-bottom:clamp(36px,5vw,64px)}
  .head p{color:var(--muted);max-width:460px;justify-self:end}

  /* ===== кнопки ===== */
  .btn{
    position:relative;display:inline-flex;align-items:center;justify-content:center;gap:12px;
    padding:15px 32px;border:1.5px solid var(--ink);background:transparent;color:var(--ink);
    font-family:var(--head);font-weight:600;font-size:1.05rem;letter-spacing:.16em;text-transform:uppercase;
    cursor:pointer;overflow:hidden;isolation:isolate;white-space:nowrap;
    transition:color .45s var(--ease),transform .3s var(--ease);
  }
  .btn::before{content:"";position:absolute;inset:0;background:var(--ink);transform:scaleX(0);transform-origin:left;transition:transform .45s var(--ease);z-index:-1}
  .btn:hover{color:var(--paper)}
  .btn:hover::before{transform:scaleX(1)}
  .btn:active{transform:scale(.97)}
  .btn svg{width:20px;height:20px;transition:transform .35s var(--ease)}
  .btn:hover svg{transform:translateX(5px)}
  .btn-solid{background:var(--ink);color:var(--paper)}
  .btn-solid::before{background:var(--paper)}
  .btn-solid:hover{color:var(--ink)}
  .btn-inv{border-color:var(--paper);color:var(--paper)}
  .btn-inv::before{background:var(--paper)}
  .btn-inv:hover{color:var(--ink)}
  .btn-sm{padding:11px 22px;font-size:.95rem}

  /* ===== шапка ===== */
  header{position:sticky;top:0;z-index:60;background:rgba(255,255,255,.92);backdrop-filter:blur(12px);-webkit-backdrop-filter:blur(12px);border-bottom:1px solid var(--hair)}
  .nav{display:flex;align-items:center;justify-content:space-between;height:74px;gap:20px}
  .logo{display:block;height:44px;width:auto;aspect-ratio:720/410;color:var(--ink)}
  .links{display:flex;align-items:center;gap:clamp(16px,2.4vw,34px)}
  .links a:not(.btn){font-family:var(--head);text-transform:uppercase;letter-spacing:.14em;font-size:1rem;position:relative;padding:4px 0}
  .links a:not(.btn)::after{content:"";position:absolute;left:0;bottom:0;height:1.5px;width:100%;background:var(--ink);transform:scaleX(0);transform-origin:right;transition:transform .4s var(--ease)}
  .links a:not(.btn):hover::after{transform:scaleX(1);transform-origin:left}
  .burger{display:none;width:46px;height:46px;border:1.5px solid var(--ink);background:none;cursor:pointer;position:relative}
  .burger i{position:absolute;left:12px;right:12px;height:2px;background:var(--ink);transition:transform .35s var(--ease),opacity .2s}
  .burger i:nth-child(1){top:16px}.burger i:nth-child(2){top:22px}.burger i:nth-child(3){top:28px}
  .burger[aria-expanded="true"] i:nth-child(1){transform:translateY(6px) rotate(45deg)}
  .burger[aria-expanded="true"] i:nth-child(2){opacity:0}
  .burger[aria-expanded="true"] i:nth-child(3){transform:translateY(-6px) rotate(-45deg)}

  /* ===== hero ===== */
  .hero{padding:clamp(40px,6vw,90px) 0 clamp(56px,8vw,110px)}
  .hero-grid{display:grid;grid-template-columns:1fr 1.05fr;gap:clamp(36px,6vw,90px);align-items:center}
  .hero h1 em{font-style:normal;display:block;-webkit-text-stroke:1.5px var(--ink);color:transparent}
  .hero .lead{margin:26px 0 34px}
  .cta{display:flex;flex-wrap:wrap;gap:14px}
  .socials{display:flex;gap:14px;margin-top:38px;align-items:center}
  .socials span{font-family:var(--head);text-transform:uppercase;letter-spacing:.18em;font-size:.9rem;color:var(--muted);margin-right:6px}
  .soc{width:46px;height:46px;border:1.5px solid var(--ink);border-radius:50%;display:grid;place-items:center;transition:background .35s,color .35s,transform .35s var(--ease)}
  .soc:hover{background:var(--ink);color:var(--paper);transform:translateY(-3px)}
  .soc svg{width:20px;height:20px}

  .stage{position:relative;aspect-ratio:1/.88;width:100%}
  .stage .hatch{position:absolute;top:0;right:0;width:46%;height:46%;background:repeating-linear-gradient(135deg,var(--ink) 0 1.5px,transparent 1.5px 12px);opacity:.28}
  .stage .outline{position:absolute;left:0;top:9%;width:84%;height:86%;border:1.5px solid var(--ink)}
  .browser{position:absolute;left:9%;top:20%;width:78%;background:var(--paper);border:1.5px solid var(--ink);box-shadow:14px 16px 0 rgba(17,17,17,.9);animation:float 7s ease-in-out infinite}
  .bar{display:flex;gap:6px;padding:10px 12px;border-bottom:1.5px solid var(--ink)}
  .bar i{width:8px;height:8px;border-radius:50%;border:1.5px solid var(--ink)}
  .page{padding:clamp(12px,2.4vw,24px)}
  .page .row{display:flex;justify-content:space-between;align-items:center;margin-bottom:clamp(14px,3vw,30px)}
  .page .row b{width:26%;height:8px;background:var(--ink)}
  .page .row span{width:34%;height:6px;background:repeating-linear-gradient(90deg,var(--ink) 0 14px,transparent 14px 22px);opacity:.6}
  .page .t1{width:70%;height:clamp(10px,2vw,18px);background:var(--ink);margin-bottom:10px}
  .page .t2{width:48%;height:clamp(10px,2vw,18px);border:1.5px solid var(--ink);margin-bottom:clamp(12px,2.4vw,24px)}
  .page .p{width:82%;height:5px;background:var(--hair);margin-bottom:6px}
  .page .btnm{display:inline-block;margin-top:clamp(10px,2vw,18px);padding:6px 16px;border:1.5px solid var(--ink);font-family:var(--head);letter-spacing:.14em;font-size:.72rem;text-transform:uppercase}
  .phone{position:absolute;right:2%;bottom:0;width:36%;background:var(--paper);border:1.5px solid var(--ink);border-radius:22px;padding:12px;box-shadow:-10px 12px 0 rgba(17,17,17,.9);animation:float 7s ease-in-out -3s infinite}
  .phone .top{height:6px;width:34%;background:var(--ink);margin:0 auto 12px;border-radius:4px}
  .msg{font-size:clamp(.6rem,1.1vw,.78rem);line-height:1.35;padding:7px 10px;margin-bottom:7px;max-width:92%;opacity:0;transform:translateY(8px);animation:pop .6s var(--ease) forwards}
  .msg.bot{border:1.5px solid var(--ink)}
  .msg.me{background:var(--ink);color:var(--paper);margin-left:auto}
  .msg:nth-of-type(1){animation-delay:.9s}.msg:nth-of-type(2){animation-delay:1.7s}.msg:nth-of-type(3){animation-delay:2.5s}
  @keyframes pop{to{opacity:1;transform:none}}
  @keyframes float{50%{transform:translateY(-10px)}}

  /* ===== бегущая строка ===== */
  .marquee{background:var(--ink);color:var(--paper);overflow:hidden;padding:18px 0;white-space:nowrap}
  .marquee div{display:inline-flex;animation:run 28s linear infinite}
  .marquee span{font-family:var(--head);text-transform:uppercase;letter-spacing:.22em;font-size:1.25rem;padding:0 28px}
  .marquee span::after{content:"/";margin-left:56px;opacity:.5}
  @keyframes run{to{transform:translateX(-50%)}}

  /* ===== услуги ===== */
  .grid3{display:grid;grid-template-columns:repeat(3,1fr);border:1.5px solid var(--ink);background:var(--paper)}
  .svc{padding:clamp(26px,3vw,40px);display:flex;flex-direction:column;gap:16px;border-right:1.5px solid var(--ink);position:relative;transition:background .45s var(--ease),color .45s var(--ease)}
  .svc:last-child{border-right:0}
  .svc .num{font-family:var(--head);font-size:1rem;letter-spacing:.2em;color:var(--muted);transition:color .45s}
  .svc svg.ic{width:54px;height:54px;stroke:currentColor;fill:none;stroke-width:1.4;margin:8px 0}
  .svc p{color:var(--muted);transition:color .45s}
  .svc ul{list-style:none;display:grid;gap:9px;font-size:.97rem}
  .svc li{display:flex;gap:12px}
  .svc li::before{content:"";flex:none;width:14px;height:1.5px;background:currentColor;margin-top:13px}
  .svc .btn{margin-top:auto;align-self:flex-start}
  .svc:hover{background:var(--ink);color:var(--paper)}
  .svc:hover p,.svc:hover .num{color:rgba(255,255,255,.65)}
  .svc:hover .btn{border-color:var(--paper);color:var(--paper)}
  .svc:hover .btn::before{background:var(--paper)}
  .svc:hover .btn:hover{color:var(--ink)}
  .flag{position:absolute;top:0;right:0;background:var(--ink);color:var(--paper);font-family:var(--head);letter-spacing:.16em;text-transform:uppercase;font-size:.82rem;padding:6px 14px;transition:background .45s,color .45s}
  .svc:hover .flag{background:var(--paper);color:var(--ink)}

  /* ===== слайдер ===== */
  .slider{position:relative}
  .track{display:flex;gap:24px;overflow-x:auto;scroll-snap-type:x mandatory;scrollbar-width:none;-webkit-overflow-scrolling:touch;padding-bottom:4px}
  .track::-webkit-scrollbar{display:none}
  .slide{flex:0 0 calc((100% - 24px)/2);scroll-snap-align:start;background:var(--paper);border:1.5px solid var(--ink);display:flex;flex-direction:column;transition:transform .45s var(--ease)}
  .slide:hover{transform:translateY(-6px)}
  .shot{position:relative;aspect-ratio:16/10;border-bottom:1.5px solid var(--ink);overflow:hidden;
    background:var(--img,none) center/cover no-repeat,repeating-linear-gradient(45deg,#ececea 0 10px,#f7f6f4 10px 20px)}
  .shot .ph{position:absolute;inset:0;display:grid;place-content:center;text-align:center;gap:6px;font-family:var(--head);text-transform:uppercase;letter-spacing:.16em;color:var(--muted);font-size:.95rem;padding:20px}
  .shot .ph b{color:var(--ink);font-size:1.6rem;font-weight:500;letter-spacing:.08em}
  .shot.has .ph{display:none}
  .meta{padding:22px 24px 26px;display:grid;gap:8px}
  .meta .tags{display:flex;gap:8px;flex-wrap:wrap}
  .meta .tags span{font-family:var(--head);text-transform:uppercase;letter-spacing:.14em;font-size:.8rem;border:1px solid var(--ink);padding:2px 10px}
  .meta p{color:var(--muted);font-size:.97rem}
  .ctrl{display:flex;align-items:center;justify-content:space-between;margin-top:30px;gap:20px}
  .dots{display:flex;gap:10px}
  .dots button{width:34px;height:3px;border:0;background:var(--hair);cursor:pointer;transition:background .3s,width .4s var(--ease)}
  .dots button.on{background:var(--ink);width:56px}
  .arrows{display:flex;gap:10px}
  .arr{width:52px;height:52px;border:1.5px solid var(--ink);background:transparent;cursor:pointer;display:grid;place-items:center;transition:background .3s,color .3s,transform .3s var(--ease)}
  .arr:hover{background:var(--ink);color:var(--paper)}
  .arr:active{transform:scale(.94)}
  .arr svg{width:22px;height:22px}


  /* ===== макеты стилей в слайдере ===== */
  .shot{container-type:inline-size}
  .mk{position:absolute;inset:0;background:var(--bg);color:var(--fg);overflow:hidden}
  .mk h4{margin:0;font-weight:inherit}
  /* минимализм */
  .mk-min{padding:4.5cqw 5cqw;display:flex;flex-direction:column;font-family:var(--head)}
  .mn-nav{display:flex;justify-content:space-between;align-items:center;font-size:2.6cqw;letter-spacing:.2em;text-transform:uppercase}
  .mn-nav b{font-weight:600;border:.35cqw solid var(--fg);padding:.5cqw 1.6cqw}
  .mn-nav span{display:flex;gap:2cqw}
  .mn-nav i{width:5cqw;height:.4cqw;background:var(--fg);opacity:.5}
  .mn-body{flex:1;display:grid;grid-template-columns:1fr 1fr;gap:4cqw;align-items:center}
  .mn-l s{display:block;width:6cqw;height:.45cqw;background:var(--fg);margin-bottom:2cqw}
  .mn-l h4{font-size:8.4cqw;line-height:.95;font-weight:500;text-transform:uppercase;letter-spacing:.03em;margin-bottom:2.4cqw}
  .mn-l p{height:.7cqw;background:var(--fg);opacity:.18;margin-bottom:1cqw;width:90%}
  .mn-btn{display:inline-block;margin-top:2cqw;border:.35cqw solid var(--fg);padding:1.2cqw 3.2cqw;font-size:2.4cqw;letter-spacing:.18em;text-transform:uppercase}
  .mn-r{position:relative;height:80%}
  .mn-fr{position:absolute;inset:0 6cqw 6cqw 0;border:.35cqw solid var(--fg)}
  .mn-bl{position:absolute;inset:6cqw 0 0 6cqw;background:var(--ac)}
  .mn-ft{display:flex;gap:1.6cqw}
  .mn-ft u{width:3.4cqw;height:3.4cqw;border:.35cqw solid var(--fg);border-radius:50%}
  .mk-min.flip .mn-l{order:2}
  .mk-min.flip .mn-bl{inset:6cqw 6cqw 0 0}
  .mk-min.flip .mn-fr{inset:0 0 6cqw 6cqw}
  /* максимализм */
  .mk-max{font-family:var(--head)}
  .mk-max h4{position:absolute;left:5cqw;top:14cqw;font-size:12.5cqw;line-height:.88;font-weight:700;text-transform:uppercase;text-shadow:.9cqw .9cqw 0 var(--c1);z-index:3}
  .mx-nav{position:absolute;left:4cqw;right:4cqw;top:3.5cqw;display:flex;justify-content:space-between;align-items:center;z-index:4;font-size:2.8cqw;font-weight:700;letter-spacing:.14em;text-transform:uppercase}
  .mx-nav b{background:var(--fg);color:var(--bg);padding:.6cqw 2cqw;transform:rotate(-3deg)}
  .mx-nav span{border:.45cqw solid var(--fg);padding:.5cqw 2cqw;border-radius:5cqw}
  .mx-c1{position:absolute;right:-6cqw;top:8cqw;width:38cqw;height:38cqw;border-radius:50%;background:var(--c1);border:.6cqw solid var(--fg)}
  .mx-c2{position:absolute;right:16cqw;bottom:8cqw;width:20cqw;height:20cqw;background:var(--c2);border:.6cqw solid var(--fg);transform:rotate(14deg);transition:transform .8s var(--ease)}
  .slide:hover .mx-c2{transform:rotate(60deg)}
  .mx-star{position:absolute;left:48cqw;top:12cqw;width:11cqw;height:11cqw;background:var(--fg);clip-path:polygon(50% 0,61% 35%,98% 35%,68% 57%,79% 91%,50% 70%,21% 91%,32% 57%,2% 35%,39% 35%);animation:mxspin 12s linear infinite}
  @keyframes mxspin{to{transform:rotate(360deg)}}
  .mx-btn{position:absolute;left:5cqw;bottom:12cqw;background:var(--fg);color:var(--bg);font-size:3.4cqw;font-weight:700;letter-spacing:.14em;text-transform:uppercase;padding:1.5cqw 4.5cqw;box-shadow:.9cqw .9cqw 0 var(--c2);z-index:4}
  .mx-badge{position:absolute;right:6cqw;top:36cqw;width:12cqw;height:12cqw;border-radius:50%;background:var(--fg);color:var(--bg);display:grid;place-items:center;font-weight:700;font-size:2.6cqw;transform:rotate(12deg);z-index:4}
  .mx-band{position:absolute;left:-4cqw;right:-4cqw;bottom:0;background:var(--fg);color:var(--bg);padding:1.6cqw 0;white-space:nowrap;transform:rotate(-2deg);z-index:5;overflow:hidden}
  .mx-band span{display:inline-block;font-size:3cqw;font-weight:700;letter-spacing:.2em;text-transform:uppercase;animation:mxband 16s linear infinite}
  @keyframes mxband{to{transform:translateX(-50%)}}
  /* swiss */
  .mk-swiss{font-family:Helvetica,'Helvetica Neue',Arial,sans-serif;padding:4cqw 5cqw}
  .sw-grid{position:absolute;inset:0 5cqw;display:grid;grid-template-columns:repeat(4,1fr)}
  .sw-grid i{border-left:.15cqw solid var(--fg);opacity:.14}
  .sw-grid i:last-child{border-right:.15cqw solid var(--fg)}
  .sw-top{position:relative;display:flex;gap:4cqw;font-size:2.2cqw;font-weight:700;padding-bottom:1.6cqw;border-bottom:.9cqw solid var(--fg)}
  .sw-top b{margin-right:auto;color:var(--ac)}
  .sw-big{position:absolute;right:5cqw;top:12cqw;font-size:30cqw;line-height:.8;font-weight:700;letter-spacing:-.06em;color:var(--ac)}
  .mk-swiss h4{position:absolute;left:5cqw;top:19cqw;font-size:8cqw;line-height:.98;font-weight:700;letter-spacing:-.035em}
  .sw-circle{position:absolute;right:22cqw;bottom:6cqw;width:17cqw;height:17cqw;border-radius:50%;background:var(--fg);transition:transform .7s var(--ease)}
  .slide:hover .sw-circle{transform:translateX(-6cqw)}
  .sw-p{position:absolute;left:5cqw;bottom:6cqw;width:38cqw;display:grid;gap:1cqw}
  .sw-p i{height:.6cqw;background:var(--fg);opacity:.35}
  .meta .btn{justify-self:start;margin-top:10px}

  /* ===== почему я ===== */
  .why{display:grid;grid-template-columns:repeat(4,1fr);gap:0;border-top:1.5px solid var(--ink)}
  .why div{padding:30px 26px 10px 0;border-right:1px solid var(--hair);padding-left:26px}
  .why div:first-child{padding-left:0}
  .why div:last-child{border-right:0}
  .why b{font-family:var(--head);font-size:3rem;font-weight:400;line-height:1;display:block;margin-bottom:10px;-webkit-text-stroke:1.2px var(--ink);color:transparent}
  .why h3{margin-bottom:8px}
  .why p{color:var(--muted);font-size:.97rem}

  /* ===== процесс ===== */
  .flow{display:grid;grid-template-columns:repeat(5,1fr);gap:0;position:relative}
  .flow::before{content:"";position:absolute;left:0;right:0;top:27px;height:1.5px;background:var(--ink)}
  .st{position:relative;padding:0 22px 0 0}
  .st .dot{width:54px;height:54px;border:1.5px solid var(--ink);background:var(--paper);display:grid;place-items:center;font-family:var(--head);font-size:1.3rem;letter-spacing:.06em;position:relative;margin-bottom:22px;transition:background .4s,color .4s}
  .st:hover .dot{background:var(--ink);color:var(--paper)}
  .st h3{font-size:1.3rem;margin-bottom:6px}
  .st p{color:var(--muted);font-size:.95rem}

  /* ===== пакеты ===== */
  .plans{display:grid;grid-template-columns:repeat(3,1fr);gap:24px;align-items:stretch}
  .plan{border:1.5px solid var(--ink);background:var(--paper);padding:clamp(26px,3vw,38px);display:flex;flex-direction:column;gap:18px;transition:transform .45s var(--ease),box-shadow .45s var(--ease)}
  .plan:hover{transform:translate(-6px,-6px);box-shadow:10px 10px 0 var(--ink)}
  .plan.top{background:var(--ink);color:var(--paper)}
  .plan.top:hover{box-shadow:10px 10px 0 rgba(17,17,17,.25)}
  .plan .sub{color:var(--muted)}
  .plan.top .sub{color:rgba(255,255,255,.6)}
  .plan ul{list-style:none;display:grid;gap:10px;border-top:1px solid currentColor;padding-top:20px;font-size:.97rem}
  .plan.top ul{border-color:rgba(255,255,255,.3)}
  .plan li{display:flex;gap:12px}
  .plan li::before{content:"";flex:none;width:14px;height:8px;border-left:2px solid currentColor;border-bottom:2px solid currentColor;transform:rotate(-45deg);margin-top:8px}
  .plan .price{font-family:var(--head);text-transform:uppercase;letter-spacing:.14em;font-size:.95rem;color:var(--muted)}
  .plan.top .price{color:rgba(255,255,255,.6)}
  .plan .btn{margin-top:auto}
  .plan.top .btn{border-color:var(--paper);color:var(--paper)}
  .plan.top .btn::before{background:var(--paper)}
  .plan.top .btn:hover{color:var(--ink)}

  /* ===== как заказать ===== */
  .order{display:grid;grid-template-columns:repeat(3,1fr);gap:0;border:1.5px solid var(--ink);background:var(--paper)}
  .order div{padding:30px;border-right:1.5px solid var(--ink);display:grid;gap:10px;align-content:start}
  .order div:last-child{border-right:0}
  .order .n{font-family:var(--head);font-size:3.2rem;line-height:1;font-weight:400;-webkit-text-stroke:1.2px var(--ink);color:transparent}
  .order p{color:var(--muted)}

  /* ===== faq ===== */
  .faq{border-top:1.5px solid var(--ink)}
  details{border-bottom:1px solid var(--hair)}
  summary{list-style:none;cursor:pointer;display:flex;justify-content:space-between;align-items:center;gap:20px;padding:24px 0;font-family:var(--head);text-transform:uppercase;letter-spacing:.05em;font-size:clamp(1.25rem,2.4vw,1.7rem);font-weight:500}
  summary::-webkit-details-marker{display:none}
  summary i{flex:none;width:30px;height:30px;border:1.5px solid var(--ink);position:relative;transition:background .3s,transform .4s var(--ease)}
  summary i::before,summary i::after{content:"";position:absolute;left:50%;top:50%;width:12px;height:1.5px;background:var(--ink);transform:translate(-50%,-50%);transition:background .3s,transform .4s var(--ease)}
  summary i::after{transform:translate(-50%,-50%) rotate(90deg)}
  details[open] summary i{background:var(--ink);transform:rotate(180deg)}
  details[open] summary i::before,details[open] summary i::after{background:var(--paper)}
  details[open] summary i::after{transform:translate(-50%,-50%) rotate(0)}
  details p{color:var(--muted);padding:0 60px 26px 0;max-width:760px;animation:drop .5s var(--ease)}
  @keyframes drop{from{opacity:0;transform:translateY(-8px)}}

  /* ===== контакты ===== */
  .contact{background:var(--ink);color:var(--paper)}
  .contact .kicker{color:rgba(255,255,255,.6)}
  .contact .kicker::before{background:var(--paper)}
  .cgrid{display:grid;grid-template-columns:1fr 1fr;gap:clamp(32px,6vw,90px);align-items:start}
  .contact .lead{color:rgba(255,255,255,.65);margin:20px 0 32px}
  .chan{display:grid;gap:0;border-top:1px solid rgba(255,255,255,.25)}
  .chan a{display:flex;align-items:center;justify-content:space-between;gap:16px;padding:20px 0;border-bottom:1px solid rgba(255,255,255,.25);transition:padding .4s var(--ease),background .4s}
  .chan a:hover{padding-left:16px;padding-right:16px;background:rgba(255,255,255,.06)}
  .chan b{display:block;font-family:var(--head);text-transform:uppercase;letter-spacing:.08em;font-size:1.4rem;font-weight:500}
  .chan small{color:rgba(255,255,255,.6);font-size:.95rem}
  .chan svg{width:24px;height:24px;transition:transform .35s var(--ease);flex:none}
  .chan a:hover svg{transform:translate(4px,-4px)}
  form{display:grid;gap:18px}
  label{display:grid;gap:8px;font-family:var(--head);text-transform:uppercase;letter-spacing:.16em;font-size:.9rem;color:rgba(255,255,255,.65)}
  input,select,textarea{width:100%;padding:14px 16px;border:1.5px solid rgba(255,255,255,.4);background:transparent;color:var(--paper);font:400 16px var(--body);letter-spacing:0;text-transform:none;border-radius:0;outline:none;transition:border-color .3s,background .3s}
  select option{color:#111}
  textarea{min-height:120px;resize:vertical}
  input::placeholder,textarea::placeholder{color:rgba(255,255,255,.35)}
  input:focus,select:focus,textarea:focus{border-color:var(--paper);background:rgba(255,255,255,.05)}
  form .btn{width:100%}
  .fine{font-size:.85rem;color:rgba(255,255,255,.5);text-align:center}

  footer{padding:30px 0;border-top:1px solid var(--hair);font-size:.93rem;color:var(--muted)}
  .foot{display:flex;justify-content:space-between;gap:16px;flex-wrap:wrap;align-items:center}
  .foot a:hover{color:var(--ink)}

  /* ===== reveal ===== */
  .reveal{opacity:0;transform:translateY(30px);transition:opacity .9s var(--ease),transform .9s var(--ease);transition-delay:var(--d,0s)}
  .reveal.in{opacity:1;transform:none}

  /* ===== адаптив ===== */
  @media (max-width:1000px){
    .hero-grid,.cgrid,.head{grid-template-columns:1fr}
    .head p{justify-self:start}
    .stage{max-width:620px;margin:0 auto}
    .grid3,.plans,.order{grid-template-columns:1fr}
    .svc{border-right:0;border-bottom:1.5px solid var(--ink)}
    .svc:last-child{border-bottom:0}
    .order div{border-right:0;border-bottom:1.5px solid var(--ink)}
    .order div:last-child{border-bottom:0}
    .why{grid-template-columns:1fr 1fr}
    .why div{border-right:0;padding-left:0;border-bottom:1px solid var(--hair);padding-bottom:26px}
    .flow{grid-template-columns:1fr;gap:28px}
    .flow::before{left:27px;right:auto;top:0;bottom:0;width:1.5px;height:auto}
    .st{display:grid;grid-template-columns:54px 1fr;gap:0 20px;padding:0}
    .st .dot{margin:0;grid-row:span 2}
    .slide{flex-basis:calc((100% - 24px)/1.35)}
  }
  @media (max-width:760px){
    .burger{display:block}
    .links{position:absolute;top:74px;left:0;right:0;background:var(--paper);flex-direction:column;align-items:stretch;gap:0;border-bottom:1.5px solid var(--ink);max-height:0;overflow:hidden;transition:max-height .5s var(--ease)}
    .links.open{max-height:520px}
    .links a:not(.btn){padding:18px var(--pad);border-top:1px solid var(--hair);font-size:1.15rem}
    .links a:not(.btn)::after{display:none}
    .links .btn{margin:18px var(--pad) 22px}
    .cta .btn{flex:1 1 100%}
    .slide{flex-basis:88%}
    .why{grid-template-columns:1fr}
    .foot{flex-direction:column;text-align:center}
    details p{padding-right:0}
    .arr{width:46px;height:46px}
  }
  @media (prefers-reduced-motion:reduce){
    *,*::before,*::after{animation:none!important;transition:none!important}
    html{scroll-behavior:auto}
    .reveal,.msg{opacity:1;transform:none}
  }
</style>
</head>
<body>

<!-- ЛОГО (используется в шапке и подвале) -->
<svg width="0" height="0" style="position:absolute" aria-hidden="true">
  <symbol id="logo" viewBox="0 0 720 410">
    <rect x="30" y="80" width="660" height="250" fill="none" stroke="currentColor" stroke-width="18"/>
    <text x="66" y="236" textLength="336" lengthAdjust="spacingAndGlyphs" font-family="Montserrat,'Segoe UI',Arial,sans-serif" font-size="122" font-weight="700" fill="currentColor">GIDE</text>
    <path d="M424 150 L470 232 L516 150" fill="none" stroke="currentColor" stroke-width="26" stroke-miterlimit="6"/>
    <g transform="translate(588 118) rotate(-38)" fill="currentColor">
      <rect x="0" y="0" width="14" height="72"/><rect x="0" y="0" width="44" height="14"/>
      <rect x="0" y="29" width="34" height="14"/><rect x="0" y="58" width="44" height="14"/>
    </g>
    <g fill="none" stroke="currentColor" stroke-width="3">
      <path d="M39 296 H350 L382 266 H468 L494 242"/>
      <path d="M39 308 H340 L372 278 H478 L504 254"/>
      <path d="M440 296 L470 266 H520 L546 242"/>
    </g>
  </symbol>
  <symbol id="arrow" viewBox="0 0 24 24"><path d="M4 12h16M14 6l6 6-6 6" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="square"/></symbol>
  <symbol id="out" viewBox="0 0 24 24"><path d="M6 18 18 6M8 6h10v10" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="square"/></symbol>
  <symbol id="tg" viewBox="0 0 24 24"><path d="m21.5 3.5-19 7.7 5.6 2 2 6.3 3.2-3.6 4.8 3.5L21.5 3.5Zm-13.4 9.7 9.9-6.1-7.6 7.3-.5 3.5-1.8-4.7Z" fill="currentColor"/></symbol>
</svg>

<header>
  <div class="wrap nav">
    <a href="#top" aria-label="GIDEV — на главную"><svg class="logo"><use href="#logo"/></svg></a>
    <button class="burger" id="burger" aria-label="Меню" aria-expanded="false"><i></i><i></i><i></i></button>
    <nav class="links" id="links">
      <a href="#services">Услуги</a>
      <a href="#works">Стили</a>
      <a href="#plans">Пакеты</a>
      <a href="#process">Процесс</a>
      <a href="#faq">FAQ</a>
      <a class="btn btn-sm" href="https://t.me/gidevvv" data-order="Консультация" target="_blank" rel="noopener">Консультация</a>
    </nav>
  </div>
</header>

<main id="top">

  <!-- 1. HERO -->
  <section class="hero">
    <div class="wrap hero-grid">
      <div>
        <p class="kicker reveal">Веб-разработка / Telegram-боты</p>
        <h1 class="reveal" style="--d:.07s">Сайты<br>и боты<em>под ключ</em></h1>
        <p class="lead reveal" style="--d:.14s">Делаю аккуратные сайты и Telegram-ботов, которые принимают заказы и заявки, пока вы занимаетесь бизнесом. Без лишнего — только то, что работает.</p>
        <div class="cta reveal" style="--d:.2s">
          <a class="btn btn-solid" href="https://t.me/gidevvv" data-order="Консультация" target="_blank" rel="noopener">Заказать <svg><use href="#arrow"/></svg></a>
          <a class="btn" href="#works">Смотреть стили</a>
        </div>
        <div class="socials reveal" style="--d:.26s">
          <span>Я в Telegram</span>
          <a class="soc" href="https://t.me/gidevvv" target="_blank" rel="noopener" aria-label="Личный профиль @gidevvv"><svg><use href="#tg"/></svg></a>
          <a class="soc" href="https://t.me/gidevv" target="_blank" rel="noopener" aria-label="Канал"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M4 10v4l12 5V5L4 10Z M16 8.5c2.2.6 3.5 1.9 3.5 3.5s-1.3 2.9-3.5 3.5M7 14.5l1.6 5h2.4l-1.4-4.2"/></svg></a>
          <a class="soc" href="https://t.me/gidevv_bot" target="_blank" rel="noopener" aria-label="Бот @gidevv_bot"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><rect x="4" y="8" width="16" height="12"/><path d="M12 8V4M9 13h.01M15 13h.01M9 17h6"/></svg></a>
        </div>
      </div>

      <div class="stage reveal" style="--d:.15s" aria-hidden="true">
        <div class="hatch"></div>
        <div class="outline"></div>
        <div class="browser">
          <div class="bar"><i></i><i></i><i></i></div>
          <div class="page">
            <div class="row"><b></b><span></span></div>
            <div class="t1"></div><div class="t2"></div>
            <div class="p"></div><div class="p" style="width:64%"></div>
            <span class="btnm">Заказать</span>
          </div>
        </div>
        <div class="phone">
          <div class="top"></div>
          <div class="msg bot">Здравствуйте! Что оформим?</div>
          <div class="msg me">Заказ</div>
          <div class="msg bot">Принято ✓ Передаю менеджеру</div>
        </div>
      </div>
    </div>
  </section>

  <div class="marquee" aria-hidden="true">
    <div>
      <span>Сайты</span><span>Telegram-боты</span><span>Консультации</span><span>Дизайн</span><span>Запуск и поддержка</span>
      <span>Сайты</span><span>Telegram-боты</span><span>Консультации</span><span>Дизайн</span><span>Запуск и поддержка</span>
    </div>
  </div>

  <!-- 2. УСЛУГИ -->
  <section id="services">
    <div class="wrap">
      <div class="head">
        <div>
          <p class="kicker reveal">01 — Услуги</p>
          <h2 class="reveal" style="--d:.06s">Что я делаю</h2>
        </div>
        <p class="reveal" style="--d:.12s">Три направления: от первого разговора до готового продукта. Можно взять что-то одно или собрать связку «сайт + бот».</p>
      </div>
      <div class="grid3 reveal">
        <article class="svc">
          <span class="num">01</span>
          <svg class="ic" viewBox="0 0 54 54"><rect x="4" y="9" width="46" height="32"/><path d="M4 17h46M19 49h16M27 41v8"/></svg>
          <h3>Сайты</h3>
          <p>Лендинги, сайты-визитки и каталоги, которые одинаково хорошо выглядят на телефоне, планшете и компьютере.</p>
          <ul><li>Дизайн под ваш бренд</li><li>Быстрая загрузка, SEO-основа</li><li>Формы заявок и связь с Telegram</li></ul>
          <a class="btn btn-sm" href="https://t.me/gidevvv" data-order="Сайт" target="_blank" rel="noopener">Заказать сайт</a>
        </article>
        <article class="svc">
          <span class="num">02</span>
          <svg class="ic" viewBox="0 0 54 54"><rect x="8" y="18" width="38" height="26"/><path d="M27 18V8M21 29h.01M33 29h.01M20 37h14"/><circle cx="27" cy="7" r="2.5"/></svg>
          <h3>Telegram-боты</h3>
          <p>Боты для приёма заказов, записи, каталога, оплаты и поддержки — клиент оформляет всё, не выходя из мессенджера.</p>
          <ul><li>Заказы и уведомления вам</li><li>Меню, каталог, корзина</li><li>Админ-панель в Telegram</li></ul>
          <a class="btn btn-sm" href="https://t.me/gidevvv" data-order="Telegram-бот" target="_blank" rel="noopener">Заказать бота</a>
        </article>
        <article class="svc">
          <span class="flag">С чего начать</span>
          <span class="num">03</span>
          <svg class="ic" viewBox="0 0 54 54"><path d="M8 10h38v26H24l-10 8v-8H8V10Z"/><path d="M17 20h20M17 27h12"/></svg>
          <h3>Консультация</h3>
          <p>Разберём вашу задачу, оценим сроки и подскажем, что нужно именно вам: сайт, бот или оба решения вместе.</p>
          <ul><li>Анализ идеи и аудитории</li><li>Подбор решения под бюджет</li><li>Понятный план действий</li></ul>
          <a class="btn btn-sm" href="https://t.me/gidevvv" data-order="Консультация" target="_blank" rel="noopener">Записаться</a>
        </article>
      </div>
    </div>
  </section>

  <!-- 3. СЛАЙДЕР: РАБОТЫ -->
  <section id="works" class="soft">
    <div class="wrap">
      <div class="head">
        <div>
          <p class="kicker reveal">02 — Стили</p>
          <h2 class="reveal" style="--d:.06s">Выберите свой стиль</h2>
        </div>
        <p class="reveal" style="--d:.12s">Один и тот же сайт можно оформить по-разному: спокойный минимализм, яркий максимализм или строгий Swiss. Листайте и выбирайте — цвета подберём под ваш бренд.</p>
      </div>

      <div class="slider reveal">
        <div class="track" id="track">
<article class="slide"><div class="shot"><div class="mk mk-min " style="--bg:#f6f2ec;--fg:#151515;--ac:#cdbba5;"><div class="mn-nav"><b>ATELIER</b><span><i></i><i></i><i></i></span></div><div class="mn-body"><div class="mn-l"><s></s><h4>Чистый<br>дизайн</h4><p></p><p></p><span class="mn-btn">Узнать больше</span></div><div class="mn-r"><div class="mn-fr"></div><div class="mn-bl"></div></div></div><div class="mn-ft"><u></u><u></u><u></u></div></div></div>
<div class="meta"><div class="tags"><span>Минимализм</span><span>песочный</span></div><h3>Минимализм · песочный</h3><p>Много воздуха, тонкие линии и спокойная палитра. Подходит студиям, экспертам и консультантам.</p><a class="btn btn-sm" href="https://t.me/gidevvv" data-order="Сайт в стиле: Минимализм · песочный" target="_blank" rel="noopener">Хочу такой стиль</a></div></article>
<article class="slide"><div class="shot"><div class="mk mk-max" style="--bg:#ffd400;--c1:#ff3d81;--c2:#2b2bff;--fg:#111;"><div class="mx-c1"></div><div class="mx-c2"></div><div class="mx-star"></div><div class="mx-nav"><b>POP!</b><span>Меню</span></div><h4>Ярко<br>и громко</h4><span class="mx-btn">Хочу!</span><div class="mx-badge">NEW</div><div class="mx-band"><span>Дизайн ✦ Дизайн ✦ Дизайн ✦ Дизайн ✦ Дизайн ✦ Дизайн ✦ Дизайн ✦ Дизайн ✦ Дизайн ✦ Дизайн ✦ </span></div></div></div>
<div class="meta"><div class="tags"><span>Максимализм</span><span>солнечный</span></div><h3>Максимализм · солнечный</h3><p>Яркие цвета, крупная типографика и смелые формы. Для брендов, которые хотят запомниться.</p><a class="btn btn-sm" href="https://t.me/gidevvv" data-order="Сайт в стиле: Максимализм · солнечный" target="_blank" rel="noopener">Хочу такой стиль</a></div></article>
<article class="slide"><div class="shot"><div class="mk mk-swiss" style="--bg:#f2f2f0;--fg:#111;--ac:#e30613;"><div class="sw-grid"><i></i><i></i><i></i><i></i></div><div class="sw-top"><b>FORM</b><span>Работы</span><span>Студия</span><span>Контакты</span></div><div class="sw-big">01</div><h4>Форма<br>следует<br>функции.</h4><div class="sw-circle"></div><div class="sw-p"><i></i><i></i><i></i></div></div></div>
<div class="meta"><div class="tags"><span>Swiss</span><span>красный</span></div><h3>Swiss · красный</h3><p>Строгая сетка, гротеск и один акцентный цвет. Чётко, читаемо, по-европейски.</p><a class="btn btn-sm" href="https://t.me/gidevvv" data-order="Сайт в стиле: Swiss · красный" target="_blank" rel="noopener">Хочу такой стиль</a></div></article>
<article class="slide"><div class="shot"><div class="mk mk-min flip" style="--bg:#e6eee4;--fg:#16231a;--ac:#8fb08f;"><div class="mn-nav"><b>LEAF</b><span><i></i><i></i><i></i></span></div><div class="mn-body"><div class="mn-l"><s></s><h4>Спокойный<br>сайт</h4><p></p><p></p><span class="mn-btn">Узнать больше</span></div><div class="mn-r"><div class="mn-fr"></div><div class="mn-bl"></div></div></div><div class="mn-ft"><u></u><u></u><u></u></div></div></div>
<div class="meta"><div class="tags"><span>Минимализм</span><span>шалфей</span></div><h3>Минимализм · шалфей</h3><p>Мягкие природные оттенки и аккуратные линии. Хорошо для услуг, связанных с заботой и комфортом.</p><a class="btn btn-sm" href="https://t.me/gidevvv" data-order="Сайт в стиле: Минимализм · шалфей" target="_blank" rel="noopener">Хочу такой стиль</a></div></article>
<article class="slide"><div class="shot"><div class="mk mk-max" style="--bg:#14002e;--c1:#00f5c4;--c2:#ff2bd6;--fg:#ffffff;"><div class="mx-c1"></div><div class="mx-c2"></div><div class="mx-star"></div><div class="mx-nav"><b>NEON</b><span>Меню</span></div><h4>Ночной<br>неон</h4><span class="mx-btn">Войти</span><div class="mx-badge">2026</div><div class="mx-band"><span>Дизайн ✦ Дизайн ✦ Дизайн ✦ Дизайн ✦ Дизайн ✦ Дизайн ✦ Дизайн ✦ Дизайн ✦ Дизайн ✦ Дизайн ✦ </span></div></div></div>
<div class="meta"><div class="tags"><span>Максимализм</span><span>неон</span></div><h3>Максимализм · неон</h3><p>Тёмный фон, свечение и насыщенные акценты. Для технологичных и молодёжных проектов.</p><a class="btn btn-sm" href="https://t.me/gidevvv" data-order="Сайт в стиле: Максимализм · неон" target="_blank" rel="noopener">Хочу такой стиль</a></div></article>
<article class="slide"><div class="shot"><div class="mk mk-swiss" style="--bg:#eceff5;--fg:#0a0a0a;--ac:#1f3cff;"><div class="sw-grid"><i></i><i></i><i></i><i></i></div><div class="sw-top"><b>GRID</b><span>Работы</span><span>Студия</span><span>Контакты</span></div><div class="sw-big">02</div><h4>Сетка<br>и порядок</h4><div class="sw-circle"></div><div class="sw-p"><i></i><i></i><i></i></div></div></div>
<div class="meta"><div class="tags"><span>Swiss</span><span>синий</span></div><h3>Swiss · синий</h3><p>Асимметричная вёрстка, крупные цифры и холодный синий акцент. Для корпоративных и IT-проектов.</p><a class="btn btn-sm" href="https://t.me/gidevvv" data-order="Сайт в стиле: Swiss · синий" target="_blank" rel="noopener">Хочу такой стиль</a></div></article>
</div>
        <div class="ctrl">
          <div class="dots" id="dots"></div>
          <div class="arrows">
            <button class="arr" id="prev" aria-label="Назад"><svg viewBox="0 0 24 24" style="transform:scaleX(-1)"><use href="#arrow"/></svg></button>
            <button class="arr" id="next" aria-label="Вперёд"><svg viewBox="0 0 24 24"><use href="#arrow"/></svg></button>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- 4. ПОЧЕМУ Я -->
  <section id="why">
    <div class="wrap">
      <div class="head">
        <div>
          <p class="kicker reveal">03 — Подход</p>
          <h2 class="reveal" style="--d:.06s">Почему это удобно</h2>
        </div>
        <p class="reveal" style="--d:.12s">Принципы, на которых строится каждый проект.</p>
      </div>
      <div class="why">
        <div class="reveal"><b>01</b><h3>Минимализм</h3><p>Ничего лишнего: чистый дизайн и понятная структура, где клиент сразу находит нужное.</p></div>
        <div class="reveal" style="--d:.08s"><b>02</b><h3>Все устройства</h3><p>Один и тот же аккуратный результат на телефоне, планшете и ноутбуке.</p></div>
        <div class="reveal" style="--d:.16s"><b>03</b><h3>Прямая связь</h3><p>Вы общаетесь напрямую со мной, а не с менеджерами. Быстрые ответы и понятные сроки.</p></div>
        <div class="reveal" style="--d:.24s"><b>04</b><h3>Под ключ</h3><p>Дизайн, разработка, запуск и поддержка — всё в одном месте, без подрядчиков.</p></div>
      </div>
    </div>
  </section>

  <!-- 5. ПРОЦЕСС -->
  <section id="process" class="soft">
    <div class="wrap">
      <div class="head">
        <div>
          <p class="kicker reveal">04 — Процесс</p>
          <h2 class="reveal" style="--d:.06s">Как мы работаем</h2>
        </div>
        <p class="reveal" style="--d:.12s">Пять понятных шагов от первого сообщения до запуска.</p>
      </div>
      <div class="flow">
        <div class="st reveal"><div class="dot">1</div><div><h3>Заявка</h3><p>Пишете мне в Telegram и коротко описываете задачу.</p></div></div>
        <div class="st reveal" style="--d:.08s"><div class="dot">2</div><div><h3>Обсуждение</h3><p>Уточняем цели, функции, сроки и бюджет.</p></div></div>
        <div class="st reveal" style="--d:.16s"><div class="dot">3</div><div><h3>Дизайн</h3><p>Показываю структуру и внешний вид до начала разработки.</p></div></div>
        <div class="st reveal" style="--d:.24s"><div class="dot">4</div><div><h3>Разработка</h3><p>Делаю проект и показываю промежуточные результаты.</p></div></div>
        <div class="st reveal" style="--d:.32s"><div class="dot">5</div><div><h3>Запуск</h3><p>Публикую, проверяю на всех устройствах и остаюсь на связи.</p></div></div>
      </div>
    </div>
  </section>

  <!-- 6. ПАКЕТЫ -->
  <section id="plans">
    <div class="wrap">
      <div class="head">
        <div>
          <p class="kicker reveal">05 — Пакеты</p>
          <h2 class="reveal" style="--d:.06s">Выберите формат</h2>
        </div>
        <p class="reveal" style="--d:.12s">Стоимость зависит от объёма задачи и называется после консультации — без скрытых платежей.</p>
      </div>
      <div class="plans">
        <article class="plan reveal">
          <h3>Старт</h3>
          <p class="sub">Лендинг или сайт-визитка для быстрого запуска.</p>
          <ul><li>Одностраничный сайт</li><li>Адаптив под все устройства</li><li>Форма заявки → Telegram</li><li>Публикация в интернете</li></ul>
          <p class="price">Стоимость — после консультации</p>
          <a class="btn btn-sm" href="https://t.me/gidevvv" data-order="Пакет «Старт»" target="_blank" rel="noopener">Обсудить</a>
        </article>
        <article class="plan top reveal" style="--d:.1s">
          <h3>Бизнес</h3>
          <p class="sub">Сайт и Telegram-бот, которые работают вместе.</p>
          <ul><li>Многостраничный сайт или каталог</li><li>Бот для заказов или записи</li><li>Уведомления о заявках вам</li><li>Админ-панель в Telegram</li><li>Поддержка после запуска</li></ul>
          <p class="price">Стоимость — после консультации</p>
          <a class="btn btn-sm" href="https://t.me/gidevvv" data-order="Пакет «Бизнес»" target="_blank" rel="noopener">Обсудить</a>
        </article>
        <article class="plan reveal" style="--d:.2s">
          <h3>Индивидуально</h3>
          <p class="sub">Нестандартная задача или сложная логика.</p>
          <ul><li>Разбор вашей идеи</li><li>Уникальный функционал</li><li>Интеграции и оплата</li><li>Сроки и этапы под вас</li></ul>
          <p class="price">Стоимость — после консультации</p>
          <a class="btn btn-sm" href="https://t.me/gidevvv" data-order="Индивидуальный проект" target="_blank" rel="noopener">Обсудить</a>
        </article>
      </div>
    </div>
  </section>

  <!-- 7. КАК ЗАКАЗАТЬ -->
  <section class="soft">
    <div class="wrap">
      <div class="head">
        <div>
          <p class="kicker reveal">06 — Заказ</p>
          <h2 class="reveal" style="--d:.06s">Как оформить заказ</h2>
        </div>
        <p class="reveal" style="--d:.12s">Никаких сложных форм: все заявки приходят мне напрямую в личные сообщения.</p>
      </div>
      <div class="order reveal">
        <div><span class="n">01</span><h3>Нажмите «Заказать»</h3><p>Выберите услугу на сайте — кнопка подставит её в сообщение.</p></div>
        <div><span class="n">02</span><h3>Откроется чат</h3><p>Вы перейдёте в мой личный профиль в Telegram с готовым текстом.</p></div>
        <div><span class="n">03</span><h3>Обсудим детали</h3><p>Отвечаю лично, уточняю задачу и называю сроки и стоимость.</p></div>
      </div>
    </div>
  </section>

  <!-- 8. FAQ -->
  <section id="faq">
    <div class="wrap">
      <div class="head">
        <div>
          <p class="kicker reveal">07 — Вопросы</p>
          <h2 class="reveal" style="--d:.06s">Частые вопросы</h2>
        </div>
        <p class="reveal" style="--d:.12s">Если не нашли ответ — напишите мне, отвечу в Telegram.</p>
      </div>
      <div class="faq reveal">
        <details open><summary>Сколько времени занимает разработка?<i></i></summary><p>Лендинг обычно делается быстрее всего, бот и многостраничный сайт требуют больше времени. Точные сроки я называю после обсуждения задачи.</p></details>
        <details><summary>Как происходит оплата?<i></i></summary><p>Условия и этапы оплаты согласовываем в личной переписке до начала работы, чтобы всё было прозрачно.</p></details>
        <details><summary>Сайт будет удобен на телефоне?<i></i></summary><p>Да. Каждый сайт проверяется на телефоне, планшете и компьютере, чтобы выглядел и работал одинаково хорошо.</p></details>
        <details><summary>Что умеет бот для заказов?<i></i></summary><p>Показывает меню или каталог, принимает заказы, отправляет вам уведомления и может иметь панель администратора прямо в Telegram.</p></details>
        <details><summary>Можно ли что-то изменить после запуска?<i></i></summary><p>Да, я остаюсь на связи: помогу с правками, обновлениями и развитием проекта.</p></details>
      </div>
    </div>
  </section>

  <!-- 9. КОНТАКТЫ -->
  <section id="contact" class="contact">
    <div class="wrap cgrid">
      <div>
        <p class="kicker reveal">08 — Контакты</p>
        <h2 class="reveal" style="--d:.06s">Обсудим<br>ваш проект?</h2>
        <p class="lead reveal" style="--d:.12s">Напишите мне напрямую — отвечу лично. Или оставьте сообщение через форму: оно откроется в моём чате.</p>
        <div class="chan reveal" style="--d:.18s">
          <a href="https://t.me/gidevvv" target="_blank" rel="noopener"><div><b>Личные сообщения</b><small>@gidevvv</small></div><svg><use href="#out"/></svg></a>
          <a href="https://t.me/gidevv" target="_blank" rel="noopener"><div><b>Telegram-канал</b><small>t.me/gidevv</small></div><svg><use href="#out"/></svg></a>
          <a href="https://t.me/gidevv_bot" target="_blank" rel="noopener"><div><b>Бот</b><small>@gidevv_bot</small></div><svg><use href="#out"/></svg></a>
        </div>
      </div>
      <form id="form" class="reveal" style="--d:.12s">
        <label>Что нужно
          <select id="service">
            <option>Консультация</option><option>Сайт</option><option>Telegram-бот</option><option>Сайт + бот</option>
          </select>
        </label>
        <label>Ваше имя<input id="name" type="text" placeholder="Как к вам обращаться" autocomplete="name"></label>
        <label>Коротко о задаче<textarea id="msg" placeholder="Например: нужен бот для приёма заказов в кафе"></textarea></label>
        <button class="btn btn-inv" type="submit">Написать в Telegram <svg><use href="#arrow"/></svg></button>
        <p class="fine">Откроется личный чат @gidevvv с готовым сообщением — останется нажать «Отправить».</p>
      </form>
    </div>
  </section>
</main>

<footer>
  <div class="wrap foot">
    <span>© <span id="year"></span> GIDEV. Все права защищены.</span>
    <span><a href="https://t.me/gidevv" target="_blank" rel="noopener">Канал</a> &nbsp;/&nbsp; <a href="https://t.me/gidevvv" target="_blank" rel="noopener">@gidevvv</a> &nbsp;/&nbsp; <a href="https://t.me/gidevv_bot" target="_blank" rel="noopener">@gidevv_bot</a></span>
  </div>
</footer>

<script>
  const PROFILE = 'https://t.me/gidevvv';  // личный профиль, куда уходят все заказы
  const $ = (s, r = document) => r.querySelector(s);
  const $$ = (s, r = document) => [...r.querySelectorAll(s)];

  $('#year').textContent = new Date().getFullYear();

  // ссылка на личный чат с готовым текстом
  const orderLink = (service, name = '', msg = '') => {
    const text = `Здравствуйте! Хочу заказать: ${service}.` +
      (name ? `\nМеня зовут ${name}.` : '') + (msg ? `\nЗадача: ${msg}` : '');
    return `${PROFILE}?text=${encodeURIComponent(text)}`;
  };
  $$('[data-order]').forEach(a => a.href = orderLink(a.dataset.order));

  $('#form').addEventListener('submit', e => {
    e.preventDefault();
    window.open(orderLink($('#service').value, $('#name').value.trim(), $('#msg').value.trim()), '_blank', 'noopener');
  });

  // мобильное меню
  const burger = $('#burger'), links = $('#links');
  burger.addEventListener('click', () => {
    burger.setAttribute('aria-expanded', links.classList.toggle('open'));
  });
  $$('#links a').forEach(a => a.addEventListener('click', () => {
    links.classList.remove('open'); burger.setAttribute('aria-expanded', 'false');
  }));

  // плавное появление
  const io = new IntersectionObserver(es => es.forEach(e => {
    if (e.isIntersecting) { e.target.classList.add('in'); io.unobserve(e.target); }
  }), { threshold: .12 });
  $$('.reveal').forEach(el => io.observe(el));

  // скрыть заглушку, если картинка существует
  $$('.shot[data-src]').forEach(s => {
    const im = new Image();
    im.onload = () => s.classList.add('has');
    im.src = s.dataset.src;
  });

  // слайдер
  const track = $('#track'), slides = $$('.slide', track), dots = $('#dots');
  slides.forEach((_, i) => {
    const b = document.createElement('button');
    b.setAttribute('aria-label', 'Слайд ' + (i + 1));
    b.onclick = () => goTo(i);
    dots.appendChild(b);
  });
  const step = () => slides[0].getBoundingClientRect().width + 24;
  const index = () => Math.round(track.scrollLeft / step());
  const goTo = i => track.scrollTo({ left: Math.max(0, Math.min(i, slides.length - 1)) * step(), behavior: 'smooth' });
  const paint = () => $$('button', dots).forEach((b, i) => b.classList.toggle('on', i === index()));
  track.addEventListener('scroll', () => requestAnimationFrame(paint), { passive: true });
  $('#next').onclick = () => { const atEnd = track.scrollLeft + track.clientWidth >= track.scrollWidth - 4; goTo(atEnd ? 0 : index() + 1); };
  $('#prev').onclick = () => goTo(index() - 1);
  paint();

  // автопрокрутка (пауза при наведении и касании)
  let timer, paused = false;
  const auto = () => { clearInterval(timer); timer = setInterval(() => { if (!paused && !document.hidden) $('#next').click(); }, 5500); };
  ['mouseenter', 'touchstart', 'focusin'].forEach(ev => track.addEventListener(ev, () => paused = true, { passive: true }));
  ['mouseleave', 'touchend', 'focusout'].forEach(ev => track.addEventListener(ev, () => paused = false, { passive: true }));
  if (!matchMedia('(prefers-reduced-motion: reduce)').matches) auto();
</script>
</body>
</html>
