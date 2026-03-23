# bloxify-topup
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bloxify Top Up</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-black text-white">

<!-- Navbar -->
<nav class="p-4 flex justify-between items-center border-b border-gray-800">
  <h1 class="text-xl font-bold text-blue-400">BLOXIFY</h1>
  <a href="#order" class="bg-blue-500 px-4 py-2 rounded-xl">Order</a>
</nav>

<!-- Hero -->
<section class="text-center py-16">
  <h2 class="text-4xl font-bold">Top Up Robux Instan</h2>
  <p class="text-gray-400 mt-2">Cepat • Murah • Auto Proses</p>
  <a href="#order" class="mt-6 inline-block bg-blue-500 px-6 py-3 rounded-2xl">Mulai Order</a>
</section>

<!-- Calculator -->
<section class="p-6 max-w-xl mx-auto">
  <h3 class="text-2xl font-bold mb-4">Kalkulator Robux</h3>
  <input type="number" id="rbx" placeholder="Masukkan jumlah Robux" class="w-full p-3 rounded bg-gray-900 mb-3">
  <button onclick="calc()" class="w-full bg-blue-500 py-3 rounded-xl">Hitung Harga</button>
  <p id="result" class="mt-4 text-lg text-green-400"></p>
</section>

<!-- Pricing -->
<section class="p-6">
  <h3 class="text-2xl font-bold mb-4">List Harga</h3>
  <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
    <div class="bg-gray-900 p-4 rounded-xl">100 R$<br>Rp9.700</div>
    <div class="bg-gray-900 p-4 rounded-xl">500 R$<br>Rp48.500</div>
    <div class="bg-gray-900 p-4 rounded-xl">1000 R$<br>Rp97.000</div>
    <div class="bg-gray-900 p-4 rounded-xl">2000 R$<br>Rp194.000</div>
  </div>
</section>

<!-- Order Form -->
<section id="order" class="p-6 max-w-xl mx-auto">
  <h3 class="text-2xl font-bold mb-4">Form Order</h3>
  <form class="space-y-4" onsubmit="sendOrder(event)">
    <input type="text" id="username" placeholder="Username Roblox" required class="w-full p-3 rounded bg-gray-900">
    <input type="number" id="amount" placeholder="Jumlah Robux" required class="w-full p-3 rounded bg-gray-900">
    <select id="payment" class="w-full p-3 rounded bg-gray-900">
      <option>QRIS</option>
      <option>DANA</option>
      <option>OVO</option>
    </select>
    <button class="w-full bg-blue-500 py-3 rounded-xl">Kirim Order</button>
  </form>
</section>

<!-- Footer -->
<footer class="text-center p-6 text-gray-500">
  © 2026 Bloxify Store
</footer>

<!-- Script -->
<script>
function calc() {
  const rbx = document.getElementById('rbx').value;
  const price = rbx * 97; // harga per robux
  document.getElementById('result').innerText = "Rp " + price.toLocaleString();
}

function sendOrder(e) {
  e.preventDefault();

  const username = document.getElementById('username').value;
  const amount = document.getElementById('amount').value;
  const payment = document.getElementById('payment').value;

  const message = `ORDER ROBUX%0AUsername: ${username}%0AJumlah: ${amount}%0APayment: ${payment}`;

  window.open(`https://wa.me/6281234567890?text=${message}`, '_blank');
}
</script>

</body>
</html>
