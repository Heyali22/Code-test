<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Website</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <nav class="navbar">
    <h2 class="logo">MySite</h2>
    <ul class="nav-links">
      <li>Home</li>
      <li>About</li>
      <li>Contact</li>
    </ul>
  </nav>

  <section class="hero">
    <h1>Mobile Responsive Website</h1>
    <p>Looks perfect on every device</p>
    <button onclick="clickMe()">Get Started</button>
  </section>

  <script src="script.js"></script>
</body>
</html>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: Arial, sans-serif;
}

body {
  background: #020617;
  color: white;
}

/* Navbar */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  background: #020617;
}

.nav-links {
  display: flex;
  gap: 20px;
  list-style: none;
}

/* Hero */
.hero {
  min-height: 90vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 20px;
}

.hero h1 {
  font-size: 3rem;
}

.hero p {
  margin: 15px 0;
  opacity: 0.8;
}

button {
  padding: 14px 28px;
  border: none;
  border-radius: 8px;
  background: #22c55e;
  font-size: 16px;
  cursor: pointer;
}

/* 📱 Mobile */
@media (max-width: 768px) {
  .nav-links {
    display: none;
  }

  .hero h1 {
    font-size: 2rem;
  }

  button {
    width: 100%;
    max-width: 280px;
  }
}