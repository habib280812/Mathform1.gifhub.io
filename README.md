# welcome to my website by habib
<!DOCTYPE html><html>
<head>
  <title>Kalkulator Matematik Sekolah Menengah</title>
  <style>
    body { font-family: Arial; margin: 40px; }
    input, select, button { margin: 5px 0; display: block; }
    .section { margin-bottom: 30px; }
  </style>
</head>
<body>
  <h1>Kalkulator Matematik Tingkatan 1 - 5</h1>  <form id="mathForm">
    <div class="section">
      <label for="topik">Pilih Topik:</label>
      <select id="topik">
        <option value="nisbah">Nombor Nisbah</option>
        <option value="faktor_gandaan">Faktor & Gandaan</option>
        <option value="kuasa">Kuasa dan Punca</option>
        <option value="nisbah_kadar">Nisbah, Kadar & Kadaran</option>
        <option value="algebra">Ungkapan Algebra</option>
        <option value="linear">Persamaan Linear</option>
        <option value="ketaksamaan">Ketaksamaan Linear</option>
        <option value="sudut">Garis & Sudut</option>
        <option value="poligon">Poligon Asas</option>
        <option value="luas">Perimeter & Luas</option>
        <option value="set">Pengenalan Set</option>
        <option value="data">Pengendalian Data</option>
        <option value="pythagoras">Teorem Pythagoras</option>
      </select>
    </div><div class="section">
  <label for="input1">Input 1:</label>
  <input type="number" id="input1">

  <label for="input2">Input 2:</label>
  <input type="number" id="input2">

  <label for="input3">(Jika perlu) Input 3:</label>
  <input type="number" id="input3">
</div>

<button type="button" onclick="kira()">Kira</button>

  </form>  <div id="hasil"></div>  <script>
    function kira() {
      const topik = document.getElementById('topik').value;
      const a = parseFloat(document.getElementById('input1').value);
      const b = parseFloat(document.getElementById('input2').value);
      const c = parseFloat(document.getElementById('input3').value);
      let hasil = "";
      switch(topik) {
        case "nisbah": hasil = a / b; break;
        case "faktor_gandaan": hasil = `Faktor: ${faktor(a)} | Gandaan: ${gandaan(a)}`; break;
        case "kuasa": hasil = `Kuasa 2: ${a**2}, Punca 2: ${Math.sqrt(a)}, Kuasa 3: ${a**3}, Punca 3: ${Math.cbrt(a)}`; break;
        case "nisbah_kadar": hasil = `Nisbah: ${nisbah(a, b)}, Kadar: ${(b!==0)?(a/b):"Tak sah"}`; break;
        case "algebra": hasil = `${a}x + ${b}, x = ${c}, Hasil: ${a*c + b}`; break;
        case "linear": hasil = `x = ${(c - b) / a}`; break;
        case "ketaksamaan": hasil = (a > 0) ? `x < ${(c - b) / a}` : `x > ${(c - b) / a}`; break;
        case "sudut": hasil = `Sudut Tepat = 90°, Sudut Lurus = 180°`; break;
        case "poligon": hasil = `Jumlah sudut = ${(a - 2) * 180}°`; break;
        case "luas": hasil = `Perimeter: ${2*(a+b)}, Luas: ${a*b}`; break;
        case "set": hasil = `Gabungan: {[...new Set([a,b,c])].join(", ")}`; break;
        case "data": hasil = `Min: ${(a+b+c)/3}, Median: ${[a,b,c].sort()[1]}`; break;
        case "pythagoras": hasil = `Hipotenus: ${Math.sqrt(a*a + b*b)}`; break;
        default: hasil = "Sila pilih topik";
      }
      document.getElementById("hasil").innerHTML = `<h3>Jawapan:</h3><p>${hasil}</p>`;
    }
    function faktor(n) {
      let f = [];
      for(let i=1; i<=n; i++) {
        if(n % i === 0) f.push(i);
      }
      return f.join(", ");
    }
    function gandaan(n) {
      let g = [];
      for(let i=1; i<=5; i++) {
        g.push(n*i);
      }
      return g.join(", ");
    }
    function nisbah(a, b) {
      function gcd(x, y) {
        while(y) [x, y] = [y, x % y];
        return x;
      }
      const d = gcd(a,b);
      return `${a/d}:${b/d}`;
    }
  </script></body>
</html>
