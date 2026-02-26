# Y
<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valentine</title>
<style>
body {
  margin: 0;
  height: 100vh;
  background: linear-gradient(to right, #ff9ecf, #ff69b4);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  font-family: Arial, sans-serif;
}

h1 {
  color: white;
  font-size: 50px;
  text-align: center;
  margin-bottom: 30px;
}

button {
  padding: 15px 25px;
  font-size: 20px;
  border: none;
  border-radius: 10px;
  background-color: white;
  color: #ff69b4;
  cursor: pointer;
  box-shadow: 0 4px 6px rgba(0,0,0,0.2);
  transition: 0.3s;
}

button:hover {
  transform: scale(1.1);
}

/* قلوب بتتحرك */
.heart {
  position: absolute;
  width: 20px;
  height: 20px;
  background-color: red;
  transform: rotate(-45deg);
  animation: float 5s linear infinite;
  top: 100%;
}

.heart:before,
.heart:after {
  content: "";
  position: absolute;
  width: 20px;
  height: 20px;
  background-color: red;
  border-radius: 50%;
}

.heart:before { top: -10px; left: 0; }
.heart:after { left: 10px; top: 0; }

@keyframes float {
  0% { transform: translateY(0) rotate(-45deg); opacity: 1; }
  100% { transform: translateY(-120vh) rotate(-45deg); opacity: 0; }
}
</style>
</head>
<body>

<h1>I love you ❤️</h1>
<button onclick="showMessage()">Press Me 💌</button>

<script>
// الزرار يطلع رسالة
function showMessage() {
  alert("Happy Valentine's Day! 💖");
}

// توليد قلوب عشوائية
setInterval(() => {
  const heart = document.createElement("div");
  heart.className = "heart";
  heart.style.left = Math.random() * 100 + "vw";
  heart.style.width = heart.style.height = (10 + Math.random()*20) + "px";
  document.body.appendChild(heart);
  setTimeout(() => { heart.remove(); }, 5000);
}, 500);
</script>

</body>
</html>
