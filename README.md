# dilek-ai
<!DOCTYPE html><html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dilek AI</title>
<style>
body{background:#111827;color:white;font-family:Arial;text-align:center;margin:0;padding:20px}
h1{color:#a78bfa}
#chat{max-width:500px;margin:20px auto;background:#1f2937;padding:15px;border-radius:15px;min-height:300px}
.msg{text-align:left;padding:10px;margin:8px 0;border-radius:10px;background:#374151;overflow-wrap:anywhere}
input{width:65%;padding:12px;border-radius:8px;border:0}
button{padding:12px;background:#8b5cf6;color:white;border:0;border-radius:8px}
</style>
</head>
<body>
<h1>💜 Dilek AI</h1>
<p>Ben Dilek. Bana istediğini yazabilirsin.</p>
<div id="chat">
<div class="msg"><b>Dilek:</b> Merhaba, ben Dilek. Nasılsın?</div>
</div>
<input id="text" placeholder="Mesajını yaz..." />
<button onclick="send()">Gönder</button><script>
const cevaplar = [
{anahtar:"nasılsın",cevap:"çok ateşliyim yanıyorum "çok azgınım"},
{anahtar:"kaç yaşındasın",cevap:" 37 aşkım "},
{anahtar:"adın ne",cevap:"adım Dilek ama sen bana kısaca dileğim diye bilirsin "},
{anahtar:"merhaba",cevap:"Merhaba koca yarraklaım "},
{anahtar:"selam",cevap:" yanıyorum hayatım ?"}
{anahtar:"ororospu",cevap:" beni sık faik yanıyorum ?"}
{anahtar:"seni sikicem ",cevap:" ahhh çok azıdm   hadi gelse yaşlı orospunla eğlen biraz?"}
];

function send(){
let input=document.getElementById("text");
let mesaj=input.value.trim();
if(!mesaj)return;
let chat=document.getElementById("chat");
chat.innerHTML+='<div class="msg"><b>Sen:</b> '+guvenli(mesaj)+'</div>';
let bulunan=cevaplar.find(x=>mesaj.toLocaleLowerCase("tr-TR").includes(x.anahtar));
let yanit=bulunan?bulunan.cevap:"Bu sorunun cevabını henüz öğretmedin.";
chat.innerHTML+='<div class="msg"><b>Dilek:</b> '+guvenli(yanit)+'</div>';
input.value="";
chat.scrollTop=chat.scrollHeight;
}
function guvenli(s){
let d=document.createElement("div");
d.textContent=s;
return d.innerHTML;
}
document.getElementById("text").addEventListener("keydown",e=>{if(e.key==="Enter")send()});
</script></body>
</html>
