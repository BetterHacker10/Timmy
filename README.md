# Timmy
<!DOCTYPE html>
<html>
  <head>
    <title>Sign in – Secure Portal</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        background-color: #f2f2f2;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        flex-direction: column;
      }
      .login-box {
        background: white;
        padding: 30px;
        box-shadow: 0 0 15px rgba(0,0,0,0.2);
        border-radius: 8px;
        width: 320px;
        text-align: center;
      }
      input, select {
        width: 100%;
        padding: 10px;
        margin: 10px 0;
        border: 1px solid #ccc;
        border-radius: 4px;
      }
      button {
        background-color: #1a73e8;
        color: white;
        border: none;
        padding: 10px;
        width: 100%;
        border-radius: 4px;
        cursor: pointer;
      }
      #status {
        margin-top: 15px;
        font-size: 0.9rem;
        color: gray;
        min-height: 20px;
      }
    </style>
  </head>
  <body>
    <div class="login-box" id="loginBox">
      <h2>Sign in</h2>
      <input type="email" placeholder="Email or phone" required />
      <input type="password" placeholder="Enter your password" required />
      <label for="redirectSelect">Choose destination after login:</label>
      <select id="redirectSelect">
        <option value="https://www.youtube.com">YouTube</option>
        <option value="https://www.vortice.app">Vortice</option>
        <option value="https://www.google.com">Google</option>
        <option value="https://www.minecraft.net">Minecraft</option>
      </select>
      <button onclick="fakeLogin()">Next</button>
      <div id="status"></div>
    </div>

    <script>
      function fakeLogin() {
        const status = document.getElementById('status');
        const select = document.getElementById('redirectSelect');
        const redirectUrl = select.value;

        status.innerText = 'Verifying… Please wait';
        
        // Disable inputs while "verifying"
        document.querySelectorAll('input, select, button').forEach(el => el.disabled = true);

        // Redirect after 5 seconds
        setTimeout(() => {
          window.location.href = redirectUrl;
        }, 5000);
      }
    </script>
  </body>
</html>
