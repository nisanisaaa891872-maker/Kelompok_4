# Kelompok_4```html
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pesan Rahasia</title>

<style>
    *{
        margin:0;
        padding:0;
        box-sizing:border-box;
        font-family: Arial, sans-serif;
    }

    body{
        background: linear-gradient(135deg,#1e1e2f,#3b3b98);
        height:100vh;
        display:flex;
        justify-content:center;
        align-items:center;
        color:white;
    }

    .container{
        width:90%;
        max-width:500px;
        background: rgba(255,255,255,0.1);
        padding:30px;
        border-radius:20px;
        backdrop-filter: blur(10px);
        box-shadow:0 10px 30px rgba(0,0,0,0.3);
    }

    h1{
        text-align:center;
        margin-bottom:20px;
    }

    label{
        display:block;
        margin-top:15px;
        margin-bottom:8px;
    }

    textarea,
    input{
        width:100%;
        padding:12px;
        border:none;
        border-radius:10px;
        outline:none;
        font-size:16px;
    }

    textarea{
        resize:none;
        height:120px;
    }

    button{
        width:100%;
        padding:12px;
        margin-top:20px;
        border:none;
        border-radius:10px;
        background:#ffcc00;
        color:black;
        font-weight:bold;
        cursor:pointer;
        transition:0.3s;
    }

    button:hover{
        background:#ffd633;
        transform:scale(1.03);
    }

    .hasil{
        margin-top:20px;
        background:rgba(0,0,0,0.2);
        padding:15px;
        border-radius:10px;
        min-height:80px;
        word-wrap:break-word;
    }

    .info{
        margin-top:10px;
        font-size:14px;
        opacity:0.8;
        text-align:center;
    }
</style>
</head>

<body>

<div class="container">
    <h1>🔒 Pesan Rahasia</h1>

    <label>Tulis Pesan:</label>
    <textarea id="pesan" placeholder="Masukkan pesan rahasia..."></textarea>

    <label>Kata Kunci:</label>
    <input type="password" id="kunci" placeholder="Masukkan kata kunci">

    <button onclick="enkripsiPesan()">Ubah Jadi Rahasia</button>

    <div class="hasil" id="hasil">
        Hasil pesan rahasia akan muncul di sini...
    </div>

    <div class="info">
        Masukkan kata kunci yang benar untuk membuka pesan.
    </div>

    <button onclick="bukaPesan()">Buka Pesan</button>
</div>

<script>
    let pesanAsli = "";
    let kataKunciBenar = "";

    // Daftar emoji rahasia
    const emojiList = [
        "😀","😎","👻","🔥","🌙","⭐","💎","🎵",
        "🍕","🚀","🐱","🦄","⚡","🌈","🎮","💀"
    ];

    function enkripsiPesan() {
        const pesan = document.getElementById("pesan").value;
        const kunci = document.getElementById("kunci").value;

        if(pesan === "" || kunci === ""){
            alert("Isi pesan dan kata kunci terlebih dahulu!");
            return;
        }

        pesanAsli = pesan;
        kataKunciBenar = kunci;

        let hasilRahasia = "";

        for(let i=0; i<pesan.length; i++){
            const randomEmoji = emojiList[Math.floor(Math.random() * emojiList.length)];
            hasilRahasia += randomEmoji;
        }

        document.getElementById("hasil").innerHTML = hasilRahasia;
    }

    function bukaPesan() {
        const inputKunci = prompt("Masukkan kata kunci untuk membuka pesan:");

        if(inputKunci === kataKunciBenar){
            document.getElementById("hasil").innerHTML =
                "✅ Pesan Asli:<br><br>" + pesanAsli;
        } else {
            alert("❌ Kata kunci salah!");
        }
    }
</script>

</body>
</html>
```
