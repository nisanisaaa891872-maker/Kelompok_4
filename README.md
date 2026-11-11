
from pptx import Presentation
from pptx.util import Inches, Pt
from pptx.dml.color import RGBColor
from pptx.enum.text import PP_ALIGN

# Membuat presentasi baru
ppt = Presentation()

# Data materi presentasi
materi = [
    ("ALGORITMA DIVIDE AND CONQUER",
     "Pencarian Nama di Kamus Menggunakan Python"),

    ("PENGERTIAN",
     "Divide and Conquer adalah algoritma yang "
     "membagi masalah besar menjadi bagian kecil "
     "agar lebih mudah diselesaikan."),

    ("CARA KERJA",
     "1. Divide: Membagi data menjadi dua bagian.\n"
     "2. Compare: Membandingkan data.\n"
     "3. Conquer: Memilih bagian yang sesuai.\n"
     "4. Repeat: Mengulangi sampai ditemukan."),

    ("CONTOH PENERAPAN",
     "Mencari nama NISA dalam daftar nama "
     "yang sudah diurutkan berdasarkan abjad "
     "menggunakan metode Binary Search."),

    ("KESIMPULAN",
     "Algoritma Divide and Conquer membantu "
     "mempercepat proses pencarian data "
     "dengan membagi masalah menjadi bagian "
     "yang lebih kecil.")
]

# Membuat setiap slide
for judul, isi in materi:

    slide = ppt.slides.add_slide(
        ppt.slide_layouts[6]
    )

    # Membuat kotak judul
    title_box = slide.shapes.add_textbox(
        Inches(0.7), Inches(0.5),
        Inches(8), Inches(1)
    )

    title = title_box.text_frame
    title.text = judul

    p = title.paragraphs[0]
    p.font.size = Pt(28)
    p.font.bold = True
    p.font.color.rgb = RGBColor(0, 70, 140)

    # Membuat kotak isi
    content_box = slide.shapes.add_textbox(
        Inches(0.8), Inches(2),
        Inches(8), Inches(4)
    )

    content = content_box.text_frame
    content.word_wrap = True
    content.text = isi

    p = content.paragraphs[0]
    p.font.size = Pt(20)
    p.font.color.rgb = RGBColor(40, 40, 40)

# Menyimpan file PPT
ppt.save("Presentasi_Divide_and_Conquer.pptx")

print("PPT berhasil dibuat!")


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
