<MADE BY Anmol Singh>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Physics Learning Games</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background: linear-gradient(135deg, #1a2a6c, #b21f1f, #fdbb2d);
            color: #333;
            min-height: 100vh;
            padding: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background-color: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
            overflow: hidden;
            border: 2px solid rgba(255, 255, 255, 0.5);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
        }

        header {
            background: linear-gradient(90deg, #2c3e50, #4ca1af);
            color: white;
            padding: 30px 20px;
            text-align: center;
            position: relative;
        }

        h1 {
            font-size: 3rem;
            margin-bottom: 10px;
            font-weight: 700;
            letter-spacing: 1px;
        }

        .tagline {
            font-style: italic;
            margin-bottom: 15px;
            font-weight: 300;
        }
        
        .watermark {
            position: absolute;
            bottom: 10px;
            right: 15px;
            font-size: 0.8rem;
            color: rgba(255, 255, 255, 0.5);
            font-weight: 300;
        }

        nav {
            background-color: #34495e;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            border-bottom: 3px solid #1abc9c;
        }

        .nav-btn {
            background-color: transparent;
            color: white;
            border: none;
            padding: 18px 35px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease-in-out;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-weight: 600;
        }

        .nav-btn:hover {
            background-color: #2c3e50;
            transform: scale(1.05);
        }

        .nav-btn.active {
            background-color: #1abc9c;
            transform: scale(1.05);
            box-shadow: 0 0 15px rgba(26, 188, 156, 0.5);
        }

        .content-section {
            padding: 30px;
            min-height: 500px;
            display: none;
            opacity: 0;
            transition: opacity 0.5s ease-in-out;
        }

        .content-section.active {
            display: block;
            opacity: 1;
        }

        .welcome {
            text-align: center;
            margin-bottom: 30px;
        }

        .game-cards {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 30px;
        }

        .card {
            background: white;
            border-radius: 15px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
            width: 320px;
            padding: 30px;
            text-align: center;
            transition: transform 0.4s ease, box-shadow 0.4s ease;
            cursor: pointer;
            border: 1px solid #ddd;
        }

        .card:hover {
            transform: translateY(-15px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }

        .card h3 {
            color: #2c3e50;
            margin-bottom: 20px;
            font-size: 1.5rem;
            font-weight: 600;
        }

        .card p {
            margin-bottom: 25px;
            color: #7f8c8d;
            font-weight: 300;
        }

        .card .btn {
            background-color: #3498db;
            color: white;
            padding: 12px 25px;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            transition: background-color 0.3s, transform 0.3s;
            text-transform: uppercase;
            font-weight: 600;
            letter-spacing: 0.5px;
        }

        .card .btn:hover {
            background-color: #2980b9;
            transform: scale(1.05);
        }

        .quiz-container, .puzzle-container {
            max-width: 800px;
            margin: 0 auto;
            animation: fadeIn 0.8s ease-in-out;
        }

        .progress-container {
            background-color: #ecf0f1;
            border-radius: 10px;
            height: 25px;
            margin-bottom: 20px;
            overflow: hidden;
            box-shadow: inset 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .progress-bar {
            height: 100%;
            background: linear-gradient(90deg, #3498db, #2ecc71);
            width: 0%;
            transition: width 0.5s ease-out;
            border-radius: 10px;
        }

        .question-number, .puzzle-round {
            font-size: 1.3rem;
            color: #7f8c8d;
            margin-bottom: 10px;
            font-weight: 300;
        }

        .question, .puzzle-question {
            font-size: 1.8rem;
            margin-bottom: 25px;
            color: #2c3e50;
            font-weight: 600;
        }

        .options {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-bottom: 30px;
        }

        .option {
            background-color: #ecf0f1;
            padding: 20px;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: center;
            font-weight: 400;
            border: 2px solid transparent;
        }

        .option:hover {
            background-color: #bdc3c7;
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .option.selected {
            background-color: #3498db;
            color: white;
            border-color: #2980b9;
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(52, 152, 219, 0.4);
        }
        
        .option.correct {
            background-color: #2ecc71;
            color: white;
            border-color: #27ae60;
            animation: pulse 1s infinite;
        }

        .option.incorrect {
            background-color: #e74c3c;
            color: white;
            border-color: #c0392b;
        }

        .quiz-controls, .puzzle-controls {
            display: flex;
            justify-content: space-between;
        }

        .quiz-btn {
            padding: 12px 25px;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            font-size: 1rem;
            transition: background-color 0.3s, transform 0.3s;
            font-weight: 600;
            text-transform: uppercase;
        }

        .prev-btn {
            background-color: #95a5a6;
            color: white;
        }

        .prev-btn:hover {
            background-color: #7f8c8d;
            transform: scale(1.05);
        }

        .next-btn {
            background-color: #3498db;
            color: white;
        }

        .next-btn:hover {
            background-color: #2980b9;
            transform: scale(1.05);
        }

        .submit-btn {
            background-color: #2ecc71;
            color: white;
        }

        .submit-btn:hover {
            background-color: #27ae60;
            transform: scale(1.05);
        }

        .quiz-result, .puzzle-result {
            text-align: center;
            display: none;
            animation: fadeIn 0.8s ease-in-out;
        }

        .score {
            font-size: 2.5rem;
            margin-bottom: 25px;
            color: #2c3e50;
            font-weight: 700;
        }

        .puzzle-image {
            width: 100%;
            height: 300px;
            background-color: #ecf0f1;
            margin-bottom: 20px;
            border-radius: 15px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 1.2rem;
            color: #7f8c8d;
            overflow: hidden;
            border: 2px solid #bdc3c7;
        }

        .puzzle-image img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
        }

        .puzzle-answer {
            width: 100%;
            padding: 15px;
            font-size: 1.2rem;
            border: 2px solid #bdc3c7;
            border-radius: 8px;
            margin-bottom: 20px;
            transition: border-color 0.3s;
        }

        .puzzle-answer:focus {
            outline: none;
            border-color: #3498db;
        }

        .about-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .about-content p {
            margin-bottom: 20px;
            line-height: 1.8;
            color: #555;
        }

        .about-content ul {
            list-style: none;
            padding: 0;
        }
        
        .about-content li {
            background-color: #f0f4f7;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            transition: transform 0.3s;
        }

        .about-content li:hover {
            transform: translateX(10px);
        }

        .about-content li i {
            margin-right: 15px;
            color: #3498db;
            font-size: 1.2rem;
        }
        
        footer {
            text-align: center;
            padding: 20px;
            background-color: #34495e;
            color: white;
            font-weight: 300;
        }

        .hint {
            background-color: #f39c12;
            color: white;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 15px;
            display: none;
            font-weight: 400;
        }

        .toggle-hint {
            background: none;
            border: none;
            color: #3498db;
            cursor: pointer;
            margin-bottom: 15px;
            font-size: 1rem;
            font-weight: 600;
            transition: color 0.3s;
        }

        .toggle-hint:hover {
            color: #2980b9;
        }

        .timer {
            text-align: center;
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: #e74c3c;
            font-weight: 700;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
        }
        
        /* Animations */
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.03); }
            100% { transform: scale(1); }
        }

        @media (max-width: 768px) {
            .options {
                grid-template-columns: 1fr;
            }

            .game-cards {
                flex-direction: column;
                align-items: center;
            }

            .card {
                width: 100%;
                max-width: 300px;
            }

            .nav-btn {
                padding: 10px 15px;
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Physics Learning Games</h1>
            <p class="tagline">Learn physics through fun quizzes and puzzles!</p>
            <span class="watermark">ANMOL SINGH / rajput_anmolsingh3</span>
        </header>

        <nav>
            <button class="nav-btn active" data-target="home">Home</button>
            <button class="nav-btn" data-target="quiz">Physics Quiz</button>
            <button class="nav-btn" data-target="puzzle">Physics Puzzles</button>
            <button class="nav-btn" data-target="about">About</button>
        </nav>

        <main>
            <section id="home" class="content-section active">
                <div class="welcome">
                    <h2>Welcome to Physics Learning Games!</h2>
                    <p>Select a game to start learning physics in a fun way</p>
                </div>

                <div class="game-cards">
                    <div class="card" data-target="quiz">
                        <h3><i class="fas fa-question-circle"></i> Physics Quiz</h3>
                        <p>Test your knowledge with 100 physics questions covering various topics</p>
                        <button class="btn">Start Quiz</button>
                    </div>

                    <div class="card" data-target="puzzle">
                        <h3><i class="fas fa-puzzle-piece"></i> Physics Puzzles</h3>
                        <p>Solve 20 challenging physics puzzles to sharpen your problem-solving skills</p>
                        <button class="btn">Start Puzzles</button>
                    </div>
                </div>
            </section>

            <section id="quiz" class="content-section">
                <div class="quiz-container">
                    <div class="progress-container">
                        <div class="progress-bar" id="quiz-progress"></div>
                    </div>

                    <div class="timer" id="quiz-timer">Time: 00:00</div>

                    <div class="question-number" id="quiz-question-number">Question 1 of 100</div>
                    <div class="question" id="quiz-question">What is the SI unit of force?</div>

                    <div class="options" id="quiz-options">
                        <div class="option">Joule</div>
                        <div class="option">Watt</div>
                        <div class="option">Newton</div>
                        <div class="option">Pascal</div>
                    </div>

                    <button class="toggle-hint" id="quiz-hint-btn"><i class="fas fa-lightbulb"></i> Show Hint</button>
                    <div class="hint" id="quiz-hint">Force is measured in Newtons, named after Sir Isaac Newton.</div>

                    <div class="quiz-controls">
                        <button class="quiz-btn prev-btn" id="quiz-prev"><i class="fas fa-arrow-left"></i> Previous</button>
                        <button class="quiz-btn next-btn" id="quiz-next">Next <i class="fas fa-arrow-right"></i></button>
                    </div>
                </div>

                <div class="quiz-result" id="quiz-result">
                    <h2>Quiz Completed!</h2>
                    <div class="score" id="quiz-score">Your score: 0/100</div>
                    <button class="quiz-btn submit-btn" id="quiz-restart">Restart Quiz</button>
                </div>
            </section>

            <section id="puzzle" class="content-section">
                <div class="puzzle-container">
                    <div class="progress-container">
                        <div class="progress-bar" id="puzzle-progress"></div>
                    </div>

                    <div class="timer" id="puzzle-timer">Time: 00:00</div>

                    <div class="puzzle-round" id="puzzle-round">Puzzle 1 of 20</div>
                    <div class="puzzle-question" id="puzzle-question">A 5kg object is dropped from a height of 20m. What is its velocity just before it hits the ground? (Ignore air resistance)</div>

                    <div class="puzzle-image">
                        <img src="https://via.placeholder.com/600x300?text=Physics+Diagram" alt="Physics Puzzle Diagram">
                    </div>

                    <button class="toggle-hint" id="puzzle-hint-btn"><i class="fas fa-lightbulb"></i> Show Hint</button>
                    <div class="hint" id="puzzle-hint">Use the equation v² = u² + 2as, where u=0, a=9.8 m/s², s=20m</div>

                    <input type="text" class="puzzle-answer" id="puzzle-answer" placeholder="Enter your answer with units">

                    <div class="puzzle-controls">
                        <button class="quiz-btn prev-btn" id="puzzle-prev"><i class="fas fa-arrow-left"></i> Previous</button>
                        <button class="quiz-btn next-btn" id="puzzle-next">Check Answer <i class="fas fa-arrow-right"></i></button>
                    </div>
                </div>

                <div class="puzzle-result" id="puzzle-result">
                    <h2>Puzzles Completed!</h2>
                    <div class="score" id="puzzle-score">You solved 0 out of 20 puzzles</div>
                    <button class="quiz-btn submit-btn" id="puzzle-restart">Restart Puzzles</button>
                </div>
            </section>

            <section id="about" class="content-section">
                <div class="about-content">
                    <h2>About Physics Learning Games</h2>
                    <p>This website is designed to make learning physics fun and engaging through interactive quizzes and puzzles.</p>
                    <p>Our quiz contains 100 questions covering various physics topics including mechanics, thermodynamics, electromagnetism, and modern physics.</p>
                    <p>The puzzle section features 20 challenging problems that apply physics concepts to real-world scenarios, helping you develop problem-solving skills.</p>
                    <p>Whether you're a student looking to improve your physics knowledge or someone who just loves science, our games offer an enjoyable way to learn!</p>

                    <h3>Features</h3>
                    <ul>
                        <li><i class="fas fa-check-circle"></i> 100 carefully selected physics questions</li>
                        <li><i class="fas fa-check-circle"></i> 20 interactive physics puzzles</li>
                        <li><i class="fas fa-check-circle"></i> Helpful hints for each question and puzzle</li>
                        <li><i class="fas fa-check-circle"></i> Progress tracking</li>
                        <li><i class="fas fa-check-circle"></i> Timer to challenge yourself</li>
                        <li><i class="fas fa-check-circle"></i> Responsive design that works on all devices</li>
                    </ul>
                </div>
            </section>
        </main>

        <footer>
            <p>Physics Learning Games &copy; 2023 | Learn physics the fun way!</p>
        </footer>
    </div>

    <script>
        // Quiz data - 100 questions
        const quizQuestions = [
            { question: "What is the SI unit of force?", options: ["Joule", "Watt", "Newton", "Pascal"], correctAnswer: 2, hint: "Force is measured in Newtons, named after Sir Isaac Newton." },
            { question: "Which law states that for every action, there is an equal and opposite reaction?", options: ["Newton's First Law", "Newton's Second Law", "Newton's Third Law", "Law of Gravitation"], correctAnswer: 2, hint: "This is Newton's Third Law of Motion." },
            { question: "What is the acceleration due to gravity on Earth?", options: ["9.8 m/s²", "8.9 m/s²", "10 m/s²", "9.8 cm/s²"], correctAnswer: 0, hint: "The standard value is approximately 9.8 meters per second squared." },
            { question: "Which of the following is a vector quantity?", options: ["Mass", "Time", "Temperature", "Velocity"], correctAnswer: 3, hint: "Vector quantities have both magnitude and direction." },
            { question: "What is the formula for calculating work?", options: ["Force × Distance", "Mass × Acceleration", "Force × Velocity", "Mass × Velocity"], correctAnswer: 0, hint: "Work is defined as force applied over a distance." },
            { question: "Which type of energy is stored in a stretched spring?", options: ["Kinetic energy", "Thermal energy", "Potential energy", "Chemical energy"], correctAnswer: 2, hint: "This is elastic potential energy." },
            { question: "What does the Law of Conservation of Energy state?", options: ["Energy cannot be created", "Energy cannot be destroyed", "Energy cannot be created or destroyed", "Energy can be created but not destroyed"], correctAnswer: 2, hint: "Energy can only be transformed from one form to another." },
            { question: "Which color of light has the longest wavelength?", options: ["Violet", "Blue", "Green", "Red"], correctAnswer: 3, hint: "Red light has the longest wavelength in the visible spectrum." },
            { question: "What is the unit of electrical resistance?", options: ["Volt", "Ampere", "Ohm", "Watt"], correctAnswer: 2, hint: "Resistance is measured in Ohms, named after Georg Ohm." },
            { question: "Which subatomic particle has a negative charge?", options: ["Proton", "Neutron", "Electron", "Photon"], correctAnswer: 2, hint: "Electrons orbit the nucleus and have a negative charge." },
            { question: "What is the SI unit of power?", options: ["Joule", "Watt", "Newton", "Volt"], correctAnswer: 1, hint: "Power is the rate at which work is done, measured in Watts." },
            { question: "Which of the following is an example of kinetic energy?", options: ["A book on a shelf", "A stretched rubber band", "A moving car", "Water in a dam"], correctAnswer: 2, hint: "Kinetic energy is the energy of motion." },
            { question: "What is the law of universal gravitation?", options: ["F = ma", "E = mc²", "F = G(m1m2)/r²", "PV = nRT"], correctAnswer: 2, hint: "This law describes the attractive force between any two objects with mass." },
            { question: "What is the SI unit of temperature?", options: ["Fahrenheit", "Celsius", "Kelvin", "Rankine"], correctAnswer: 2, hint: "Kelvin is the absolute thermodynamic temperature scale." },
            { question: "Which state of matter has a fixed volume but no fixed shape?", options: ["Solid", "Liquid", "Gas", "Plasma"], correctAnswer: 1, hint: "Liquids take the shape of their container but have a constant volume." },
            { question: "What is the process by which a gas turns into a liquid?", options: ["Evaporation", "Sublimation", "Condensation", "Freezing"], correctAnswer: 2, hint: "Condensation is the reverse of evaporation." },
            { question: "Who is known as the 'father of modern physics'?", options: ["Isaac Newton", "Galileo Galilei", "Albert Einstein", "Stephen Hawking"], correctAnswer: 2, hint: "He developed the theory of relativity." },
            { question: "What is the speed of light in a vacuum?", options: ["3 x 10⁸ m/s", "343 m/s", "6.67 x 10⁻¹¹ N m²/kg²", "1.6 x 10⁻¹⁹ C"], correctAnswer: 0, hint: "This is one of the fundamental constants of the universe." },
            { question: "What is the principle of a simple pendulum?", options: ["F = ma", "Simple harmonic motion", "Conservation of energy", "All of the above"], correctAnswer: 1, hint: "The periodic motion of a pendulum is a classic example of this." },
            { question: "Which of the following is not a fundamental force of nature?", options: ["Strong nuclear force", "Electromagnetism", "Frictional force", "Gravity"], correctAnswer: 2, hint: "Friction is a result of electromagnetic forces at the molecular level." },
            { question: "What is the unit of electrical current?", options: ["Volt", "Ohm", "Ampere", "Watt"], correctAnswer: 2, hint: "Current is the flow of electric charge, measured in Amperes." },
            { question: "What is the phenomenon of a light ray bending when it passes from one medium to another?", options: ["Reflection", "Refraction", "Diffraction", "Interference"], correctAnswer: 1, hint: "Think about light passing from air to water." },
            { question: "What does E=mc² represent?", options: ["Kinetic Energy", "Potential Energy", "Mass-Energy Equivalence", "Ohm's Law"], correctAnswer: 2, hint: "This is a famous equation from Albert Einstein." },
            { question: "What is the formula for the period of a simple pendulum?", options: ["T = 2π√(l/g)", "T = 2π√(g/l)", "T = mgh", "T = ½mv²"], correctAnswer: 0, hint: "The period depends on the length and gravity." },
            { question: "What is the SI unit of pressure?", options: ["Pascal", "Newton", "Joule", "Watt"], correctAnswer: 0, hint: "Pressure is force per unit area." },
            { question: "What is the force of attraction between two masses?", options: ["Electric force", "Magnetic force", "Gravitational force", "Strong force"], correctAnswer: 2, hint: "This force governs the motion of planets and stars." },
            { question: "What is the principle behind a rocket's propulsion?", options: ["Newton's First Law", "Newton's Second Law", "Newton's Third Law", "Law of Conservation of Momentum"], correctAnswer: 2, hint: "For every action, there's an equal and opposite reaction." },
            { question: "Which of these is a scalar quantity?", options: ["Velocity", "Displacement", "Acceleration", "Speed"], correctAnswer: 3, hint: "Scalar quantities have only magnitude." },
            { question: "What is the unit of magnetic flux?", options: ["Tesla", "Weber", "Henry", "Faraday"], correctAnswer: 1, hint: "It is named after a German physicist." },
            { question: "What is the phenomenon of a sound wave bouncing off a surface?", options: ["Reflection", "Refraction", "Diffraction", "Interference"], correctAnswer: 0, hint: "Think of an echo." },
            { question: "What is the function of a transformer?", options: ["To convert AC to DC", "To step up or step down voltage", "To generate electricity", "To measure resistance"], correctAnswer: 1, hint: "It works on the principle of electromagnetic induction." },
            { question: "Which material is a good conductor of electricity?", options: ["Wood", "Glass", "Copper", "Rubber"], correctAnswer: 2, hint: "Metals are typically good conductors." },
            { question: "What is the formula for calculating electric power?", options: ["P = V × I", "P = V / I", "P = I / V", "P = R × I"], correctAnswer: 0, hint: "Power equals voltage times current." },
            { question: "What is the process of heat transfer through direct contact?", options: ["Convection", "Radiation", "Conduction", "Absorption"], correctAnswer: 2, hint: "Think of touching a hot stove." },
            { question: "What is the SI unit of electric charge?", options: ["Volt", "Ampere", "Ohm", "Coulomb"], correctAnswer: 3, hint: "It is named after Charles-Augustin de Coulomb." },
            { question: "What is the bending of light as it passes an obstacle?", options: ["Reflection", "Refraction", "Diffraction", "Scattering"], correctAnswer: 2, hint: "This phenomenon explains why shadows have fuzzy edges." },
            { question: "What is the formula for momentum?", options: ["p = m + v", "p = m × v", "p = m / v", "p = a × v"], correctAnswer: 1, hint: "Momentum is a product of mass and velocity." },
            { question: "Which type of heat transfer occurs in fluids (liquids and gases)?", options: ["Conduction", "Convection", "Radiation", "Insulation"], correctAnswer: 1, hint: "This process causes a hot air balloon to rise." },
            { question: "What is the SI unit of frequency?", options: ["Hertz", "Meter", "Second", "Watt"], correctAnswer: 0, hint: "It measures cycles per second." },
            { question: "What is the unit of energy?", options: ["Watt", "Newton", "Joule", "Pascal"], correctAnswer: 2, hint: "Energy is the capacity to do work." },
            { question: "What does Ohm's law state?", options: ["V = IR", "F = ma", "E = mc²", "P = VI"], correctAnswer: 0, hint: "This law relates voltage, current, and resistance." },
            { question: "What is the formula for the gravitational potential energy?", options: ["PE = ½mv²", "PE = mgh", "PE = VI", "PE = Fd"], correctAnswer: 1, hint: "It depends on mass, height, and gravity." },
            { question: "What is the SI unit of electric potential (voltage)?", options: ["Ampere", "Volt", "Ohm", "Watt"], correctAnswer: 1, hint: "Named after Alessandro Volta." },
            { question: "What is the temperature at which water boils at standard atmospheric pressure?", options: ["0°C", "50°C", "100°C", "212°C"], correctAnswer: 2, hint: "This is a common reference point for temperature." },
            { question: "What is the phenomenon of a sound source moving relative to an observer, causing a change in pitch?", options: ["Doppler effect", "Refraction", "Diffraction", "Supersonic boom"], correctAnswer: 0, hint: "This explains why a siren sounds different as it approaches and then passes you." },
            { question: "What does a seismograph measure?", options: ["Wind speed", "Rainfall", "Earthquakes", "Temperature"], correctAnswer: 2, hint: "Seismology is the study of seismic waves." },
            { question: "Which of these is the coldest possible temperature?", options: ["0°C", "-273.15 K", "0 K", "-459.67 °F"], correctAnswer: 2, hint: "This is known as absolute zero." },
            { question: "What is the half-life of a radioactive isotope?", options: ["The time it takes for half of the atoms to decay", "The time it takes for all of the atoms to decay", "The amount of energy released", "The mass of the isotope"], correctAnswer: 0, hint: "This is a measure of the stability of a nucleus." },
            { question: "Which part of the electromagnetic spectrum has the highest frequency?", options: ["Radio waves", "Visible light", "X-rays", "Gamma rays"], correctAnswer: 3, hint: "These are produced by the most energetic events in the universe." },
            { question: "What is the SI unit of luminous intensity?", options: ["Lumen", "Lux", "Candela", "Watt"], correctAnswer: 2, hint: "It measures the power emitted by a light source in a particular direction." },
            { question: "What is the relationship between frequency, wavelength, and speed of a wave?", options: ["v = fλ", "v = f/λ", "λ = vf", "f = vλ"], correctAnswer: 0, hint: "Speed equals frequency times wavelength." },
            { question: "What is the conservation of momentum?", options: ["In a closed system, total momentum is constant", "Momentum is always increasing", "Momentum is always decreasing", "Momentum is proportional to force"], correctAnswer: 0, hint: "This principle explains what happens in collisions." },
            { question: "What is the difference between a conductor and an insulator?", options: ["Conductors are shiny, insulators are not", "Conductors allow heat and electricity to flow, insulators don't", "Conductors are always solid, insulators are not", "Conductors are magnetic, insulators are not"], correctAnswer: 1, hint: "Think of copper wire versus rubber." },
            { question: "What is the unit of capacitance?", options: ["Farad", "Henry", "Tesla", "Ohm"], correctAnswer: 0, hint: "Named after Michael Faraday." },
            { question: "What is the purpose of a fuse in an electrical circuit?", options: ["To store energy", "To increase voltage", "To prevent overheating and fire", "To increase resistance"], correctAnswer: 2, hint: "It is a safety device." },
            { question: "What is the mass of a proton?", options: ["1.672 x 10⁻²⁷ kg", "9.11 x 10⁻³¹ kg", "1.674 x 10⁻²⁷ kg", "1.6 x 10⁻¹⁹ C"], correctAnswer: 0, hint: "It's slightly less than a neutron's mass." },
            { question: "What is the phenomenon where an object's mass appears to increase as its speed approaches the speed of light?", options: ["Doppler effect", "Time dilation", "Mass-energy equivalence", "Relativistic mass increase"], correctAnswer: 3, hint: "This is a consequence of Einstein's theory of relativity." },
            { question: "What is the SI unit of magnetic field strength?", options: ["Weber", "Tesla", "Henry", "Gauss"], correctAnswer: 1, hint: "Named after Nikola Tesla." },
            { question: "What is the buoyant force on a submerged object equal to?", options: ["The weight of the object", "The volume of the object", "The weight of the fluid displaced", "The pressure of the fluid"], correctAnswer: 2, hint: "This is Archimedes' Principle." },
            { question: "What is the formula for kinetic energy?", options: ["KE = mgh", "KE = ½mv²", "KE = Fd", "KE = qV"], correctAnswer: 1, hint: "It depends on mass and velocity squared." },
            { question: "Which of the following is not a form of electromagnetic radiation?", options: ["Gamma rays", "Sound waves", "Radio waves", "Infrared"], correctAnswer: 1, hint: "Sound waves are mechanical waves, not electromagnetic." },
            { question: "What is the process of generating an electric current in a conductor by a changing magnetic field?", options: ["Electrostatics", "Electromagnetic induction", "Photoelectric effect", "Ohm's law"], correctAnswer: 1, hint: "This principle is used in generators and transformers." },
            { question: "What is the SI unit of momentum?", options: ["N⋅s", "J", "W", "kg⋅m/s"], correctAnswer: 3, hint: "Momentum is mass times velocity." },
            { question: "What is the conservation of energy?", options: ["Energy can be created but not destroyed", "Energy can be destroyed but not created", "Energy is always conserved in a closed system", "Energy is always lost as heat"], correctAnswer: 2, hint: "Total energy remains constant." },
            { question: "What is the SI unit of heat energy?", options: ["Calorie", "Joule", "Watt", "Celsius"], correctAnswer: 1, hint: "Heat is a form of energy." },
            { question: "What is the phenomenon of a particle or wave bouncing back from a surface?", options: ["Refraction", "Reflection", "Diffraction", "Absorption"], correctAnswer: 1, hint: "Think of a mirror." },
            { question: "What is a projectile?", options: ["An object that falls straight down", "An object moving under the influence of gravity only", "An object on a ramp", "An object moving at a constant speed"], correctAnswer: 1, hint: "The motion of a thrown ball is a classic example." },
            { question: "What is the SI unit of angular velocity?", options: ["m/s", "rad/s", "Hz", "m"], correctAnswer: 1, hint: "It measures the rate of rotation." },
            { question: "What is the formula for centripetal force?", options: ["F = mv", "F = ma", "F = mv²/r", "F = mgh"], correctAnswer: 2, hint: "This force keeps an object moving in a circle." },
            { question: "Which of the following describes a black body?", options: ["A body that absorbs all radiation", "A body that reflects all radiation", "A body that only emits visible light", "A body that is always black"], correctAnswer: 0, hint: "It is a theoretical object used in thermodynamics." },
            { question: "What is the primary function of a solar cell?", options: ["To generate heat", "To convert light energy to electrical energy", "To store energy", "To produce light"], correctAnswer: 1, hint: "It works on the photoelectric effect." },
            { question: "What is the SI unit of viscosity?", options: ["Pascal-second", "Newton", "Joule", "Watt"], correctAnswer: 0, hint: "It measures a fluid's resistance to flow." },
            { question: "What is the relationship between heat and temperature?", options: ["They are the same thing", "Temperature is a measure of average kinetic energy, heat is energy transfer", "Heat is a measure of average kinetic energy, temperature is energy transfer", "They are unrelated"], correctAnswer: 1, hint: "A cup of coffee has a high temperature, but a swimming pool has more heat." },
            { question: "What is a simple machine?", options: ["A complex device", "A device that makes work easier", "A device that creates energy", "A device with no moving parts"], correctAnswer: 1, hint: "Levers, pulleys, and inclined planes are examples." },
            { question: "What is the SI unit of magnetic flux density?", options: ["Weber", "Tesla", "Henry", "Farad"], correctAnswer: 1, hint: "Often referred to as magnetic field strength." },
            { question: "What is the law of refraction also known as?", options: ["Newton's Law", "Snell's Law", "Hooke's Law", "Ohm's Law"], correctAnswer: 1, hint: "It is named after Willebrord Snellius." },
            { question: "What is the mass of an electron?", options: ["1.672 x 10⁻²⁷ kg", "9.11 x 10⁻³¹ kg", "1.674 x 10⁻²⁷ kg", "1.6 x 10⁻¹⁹ C"], correctAnswer: 1, hint: "It is much lighter than a proton or neutron." },
            { question: "Which of the following is an example of an insulator?", options: ["Silver", "Copper", "Aluminum", "Glass"], correctAnswer: 3, hint: "Insulators do not conduct electricity well." },
            { question: "What is the photoelectric effect?", options: ["The emission of electrons when light hits a material", "The bending of light", "The reflection of light", "The creation of light from electricity"], correctAnswer: 0, hint: "Einstein's work on this earned him the Nobel Prize." },
            { question: "What is the SI unit of electric field strength?", options: ["Volt", "Newton", "Newton per Coulomb", "Joule"], correctAnswer: 2, hint: "It is force per unit charge." },
            { question: "What is the principle behind a hydraulic press?", options: ["Bernoulli's Principle", "Pascal's Principle", "Archimedes' Principle", "Newton's Laws"], correctAnswer: 1, hint: "Pressure applied to an enclosed fluid is transmitted equally throughout." },
            { question: "What is a semiconductor?", options: ["A material that conducts electricity perfectly", "A material that does not conduct electricity", "A material that conducts electricity under certain conditions", "A material that is always magnetic"], correctAnswer: 2, hint: "Silicon and germanium are common examples." },
            { question: "What is the SI unit of inductance?", options: ["Farad", "Henry", "Weber", "Tesla"], correctAnswer: 1, hint: "It is named after Joseph Henry." },
            { question: "What is the conservation of mechanical energy?", options: ["Total mechanical energy is always lost", "Potential energy is always converted to kinetic energy", "In a system with no friction, total mechanical energy is constant", "Mechanical energy cannot be created or destroyed"], correctAnswer: 2, hint: "This applies to systems where non-conservative forces like friction are negligible." },
            { question: "Which of the following is a physical quantity that measures the rotational inertia of a body?", options: ["Torque", "Angular momentum", "Moment of inertia", "Angular acceleration"], correctAnswer: 2, hint: "It is the rotational analog of mass." },
            { question: "What is a photon?", options: ["A particle with mass", "A quantum of light or other electromagnetic radiation", "A negatively charged particle", "A positively charged particle"], correctAnswer: 1, hint: "It has no mass and travels at the speed of light." },
            { question: "What is the formula for calculating torque?", options: ["τ = F/r", "τ = Fr", "τ = Fd", "τ = ma"], correctAnswer: 1, hint: "Torque is a rotational force." },
            { question: "What is the principle of superposition?", options: ["Two waves can't occupy the same space", "When two waves meet, their amplitudes add up", "Waves always cancel each other out", "Waves travel in a straight line"], correctAnswer: 1, hint: "This explains interference and standing waves." },
            { question: "What is the SI unit of sound intensity?", options: ["Decibel", "Hertz", "Watt", "Joule"], correctAnswer: 0, hint: "It is a logarithmic scale." },
            { question: "Which force is responsible for holding the nucleus of an atom together?", options: ["Strong nuclear force", "Weak nuclear force", "Electromagnetic force", "Gravitational force"], correctAnswer: 0, hint: "It is the strongest of the four fundamental forces." },
            { question: "What is the SI unit of specific heat capacity?", options: ["J/kg", "J/(kg·K)", "J/K", "J·K"], correctAnswer: 1, hint: "It measures the energy required to raise a unit of mass by one degree." },
            { question: "What is the process of a solid turning directly into a gas?", options: ["Evaporation", "Melting", "Sublimation", "Condensation"], correctAnswer: 2, hint: "Dry ice is a classic example of this." },
            { question: "Which law relates the pressure and volume of a gas at a constant temperature?", options: ["Charles's Law", "Boyle's Law", "Gay-Lussac's Law", "Avogadro's Law"], correctAnswer: 1, hint: "P₁V₁ = P₂V₂" },
            { question: "What is the main difference between nuclear fission and fusion?", options: ["Fission is splitting atoms, fusion is combining them", "Fusion is splitting atoms, fission is combining them", "Fission uses heat, fusion uses light", "Fission is a natural process, fusion is not"], correctAnswer: 0, hint: "Fission is used in nuclear power plants, fusion powers the sun." },
            { question: "What is the SI unit of electric flux?", options: ["N·m²/C", "V·m", "V/m", "C/m²"], correctAnswer: 1, hint: "It is a measure of the electric field passing through a surface." },
            { question: "What is the principle that explains why objects float in water?", options: ["Newton's Law", "Archimedes' Principle", "Pascal's Principle", "Bernoulli's Principle"], correctAnswer: 1, hint: "The buoyant force is key." },
            { question: "What is the formula for the electrical potential energy of a charge in an electric field?", options: ["PE = qV", "PE = ½mv²", "PE = mgh", "PE = Fd"], correctAnswer: 0, hint: "It depends on the charge and the electric potential." },
            { question: "What is a cyclotron?", options: ["A type of vacuum cleaner", "A particle accelerator", "A form of a bicycle", "A type of circuit"], correctAnswer: 1, hint: "It uses a magnetic field to accelerate charged particles." },
            { question: "Which of these is the SI unit of torque?", options: ["Newton", "Joule", "Newton-meter", "Watt"], correctAnswer: 2, hint: "Torque is a rotational force." },
            { question: "What is the Doppler effect for light?", options: ["A change in brightness", "A change in color (redshift/blueshift)", "A change in speed", "A change in reflection"], correctAnswer: 1, hint: "This is used by astronomers to determine if galaxies are moving toward or away from us." },
            { question: "What is the formula for the period of a wave?", options: ["T = f", "T = 1/f", "T = v/λ", "T = vλ"], correctAnswer: 1, hint: "Period is the reciprocal of frequency." },
            { question: "What is the formula for pressure?", options: ["P = V/I", "P = F/A", "P = ma", "P = Fd"], correctAnswer: 1, hint: "Pressure is force divided by area." },
            { question: "What is the unit of electric current?", options: ["Ohm", "Ampere", "Volt", "Watt"], correctAnswer: 1, hint: "Named after André-Marie Ampère." },
            { question: "What is the law of reflection?", options: ["The angle of incidence equals the angle of refraction", "Light always travels in a straight line", "The angle of incidence equals the angle of reflection", "Light always disperses"], correctAnswer: 2, hint: "This is why mirrors work." },
            { question: "What is the principle behind a generator?", options: ["Ohm's Law", "Pascal's Principle", "Electromagnetic induction", "Conservation of momentum"], correctAnswer: 2, hint: "It converts mechanical energy into electrical energy." },
            { question: "What is a superconductor?", options: ["A material with high resistance", "A material with zero electrical resistance below a certain temperature", "A material that is highly magnetic", "A material that conducts heat well"], correctAnswer: 1, hint: "This phenomenon has applications in MRI machines." },
            { question: "What is the SI unit of heat capacity?", options: ["Joule", "Watt", "Joule per Kelvin", "Calorie"], correctAnswer: 2, hint: "It measures the amount of heat needed to raise the temperature of a body by one degree." },
            { question: "What is the purpose of a capacitor in a circuit?", options: ["To store electrical energy", "To increase current", "To decrease voltage", "To generate power"], correctAnswer: 0, hint: "It's like a battery that can be charged and discharged quickly." },
            { question: "What is the conservation of angular momentum?", options: ["In a closed system, angular momentum is constant", "Angular momentum is always increasing", "Angular momentum is always decreasing", "Angular momentum is proportional to force"], correctAnswer: 0, hint: "This is why a spinning ice skater speeds up when they pull their arms in." },
            { question: "What is the name for the amount of heat needed to change a liquid to a gas at a constant temperature?", options: ["Specific heat", "Latent heat of fusion", "Latent heat of vaporization", "Heat of combustion"], correctAnswer: 2, hint: "This is why steam burns are so severe." },
            { question: "What is a transformer?", options: ["A device that converts AC to DC", "A device that changes the voltage of an AC current", "A device that converts light to electricity", "A type of battery"], correctAnswer: 1, hint: "They are essential for power grids." },
            { question: "What is the SI unit of power?", options: ["Joule per second", "Newton", "Pascal", "Volt"], correctAnswer: 0, hint: "Power is the rate of doing work." },
            { question: "What is the formula for the force of friction?", options: ["F_friction = μN", "F_friction = ma", "F_friction = mg", "F_friction = Fd"], correctAnswer: 0, hint: "It depends on the coefficient of friction and the normal force." },
            { question: "What is a black hole?", options: ["A very dense star", "A region of spacetime where gravity is so strong that nothing, not even light, can escape", "A type of supernova", "A galaxy with no stars"], correctAnswer: 1, hint: "Its existence is predicted by general relativity." },
            { question: "What is the SI unit of magnetic field strength?", options: ["Weber", "Tesla", "Henry", "Farad"], correctAnswer: 1, hint: "Named after Nikola Tesla." },
            { question: "What is the formula for the period of a spring's oscillation?", options: ["T = 2π√(k/m)", "T = 2π√(m/k)", "T = 2π√(l/g)", "T = ½mv²"], correctAnswer: 1, hint: "It depends on the mass and the spring constant." },
            { question: "What is the function of a resistor in an electrical circuit?", options: ["To increase current", "To decrease current and dissipate energy", "To store energy", "To generate power"], correctAnswer: 1, hint: "It resists the flow of electrons." },
            { question: "What is the law that describes the force between two charged objects?", options: ["Newton's Law", "Ohm's Law", "Coulomb's Law", "Faraday's Law"], correctAnswer: 2, hint: "This law is analogous to the law of universal gravitation." }
        ];

        // Puzzle data - 20 puzzles
        const puzzleQuestions = [
            { question: "A 5kg object is dropped from a height of 20m. What is its velocity just before it hits the ground? (Ignore air resistance)", answer: "20 m/s", hint: "Use the equation v² = u² + 2as, where u=0, a=9.8 m/s², s=20m" },
            { question: "If a car accelerates from 0 to 60 km/h in 10 seconds, what is its acceleration in m/s²?", answer: "1.67 m/s²", hint: "First convert km/h to m/s, then use a = (v-u)/t" },
            { question: "A force of 20N is applied to an object causing it to accelerate at 5 m/s². What is the mass of the object?", answer: "4 kg", hint: "Use Newton's second law: F = m × a" },
            { question: "How much work is done when a 10N force moves an object 5m in the direction of the force?", answer: "50 J", hint: "Work = Force × Distance" },
            { question: "What is the kinetic energy of a 2kg object moving at 3m/s?", answer: "9 J", hint: "Kinetic energy = ½ × m × v²" },
            { question: "A 100W light bulb is left on for 5 hours. How much energy in Joules did it consume?", answer: "1.8 x 10^6 J", hint: "Energy = Power × Time. Convert hours to seconds." },
            { question: "An object with a mass of 10kg is at a height of 5m. What is its gravitational potential energy?", answer: "490 J", hint: "PE = mgh. Use g = 9.8 m/s²." },
            { question: "A current of 2A flows through a resistor with a resistance of 10Ω. What is the voltage across the resistor?", answer: "20 V", hint: "Use Ohm's Law: V = IR." },
            { question: "What is the frequency of a wave with a speed of 300 m/s and a wavelength of 3m?", answer: "100 Hz", hint: "Use the wave equation: v = fλ." },
            { question: "A 20kg block is pushed across a floor with a force of 50N. The coefficient of friction is 0.2. What is the net force on the block?", answer: "30.4 N", hint: "Net Force = Applied Force - Frictional Force. F_friction = μN = μmg." },
            { question: "How much power is required to lift a 50kg object to a height of 10m in 5 seconds?", answer: "980 W", hint: "Power = Work / Time. Work = mgh." },
            { question: "A car traveling at 20 m/s slams on its brakes and stops in 4 seconds. What is its acceleration?", answer: "-5 m/s²", hint: "a = (v_f - v_i) / t. The final velocity is 0." },
            { question: "What is the momentum of a 5kg object moving at 10 m/s?", answer: "50 kg⋅m/s", hint: "Momentum = mass × velocity." },
            { question: "An object has a volume of 0.5 m³ and is fully submerged in water. What is the buoyant force on the object? (Density of water = 1000 kg/m³)", answer: "4900 N", hint: "Buoyant force = Weight of displaced fluid = ρVg." },
            { question: "A sound wave has a frequency of 500 Hz. If its speed is 343 m/s, what is its wavelength?", answer: "0.686 m", hint: "λ = v/f." },
            { question: "If the temperature of 2kg of water is raised by 5°C, how much heat energy is added? (Specific heat of water = 4186 J/kg°C)", answer: "41860 J", hint: "Q = mcΔT." },
            { question: "A car of mass 1500 kg moving at 10 m/s collides with a stationary car of mass 1000 kg. If they stick together, what is their final velocity?", answer: "6 m/s", hint: "Use conservation of momentum: m₁v₁ = (m₁ + m₂)v_f." },
            { question: "What is the electric force between two charges of +1C each, separated by 1m? (k = 9 x 10⁹ N⋅m²/C²)", answer: "9 x 10^9 N", hint: "Use Coulomb's Law: F = k(q₁q₂)/r²." },
            { question: "An object is launched at 30 m/s at an angle of 30 degrees to the horizontal. What is its initial vertical velocity?", answer: "15 m/s", hint: "Use trigonometry: v_y = v_initial × sin(θ)." },
            { question: "A transformer has 100 turns in the primary coil and 200 turns in the secondary coil. If the input voltage is 120V, what is the output voltage?", answer: "240 V", hint: "V_s / V_p = N_s / N_p." }
        ];

        // General functionality
        const sections = document.querySelectorAll('.content-section');
        const navButtons = document.querySelectorAll('.nav-btn');
        const cardButtons = document.querySelectorAll('.card');

        function switchSection(targetId) {
            sections.forEach(section => {
                section.classList.remove('active');
            });
            document.getElementById(targetId).classList.add('active');
            
            navButtons.forEach(btn => {
                btn.classList.remove('active');
            });
            document.querySelector(`.nav-btn[data-target="${targetId}"]`).classList.add('active');

            // Reset timers when switching sections
            clearInterval(quizTimer);
            clearInterval(puzzleTimer);
            if (targetId === 'quiz') startQuiz();
            if (targetId === 'puzzle') startPuzzle();
        }
        
        navButtons.forEach(btn => {
            btn.addEventListener('click', () => switchSection(btn.dataset.target));
        });

        cardButtons.forEach(card => {
            card.addEventListener('click', () => switchSection(card.dataset.target));
        });

        // Quiz functionality
        let currentQuizQuestion = 0;
        let quizScore = 0;
        let quizTime = 0;
        let quizTimer;
        let quizAnswered = false;

        const quizQuestionElement = document.getElementById('quiz-question');
        const quizQuestionNumberElement = document.getElementById('quiz-question-number');
        const quizOptionsElement = document.getElementById('quiz-options');
        const quizProgressElement = document.getElementById('quiz-progress');
        const quizScoreElement = document.getElementById('quiz-score');
        const quizResultElement = document.getElementById('quiz-result');
        const quizContainerElement = document.querySelector('.quiz-container');
        const quizHintElement = document.getElementById('quiz-hint');
        const quizHintBtnElement = document.getElementById('quiz-hint-btn');
        const quizTimerElement = document.getElementById('quiz-timer');
        const quizNextBtn = document.getElementById('quiz-next');
        const quizPrevBtn = document.getElementById('quiz-prev');

        function startQuiz() {
            currentQuizQuestion = 0;
            quizScore = 0;
            quizTime = 0;
            quizAnswered = false;
            displayQuizQuestion();
            startQuizTimer();
            quizPrevBtn.style.visibility = 'hidden';
            quizNextBtn.textContent = 'Next';
            quizContainerElement.style.display = 'block';
            quizResultElement.style.display = 'none';
        }

        function displayQuizQuestion() {
            const question = quizQuestions[currentQuizQuestion];
            quizQuestionNumberElement.textContent = `Question ${currentQuizQuestion + 1} of ${quizQuestions.length}`;
            quizQuestionElement.textContent = question.question;
            quizProgressElement.style.width = `${((currentQuizQuestion + 1) / quizQuestions.length) * 100}%`;

            quizOptionsElement.innerHTML = '';
            question.options.forEach((option, index) => {
                const optionElement = document.createElement('div');
                optionElement.classList.add('option');
                optionElement.textContent = option;
                optionElement.addEventListener('click', () => selectQuizOption(index));
                quizOptionsElement.appendChild(optionElement);
            });
            
            quizAnswered = false;
            quizNextBtn.textContent = 'Next';
            quizHintElement.style.display = 'none';
            quizHintBtnElement.textContent = 'Show Hint';
            
            if (currentQuizQuestion === 0) {
                quizPrevBtn.style.visibility = 'hidden';
            } else {
                quizPrevBtn.style.visibility = 'visible';
            }
        }

        function selectQuizOption(index) {
            if (quizAnswered) return;

            const options = document.querySelectorAll('.quiz-container .option');
            options.forEach((option, i) => {
                option.classList.remove('selected');
                if (i === index) {
                    option.classList.add('selected');
                }
            });
        }

        function checkAndProceedQuiz() {
            const selectedOption = document.querySelector('.quiz-container .option.selected');
            if (!selectedOption) {
                alert('Please select an answer');
                return;
            }

            if (!quizAnswered) {
                const selectedIndex = Array.from(selectedOption.parentNode.children).indexOf(selectedOption);
                const question = quizQuestions[currentQuizQuestion];
                const options = document.querySelectorAll('.quiz-container .option');

                if (selectedIndex === question.correctAnswer) {
                    quizScore++;
                    selectedOption.classList.add('correct');
                } else {
                    selectedOption.classList.add('incorrect');
                    options[question.correctAnswer].classList.add('correct');
                }
                quizAnswered = true;
                quizNextBtn.textContent = 'Continue';
            } else {
                currentQuizQuestion++;
                if (currentQuizQuestion < quizQuestions.length) {
                    displayQuizQuestion();
                } else {
                    finishQuiz();
                }
            }
        }

        function prevQuizQuestion() {
            if (currentQuizQuestion > 0) {
                currentQuizQuestion--;
                displayQuizQuestion();
            }
        }

        function finishQuiz() {
            clearInterval(quizTimer);
            quizContainerElement.style.display = 'none';
            quizResultElement.style.display = 'block';
            quizScoreElement.textContent = `Your score: ${quizScore}/${quizQuestions.length}`;
        }

        function toggleQuizHint() {
            if (quizHintElement.style.display === 'block') {
                quizHintElement.style.display = 'none';
                quizHintBtnElement.textContent = 'Show Hint';
            } else {
                quizHintElement.textContent = quizQuestions[currentQuizQuestion].hint;
                quizHintElement.style.display = 'block';
                quizHintBtnElement.textContent = 'Hide Hint';
            }
        }

        function startQuizTimer() {
            clearInterval(quizTimer);
            quizTime = 0;
            updateQuizTimer();
            quizTimer = setInterval(() => {
                quizTime++;
                updateQuizTimer();
            }, 1000);
        }

        function updateQuizTimer() {
            const minutes = Math.floor(quizTime / 60);
            const seconds = quizTime % 60;
            quizTimerElement.textContent = `Time: ${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
        }

        // Puzzle functionality
        let currentPuzzle = 0;
        let puzzleScore = 0;
        let puzzleTime = 0;
        let puzzleTimer;

        const puzzleQuestionElement = document.getElementById('puzzle-question');
        const puzzleRoundElement = document.getElementById('puzzle-round');
        const puzzleAnswerElement = document.getElementById('puzzle-answer');
        const puzzleProgressElement = document.getElementById('puzzle-progress');
        const puzzleScoreElement = document.getElementById('puzzle-score');
        const puzzleResultElement = document.getElementById('puzzle-result');
        const puzzleContainerElement = document.querySelector('.puzzle-container');
        const puzzleHintElement = document.getElementById('puzzle-hint');
        const puzzleHintBtnElement = document.getElementById('puzzle-hint-btn');
        const puzzleTimerElement = document.getElementById('puzzle-timer');
        const puzzlePrevBtn = document.getElementById('puzzle-prev');
        const puzzleNextBtn = document.getElementById('puzzle-next');

        function startPuzzle() {
            currentPuzzle = 0;
            puzzleScore = 0;
            puzzleTime = 0;
            displayPuzzle();
            startPuzzleTimer();
            puzzlePrevBtn.style.visibility = 'hidden';
            puzzleNextBtn.textContent = 'Check Answer';
            puzzleContainerElement.style.display = 'block';
            puzzleResultElement.style.display = 'none';
        }

        function displayPuzzle() {
            const puzzle = puzzleQuestions[currentPuzzle];
            puzzleRoundElement.textContent = `Puzzle ${currentPuzzle + 1} of ${puzzleQuestions.length}`;
            puzzleQuestionElement.textContent = puzzle.question;
            puzzleProgressElement.style.width = `${((currentPuzzle + 1) / puzzleQuestions.length) * 100}%`;
            puzzleAnswerElement.value = '';
            
            puzzleHintElement.style.display = 'none';
            puzzleHintBtnElement.textContent = 'Show Hint';
            
            if (currentPuzzle === 0) {
                puzzlePrevBtn.style.visibility = 'hidden';
            } else {
                puzzlePrevBtn.style.visibility = 'visible';
            }
        }

        function checkPuzzleAnswer() {
            const userAnswer = puzzleAnswerElement.value.trim();
            if (!userAnswer) {
                alert('Please enter your answer');
                return;
            }
            
            const correctAnswer = puzzleQuestions[currentPuzzle].answer.toLowerCase();
            const isCorrect = userAnswer.toLowerCase() === correctAnswer;

            if (isCorrect) {
                alert('Correct answer! ✅');
                puzzleScore++;
            } else {
                alert(`Incorrect answer. The correct answer is: ${puzzleQuestions[currentPuzzle].answer} ❌`);
            }
            
            currentPuzzle++;
            if (currentPuzzle < puzzleQuestions.length) {
                displayPuzzle();
            } else {
                finishPuzzle();
            }
        }
        
        function prevPuzzle() {
            if (currentPuzzle > 0) {
                currentPuzzle--;
                displayPuzzle();
            }
        }

        function finishPuzzle() {
            clearInterval(puzzleTimer);
            puzzleContainerElement.style.display = 'none';
            puzzleResultElement.style.display = 'block';
            puzzleScoreElement.textContent = `You solved ${puzzleScore} out of ${puzzleQuestions.length} puzzles`;
        }

        function togglePuzzleHint() {
            if (puzzleHintElement.style.display === 'block') {
                puzzleHintElement.style.display = 'none';
                puzzleHintBtnElement.textContent = 'Show Hint';
            } else {
                puzzleHintElement.textContent = puzzleQuestions[currentPuzzle].hint;
                puzzleHintElement.style.display = 'block';
                puzzleHintBtnElement.textContent = 'Hide Hint';
            }
        }

        function startPuzzleTimer() {
            clearInterval(puzzleTimer);
            puzzleTime = 0;
            updatePuzzleTimer();
            puzzleTimer = setInterval(() => {
                puzzleTime++;
                updatePuzzleTimer();
            }, 1000);
        }

        function updatePuzzleTimer() {
            const minutes = Math.floor(puzzleTime / 60);
            const seconds = puzzleTime % 60;
            puzzleTimerElement.textContent = `Time: ${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
        }

        // Event listeners
        document.getElementById('quiz-next').addEventListener('click', checkAndProceedQuiz);
        document.getElementById('quiz-prev').addEventListener('click', prevQuizQuestion);
        document.getElementById('quiz-restart').addEventListener('click', startQuiz);
        document.getElementById('quiz-hint-btn').addEventListener('click', toggleQuizHint);

        document.getElementById('puzzle-next').addEventListener('click', checkPuzzleAnswer);
        document.getElementById('puzzle-prev').addEventListener('click', prevPuzzle);
        document.getElementById('puzzle-restart').addEventListener('click', startPuzzle);
        document.getElementById('puzzle-hint-btn').addEventListener('click', togglePuzzleHint);

        // Initial setup
        startQuiz();
        startPuzzle();
        // Hide puzzle section initially
        document.getElementById('puzzle').classList.remove('active');
        document.getElementById('quiz').classList.remove('active');
    </script>
</body>
</html>
