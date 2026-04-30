<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flappy Bird - Chill Edition</title>
    <style>
        body { margin: 0; overflow: hidden; background: #222; display: flex; justify-content: center; align-items: center; height: 100vh; font-family: 'Arial', sans-serif; }
        canvas { background: #70c5ce; border: 4px solid #fff; box-shadow: 0 0 20px rgba(0,0,0,0.5); }
        #ui { position: absolute; color: white; text-align: center; pointer-events: none; text-shadow: 2px 2px 4px rgba(0,0,0,0.5); z-index: 10; }
    </style>
</head>
<body>

    <div id="ui">
        <h1 id="scoreDisplay">Score: 0</h1>
        <p id="msg">Press SPACE or CLICK to Start</p>
    </div>
    <canvas id="gameCanvas"></canvas>

<script>
    const canvas = document.getElementById("gameCanvas");
    const ctx = canvas.getContext("2d");
    const scoreDisplay = document.getElementById("scoreDisplay");
    const msg = document.getElementById("msg");

    canvas.width = 320;
    canvas.height = 480;

    // --- CHILL SETTINGS ---
    const GRAVITY = 0.18;
    const JUMP = -3.8;
    const PIPE_SPEED = 1.6;      // Slower horizontal movement
    const BG_SPEED = 0.5;        // Even slower background
    const PIPE_SPAWN_RATE = 150; // More frames between new pipes (increased from 100)
    const PIPE_GAP = 140;        // Slightly larger vertical opening

    let bird, pipes, backgrounds, frame, score, gameRunning;

    function resetGame() {
        bird = { x: 50, y: 150, w: 34, h: 24, velocity: 0, rotation: 0 };
        pipes = [];
        backgrounds = [
            { x: 0, y: 300, w: 100 },
            { x: 150, y: 350, w: 80 },
            { x: 300, y: 320, w: 120 }
        ];
        frame = 0;
        score = 0;
        gameRunning = false;
        scoreDisplay.innerText = "Score: 0";
        msg.style.opacity = 1;
        msg.innerText = "Press SPACE or CLICK to Start";
    }

    function spawnPipe() {
        const minHeight = 50;
        const maxHeight = canvas.height - PIPE_GAP - minHeight - 22;
        const height = Math.floor(Math.random() * (maxHeight - minHeight + 1)) + minHeight;
        pipes.push({ x: canvas.width, y: 0, w: 50, h: height, passed: false });
    }

    function drawBird() {
        ctx.save();
        ctx.translate(bird.x + bird.w / 2, bird.y + bird.h / 2);
        bird.rotation = Math.min(Math.PI / 4, Math.max(-Math.PI / 4, bird.velocity * 0.1));
        ctx.rotate(bird.rotation);

        // Body
        ctx.fillStyle = "#f1c40f";
        ctx.beginPath(); ctx.ellipse(0, 0, bird.w / 2, bird.h / 2, 0, 0, Math.PI * 2); ctx.fill();
        ctx.strokeStyle = "#000"; ctx.lineWidth = 2; ctx.stroke();

        // Wing
        ctx.fillStyle = "#f39c12";
        ctx.beginPath(); ctx.ellipse(-5, 2, 8, 5, 0, 0, Math.PI * 2); ctx.fill(); ctx.stroke();

        // Eye
        ctx.fillStyle = "#fff";
        ctx.beginPath(); ctx.arc(8, -4, 4, 0, Math.PI * 2); ctx.fill(); ctx.stroke();
        ctx.fillStyle = "#000"; ctx.beginPath(); ctx.arc(10, -4, 1.5, 0, Math.PI * 2); ctx.fill();

        // Beak
        ctx.fillStyle = "#e67e22";
        ctx.beginPath(); ctx.moveTo(14, 0); ctx.lineTo(22, 2); ctx.lineTo(14, 5); ctx.closePath(); ctx.fill(); ctx.stroke();

        ctx.restore();
    }

    function update() {
        if (!gameRunning) return;

        backgrounds.forEach(bg => {
            bg.x -= BG_SPEED;
            if (bg.x + bg.w < 0) bg.x = canvas.width;
        });

        bird.velocity += GRAVITY;
        bird.y += bird.velocity;

        if (bird.y + bird.h > canvas.height - 22 || bird.y < 0) gameOver();

        // Spawning based on the new, slower rate
        if (frame % PIPE_SPAWN_RATE === 0) spawnPipe();

        pipes.forEach((pipe, index) => {
            pipe.x -= PIPE_SPEED;

            if (!pipe.passed && bird.x > pipe.x + pipe.w) {
                score++;
                scoreDisplay.innerText = `Score: ${score}`;
                pipe.passed = true;
            }

            if (bird.x + bird.w - 5 > pipe.x && bird.x + 5 < pipe.x + pipe.w) {
                if (bird.y + 5 < pipe.h || bird.y + bird.h - 5 > pipe.h + PIPE_GAP) {
                    gameOver();
                }
            }

            if (pipe.x + pipe.w < 0) pipes.splice(index, 1);
        });

        frame++;
    }

    function draw() {
        ctx.fillStyle = "#70c5ce";
        ctx.fillRect(0, 0, canvas.width, canvas.height);

        ctx.fillStyle = "#8ed0d8";
        backgrounds.forEach(bg => {
            ctx.beginPath();
            ctx.arc(bg.x, bg.y, bg.w / 2, 0, Math.PI * 2);
            ctx.arc(bg.x + 30, bg.y - 10, bg.w / 2, 0, Math.PI * 2);
            ctx.arc(bg.x + 60, bg.y, bg.w / 2, 0, Math.PI * 2);
            ctx.fill();
        });

        pipes.forEach(pipe => {
            ctx.fillStyle = "#2ecc71";
            ctx.fillRect(pipe.x, 0, pipe.w, pipe.h);
            ctx.strokeRect(pipe.x, 0, pipe.w, pipe.h);
            const bottomY = pipe.h + PIPE_GAP;
            ctx.fillRect(pipe.x, bottomY, pipe.w, canvas.height - bottomY);
            ctx.strokeRect(pipe.x, bottomY, pipe.w, canvas.height - bottomY);
        });

        drawBird();

        ctx.fillStyle = "#ded895";
        ctx.fillRect(0, canvas.height - 22, canvas.width, 22);
        ctx.fillStyle = "#222";
        ctx.fillRect(0, canvas.height - 24, canvas.width, 2);

        requestAnimationFrame(() => {
            update();
            draw();
        });
    }

    function gameOver() {
        gameRunning = false;
        msg.style.opacity = 1;
        msg.innerText = "Game Over! Click to Restart";
    }

    function input() {
        if (!gameRunning) {
            if (msg.innerText.includes("Game Over")) resetGame();
            gameRunning = true;
            msg.style.opacity = 0;
        }
        bird.velocity = JUMP;
    }

    window.addEventListener("keydown", (e) => { if (e.code === "Space" || e.code === "ArrowUp") input(); });
    window.addEventListener("mousedown", input);
    canvas.addEventListener("touchstart", (e) => { e.preventDefault(); input(); });

    resetGame();
    draw();
</script>
</body>
</html>
