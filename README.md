<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no" />
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
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      background: linear-gradient(to bottom, #d1d9ff, #e3e8ff);
    }
    /* Hide number input arrows for better UX on mobile */
    input[type=number]::-webkit-inner-spin-button, 
    input[type=number]::-webkit-outer-spin-button { 
      -webkit-appearance: none; 
      margin: 0; 
    }
    input[type=number] {
      -moz-appearance: textfield;
    }
  </style>
</head>
<body class="min-h-screen flex items-center justify-center p-4 sm:p-6">
  <div class="bg-white rounded-[40px] shadow-lg flex flex-col md:flex-row max-w-4xl w-full max-h-[calc(100vh-48px)] overflow-auto">
    
    <!-- Left Panel -->
    <div class="bg-[#4f6ef7] flex flex-col justify-center items-center flex-[1.2] rounded-t-[40px] md:rounded-l-[40px] md:rounded-tr-none p-8 sm:p-10 text-white min-h-[280px] md:min-h-auto">
      <h1 class="text-4xl font-extrabold leading-tight text-center mb-4 sm:mb-6">Welcome</h1>
      <p class="text-lg text-center mb-8 sm:mb-10 max-w-xs sm:max-w-sm">Please login as Customer or Dealer</p>
      <i class="fas fa-users text-7xl sm:text-8xl"></i>
    </div>

    <!-- Right Panel -->
    <div class="flex-[1.8] p-6 sm:p-10 md:p-12 flex flex-col justify-center rounded-b-[40px] md:rounded-r-[40px] md:rounded-bl-none bg-white min-h-[360px] md:min-h-auto">
      <h2 class="text-3xl font-extrabold text-gray-900 mb-8">Login</h2>
      <form class="space-y-6" onsubmit="handleLogin(event)" novalidate>
        
        <!-- User Type Selection -->
        <div>
          <select id="userType" class="w-full rounded-lg bg-[#f3f3f3] py-3 px-4 text-gray-700 focus:outline-none focus:ring-2 focus:ring-[#4f6ef7] transition" required>
            <option value="customer">Customer</option>
            <option value="dealer">Dealer</option>
          </select>
        </div>

        <!-- User ID -->
        <div class="relative">
          <input
            type="text"
            id="userId"
            placeholder="Enter your User ID"
            class="w-full rounded-lg bg-[#f3f3f3] py-3 px-4 pr-12 text-gray-700 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-[#4f6ef7] transition"
            required
            autocomplete="username"
            inputmode="text"
            aria-label="User ID"
          />
          <i class="fas fa-user absolute right-4 top-1/2 -translate-y-1/2 text-gray-500 pointer-events-none"></i>
        </div>

        <!-- Password -->
        <div class="relative">
          <input
            type="password"
            id="password"
            placeholder="Enter your Password"
            class="w-full rounded-lg bg-[#f3f3f3] py-3 px-4 pr-12 text-gray-700 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-[#4f6ef7] transition"
            required
            autocomplete="current-password"
            aria-label="Password"
          />
          <i class="fas fa-lock absolute right-4 top-1/2 -translate-y-1/2 text-gray-500 pointer-events-none"></i>
        </div>

        <!-- Submit Button -->
        <button
          type="submit"
          class="w-full bg-[#4f6ef7] text-white font-extrabold py-3 rounded-lg text-lg hover:bg-[#3b54c1] transition-shadow shadow-md hover:shadow-lg"
          aria-label="Login"
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
      const userId = document.getElementById("userId").value.trim();
      const password = document.getElementById("password").value;

      if (!userId) {
        alert("Please enter your User ID.");
        return;
      }
      if (!password) {
        alert("Please enter your Password.");
        return;
      }

      alert(`Logging in as ${userType.toUpperCase()} with ID: ${userId}`);
    }
  </script>
</body>
</html>
