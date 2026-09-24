<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Khusus capiibayaa kuu sayangg :D</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.5.1/dist/confetti.browser.min.js"></script>
    <style>
        :root {
            --pink-soft: #e4caad;
            --pink-hot: #705123;
            --dark-red: #413213;
        }

        body {
            margin: 0; padding: 0;
            font-family: 'Poppins', sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
            background: linear-gradient(rgba(255, 206, 143, 0.8), rgba(255, 220, 168, 0.8)), 
                        url('https://capii.edgeone.app/How%20to%20make%20your%20phone%20aesthetic%20🌷%20Android%20Customization,%20Cute%20home%20screen%20💞%20Aesthetic%20Realme%20C53.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            overflow-x: hidden;
        }

        /* --- GOOGLE NOTIFICATION --- */
        #googleNotif {
            position: fixed;
            top: -100px;
            left: 50%;
            transform: translateX(-50%);
            width: 90%;
            max-width: 400px;
            background: white;
            border-radius: 12px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.15);
            display: flex;
            align-items: center;
            padding: 15px;
            z-index: 3000;
            transition: 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }
        #googleNotif.show { top: 20px; }
        .google-icon { width: 40px; height: 40px; margin-right: 15px; }

        /* --- FOTO ANIMASI POPUP --- */
        #photoPopup {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0);
            width: 80%;
            max-width: 350px;
            z-index: 2500;
            transition: 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
            border: 10px solid white;
            border-radius: 20px;
            box-shadow: 0 20px 50px rgba(0,0,0,0.3);
            background: white;
        }
        #photoPopup.active { transform: translate(-50%, -50%) scale(1); }
        #photoPopup img { width: 100%; border-radius: 10px; display: block; }

        /* --- OVERLAY AWAL --- */
        #overlay {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: var(--pink-soft);
            z-index: 4000;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: 0.5s;
        }

        /* --- FRAME & CONTENT --- */
        .frame-container { margin-top: 50px; width: 90%; max-width: 600px; }
        .photo-frame { background: white; padding: 12px; border-radius: 15px; animation: float 5s ease-in-out infinite; box-shadow: 0 15px 35px rgba(0,0,0,0.2); }
        .image-wrapper { width: 100%; padding-top: 56.25%; position: relative; overflow: hidden; border-radius: 10px; }
        .image-wrapper img { position: absolute; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover; }

        @keyframes float { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-15px); } }

        .content { text-align: center; max-width: 500px; width: 85%; margin: 30px auto; }
        .rose-icon { font-size: 60px; cursor: pointer; animation: pulse 2s infinite; }
        @keyframes pulse { 0%, 100% { transform: scale(1); } 50% { transform: scale(1.1); } }

        #letterBox { background: rgba(255, 255, 255, 0.9); padding: 30px; border-radius: 20px; border: 2px dashed var(--pink-hot); display: none; text-align: left; }
        .typewriter-text { font-family: 'Dancing Script', cursive; font-size: 1.4rem; color: var(--dark-red); line-height: 1.6; white-space: pre-line; }

        /* --- QUIZ SECTION --- */
        #quizSection { display: none; margin-top: 30px; }
        
        /* Mengatur tombol agar sejajar ke samping */
        .btn-group { 
            display: flex; 
            justify-content: center; 
            align-items: center;
            gap: 40px; /* Jarak antar tombol */
            margin-top: 20px; 
            min-height: 80px;
            position: relative;
        }

        .btn { 
            padding: 12px 35px; 
            border: none; 
            border-radius: 25px; 
            font-weight: bold; 
            cursor: pointer; 
            transition: 0.3s;
            font-family: 'Poppins', sans-serif;
        }

        .btn-yes { 
            background: #80522d; 
            color: white; 
            z-index: 10;
        }

        /* Tombol No sekarang punya posisi relatif awal agar tidak di tengah */
        .btn-no { 
            background: #d3ac73; 
            color: white; 
            transition: 0.2s ease;
            white-space: nowrap;
        }

        .btn-open { padding: 15px 35px; background: var(--pink-hot); color: white; border: none; border-radius: 50px; font-weight: bold; cursor: pointer; }
    </style>
</head>
<body>

    <div id="googleNotif">
        <img src="https://changing-gold-q8elkgaywc.edgeone.app/Capybara.jpg" class="google-icon" alt="G">
        <div>
            <b style="color: #5f6368; font-size: 0.8rem;">Google Assistant</b>
            <p style="margin: 0; font-size: 0.9rem; color: #202124;">Capiibaya bilang dia sayang kamu juga! ❤️</p>
        </div>
    </div>

    <div id="photoPopup">
        <img src="https://noble-turquoise-vacgrc2arh.edgeone.app/Capybara%20Wow%20GIF%20by%20sansanplanet%20-%20Find%20&%20Share%20on%20GIPHY.gif" alt="Foto Kita Sayang">
        <p style="text-align: center; font-weight: bold; color: var(--pink-hot); margin: 10px 0;">YEAAAYY KAMUUU SAYANGGG AKUWUQUQU YEYEYEYEY</p>
    </div>

    <div id="overlay">
        <button class="btn-open" onclick="init()">klik tombol inii sayangg ❤️</button>
    </div>

    <audio id="music" loop>
        <source src="https://melodic-teal-eolzi37qea.edgeone.app/John%20Mayer%20-%20You%27re%20Gonna%20Live%20Forever%20In%20Me%20_%20Lirik%20Terjemahan.mp3" type="audio/mpeg">
    </audio>

    <div class="frame-container">
        <div class="photo-frame">
            <div class="image-wrapper">
                <img src="https://open-turquoise-8m0zznbgyb.edgeone.app/Gwe%20dan%20cikaimot.jpg.jpeg" alt="Foto Kita">
            </div>
        </div>
    </div>

    <div class="content">
        <div class="rose-icon" onclick="startTyping()">🦫</div>
        <p id="hint">klik capiibayaa yang adaa di atass :D</p>

        <div id="letterBox">
            <div id="textTarget" class="typewriter-text"></div>
        </div>

        <div id="quizSection">
            <h3 style="color: var(--dark-red);">Do you love me?😢</h3>
            <div class="btn-group">
                <button class="btn btn-yes" onclick="showEverything()">YEAAAA!!!</button>
                <button id="btnNo" class="btn btn-no" onmouseover="moveButton()" onclick="moveButton()">no :< </button>
            </div>
        </div>
    </div>

    <script>
        const pesan = `Sweet message special for Dechika Aulia -
20/02/2026

Gakerasaa yaa... udaahh 1 bulaaann ajaa kitaa ngejalanin relationship ini hehe. padahal kaloo akuu flashback ke awal kitaa ketemuu tuh kita cuman temen ekskul biasaa🙄🙄 dan juga dulu kita ga sedekat itu, i mean. terus kalo kita bercanda, ngomong bareng, aku ngerasa seneng banget tau sayanggg karena hati aku kekamu beda sama ke yang lain, pas awal awal akutuh ngerasa aneh sama perasaan aku sendiri tau.. kek mana yaa sayangg, kek " loh masa aku suka sama cewe sih?? gamungkin kocak, padahal aku cuman sebatas kagum aja sama chika, karena chika cantik makanya aku kagum sama dia, gamungkin aku suka sampe segininya" karena ya sayang pas aku kenal kamu sikap aku jadi beda.. aku jadi pengen berteman sama semua anak db rasanya biar bisa deket sama kamu, padahal aku orang nya pemalu banget bisa di bilang.. tapi karena aku nekat mau temenan sama kamu makanya aku nemenin semua anak db biar bisa dekat juga samaa kamu. sebenarnya ini sikrit sih sayang, makanya aku jadi se friendly ini dan jadi sebanyak ini teman ku karena aku nekat buat deketin kamu doang sayang. kalo bukan karena kamu & masuk ekskul db aku gabakal se extrovert ini sayangg :( aku asli nya introvert yang maksa jadi extrovert, waktu smp aku memang kadang sedikit extrovert tapi extrovert nya tuh kek ga kaya di smk ini sayang, pas di smk aku bener bener berubah, intinya i lost my old self. karena bby, & karena pergaulan disini aku bisa belajar bahwa penampilan selayaknya cewe itu penting. semenjak aku kenal bby, aku makin semangat ubahin hidup aku sayang.. aku beneran makin jadi cewe feminim meskipun kadang masih ada masc nya sedikit. yaa jadii gitu dehh, intinya aku mau bilang kalau bby tuh beneran udah mengubah hidup aku yang suram ini jadi berwarna, karena bby aku semakin semangat buat jalanin hidup setiap harinya ehehgege loafyuu:3

Oiyaa sayangg, aku jadi keinget deh.. dulu akutuh cuma bisa kagum sama kamu diem diem.. meskipun kadang biar bisa deket sama bby tuh aku harus bully bby dulu eheheheh ( caper gila). intinya lowkey admiring you every single day babe. When i see you, ketawa, cara bby ngomong, cara bby jadi diri bby sendiri.. semuanya tuh kayak ada magnetnya tauk, bisa bikin hati aku ketarik oleh magnet mu itu.. intinya aku sering mikir kaya " yatuhan, kok bisa ya ada cewe secantik dia ini? aku  beneran kali ini ketemu selera cewe ku sendiri di depan mata ku sendiri.." intinya bby tu bukan cuma cantik luarr yeahh, tapi auranya, vibesnya bby,  the way you carry yourself… it hits different. 

Tbh, dulu akutuh ngerasa bby tu out of my league banget sayang. Kayak mustahil aja deh bisa deket banget sama bby, apalagi kalau jadi pacar kamu juga itu paling mustahil banget deh. intinya ya sayang aku cuma bisa jadi secret admirer yang senengg banget kalau kamu senyum, yang diem diem ngerasa hari aku bakal jadi better cuma karena liatt bby seorang. And now look at us. Sekarang kamu bukann cuma perempuan yang aku kagumi dari kejauhan lagi. you are now my gf, kamu sekarang jadi orang yang bisa aku chat setiao hari, yang bisa aku panggil sayang, yang bisaa aku manja manjain tiap hari :(( aku beneran ga berhenti bersyukurr kalo dapetin bby, aku gamau kecewain pacar aku. Aku selalu bilang sama kamu sayang, kalo aku ga nyangka bisa sama kamu sayang. Terus juga aku bisa ceritain hal hal random sampe yang serius sekali pun. Itu tuh rasanya unreal banget sayangg.. ganyangka :((

Kadang tuhh ya sayang aku masih suka mikir, "she's really mine? dia beneran punya ku nih?"
Kayak apa yah... how perempuan secantik, sebaik, humoris, sehangat kamu milih orang kaya aku?? out of everyone, you chose me? itu beneran bikin aku ngerasa jadi orang yang paling beruntung banget. 1 month ini maybe keliatannya sangat singkat buat orang lain. But for me?  it means so much. Karena ya sayang di 1 bulan ini aku ngerasain gimana rasanya di cintai sama orang yang dulu cuma bisa kagumi diam diam. Dan juga aku ngerasain gimana rasanya punya kamu dalam hidup aku, bukan cuman di angan angan aja sayang, tapi beneran di hidup aku. Karena bby juga aku jadi tau gimana rasanya jatuh cinta mendalam tuh :D

Thank you for everything ya sayang ku, udah mau nerima aku. Dan juga udah mau buka hati kamu buat aku seorang :(( terus udah mau sayang dan cinta sama aku dengan cara bbyyy yang tulus ituuu. Sayang juga bikin aku selalu ngerasa cukup, dan sayang juga selalu bikin aku ngerasa di hargai. Sayang tuh selalu bikin aku ngerasa jadi versi terbaik dari diri akuu.

From just an extracurricular crush... to my gf, my safe place, my favorite notification, my prettiest plot twist.

Aku gak tau kedepannya kita bakal gimanaa, tapi satu hal yang pasti... aku bersyukur banget perjalanan kecil kita ini bisa  dimulai dari sebatas "temen ekskul"  dan berubah jadi "kita". Still crazy to think the girl i used to admire from afar is now the one i call mine. And trust me.. i'll never take that for granted.🤍

---------------------------------------------------------------------

From : Ghina Lathifah Inayatullah`;

        function init() {
            document.getElementById('overlay').style.opacity = '0';
            setTimeout(() => { document.getElementById('overlay').style.display = 'none'; }, 500);
            document.getElementById('music').play();
            confetti({ particleCount: 100, spread: 70, origin: { y: 0.6 }, colors: ['#705123', '#e4caad'] });
        }

        let hasStarted = false;
        function startTyping() {
            if(hasStarted) return;
            hasStarted = true;
            document.getElementById('hint').style.display = 'none';
            document.getElementById('letterBox').style.display = 'block';
            let i = 0;
            const target = document.getElementById("textTarget");
            function type() {
                if (i < pesan.length) {
                    target.innerHTML += pesan.charAt(i);
                    i++;
                    setTimeout(type, 50);
                    window.scrollTo({ top: document.body.scrollHeight, behavior: 'smooth' });
                } else {
                    document.getElementById('quizSection').style.display = 'block';
                }
            }
            type();
        }

        // Fungsi menggerakkan tombol "Gak"
        function moveButton() {
            const btn = document.getElementById('btnNo');
            // Menghitung area aman agar tombol tidak keluar layar
            const x = Math.random() * (window.innerWidth - btn.offsetWidth - 20);
            const y = Math.random() * (window.innerHeight - btn.offsetHeight - 20);
            
            btn.style.position = 'fixed';
            btn.style.left = x + 'px';
            btn.style.top = y + 'px';
            btn.style.zIndex = "9999";
        }

        function showEverything() {
            const notif = document.getElementById('googleNotif');
            notif.classList.add('show');
            
            const popup = document.getElementById('photoPopup');
            popup.classList.add('active');

            confetti({
                particleCount: 200,
                spread: 160,
                origin: { y: 0.8 },
                colors: ['#ff4d6d', '#ffffff', '#705123']
            });

            setTimeout(() => {
                notif.classList.remove('show');
            }, 6000);
        }
    </script>
</body>
</html>
