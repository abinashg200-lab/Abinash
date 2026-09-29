<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SecureBank - Training Login</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      font-family: Arial, Helvetica, sans-serif;
      background: white;
      color: #111;
      display: flex;
      flex-direction: column;
    }

    .training-banner {
      background: #eef8ff;
      border-bottom: 1px solid #c9e6f8;
      padding: 14px 24px;
      font-size: 15px;
      line-height: 1.45;
      color: #17445c;
    }

    .training-banner strong {
      color: #0b5f87;
    }

    .page {
      flex: 1;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 40px 20px;
      position: relative;
      overflow: hidden;
    }

    .shape-left {
      position: absolute;
      left: -120px;
      width: 430px;
      height: 430px;
      background: #f7f0df;
      transform: rotate(45deg);
      opacity: 0.6;
    }

    .shape-right {
      position: absolute;
      right: -110px;
      width: 310px;
      height: 310px;
      border: 3px solid #21b7aa;
      transform: rotate(45deg);
      opacity: 0.6;
    }

    .card {
      width: 550px;
      max-width: 100%;
      background: white;
      border: 1px solid #d6d0c6;
      border-radius: 26px;
      padding: 36px 38px 42px;
      position: relative;
      z-index: 2;
      box-shadow: 0 8px 30px rgba(0, 0, 0, 0.06);
    }

    .brand {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 13px;
      margin-bottom: 35px;
    }

    .logo {
      width: 45px;
      height: 45px;
      background: #ffd21a;
      transform: rotate(45deg);
      position: relative;
    }

    .logo::after {
      content: "";
      position: absolute;
      width: 18px;
      height: 18px;
      background: white;
      right: 0;
      bottom: 0;
      clip-path: polygon(100% 0, 100% 100%, 0 100%);
    }

    .brand-name {
      font-size: 28px;
      font-weight: bold;
    }

    h1 {
      font-size: 23px;
      margin-bottom: 24px;
    }

    label {
      display: block;
      font-size: 14px;
      margin-bottom: 7px;
    }

    input {
      width: 100%;
      padding: 16px;
      border: 1px solid #cfcfcf;
      border-radius: 10px;
      font-size: 16px;
      margin-bottom: 18px;
      outline: none;
    }

    input:focus {
      border-color: #168f86;
      box-shadow: 0 0 0 3px rgba(22, 143, 134, 0.12);
    }

    button {
      width: 100%;
      border: none;
      border-radius: 28px;
      padding: 15px;
      font-size: 16px;
      cursor: pointer;
      background: #ffd21a;
      color: #111;
      font-weight: 600;
    }

    button:hover {
      background: #f5c500;
    }

    .links {
      margin-top: 22px;
      text-align: center;
      font-size: 14px;
    }

    .links a {
      color: #164d68;
      text-decoration: underline;
    }

    .notice {
      display: none;
      margin-top: 24px;
      padding: 18px;
      border-radius: 12px;
      background: #fff4d6;
      border: 1px solid #f0d27a;
      line-height: 1.5;
      font-size: 14px;
    }

    .notice strong {
      display: block;
      margin-bottom: 7px;
      font-size: 17px;
    }

    footer {
      text-align: center;
      padding: 18px;
      font-size: 12px;
      color: #666;
    }

    @media (max-width: 600px) {
      .card {
        padding: 28px 22px 32px;
      }

      .training-banner {
        font-size: 13px;
        padding: 12px 16px;
      }
    }
  </style>
</head>

<body>

  <div class="training-banner">
    <strong>CYBERSECURITY TRAINING SIMULATION:</strong>
    This is a fictional login page for security awareness training.
    Do not enter real banking credentials.
  </div>

  <main class="page">

    <div class="shape-left"></div>
    <div class="shape-right"></div>

    <section class="card">

      <div class="brand">
        <div class="logo"></div>
        <div class="brand-name">SecureBank</div>
      </div>

      <h1>Training Login</h1>

      <form id="loginForm" autocomplete="off">

        <label for="clientId">
          Training ID
        </label>

        <input
          id="clientId"
          type="text"
          placeholder="Enter training ID"
          required
        >

        <label for="password">
          Training Password
        </label>

        <input
          id="password"
          type="password"
          placeholder="Enter training password"
          required
        >

        <button type="submit">
          Log in
        </button>

      </form>

      <div class="links">
        <a href="#" onclick="showTip(event)">
          Forgot your training ID?
        </a>
      </div>

      <div id="notice" class="notice"></div>

    </section>

  </main>

  <footer>
    SecureBank Cybersecurity Awareness Program —
    Fictional training environment
  </footer>


  <script>

    /*
      SECURITY TRAINING SIMULATION

      This page intentionally does NOT:
      - send credentials to a server
      - save credentials
      - store passwords in localStorage
      - log passwords
      - transmit information
    */

    const form = document.getElementById("loginForm");
    const notice = document.getElementById("notice");

    form.addEventListener("submit", function(event) {

      event.preventDefault();

      // Values are intentionally not stored or transmitted.
      document.getElementById("clientId").value;
      document.getElementById("password").value;

      // Clear the fields immediately.
      form.reset();

      // Display training result.
      notice.style.display = "block";

      notice.innerHTML = `
        <strong>🛡️ Phishing Awareness Check</strong>

        This was a cybersecurity training simulation.

        Your entered information was not saved or transmitted.

        <br><br>

        <b>Warning signs to check:</b>

        <ul>
          <li>Unexpected login pages</li>
          <li>Unfamiliar website addresses</li>
          <li>Requests for passwords</li>
          <li>Links received from unexpected messages</li>
        </ul>
      `;

    });


    function showTip(event) {

      event.preventDefault();

      notice.style.display = "block";

      notice.innerHTML = `
        <strong>Security Tip</strong>

        Never enter banking credentials into a page unless
        you have verified the website address and reached the
        website through a trusted source.
      `;
    }

  </script>

</body>
</html>
