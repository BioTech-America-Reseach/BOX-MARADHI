Here is the final HTML document arranged with a clean structure for all 26 letters (A–Z), each with its own picture, health guidance, terrifying animations (lizard, spider, shaking effects), and a WhatsApp panic button. The layout is scrollable, and the system locks to the first chosen letter.
```html
<!DOCTYPE html>
<html lang="sw">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>KABURI LA HERUFI ZOTE | TIBA ASILI YA KUTISHA</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            cursor: crosshair;
            user-select: none;
        }

        /* BACKGROUND YA GIZA NA MACHOZI YA DAMU */
        body {
            background: radial-gradient(circle at 25% 10%, #0a0500, #010101);
            min-height: 100vh;
            font-family: 'Courier New', 'Creepster', monospace;
            overflow-x: hidden;
            position: relative;
        }

        /* LAYER YA KUTETEMESHA NA KUANGAZA */
        body::before {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: repeating-linear-gradient(0deg, rgba(100, 20, 10, 0.25) 0px, rgba(100, 20, 10, 0.25) 2px, transparent 2px, transparent 12px),
                        repeating-linear-gradient(90deg, rgba(130, 20, 0, 0.2) 0px, rgba(130, 20, 0, 0.2) 1px, transparent 1px, transparent 9px);
            pointer-events: none;
            z-index: 2;
            animation: flickerBlood 2.2s infinite;
        }

        @keyframes flickerBlood {
            0% { opacity: 0.8; }
            30% { opacity: 1; filter: blur(0.2px); }
            70% { opacity: 0.85; }
            100% { opacity: 0.9; }
        }

        /* UTANDO WA BUIBUI PEMBENI */
        .cobweb {
            position: fixed;
            width: 220px;
            height: 220px;
            background: radial-gradient(circle, rgba(110,70,35,0.25) 2px, transparent 2px);
            background-size: 28px 28px;
            pointer-events: none;
            z-index: 3;
        }
        .cobweb1 { top: 0; left: 0; }
        .cobweb2 { bottom: 0; right: 0; transform: rotate(180deg); }
        .cobweb3 { top: 20%; right: 3%; width: 140px; }

        /* KIKUBWA CHA MAUDHUI */
        .app-container {
            max-width: 1300px;
            margin: 1.5rem auto;
            background: rgba(8, 5, 2, 0.88);
            backdrop-filter: blur(8px);
            border-radius: 2.6rem;
            border: 2px solid #8a2e18;
            box-shadow: 0 0 45px rgba(190, 0, 0, 0.6), inset 0 0 18px rgba(255, 60, 0, 0.3);
            padding: 1.8rem;
            position: relative;
            z-index: 20;
            transition: 0.2s;
        }

        h1 {
            font-size: 2.1rem;
            font-weight: 800;
            text-align: center;
            color: #fbc994;
            text-transform: uppercase;
            letter-spacing: 3px;
            text-shadow: 0 0 8px #8b0000, 2px 2px 0 #3a1800;
            background: #170c06b3;
            border-radius: 60px;
            padding: 0.7rem;
            animation: titleShake 1.5s infinite;
        }

        @keyframes titleShake {
            0% { transform: skew(0deg); text-shadow: 2px 2px 0 darkred; }
            30% { transform: skew(0.7deg); text-shadow: -1px 0px 0 #a12222; }
            70% { transform: skew(-0.4deg); text-shadow: 1px -1px 0 #b33a1a; }
            100% { transform: skew(0deg); }
        }

        .sub {
            text-align: center;
            color: #d6935c;
            border-bottom: 2px dashed #b6421e;
            display: inline-block;
            width: auto;
            margin: 0 auto 1.8rem;
            padding-bottom: 0.4rem;
            font-weight: bold;
            font-size: 1rem;
        }

        /* GRID YA HERUFI ZOTE 26 (A-Z) */
        .sanduku-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(100px, 112px));
            justify-content: center;
            gap: 1rem;
            max-height: 500px;
            overflow-y: auto;
            padding: 1.2rem;
            background: #0a0602cc;
            border-radius: 2rem;
            box-shadow: inset 0 0 20px #1c0e04, 0 12px 28px black;
            scroll-behavior: smooth;
            margin-bottom: 2rem;
        }

        /* KISANDUKU KIMOJA CHA HERUFI */
        .letter-card {
            background: #231b12;
            border-radius: 1.5rem;
            padding: 0.6rem 0.2rem;
            text-align: center;
            cursor: pointer;
            transition: all 0.2s cubic-bezier(0.4, 1.2, 0.6, 1);
            border: 1px solid #aa4a26;
            box-shadow: 0 5px 14px black;
            position: relative;
        }

        .letter-card:hover {
            transform: scale(1.07) rotate(1deg);
            background: #452d1c;
            box-shadow: 0 0 18px #ff5e1a;
            border-color: #f7763e;
        }

        .letter-card:hover::after {
            content: "👁️🧿";
            position: absolute;
            top: -12px;
            right: -8px;
            font-size: 20px;
            filter: drop-shadow(0 0 3px red);
            opacity: 1;
        }

        .letter-img svg {
            filter: drop-shadow(0 0 5px #c95a2a);
        }

        .letter-label {
            font-weight: bold;
            background: #1c0f07;
            color: #ffbc86;
            border-radius: 30px;
            font-size: 0.85rem;
            padding: 3px 8px;
            display: inline-block;
        }

        /* PANEL YA TAARIFA ZA KUTISHA */
        .health-panel {
            margin-top: 1.8rem;
            background: #0c0703e6;
            border-radius: 2rem;
            padding: 1.2rem;
            border-left: 12px solid #c53e1a;
            color: #fad6ae;
            backdrop-filter: blur(12px);
            box-shadow: 0 0 28px #5c1a0a;
        }
        .info-card {
            background: #1a1209e0;
            border-radius: 1.2rem;
            padding: 0.9rem;
            margin-bottom: 1rem;
            border: 1px solid #b6532a;
        }
        .dawa-item {
            background: #2b1d10;
            border-left: 5px solid #e3642a;
            margin-bottom: 7px;
            padding: 6px 8px;
        }
        .advice-badge {
            background: #441e1a;
            color: #ffcd97;
            text-align: center;
            border-radius: 40px;
            padding: 8px;
            font-weight: bold;
            animation: pulseWarning 1s infinite;
        }
        @keyframes pulseWarning {
            0% { box-shadow: 0 0 0 0 #b33a1a; }
            100% { box-shadow: 0 0 0 6px rgba(180, 40, 0, 0); }
        }

        /* WHATSAPP BUTTON YA KUTISHA */
        .whatsapp-horror {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: linear-gradient(135deg, #1f542e, #0f301d);
            color: #ffddb0;
            padding: 12px 20px;
            border-radius: 60px;
            font-weight: bold;
            z-index: 1000;
            box-shadow: 0 0 0 3px #5a1e0a, 0 0 0 6px #aa3c1a;
            cursor: pointer;
            font-family: monospace;
            backdrop-filter: blur(5px);
            border: 1px solid #f5783a;
            transition: 0.2s;
            animation: zombiePulse 1.3s infinite;
        }
        @keyframes zombiePulse {
            0% { transform: scale(1); background: #0f3a22; }
            50% { transform: scale(1.05); background: #2a784e; box-shadow: 0 0 0 6px #ad2f2f; }
            100% { transform: scale(1); }
        }
        .whatsapp-horror:hover {
            transform: scale(1.12);
            background: #428f62;
            color: black;
        }

        /* MJUSI ANAYETAMBAA (LIZARD) */
        .lizard-walk {
            position: fixed;
            bottom: 0;
            left: -130px;
            font-size: 58px;
            z-index: 10001;
            filter: drop-shadow(0 0 14px #2f0400);
            pointer-events: none;
            animation: lizardCrawl 20s linear infinite;
        }
        @keyframes lizardCrawl {
            0% { left: -130px; transform: scaleX(1); }
            49% { transform: scaleX(1); }
            50% { transform: scaleX(-1); }
            100% { left: 110%; transform: scaleX(-1); }
        }

        /* BUIBUI ANAYEKATIZA KWA NJIA YA KUTISHA */
        .spider-crossing {
            position: fixed;
            top: 15%;
            left: 5%;
            font-size: 52px;
            z-index: 10002;
            filter: drop-shadow(0 0 10px black);
            pointer-events: none;
            transition: all 0.9s ease-in-out;
            animation: spiderTwitch 0.3s infinite alternate;
        }
        @keyframes spiderTwitch {
            from { transform: translate(1px, 1px) rotate(1deg); }
            to { transform: translate(-2px, -2px) rotate(-3deg); }
        }

        /* KUTETEMEKA KWA KUTISHA */
        .shake-global {
            animation: earthShake 0.18s infinite;
        }
        @keyframes earthShake {
            0% { transform: translate(1px, 0px); }
            50% { transform: translate(-2px, 1px); }
            100% { transform: translate(0px, -1px); }
        }

        /* DAMU IKITIRIRIKA */
        .blood-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: repeating-linear-gradient(0deg, rgba(150, 0, 0, 0.12) 0px, rgba(150, 0, 0, 0.12) 4px, transparent 4px, transparent 20px);
            pointer-events: none;
            z-index: 9;
        }

        /* MODAL YA KUTHIBITISHA JINA */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.96);
            backdrop-filter: blur(16px);
            z-index: 2000;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .modal-card {
            background: #1d0c05;
            border: 3px solid #c2410c;
            border-radius: 2rem;
            padding: 2rem;
            color: #ffb680;
            text-align: center;
            width: 90%;
            max-width: 380px;
            box-shadow: 0 0 70px rgb(180, 0, 0);
            animation: modalFlicker 0.9s infinite;
        }
        @keyframes modalFlicker {
            0% { border-color: #b33a1a; }
            50% { border-color: #ff4d1a; box-shadow: 0 0 40px red; }
        }
        .modal-card input {
            background: #2b1a0e;
            border: 1px solid #b45f2e;
            border-radius: 40px;
            padding: 10px;
            width: 85%;
            color: #ffdbb5;
            font-weight: bold;
            margin: 12px 0;
        }
        .modal-card button {
            background: #712e18;
            color: white;
            border: none;
            padding: 8px 22px;
            border-radius: 30px;
            margin: 5px;
            cursor: pointer;
        }
        .modal-card button:hover {
            background: #bc471f;
            box-shadow: 0 0 15px red;
        }
        .hidden { display: none; }
        footer {
            text-align: center;
            font-size: 0.7rem;
            color: #794d2e;
            margin-top: 1rem;
        }
        .sanduku-grid::-webkit-scrollbar {
            width: 8px;
            background: #2f1a0c;
        }
        .sanduku-grid::-webkit-scrollbar-thumb {
            background: #ac4c2a;
            border-radius: 10px;
        }
    </style>
</head>
<body>
<div class="blood-overlay"></div>
<div class="cobweb cobweb1"></div>
<div class="cobweb cobweb2"></div>
<div class="cobweb cobweb3"></div>

<!-- MJUSI (LIZARD) -->
<div class="lizard-walk" id="lizardScary">🦎💀🦎</div>
<!-- BUIBUI (SPIDER) -->
<div class="spider-crossing" id="spiderMoving">🕷️🩸🕸️</div>

<main class="app-container">
    <h1>🧿 MAKABURI YA HERUFI ZOTE A - Z 🧿</h1>
    <div style="text-align: center;"><span class="sub">👇 TEMBEZA, CHAGUA HERUFI YAKO, JAZA JINA 👇</span></div>

    <!-- GRID YA HERUFI 26 (A hadi Z) -->
    <div id="sandukuGrid" class="sanduku-grid"></div>
    <div id="healthResultArea" class="health-panel hidden"></div>
    <footer>💀 ONYO: Dalili zinazotolewa ni za kutisha. Tiba asili ina madhara makubwa. 💀</footer>
</main>

<!-- KITUO CHA WHATSAPP -->
<div class="whatsapp-horror" id="whatsappBtn">
    🧛 WASILIANA NA MGANGA WA GIZA 🧛 | +255 762 286 282
</div>

<script>
    // ---------------------------------------------------------------
    // DATA ZA AFYA KWA HERUFI ZOTE 26 (A hadi Z) - ZA KIPEKEE KILA HERUFI
    // ---------------------------------------------------------------
    const diseasePool = [
        "Homa ya maiti ya usiku", "Kifua kikuu cha kuzimu", "Ugonjwa wa ngozi inayoyeyuka", "Kisukari cha damu nyeusi", "Pumu ya roho chafu",
        "Shinikizo la damu la kifo", "Uvimbe wa nyongo unaolia", "Kikohozi cha kaburi", "Malaria ya mizimu", "Kipindupindu cha mabuu",
        "Ugonjwa wa figo kukauka", "Kifafa cha mwezi mwekundu", "Ugonjwa wa mishipa ya wadudu", "Maji tumboni ya giza", "Wengu wa kuruka usiku",
        "Kuvimba kwa ubongo kwa pepo", "Anemia nyeusi ya makaburini", "Ugonjwa wa meno ya nyoka", "Tezi la kusema la kuchizwa", "Kupooza kwa ghafla"
    ];
    const foodPool = [
        "Nyama ya mbuzi mweusi aliyechinjwa usiku", "Mchicha wa makaburi", "Maziwa ya punda mwitu", "Maharagwe ya wafu", "Uji wa mifupa ya kuku mweusi",
        "Viazi vikuu vya giza", "Nazi iliyooza usiku wa manane", "Samaki wa mto uliokufa", "Asali nyeusi ya nyuki wachawi", "Tende za ushirikina"
    ];
    const symptomTemplate = [
        "Kutapika vitu vyeusi na kusikia sauti za huzuni", "Kusikia makosa yako yanakurupia usiku", "Ngozi kuwa na alama za kuchomwa moto wa roho", 
        "Kukosa usingizi na ndoto zenye macho mekundu", "Kuhisi kama kuna mkono unakukaba kooni", "Mwili kutetemeka bila kutarajia na jicho la tatu", 
        "Kutembea usingizini na kufika kaburini", "Kukosa pumzi unapoona kivuli chako", "Kutamka lugha za kale wakati wa usingizi", "Kuona nyusi wadogo wakikukaribia"
    ];
    const remedyBase = [
        "Maji ya majani ya mwewe + unga wa fuvu", "Kuvuta moshi wa uvumba mweusi na tangawizi", "Kupaka mafuta ya mjusi mweusi kwa saba", 
        "Kunywa mchanganyiko wa asali na udongo wa kaburi", "Kutumbuiza majani ya mpera usiku wa manane", "Kufunga sadaka ya damu ya jogoo mweusi", 
        "Kulala kwenye magunia ya maiti", "Kunywa maji ya mchicha na sumu ya nge", "Kusugua mwili kwa majani ya mlonge usiku", 
        "Kupiga kelele za kichaa kabla ya alfajiri"
    ];
    const prognosisText = "UTABIRI: Ukiendelea kukaa na tabia hizi, roho yako itateseka. Tiba asili ya giza inaweza kukupa nafuu, lakini uwe tayari kukutana na mapepo. Fuata ushauri wa mganga asili kabla ya mwezi kupotea.";

    // Kila herufi itapata data tofauti kwa kutumia indeksi
    function generateHealthData(letter) {
        const idx = letter.charCodeAt(0) - 65; // 0-25
        // Magonjwa 10 (chukua kutoka pool kwa rotation)
        const diseases = diseasePool.slice(0, 10).map((d, i) => `${d} [${letter}-${i+1}]`);
        const foods = foodPool.slice(0, 5).map((f, i) => `${f} ~ uchawi wa herufi ${letter}`);
        const symptomsList = [];
        for (let i = 0; i < 5; i++) {
            const symIdx = (idx + i) % symptomTemplate.length;
            const remIdx = (idx + i*2) % remedyBase.length;
            symptomsList.push({
                symptom: `💀 ${symptomTemplate[symIdx]} (herufi ${letter})`,
                dawa: `🍃 Tiba asili: ${remedyBase[remIdx]} + mizinga ya ${letter.toLowerCase()}`
            });
        }
        return { diseases, foods, symptoms: symptomsList, prognosis: `${prognosisText} Utabiri maalum kwa herufi ${letter}: Roho yako itapambana na pepo 7.` };
    }

    // HERUFI ZOTE A hadi Z
    const allLetters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ".split('');
    let locked = false;
    let lockedLetter = null;
    let selectedCardElem = null;

    const gridContainer = document.getElementById('sandukuGrid');
    const healthPanel = document.getElementById('healthResultArea');

    // TENGENEZA PICHA ZA HERUFI (SVG)
    function createLetterIcon(letter) {
        const svgNS = "http://www.w3.org/2000/svg";
        const svg = document.createElementNS(svgNS, "svg");
        svg.setAttribute("viewBox", "0 0 100 100");
        svg.setAttribute("width", "56");
        svg.setAttribute("height", "56");
        const rect = document.createElementNS(svgNS, "rect");
        rect.setAttribute("width", "100");
        rect.setAttribute("height", "100");
        rect.setAttribute("rx", "35");
        rect.setAttribute("fill", "#261a0e");
        rect.setAttribute("stroke", "#bb542a");
        rect.setAttribute("stroke-width", "2.5");
        const text = document.createElementNS(svgNS, "text");
        text.setAttribute("x", "50");
        text.setAttribute("y", "70");
        text.setAttribute("font-size", "58");
        text.setAttribute("font-weight", "bold");
        text.setAttribute("fill", "#f5a56e");
        text.setAttribute("text-anchor", "middle");
        text.textContent = letter;
        svg.appendChild(rect);
        svg.appendChild(text);
        return svg;
    }

    // ONYESHA VISANDUKU VYA HERUFI ZOTE (A-Z kwa utaratibu mzuri)
    function renderLetterBoxes() {
        gridContainer.innerHTML = '';
        allLetters.forEach(letter => {
            const box = document.createElement('div');
            box.className = 'letter-card';
            box.setAttribute('data-letter', letter);
            const imgDiv = document.createElement('div');
            imgDiv.className = 'letter-img';
            imgDiv.appendChild(createLetterIcon(letter));
            const label = document.createElement('div');
            label.className = 'letter-label';
            label.textContent = `HERUFI ${letter} ⚰️`;
            box.appendChild(imgDiv);
            box.appendChild(label);
            box.addEventListener('click', (e) => handleBoxClick(box, letter));
            gridContainer.appendChild(box);
        });
    }

    // ONYESHA MAELEZO YA AFYA
    function displayHealthForLetter(letter) {
        const data = generateHealthData(letter);
        const symptomsHtml = data.symptoms.map(s => `<div class="dawa-item"><strong>⚠️ DALILI HATARI: ${s.symptom}</strong><br/>🧿 ${s.dawa}</div>`).join('');
        healthPanel.innerHTML = `
            <h3 style="color:#ff9f6e;">🩸 MATOKEO YA KIFO KWA HERUFI "${letter}" 🩸</h3>
            <div class="info-card"><h4>🕷️ MAGONJWA 10 YA KUTISHA</h4><ul>${data.diseases.map(d => `<li>⚰️ ${d}</li>`).join('')}</ul></div>
            <div class="info-card"><h4>🍄 VYAKULA 5 VYA GIZA (AZINGATIE)</h4><ul>${data.foods.map(f => `<li>🌑 ${f}</li>`).join('')}</ul></div>
            <div class="info-card"><h4>⚠️ DALILI HATARI + TIBA ASILI (5)</h4>${symptomsHtml}</div>
            <div class="info-card"><h4>📜 UTABIRI WA KUTISHA</h4><p>${data.prognosis}</p><div class="advice-badge">🧙 MGANGA ASILI: FUATA MAAGIZO KWA USIKU WA MANANE</div></div>
        `;
        healthPanel.classList.remove('hidden');
        // Kutetemeka kidogo wakati wa kusoma
        document.body.classList.add('shake-global');
        setTimeout(() => document.body.classList.remove('shake-global'), 500);
    }

    // ONDOA VISANDUKU VINGINE ISIPOKUWA CHAGUO LA KWANZA
    function removeOtherBoxes(keptBox) {
        const allBoxes = document.querySelectorAll('.letter-card');
        allBoxes.forEach(box => {
            if (box !== keptBox) box.remove();
        });
        let msgDiv = document.getElementById('lockWarning');
        if (!msgDiv) {
            msgDiv = document.createElement('div');
            msgDiv.id = 'lockWarning';
            msgDiv.className = 'advice-badge';
            msgDiv.style.marginTop = '1.2rem';
            gridContainer.parentNode.insertBefore(msgDiv, gridContainer.nextSibling);
        }
        msgDiv.innerHTML = '💀💀 UMEFUNGWA HERUFI YAKO. VISANDUKU VINGINE VIMETOWA. HUWEZI KUBADILI! MATOKEO YAMEREJESHWA. 💀💀';
    }

    // MODAL YA KUTHIBITISHA JINA
    function confirmLetterSelection(letter, callback) {
        const modalLayer = document.createElement('div');
        modalLayer.className = 'modal-overlay';
        modalLayer.innerHTML = `
            <div class="modal-card">
                <h2>🩸 THIBITISHA KWA DAMU YAKO 🩸</h2>
                <p>Umechagua herufi <strong style="font-size:2rem;color:#ff7a3a;">${letter}</strong></p>
                <p>ANDIKA JINA LAKO KWA OGOPI (ijaze)</p>
                <input type="text" id="scaryNameInput" placeholder="Mfano: Shetani Juma..." autocomplete="off">
                <br/>
                <button id="confirmScary">💀 NAKUBALI KIFO CHANGU 💀</button>
                <button id="cancelScary" style="background:#5a2a1a;">❌ GHairi</button>
            </div>
        `;
        document.body.appendChild(modalLayer);
        const nameInput = modalLayer.querySelector('#scaryNameInput');
        const confirmBtn = modalLayer.querySelector('#confirmScary');
        const cancelBtn = modalLayer.querySelector('#cancelScary');
        confirmBtn.onclick = () => {
            const userName = nameInput.value.trim();
            if (userName === "") {
                alert("LAZIMA UANDIKE JINA LAKO! KABURI LINA KUSUBIRI.");
                return;
            }
            modalLayer.remove();
            callback(userName);
        };
        cancelBtn.onclick = () => modalLayer.remove();
    }

    // HANDLER KWA KUBOFYA KISANDUKU
    function handleBoxClick(card, letter) {
        if (locked) {
            if (letter !== lockedLetter) {
                alert(`🧟‍♂️ UMEJIFUNGIA HERUFI ${lockedLetter}! HUWEZI KUBADILISHA. Visanduku vingine vitaangamia tena. 🧟‍♂️`);
                if (selectedCardElem && document.body.contains(selectedCardElem)) {
                    removeOtherBoxes(selectedCardElem);
                } else {
                    const lockedCard = document.querySelector(`.letter-card[data-letter="${lockedLetter}"]`);
                    if (lockedCard) removeOtherBoxes(lockedCard);
                    else location.reload();
                }
                displayHealthForLetter(lockedLetter);
            } else {
                displayHealthForLetter(lockedLetter);
            }
            return;
        }
        // SIO LOCKED: onyesha modal kwa mara ya kwanza
        confirmLetterSelection(letter, (jina) => {
            locked = true;
            lockedLetter = letter;
            selectedCardElem = card;
            displayHealthForLetter(letter);
            // Weka ujumbe wa kufunga
            let permMsg = document.getElementById('permLockMsg');
            if (!permMsg) {
                permMsg = document.createElement('div');
                permMsg.id = 'permLockMsg';
                permMsg.className = 'advice-badge';
                permMsg.style.background = '#3a1912';
                gridContainer.parentNode.insertBefore(permMsg, gridContainer.nextSibling);
            }
            permMsg.innerHTML = `🕸️ ${jina.toUpperCase()}, UMEZIKWA KWA HERUFI "${letter}". SASA HUTABADILI HERUFI NDIYO IMESALIA. UKIBOFYA HERUFI NYINGINE UTAONA MATESO. 🕸️`;
        });
    }

    // WASILIANA WHATSAPP
    const waBtn = document.getElementById('whatsappBtn');
    waBtn.addEventListener('click', () => {
        window.open('https://wa.me/255762286282?text=NATAKA%20TIBA%20YA%20KUTISHA%20NA%20USHAURI%20WA%20GIZA%20-%20NIMEJIFUNGUA%20HERUFI', '_blank');
    });

    // MIONDOKO YA KUTISHA: BUIBUI, MJUSI, NA MATETEMEKO
    const spider = document.getElementById('spiderMoving');
    function randomSpiderMove() {
        const maxW = window.innerWidth - 90;
        const maxH = window.innerHeight - 90;
        const randX = Math.random() * maxW;
        const randY = Math.random() * maxH;
        spider.style.left = randX + 'px';
        spider.style.top = randY + 'px';
        setTimeout(randomSpiderMove, 4000 + Math.random() * 2000);
    }
    randomSpiderMove();

    // BADILISHA SUURA YA MJUSI MARA KWA MARA
    const lizard = document.getElementById('lizardScary');
    setInterval(() => {
        const horrors = ['🦎💀', '🦎🩸', '🐍🦎', '🦂🦎', '🦎👁️'];
        if (Math.random() > 0.75) {
            lizard.textContent = horrors[Math.floor(Math.random() * horrors.length)];
            setTimeout(() => { lizard.textContent = '🦎💀🦎'; }, 2000);
        }
    }, 5000);

    // KUTETEMEZA SKRINI KWA MSHTUKO
    setInterval(() => {
        if (Math.random() > 0.7) {
            document.body.classList.add('shake-global');
            setTimeout(() => document.body.classList.remove('shake-global'), 350);
        }
        if (!healthPanel.classList.contains('hidden')) {
            healthPanel.style.transform = `translate(${Math.random() * 2 - 1}px, ${Math.random() * 2 - 1}px)`;
            setTimeout(() => { healthPanel.style.transform = ''; }, 120);
        }
    }, 4800);

    // RENDER GRID YA HERUFI ZOTE (A-Z)
    renderLetterBoxes();
    healthPanel.classList.add('hidden');
    console.log("MAUMBO YA KUTISHA YAMEANZA, HERUFI ZOTE 26 ZIPO TAYARI.");
</script>
</body>
</html>
```
