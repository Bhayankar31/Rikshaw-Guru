<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Login Page</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css"
  />
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap');
    body {
      font-family: 'Inter', sans-serif;
    }
  </style>
</head>
<body class="min-h-screen bg-gradient-to-b from-[#d1d9ff] to-[#e3e8ff] flex items-center justify-center p-6">
  <div class="bg-white rounded-[40px] shadow-[0_10px_30px_rgba(0,0,0,0.1)] flex max-w-4xl w-full max-h-[500px] overflow-hidden flex-col md:flex-row">
    
    <!-- Left Panel -->
    <div class="bg-[#7399ff] flex flex-col justify-center items-center flex-[1.2] rounded-t-[40px] md:rounded-l-[40px] md:rounded-tr-none p-10 text-white">
      <h1 class="text-4xl font-extrabold leading-tight text-center mb-6">Welcome</h1>
      <p class="text-lg text-center mb-10">Please login as Customer or Dealer</p>
      <i class="fas fa-users text-6xl"></i>
    </div>

    <!-- Right Panel -->
    <div class="flex-[1.8] p-8 md:p-12 flex flex-col justify-center rounded-b-[40px] md:rounded-r-[40px] md:rounded-bl-none bg-white">
      <h2 class="text-3xl font-extrabold text-gray-800 mb-6">Login</h2>
      <form class="space-y-6" onsubmit="handleLogin(event)">
        
        <!-- User Type Selection -->
        <div class="relative">
          <select id="userType" class="w-full rounded-md bg-[#f3f3f3] py-3 px-4 text-gray-600 focus:outline-none focus:ring-2 focus:ring-[#7399ff]">
            <option value="customer">Customer</option>
            <option value="dealer">Dealer</option>
          </select>
        </div>

        <!-- User ID -->
        <div class="relative">
          <input
            type="text"
            id="userId"
            placeholder="User ID"
            class="w-full rounded-md bg-[#f3f3f3] py-3 px-4 pr-12 text-gray-600 placeholder-gray-600 focus:outline-none focus:ring-2 focus:ring-[#7399ff]"
            required
          />
          <i class="fas fa-user absolute right-4 top-1/2 -translate-y-1/2 text-gray-700"></i>
        </div>

        <!-- Password -->
        <div class="relative">
          <input
            type="password"
            id="password"
            placeholder="Password"
            class="w-full rounded-md bg-[#f3f3f3] py-3 px-4 pr-12 text-gray-600 placeholder-gray-600 focus:outline-none focus:ring-2 focus:ring-[#7399ff]"
            required
          />
          <i class="fas fa-lock absolute right-4 top-1/2 -translate-y-1/2 text-gray-700"></i>
        </div>

        <!-- Submit Button -->
        <button
          type="submit"
          class="w-full bg-[#7399ff] text-white font-extrabold py-3 rounded-md text-lg hover:bg-[#5a7de6] transition"
        >
          Login
        </button>
      </form>
    </div>
  </div>

  <script>
    function handleLogin(e) {
      e.preventDefault();
      const userType = document.getElementById("userType").value;
      const userId = document.getElementById("userId").value;
      const password = document.getElementById("password").value;

      alert(Logging in as ${userType.toUpperCase()} with ID: ${userId});
    }
  </script>
</body>
</html>
