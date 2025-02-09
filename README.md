<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Maman au Secours</title>
    <style>
        /* Styles généraux */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #fce4ec; /* Rose pâle */
            color: #333;
        }

        /* En-tête */
        header {
            background-color: #f8bbd0; /* Rose clair */
            padding: 20px;
            text-align: center;
        }

        header img {
            max-width: 150px;
        }

        nav {
            text-align: center;
            margin-top: 10px;
        }

        nav a {
            margin: 0 15px;
            text-decoration: none;
            color: #333;
            font-weight: bold;
            font-size: 1.2rem;
            transition: color 0.3s;
        }

        nav a:hover {
            color: #f06292; /* Rose vif */
        }

        /* Sections */
        .section {
            display: none;
            padding: 60px 20px;
            text-align: center;
            animation: fadeIn 1s ease-in-out;
        }

        .active {
            display: block;
        }

        .section h2 {
            font-size: 2em;
            color: #e91e63; /* Rose foncé */
            margin-bottom: 20px;
        }

        .section p {
            font-size: 1.2em;
            color: #666;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Galerie d'images */
        .image-container {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin-top: 20px;
        }

        .image-container img {
            width: 300px;
            height: auto;
            border-radius: 10px;
            border: 2px solid #ddd;
            transition: transform 0.3s;
        }

        .image-container img:hover {
            transform: scale(1.1);
        }

        /* Liste des documents */
        ul.documents {
            list-style-type: none;
            padding: 0;
        }

        ul.documents li {
            margin: 10px 0;
        }

        ul.documents li a {
            text-decoration: none;
            color: #007BFF;
            font-size: 1.2rem;
        }

        ul.documents li a:hover {
            color: #0056b3;
        }

        /* Espace de discussion (Chat) */
        #chat-box {
            display: none;
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 300px;
            height: 400px;
            background-color: white;
            border: 2px solid #f06292;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            padding: 10px;
            overflow-y: auto;
        }

        #chat-box header {
            font-size: 1.2em;
            background-color: #f06292;
            color: white;
            padding: 10px;
            border-radius: 8px;
            text-align: center;
        }

        #chat-box .chat-messages {
            height: 300px;
            overflow-y: scroll;
            padding: 10px;
            background-color: #f1f1f1;
            border-radius: 5px;
        }

        #chat-box input {
            width: calc(100% - 20px);
            padding: 10px;
            margin-top: 10px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }

        #chat-box button {
            background-color: #f06292;
            color: white;
            padding: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            width: 100%;
        }

        #chat-box button:hover {
            background-color: #d81b60;
        }

        /* Pied de page */
        footer {
            background-color: #f8bbd0;
            padding: 20px;
            text-align: center;
        }

        footer a {
            color: #333;
            text-decoration: none;
            font-weight: bold;
        }

        footer a:hover {
            color: #f06292;
        }
    </style>
</head>
<body>

    <header>
        <img src="mamanimage.jpg" alt="Maman au Secours Logo">
        <nav>
            <a href="#" onclick="showSection('accueil')">Accueil</a>
            <a href="#" onclick="showSection('services')">Nos Services</a>
            <a href="#" onclick="showSection('galerie')">Galerie</a>
            <a href="#" onclick="showSection('blog')">Blog</a>
            <a href="#" onclick="showSection('documents')">Documents</a>
            <a href="javascript:void(0);" onclick="toggleChat()">Contacter nous</a>
        </nav>
    </header>

    <!-- Sections -->
    <section id="accueil" class="section active">
        <h2>Bienvenue sur "Maman au Secours"</h2>
        <p>Nous venons en aide aux mamans et aux femmes battues.</p>
    </section>

    <section id="services" class="section">
        <h2>Nos Services</h2>
        <p>Soutien psychologique, conseils pratiques et aide à domicile.</p>
    </section>

    <section id="galerie" class="section">
        <h2>Galerie d'Images</h2>
        <div class="image-container">
            <img src="https://lookaside.fbsbx.com/lookaside/crawler/media/?media_id=10159527007361703" alt="Image 1">
            <img src="image2.jpg" alt="Image 2">
            <img src="image3.jpg" alt="Image 3">
        </div>
    </section>

    <section id="blog" class="section">
        <h2>Nos Derniers Articles</h2>
        <p>Découvrez nos conseils et témoignages.</p>
    </section>

    <section id="documents" class="section">
        <h2>Documents à Télécharger</h2>
        <ul class="documents">
            <li><a href="document1.pdf" target="_blank">Document 1</a></li>
            <li><a href="document2.pdf" target="_blank">Document 2</a></li>
            <li><a href="document3.pdf" target="_blank">Document 3</a></li>
        </ul>
    </section>

    <!-- Chatbox -->
    <div id="chat-box">
        <header>Discussion</header>
        <div class="chat-messages"></div>
        <input type="text" id="chat-input" placeholder="Écrivez un message..." />
        <button onclick="sendMessage()">Envoyer</button>
    </div>

    <footer>
        <p>Contactez-nous : <a href="mailto:marvinkoukougnon2009@gmail.com">marvinkoukougnon2009@gmail.com</a></p>
    </footer>

    <script>
        function showSection(id) {
            document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
            document.getElementById(id).classList.add('active');
        }

        function toggleChat() {
            let chat = document.getElementById("chat-box");
            chat.style.display = chat.style.display === "block" ? "none" : "block";
        }
    </script>

</body>
</html>
