# ディレクトリ構成とファイル出力のためのコード
import os

# ディレクトリ構成
base_dir = "/mnt/data/english_matching_service"
dirs = [
    base_dir,
    f"{base_dir}/css",
    f"{base_dir}/js"
]

# HTMLコード（index.html）
html_code = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>English Match</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <header>
        <h1>English Match</h1>
        <nav>
            <a href="#teachers">Teachers</a>
            <a href="#contact">Contact</a>
            <a href="#login">Login</a>
        </nav>
    </header>

    <main>
        <section id="teachers">
            <h2>Available English Teachers</h2>
            <div class="teacher-card">
                <h3>John Doe</h3>
                <p>Experience: 5 years</p>
                <p>Specialty: Conversational English</p>
            </div>
            <!-- 他の教師のカードもここに追加 -->
        </section>

        <section id="contact">
            <h2>Contact Us</h2>
            <form id="contactForm">
                <input type="text" placeholder="Your Name" required>
                <input type="email" placeholder="Your Email" required>
                <textarea placeholder="Your Message" required></textarea>
                <button type="submit">Send</button>
            </form>
        </section>

        <section id="ads">
            <h2>Advertisements</h2>
            <div class="ad">Place your ad here!</div>
        </section>

        <section id="login">
            <h2>Login / Sign Up</h2>
            <form id="loginForm">
                <input type="email" placeholder="Email" required>
                <input type="password" placeholder="Password" required>
                <button type="submit">Login</button>
            </form>
            <form id="signupForm">
                <input type="email" placeholder="Email" required>
                <input type="password" placeholder="Password" required>
                <button type="submit">Sign Up</button>
            </form>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 English Match</p>
    </footer>

    <script src="js/script.js"></script>
</body>
</html>
"""

# CSSコード（style.css）
css_code = """
body {
    font-family: Arial, sans-serif;
    background-color: #f0f8ff;
    color: #333;
    margin: 0;
    padding: 0;
}
header {
    background-color: #0077cc;
    color: white;
    padding: 1em;
    text-align: center;
}
nav a {
    color: white;
    margin: 0 1em;
    text-decoration: none;
}
section {
    padding: 2em;
}
.teacher-card, .ad {
    border: 1px solid #ccc;
    padding: 1em;
    margin-top: 1em;
    background-color: #fff;
}
form {
    margin-top: 1em;
}
input, textarea, button {
    display: block;
    margin: 0.5em 0;
    padding: 0.5em;
    width: 100%;
    max-width: 400px;
}
footer {
    background-color: #0077cc;
    color: white;
    text-align: center;
    padding: 1em;
}
"""

# JavaScriptコード（script.js）
js_code = """
document.getElementById('contactForm').addEventListener('submit', function(e) {
    e.preventDefault();
    alert('Thank you for contacting us!');
});
document.getElementById('loginForm').addEventListener('submit', function(e) {
    e.preventDefault();
    alert('Login function is not implemented yet.');
});
document.getElementById('signupForm').addEventListener('submit', function(e) {
    e.preventDefault();
    alert('Signup function is not implemented yet.');
});
"""

# ディレクトリ作成
for d in dirs:
    os.makedirs(d, exist_ok=True)

# ファイル保存
with open(f"{base_dir}/index.html", "w") as f:
    f.write(html_code)

with open(f"{base_dir}/css/style.css", "w") as f:
    f.write(css_code)

with open(f"{base_dir}/js/script.js", "w") as f:
    f.write(js_code)

base_dir
