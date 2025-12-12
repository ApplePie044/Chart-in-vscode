# Chart-in-vscode
Hur man skapar en chart med hjälp av Javascript och HTML i vscode.

1. Öppna vscode.
2. Skapa en `package.json`
3. Klipp in koden nedan i json filen.
 ```Javascript {
  "name": "chartjs-example",
  "version": "1.0.0",
  "license": "MIT",
  "scripts": {
    "dev": "parcel src/index.html",
    "build": "parcel build src/index.html"
  },
  "devDependencies": {
    "parcel": "^2.6.2"
  },
  "dependencies": {
    "@cubejs-client/core": "^0.31.0",
    "chart.js": "^4.0.0"
  }
}
```
4. Ladda ner Chart-js och JavaScript i vscode terminalen. Går även att ladda ner via cmd men var då noga med att gå in i rätt folder innan du laddar ner.
5. skriv sedan npm `install` to installera beroenden till modulerna.
6. skapa en `src` folden och skapa en `index.html` och placera den i `src` foldern.
7. Kopiera in koden nedan i `index.html`.
```html <!doctype html>
<html lang="en">
  <head>
    <title>Chart.js example</title>
  </head>
  <body>
    <!-- <div style="width: 500px;"><canvas id="dimensions"></canvas></div><br/> -->
    <div style="width: 800px;"><canvas id="acquisitions"></canvas></div>

    <!-- <script type="module" src="dimensions.js"></script> -->
    <script type="module" src="acquisitions.js"></script>
  </body>
</html>
```

8. Skapa en `acquisitions.js` fil i `src`foldern.
9. Kopiera in koden nedan i json filen.
```Javascript import Chart from 'chart.js/auto'

(async function() {
  const data = [
    { year: 2010, count: 10 },
    { year: 2011, count: 20 },
    { year: 2012, count: 15 },
    { year: 2013, count: 25 },
    { year: 2014, count: 22 },
    { year: 2015, count: 30 },
    { year: 2016, count: 28 },
  ];

  new Chart(
    document.getElementById('acquisitions'),
    {
      type: 'bar',
      data: {
        labels: data.map(row => row.year),
        datasets: [
          {
            label: 'Acquisitions by year',
            data: data.map(row => row.count)
          }
        ]
      }
    }
  );
})();
```

Det ska nu gå att starta charten i vscode genom att gå live. Om du använder cmd istället för vscode terminalen ska du skriva in `npm run dev` för att starta charten. med Ctrl C avbryter man. Gå till http://localhost:1234/ för att se charten.

<img width="1258" height="644" alt="image" src="https://github.com/user-attachments/assets/c7679b87-f7b4-435d-b2e0-f957317394ea" />



# Begrepp och kort förklaring
* json: json är ett filformat man kan använda Javascript i. {} betyder object i en json fil och inte början och slutet på en funktion som det betyder i exempelvis html. 
* Object: Ett object är en variabel som kan hålla flera variabler. Skrivs i Javascript.
* Array: En array är en grupp med objects och markeras med []. Skrivs i Javascript. 
