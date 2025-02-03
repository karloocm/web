<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>San Valentín Interactivo</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Mi princesa, ¿Podria ser tu San Valentín? ❤️</h1>
        <div class="buttons">
            <button id="yesBtn">Sí ❤️</button>
            <button id="noBtn">No 💔</button>
        </div>
    </div>

    <div class="response" id="response"></div>
    
    <div class="hearts"></div>

    <script src="script.js"></script>
</body>
</html>

const yesBtn = document.getElementById('yesBtn');
const noBtn = document.getElementById('noBtn');
const response = document.getElementById('response');

// Acción para el botón "Sí"
yesBtn.addEventListener('click', () => {
    response.style.display = 'block';
    response.textContent = "¡Sabía que dirías que síii! ❤️Te amo como no tienes ideaa😽❤️";
});

// Acción para el botón "No"
noBtn.addEventListener('mouseover', () => {
    const randomX = Math.random() * (window.innerWidth - noBtn.offsetWidth);
    const randomY = Math.random() * (window.innerHeight - noBtn.offsetHeight);

    noBtn.style.left = `${randomX}px`;
    noBtn.style.top = `${randomY}px`;
});

/* Estilo general */
body {
    margin: 0;
    padding: 0;
    background: url('https://placekitten.com/800/600') center/cover no-repeat fixed;
    font-family: 'Arial', sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    overflow: hidden;
    position: relative;
    text-align: center;
}

/* Fondo borroso */
body::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: inherit;
    filter: blur(8px);
    z-index: -1;
    opacity: 0.7;
}

/* Contenedor */
.container {
    background: rgba(255, 255, 255, 0.9);
    padding: 20px 30px;
    border-radius: 15px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
    position: relative;
    z-index: 1;
    max-width: 90%;
    width: 350px;
}

h1 {
    color: #ff6f91;
    font-size: 2rem;
    margin-bottom: 20px;
}

/* Botones */
button {
    padding: 15px 30px;
    font-size: 1.2rem;
    border: none;
    border-radius: 20px;
    cursor: pointer;
    margin: 10px;
    transition: transform 0.3s ease;
}

#yesBtn {
    background-color: #ff6b6b;
    color: white;
}

#yesBtn:hover {
    background-color: #ff4757;
    transform: scale(1.1);
}

#noBtn {
    background-color: #6c757d;
    color: white;
    position: absolute;
    transition: top 0.3s, left 0.3s;
}

/* Corazones animados */
.hearts::before, .hearts::after {
    content: "❤️";
    position: absolute;
    font-size: 2rem;
    animation: float 5s infinite ease-in-out;
    opacity: 0.8;
}

/* Animación de los corazones */
@keyframes float {
    from {
        transform: translateY(100vh) scale(0.5);
        opacity: 0;
    }
    to {
        transform: translateY(-10vh) scale(1.5);
        opacity: 1;
    }
}

/* Respuesta */
.response {
    font-size: 1.5rem;
    margin-top: 20px;
    color: #ff6f91;
    display: none;
}
background-image: url(https://ibb.co/LD1Sds3w);
