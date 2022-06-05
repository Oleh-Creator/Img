<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
.wrap{
    width: 100%;
    height: 100vh;
    background-size: cover;
    display: flex;
    justify-content: center;
    align-items: center;
}
.inp{
    width: 40%;
    height: 50px;
    background-color: rgba(0, 0, 0, 0.5);
    border: none;
    padding: 0 20px;
    outline: none;
    border-radius: 10px;
    color: white;
    font-size: 28px;
    font-family: Montserrat;
    margin: 10px;
}
.findPhoto{
    padding: 15px 30px;
    background-color: rgba(0, 0, 0, 0.9);
    border:none;
    color: #fff;
    border-radius: 10xp;
}
::placeholder{
    color:#fff
}
    </style>
</head>
<body>
    <div class="wrap" id="wrap">
        <input type="text" id="inp" placeholder="Введи тему зображення" class="inp">
        <button id="findPhoto" class="findPhoto">Знайти</button>
    </div>
    <script>
function getPhoto(){
    fetch('https://source.unsplash.com/1920x1080')
.then(res=>{
    let pic =(res.url);
    wrap.style.backgroundImage = "url("+pic+")";
    inp.value = '';
})
}
getPhoto();
        
     findPhoto.onclick = function(){                   
fetch('https://source.unsplash.com/1920x1080/?'+inp.value)
.then(res=>{
    let pic =(res.url);
    wrap.style.backgroundImage = "url("+pic+")";
    inp.value = '';
})
     }
     setInterval(function(){
         getPhoto();
     },100000)
    </script>
</body>
</html>
