<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Trade with Himanshu</title>
  <style>
    body {
      transition: 0.3s;
    }
    body.light {
      background: #ffffff;
      color: #000000;
    }
    body.light .card {
      background: #f0f0f0;
      color: #000;
    }
    body.light header {
      background: #e5e5e5;
      color:#000;
    }

    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      background: #0d0f16;
      color: #ffffff;
    }
    header {
      padding: 40px;
      text-align: center;
      background: #131722;
    }
    header h1 {
      margin: 0;
      font-size: 2.5rem;
    }
    section {
      padding: 30px;
      max-width: 900px;
      margin: auto;
    }
    .card {
      background: #1b1f2b;
      padding: 20px;
      margin: 20px 0;
      border-radius: 12px;
      box-shadow: 0 0 10px rgba(0,0,0,0.3);
    }
    h2 {
      margin-top: 0;
      color: #4db8ff;
    }
    .btn {
      display: inline-block;
      padding: 12px 20px;
      margin-top: 15px;
      background: #4db8ff;
      color: #000;
      font-weight: bold;
      border-radius: 8px;
      text-decoration: none;
    }
    footer {
      text-align: center;
      padding: 20px;
      margin-top: 40px;
      background: #131722;
      color: #777;
    }
  </style>
<script>
function toggleTheme(){
  document.body.classList.toggle('light');
}
</script>
<script>
function calculateRisk(){
  const entry = parseFloat(document.querySelector('input[placeholder="Entry Price"]').value) || 0;
  const sl = parseFloat(document.querySelector('input[placeholder="Stop Loss"]').value) || 0;
  const target = parseFloat(document.querySelector('input[placeholder="Target"]').value) || 0;
  const qty = parseFloat(document.querySelector('input[placeholder="Quantity"]').value) || 0;

  const risk = Math.abs(entry - sl) * qty;
  const reward = Math.abs(target - entry) * qty;
  const rr = reward && risk ? (reward / risk).toFixed(2) : 0;

  document.getElementById('riskVal').innerText = risk.toFixed(2);
  document.getElementById('rewardVal').innerText = reward.toFixed(2);
  document.getElementById('rrVal').innerText = rr;
}
</script>
<script>
function calculateRisk(){
  const entry = parseFloat(document.querySelector('input[placeholder="Entry Price"]').value) || 0;
  const sl = parseFloat(document.querySelector('input[placeholder="Stop Loss"]').value) || 0;
  const target = parseFloat(document.querySelector('input[placeholder="Target"]').value) || 0;
  const qty = parseFloat(document.querySelector('input[placeholder="Quantity"]').value) || 0;

  const risk = Math.abs(entry - sl) * qty;
  const reward = Math.abs(target - entry) * qty;
  const rr = reward && risk ? (reward / risk).toFixed(2) : 0;

  document.getElementById('riskVal').innerText = risk.toFixed(2);
  document.getElementById('rewardVal').innerText = reward.toFixed(2);
  document.getElementById('rrVal').innerText = rr;
}

function saveTrade(){
  const sym = document.querySelector('input[placeholder="Stock / Symbol"]').value;
  const entry = document.querySelector('input[placeholder="Entry Price"]').value;
  const sl = document.querySelector('input[placeholder="Stop Loss"]').value;
  const target = document.querySelector('input[placeholder="Target"]').value;
  const qty = document.querySelector('input[placeholder="Quantity"]').value;
  const risk = document.getElementById('riskVal').innerText;
  const reward = document.getElementById('rewardVal').innerText;
  const rr = document.getElementById('rrVal').innerText;

  const table = document.getElementById('tradeTable');
  const row = table.insertRow();
  row.innerHTML = <td>${sym}</td><td>${entry}</td><td>${sl}</td><td>${target}</td><td>${qty}</td><td>${risk}</td><td>${reward}</td><td>${rr}</td>;
}

function exportExcel(){
  let table = document.getElementById('tradeTable').outerHTML;
  let file = new Blob([table], {type:'application/vnd.ms-excel'});
  let a = document.createElement('a');
  a.href = URL.createObjectURL(file);
  a.download = 'Trades.xlsx';
  a.click();
}
</script>
</head>
<body>
  <header>
    <button onclick="toggleTheme()" style="position:absolute; top:20px; right:20px; padding:8px 14px; border-radius:8px; border:none; cursor:pointer; font-weight:bold;">🌗 Mode</button>
    <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABgAAAAQACAIAAACoEwUVAACmXGNhQlgAAKZcanV...IAAAKoAOJtxA3VybjpjMnBhOmQyYjllZjY0LTI5NzgtNGNkZS1iZWRlLWJmYzUz" alt="Logo" style="width:120px;margin-bottom:20px;"/>
    <h1>Trade with Himanshu</h1>
    <p>Tracking my progress, learning, and strategies in the stock market</p>
  </header>

  <section>
    <div class="card" style="text-align:center; border:2px solid #4db8ff;">
      <h2>📣 Follow Me</h2>
      <p>Stay connected for trading updates, tips & daily insights!</p>
      <a class="btn" href="https://www.instagram.com/himanshu_goswami_0808" target="_blank">Instagram</a>
      <a class="btn" href="https://youtube.com/@himanshugoswami0808?si=6awvcSJqlvbz4HI0" target="_blank">YouTube</a>
      <br><br>
      <button style="padding:12px 22px; background:#ff0000; color:#fff; border:none; border-radius:10px; font-size:1rem; cursor:pointer; font-weight:bold;">🔔 Subscribe</button>
    </div></h2>
      <p>Stay connected for trading updates, tips & daily insights!</p>
      <a class="btn" href="https://www.instagram.com/himanshu_goswami_0808" target="_blank">Instagram</a>
      <a class="btn" href="https://youtube.com/@himanshugoswami0808?si=6awvcSJqlvbz4HI0" target="_blank">YouTube</a>
    </div>
    <div class="card">
      <h2>About Me</h2>
      <p>I am starting my trading journey to learn price action, chart patterns, intraday strategies and improve discipline. This site will be my place to track everything.</p>
    </div>

    <div class="card">
      <h2>Daily Logs</h2>
      <p>Here I will write my daily trades, wins, losses, and emotions. Journaling helps build discipline.</p>
      <a class="btn" href="#">Add Today's Log</a>
    </div>

    <div class="card">
      <h2>My Trading Rules</h2>
      <ul>
        <li>Always use stop-loss</li>
        <li>Never over-leverage</li>
        <li>Trade only my setup</li>
        <li>Stay calm and follow plan</li>
        <li>No revenge trading</li>
      </ul>
    </div>

    <div class="card">
      <h2>Learning Resources</h2>
      <p>Price Action → Risk Management → Chart Patterns → Intraday Strategy</p>
      <a class="btn" href="#">View Resources</a>
    </div>
      <div class="card">
      <h2>Upload Daily Trade Screenshot</h2>
      <p>You can upload your trade screenshot here to keep track of your progress.</p>
      <input type="file" accept="image/*" style="margin-top:10px;">
    </div>

      <div class="card">
      <h2>P&L Tracker</h2>
      <p>Track your Daily, Weekly, and Monthly Profit & Loss here:</p>
      <table style="width:100%; border-collapse: collapse; margin-top:15px;">
        <tr style="background:#2a2f3d;">
          <th style="padding:10px; border:1px solid #444;">Date</th>
          <th style="padding:10px; border:1px solid #444;">Trade Count</th>
          <th style="padding:10px; border:1px solid #444;">Profit</th>
          <th style="padding:10px; border:1px solid #444;">Loss</th>
          <th style="padding:10px; border:1px solid #444;">Net P&L</th>
        </tr>
        <tr>
          <td style="padding:10px; border:1px solid #444;">--</td>
          <td style="padding:10px; border:1px solid #444;">--</td>
          <td style="padding:10px; border:1px solid #444;">--</td>
          <td style="padding:10px; border:1px solid #444;">--</td>
          <td style="padding:10px; border:1px solid #444;">--</td>
        </tr>
      </table>
      <button style="margin-top:15px; padding:10px 20px; background:#4db8ff; border:none; border-radius:8px; font-weight:bold; cursor:pointer;">Add Entry</button>
    </div>

      <div class="card">
      <h2>My Trading Rules</h2>
      <ul>
        <li>Always use Stop-Loss</li>
        <li>Risk only 1–2% per trade</li>
        <li>Follow only one setup</li>
        <li>No revenge trading</li>
        <li>Trade only when mind is calm</li>
      </ul>
    </div>

    <div class="card">
      <h2>Social Links</h2>
      <p>Connect with me on:</p>
      <a class="btn" href="#">Instagram</a>
      <a class="btn" href="https://www.instagram.com/himanshu_goswami_0808" target="_blank">Instagram</a>
      <a class="btn" href="#">YouTube</a>
      <a class="btn" href="https://youtube.com/@himanshugoswami0808?si=6awvcSJqlvbz4HI0" target="_blank">YouTube</a>
      <a class="btn" href="#">Telegram</a>
    </div>

    <div class="card">
      <h2>How to Host This Website (Free)</h2>
      <p>1. Go to GitHub → Create account<br>
         2. Create new repository → Name it <b>username.github.io</b><br>
         3. Upload these files<br>
         4. Website will be live instantly!</p>
    </div>

      <div class="card">
      <h2>Risk Management Tracker</h2>
      <p>Enter your trade details to calculate and manage risk properly.</p></h2>
      <p>Enter your trade details to calculate and manage risk properly.</p>

      <form style="display:grid; gap:12px; grid-template-columns:1fr 1fr; margin-top:15px;">
        <input type="text" placeholder="Stock / Symbol" style="padding:10px; border-radius:8px; border:1px solid #444;">
        <input type="number" placeholder="Entry Price" style="padding:10px; border-radius:8px; border:1px solid #444;">
        <input type="number" placeholder="Stop Loss" style="padding:10px; border-radius:8px; border:1px solid #444;">
        <input type="number" placeholder="Target" style="padding:10px; border-radius:8px; border:1px solid #444;">
        <input type="number" placeholder="Quantity" style="padding:10px; border-radius:8px; border:1px solid #444;">
      </form>

      <button style="margin-top:15px; padding:12px 20px; background:#4db8ff; border:none; border-radius:10px; font-weight:bold; cursor:pointer; width:100%;">Calculate Risk" onclick="calculateRisk()"</button>

      <div style="margin-top:20px; padding:15px; background:#11141b; border-radius:10px; border:1px solid #333;">
        <p><b>Risk per Trade:</b> <span id='riskVal'>--</span></p>
        <p><b>Reward:</b> <span id='rewardVal'>--</span></p>
        <p><b>Risk : Reward Ratio:</b> <span id='rrVal'>--</span></p>
      </div>

    <div class="card">
      <h2>Saved Trades</h2>
      <table id="tradeTable" style="width:100%; border-collapse: collapse; margin-top:10px;">
        <tr style="background:#2a2f3d;">
          <th style="padding:8px; border:1px solid #444;">Symbol</th>
          <th style="padding:8px; border:1px solid #444;">Entry</th>
          <th style="padding:8px; border:1px solid #444;">SL</th>
          <th style="padding:8px; border:1px solid #444;">Target</th>
          <th style="padding:8px; border:1px solid #444;">Qty</th>
          <th style="padding:8px; border:1px solid #444;">Risk</th>
          <th style="padding:8px; border:1px solid #444;">Reward</th>
          <th style="padding:8px; border:1px solid #444;">RR</th>
        </tr>
      </table>
      <button onclick="saveTrade()" style="margin-top:15px; padding:10px 20px; background:#4db8ff; border:none; border-radius:10px; font-weight:bold; cursor:pointer;">Save Trade</button>
      <button onclick="exportExcel()" style="margin-top:15px; margin-left:10px; padding:10px 20px; background:#3aff7a; border:none; border-radius:10px; font-weight:bold; cursor:pointer;">Export to Excel</button>
    </div>

  </section>

  <footer>
    © 2025 Trade with Himanshu. All Rights Reserved.
  </footer>

  <section id="risk-management-topics" class="p-6 bg-gray-100 rounded-xl mb-6">
    <h2 class="text-2xl font-bold mb-4">Risk Management Topics</h2>
    <ul class="list-disc pl-6 space-y-2">
      <li>Position sizing strategies</li>
      <li>Risk per trade calculation</li>
      <li>Reward expectancy & R:R ratio</li>
      <li>Stop-loss placement techniques</li>
      <li>Capital protection rules</li>
      <li>Drawdown control</li>
      <li>Win-rate vs R:R balance</li>
      <li>Emotional discipline in risk management</li>
      <li>Daily, weekly & monthly risk limits</li>
    </ul>
  </section>
</body>
</html>
