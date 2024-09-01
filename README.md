<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Magi Manga Collection</title>
<style>
/* Global Styles */
body {
    background-color: #000; /* Black background */
    color: #fff; /* White text */
    font-family: Arial, sans-serif; /* Example font */
    margin: 0;
    padding: 0;
}

.container {
    position: relative;
    width: 100%;
    max-width: 800px; /* Adjust width as needed */
    margin: 20px auto;
    padding: 0 20px;
}

/* Slider Styles */
.slider {
    position: relative;
    overflow: hidden;
}

.slide {
    display: none;
}

.slide img {
    width: 100%;
    height: auto;
    display: block;
}

.play-button {
    position: absolute;
    bottom: 10px; /* Adjust positioning */
    right: 10px; /* Adjust positioning */
    background-color: #000000; /* Black background for the button */
    color: #ffffff;
    padding: 10px 20px;
    border: none;
    border-radius: 100px; /* Rounded border */
    font-size: 16px;
    text-decoration: none; /* Remove underlines */
    transition: background-color 0.3s ease;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Add shadow */
}

.play-button:hover {
    background-color: #b30000; /* Darker shade on hover */
}

.navigation {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 100%; /* Full width */
    text-align: center; /* Center align the buttons */
}

.prev, .next {
    background-color: transparent; /* Transparent background */
    color: #000000; /* Blue color for the buttons */
    border: none;
    font-size: 48px; /* Larger font size */
    cursor: pointer;
    margin: 0 20px; /* Increased margin */
    transition: color 0.3s ease; /* Transition color */
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
}

.prev {
    left: 20px; /* Adjust left positioning */
}

.next {
    right: 20px; /* Adjust right positioning */
}

.prev:hover, .next:hover {
    color: #0056b3; /* Darker blue color on hover */
}

/* Recently Posted Widget Styles */
.recent-posts {
    margin-top: 20px;
}

.recent-posts h2 {
    font-size: 24px;
    margin-bottom: 10px;
    color: #ffffff; /* White color */
    text-align: center;
}

.recent-posts ul {
    list-style-type: none;
    padding: 0;
}

.recent-posts .post-item {
    margin-bottom: 10px;
}

.recent-posts .post-item a {
    color: #fff;
    text-decoration: none;
    font-size: 18px;
}

/* Two Images Side by Side */
.image-container {
    display: flex;
    justify-content: space-between;
    margin-top: 20px;
}

.image-container figure {
    width: 48%; /* Adjust width as needed */
    position: relative;
}

.image-container img {
    width: 100%;
    height: auto;
    display: block;
}

.image-container figcaption {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.7); /* Semi-transparent black background */
    color: #fff;
    padding: 10px;
    margin: 0;
    text-align: center;
}

@media (max-width: 600px) {
    .image-container {
        flex-direction: column;
    }

    .image-container figure {
        width: 100%; /* Full width on smaller screens */
        margin-bottom: 10px;
    }
}
</style>
</head>
<body>

<div class="container">
    <div class="slider">
        <div class="slide">
            <img src="https://i.pinimg.com/originals/0b/64/f9/0b64f98f2d2eb72007bd89db678d9ae1.jpg" alt="Magi Manga Cover 1">
            <a href="https://example.com/play-online" class="play-button">Play Online</a>
        </div>
        <div class="slide">
            <img src="https://upload.wikimedia.org/wikipedia/en/thumb/7/77/Magi_%28manga%29_volume_2_cover.jpg/220px-Magi_%28manga%29_volume_2_cover.jpg" alt="Magi Manga Cover 2">
            <a href="https://example.com/play-online" class="play-button">Play Online</a>
        </div>
        <div class="slide">
            <img src="https://upload.wikimedia.org/wikipedia/en/thumb/7/77/Magi_%28manga%29_volume_3_cover.jpg/220px-Magi_%28manga%29_volume_3_cover.jpg" alt="Magi Manga Cover 3">
            <a href="https://example.com/play-online" class="play-button">Play Online</a>
        </div>
        <div class="slide">
            <img src="https://upload.wikimedia.org/wikipedia/en/thumb/7/77/Magi_%28manga%29_volume_4_cover.jpg/220px-Magi_%28manga%29_volume_4_cover.jpg" alt="Magi Manga Cover 4">
            <a href="https://example.com/play-online" class="play-button">Play Online</a>
        </div>

        <!-- Navigation Buttons -->
        <button class="prev" onclick="plusSlides(-1)">&#10094;</button>
        <button class="next" onclick="plusSlides(1)">&#10095;</button>
    </div>

    <!-- Recently Posted Widget -->
    <div class="recent-posts">
        <h2>Recently Posted</h2>
        <ul class="post-list">
            <!-- Placeholder list items -->
        </ul>
    </div>

    <!-- Two Images Side by Side -->
    <div class="image-container">
        <figure>
            <img src="https://i.pinimg.com/originals/0b/64/f9/0b64f98f2d2eb72007bd89db678d9ae1.jpg" alt="Magi Manga Cover 2">
            <figcaption>Magi Manga Volume 2</figcaption>
        </figure>
        <figure>
            <img src="https://i.pinimg.com/originals/0b/64/f9/0b64f98f2d2eb72007bd89db678d9ae1.jpg" alt="Magi Manga Cover 3">
            <figcaption>Magi Manga Volume 3</figcaption>
        </figure>
    </div>
</div>

<script>
let slideIndex = 1;
showSlides(slideIndex);

function plusSlides(n) {
    showSlides(slideIndex += n);
}

function showSlides(n) {
    let slides = document.getElementsByClassName("slide");
    if (n > slides.length) { slideIndex = 1 }
    if (n < 1) { slideIndex = slides.length }
    for (let slide of slides) {
        slide.style.display = "none";
    }
    slides[slideIndex - 1].style.display = "block";
}
    from flask import Flask, redirect, request, session, url_for
import requests
import os

app = Flask(__name__)
app.secret_key = 'your_secret_key'  # Replace with a random secret key

# GitHub OAuth configuration
CLIENT_ID = 'your_client_id'  # Replace with your GitHub OAuth app client ID
CLIENT_SECRET = 'your_client_secret'  # Replace with your GitHub OAuth app client secret
AUTHORIZE_URL = 'https://github.com/login/oauth/authorize'
TOKEN_URL = 'https://github.com/login/oauth/access_token'
USER_API_URL = 'https://api.github.com/user'

@app.route('/')
def home():
    return '<a href="/login">Log in with GitHub</a>'

@app.route('/login')
def login():
    return redirect(f'{AUTHORIZE_URL}?client_id={CLIENT_ID}&scope=user')

@app.route('/callback')
def callback():
    code = request.args.get('code')
    if code is None:
        return 'Error: No code provided'

    # Exchange code for access token
    token_response = requests.post(
        TOKEN_URL,
        headers={'Accept': 'application/json'},
        data={
            'client_id': CLIENT_ID,
            'client_secret': CLIENT_SECRET,
            'code': code
        }
    )
    token_json = token_response.json()
    access_token = token_json.get('access_token')

    if access_token is None:
        return 'Error: No access token received'

    # Use access token to get user info
    user_response = requests.get(
        USER_API_URL,
        headers={'Authorization': f'token {access_token}'}
    )
    user_json = user_response.json()

    # Store user info in session
    session['user'] = user_json

    return redirect(url_for('profile'))

@app.route('/profile')
def profile():
    user = session.get('user')
    if user is None:
        return redirect(url_for('home'))

    return f"""
    <h1>{user['login']}</h1>
    <img src="{user['avatar_url']}" alt="Avatar" width="100">
    <p><a href="{user['html_url']}">GitHub Profile</a></p>
    <a href="/logout">Log out</a>
    """

@app.route('/logout')
def logout():
    session.pop('user', None)
    return redirect(url_for('home'))

if __name__ == '__main__':
    app.run(debug=True)
</script>

</body>
</html>
