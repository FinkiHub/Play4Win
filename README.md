<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Kalkulator za smeni 2026</title>
</head>
<body>

<h2>Kalkulator za smeni 2026</h2>

<label>Den: <input type="number" id="den" min="1" max="31"></label><br><br>
<label>Mesec: <input type="number" id="mesec" min="1" max="12"></label><br><br>

<button onclick="presmetaj()">Presmetaj</button>

<p id="rezultat"></p>

<script>
function presmetaj() {
    let den = Number(document.getElementById("den").value);
    let mesec = Number(document.getElementById("mesec").value);

    let denoviVoMesec = [31,28,31,30,31,30,31,31,30,31,30,31];

    // presmetka na reden den vo godinata
    let denVoGodina = 0;
    for(let i = 0; i < mesec - 1; i++) {
        denVoGodina += denoviVoMesec[i];
    }
    denVoGodina += den;

    let ciklusDen = (denVoGodina - 1) % 8;

    let mimi, natali, bojana, tamara;

    if(ciklusDen < 2) {        // 1-2 денови
        mimi = "Sloboden den";
        natali = "Treta smena";
        bojana = "Megju smena";
        tamara = "Vtora smena";
    } else if(ciklusDen < 4) { // 3-4 денови
        mimi = "Treta smena";
        natali = "Megju smena";
        bojana = "Vtora smena";
        tamara = "Sloboden den";
    } else if(ciklusDen < 6) { // 5-6 денови
        mimi = "Megju smena";
        natali = "Vtora smena";
        bojana = "Sloboden den";
        tamara = "Treta smena";
    } else {                    // 7-8 денови
        mimi = "Vtora smena";
        natali = "Sloboden den";
        bojana = "Treta smena";
        tamara = "Megju smena";
    }

    document.getElementById("rezultat").innerHTML =
        `<b>Mimi:</b> ${mimi}<br>` +
        `<b>Natali:</b> ${natali}<br>` +
        `<b>Bojana:</b> ${bojana}<br>` +
        `<b>Tamara:</b> ${tamara}`;
}
</script>

</body>
</html>
