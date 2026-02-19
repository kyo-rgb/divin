<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>A Hug For You</title>
<link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;600&display=swap" rel="stylesheet">
<style>
  body{margin:0;height:100vh;display:flex;justify-content:center;align-items:center;background: radial-gradient(circle at top,#ffe4f1,#fff3e6,#e8f7ff);font-family:'Quicksand',sans-serif;text-align:center;overflow:hidden}
  h1{color:#ff5fa2;margin-top:20px;font-weight:600;letter-spacing:.5px}
  .bear{position:relative;width:230px;height:240px;animation:bounce 3s ease-in-out infinite}
  .bear.squeeze{animation:bounce 3s ease-in-out infinite, squeeze 0.6s ease-in-out 2}
  @keyframes squeeze{0%{transform:scale(1)}50%{transform:scale(0.9,1.05)}100%{transform:scale(1)}}
  @keyframes bounce{0%,100%{transform:translateY(0)}50%{transform:translateY(-12px)}}
  .head{width:150px;height:140px;background:#fff;border-radius:70px;position:absolute;left:50%;transform:translateX(-50%);top:0;box-shadow:0 12px 25px rgba(0,0,0,.12)}
  .ear{width:55px;height:55px;background:#fff;border-radius:50%;position:absolute;top:-20px;box-shadow:0 6px 12px rgba(0,0,0,.1)}
  .ear.left{left:-10px}.ear.right{right:-10px}
  .ear:after{content:"";position:absolute;width:28px;height:28px;background:#ffd1e6;border-radius:50%;top:50%;left:50%;transform:translate(-50%,-50%)}
  .eye{width:16px;height:16px;background:#2d2d2d;border-radius:50%;position:absolute;top:55px}
  .eye.left{left:40px}.eye.right{right:40px}
  .eye:after{content:"";position:absolute;width:6px;height:6px;background:white;border-radius:50%;top:2px;left:3px}
  .blush{width:26px;height:14px;background:#ffc1da;border-radius:50%;position:absolute;top:78px;opacity:.8}
  .blush.left{left:22px}.blush.right{right:22px}
  .mouth{width:36px;height:20px;border-bottom:4px solid #2d2d2d;border-radius:0 0 40px 40px;position:absolute;top:82px;left:50%;transform:translateX(-50%)}
  .body{width:170px;height:140px;background:#fff;border-radius:80px;position:absolute;left:50%;transform:translateX(-50%);top:110px;box-shadow:0 12px 25px rgba(0,0,0,.12)}
  .arm{width:110px;height:38px;background:#fff;border-radius:40px;position:absolute;top:140px;box-shadow:0 8px 18px rgba(0,0,0,.12);animation:hug 2.4s ease-in-out infinite}
  .arm.left{left:-20px;transform-origin:right center}
  .arm.right{right:-20px;transform-origin:left center;animation-delay:1.2s}
  @keyframes hug{0%,100%{transform:rotate(0deg)}50%{transform:rotate(55deg)}}
  .hug{position:fixed;font-size:28px;animation:fall linear forwards}
  @keyframes fall{0%{transform:translateY(-10vh) rotate(0);opacity:1}100%{transform:translateY(110vh) rotate(360deg);opacity:0.9}}
  button{margin-top:24px;padding:10px 20px;border:none;border-radius:25px;background:#ff6fb0;color:white;font-size:14px;cursor:pointer;box-shadow:0 6px 15px rgba(255,111,176,.4)}
</style>
</head>
<body>
<div>
  <div class="bear">
    <div class="head">
      <div class="ear left"></div>
      <div class="ear right"></div>
      <div class="eye left"></div>
      <div class="eye right"></div>
      <div class="blush left"></div>
      <div class="blush right"></div>
      <div class="mouth"></div>
    </div>
    <div class="body"></div>
    <div class="arm left"></div>
    <div class="arm right"></div>
  </div>
  <h1>divin cutie, i hope this makes your day better 💗</h1>
  <button onclick="hugRain()">send more hugs</button>
</div>
<script>
function hugRain(){
  const bear=document.querySelector('.bear');
  bear.classList.add('squeeze');
  setTimeout(()=>bear.classList.remove('squeeze'),1200);
  for(let i=0;i<40;i++){
    const h=document.createElement('div');
    h.className='hug';
    h.innerText='🤗';
    h.style.left=Math.random()*100+'vw';
    h.style.animationDuration=(3+Math.random()*2)+'s';
    document.body.appendChild(h);
    setTimeout(()=>h.remove(),5000);
  }
}
</script>
</body>
</html>
