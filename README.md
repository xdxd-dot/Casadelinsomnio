<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Casa del Horror - Fantasmas Reales</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Creepster&family=Inter:wght@400;700&display=swap');

        body {
            font-family: 'Inter', sans-serif;
            background-color: #0d0d0d; /* Dark background for horror atmosphere */
            color: #f0f0f0; /* Light text */
            overflow-x: hidden; /* Prevent horizontal scroll */
        }

        .creepster-font {
            font-family: 'Creepster', cursive;
        }

        .haunted-gradient {
            background: linear-gradient(180deg, rgba(0,0,0,1) 0%, rgba(20,0,0,1) 50%, rgba(0,0,0,1) 100%);
        }

        .shudder {
            animation: shudder 0.5s infinite alternate;
        }

        @keyframes shudder {
            0% { transform: translate(1px, 1px); }
            25% { transform: translate(-1px, -2px); }
            50% { transform: translate(-3px, 0px); }
            75% { transform: translate(3px, 2px); }
            100% { transform: translate(1px, -1px); }
        }

        .pulse-red {
            animation: pulse-red 2s infinite ease-in-out;
        }

        @keyframes pulse-red {
            0%, 100% { filter: brightness(1); }
            50% { filter: brightness(1.5); }
        }

        .ghost-appear {
            animation: ghost-appear 3s forwards;
            opacity: 0;
            transform: translateY(50px);
        }

        @keyframes ghost-appear {
            0% { opacity: 0; transform: translateY(50px); }
            50% { opacity: 0.7; transform: translateY(-10px); }
            100% { opacity: 0.5; transform: translateY(0); }
        }

        .button-glow {
            box-shadow: 0 0 10px rgba(255, 0, 0, 0.7), 0 0 20px rgba(255, 0, 0, 0.4), 0 0 30px rgba(255, 0, 0, 0.2);
            transition: all 0.3s ease;
        }
        .button-glow:hover {
            box-shadow: 0 0 15px rgba(255, 0, 0, 1), 0 0 30px rgba(255, 0, 0, 0.6), 0 0 45px rgba(255, 0, 0, 0.3);
            transform: scale(1.05);
        }

        /* Styles for the exploration section */
        .room-description {
            min-height: 150px; /* Ensure the container has height */
        }

        .ghost-figure {
            font-size: 5rem; /* Large size for ghosts */
            display: inline-block;
            margin: 0 1rem;
        }
        .ghost-charlotte {
            color: #b0c4de; /* Light ghostly blue */
            animation: float-charlotte 4s infinite ease-in-out alternate;
        }
        .ghost-stephen {
            color: #8b0000; /* Dark ghostly red */
            animation: float-stephen 4s infinite ease-in-out alternate-reverse;
        }

        @keyframes float-charlotte {
            0% { transform: translateY(0) rotate(-2deg); opacity: 0.6; }
            50% { transform: translateY(-10px) rotate(2deg); opacity: 0.8; }
            100% { transform: translateY(0) rotate(-2deg); opacity: 0.6; }
        }

        @keyframes float-stephen {
            0% { transform: translateY(0) rotate(3deg); opacity: 0.7; }
            50% { transform: translateY(10px) rotate(-3deg); opacity: 0.5; }
            100% { transform: translateY(0) rotate(3deg); opacity: 0.7; }
        }
    </style>
</head>
<body class="haunted-gradient min-h-screen flex flex-col items-center justify-center p-4">

    <!-- Header -->
    <header class="text-center mb-8">
        <h1 class="creepster-font text-6xl md:text-8xl text-red-700 shudder mb-4">La Mansión del Lamento</h1>
        <p class="text-lg md:text-xl text-gray-300">Donde los muertos no descansan y los secretos no mueren...</p>
    </header>

    <!-- Main Content -->
    <main class="w-full max-w-4xl bg-gray-900 rounded-lg shadow-lg overflow-hidden border border-gray-700 relative">
        <!-- Main house image, inspired by your references -->
        <div class="relative w-full h-80 md:h-96">
            <img src="https://placehold.co/1200x500/1a1a1a/e0e0e0?text=Hawton+Mere"
                 alt="Hawton Mere"
                 onerror="this.onerror=null;this.src='https://placehold.co/1200x500/1a1a1a/e0e0e0?text=Hawton+Mere';"
                 class="w-full h-full object-cover rounded-t-lg opacity-80">
            <!-- Overlay details for horror atmosphere -->
            <div class="absolute inset-0 bg-black bg-opacity-50 flex items-center justify-center">
                <div class="text-center">
                    <span class="text-5xl md:text-7xl text-red-500 creepy-effect">👁️</span>
                    <p class="text-white text-lg mt-2 creepy-effect">El ojo que todo lo ve...</p>
                </div>
            </div>
            <!-- Windows with red glow effect, inspired by the first image -->
            <div class="absolute top-1/3 left-1/4 w-8 h-10 bg-red-800 rounded-sm pulse-red hidden md:block"></div>
            <div class="absolute top-1/3 right-1/4 w-8 h-10 bg-red-800 rounded-sm pulse-red hidden md:block"></div>
            <div class="absolute top-1/2 left-1/3 w-10 h-12 bg-red-800 rounded-sm pulse-red hidden md:block"></div>
            <div class="absolute top-1/2 right-1/3 w-10 h-12 bg-red-800 rounded-sm pulse-red hidden md:block"></div>
        </div>

        <!-- Story or Description Section with Challenge -->
        <section class="p-6 md:p-8">
            <h2 class="text-3xl md:text-4xl creepster-font text-red-600 mb-4">Bienvenidos a la Oscuridad...</h2>
            <p class="text-gray-400 leading-relaxed mb-6">
                Desde el momento de la llegada, Hawton Mere se revela. Tras cruzar el puente que atraviesa el foso, una sola luz brillaba en la oscuridad de las altas paredes y un destello dorado se reflejaba en las aguas turbias. De pronto, todo el brillo desaparece al pasar bajo el arco del portón de acceso a la casa y, con un estruendo, se entra al patio. La enorme entrada de la casa es impactante por lo oscura que resulta. La iluminación la proporcionan unas velas y unas lámparas de aceite que brindan poca luz, pareciendo más bien aumentar la negrura de las sombras. Una energía extraña inunda el aire y brilla como una luz negra desde cada sombra. Se escucha un murmullo que sube y baja de volumen. Todos los sentidos indican que hay peligro —peligro mortal—.
            </p>

            <!-- New section for Charlotte and Stephen ghosts (swapped position) -->
            <section class="mt-10">
                <h2 class="text-3xl md:text-4xl creepster-font text-red-600 mb-4">Los Antiguos Moradores: Fantasmas Atrapados</h2>
                <p class="text-gray-400 leading-relaxed mb-6">
                    Los espíritus de Charlotte y Sir Stephen Clarendon están condenados a vagar por Hawton Mere, atrapados por los horribles crímenes que marcaron su final. ¿Se atreve a invocar a los fantasmas que aún se lamentan por la casa y por fuera de ella?
                </p>
                <div class="flex flex-col md:flex-row justify-center gap-4 mb-6">
                    <button id="invokeCharlotteButton"
                            class="bg-purple-800 hover:bg-purple-900 text-white font-bold py-3 px-6 rounded-lg transition-all duration-300 button-glow">
                        Invocar a Charlotte
                    </button>
                    <button id="invokeStephenButton"
                            class="bg-green-800 hover:bg-green-900 text-white font-bold py-3 px-6 rounded-lg transition-all duration-300 button-glow">
                        Invocar a Sir Stephen
                    </button>
                </div>

                <!-- Container for Charlotte's ghost -->
                <div id="charlotteGhostContainer" class="hidden mt-8 p-4 bg-gray-800 border border-purple-700 rounded-lg text-center">
                    <h3 class="text-2xl creepster-font text-purple-400 mb-3">El Fantasma de Charlotte <span class="ghost-figure ghost-charlotte">🔥</span></h3>
                    <p class="text-gray-400 text-sm italic">
                        "El fantasma de Charlotte, eternamente hermosa pero consumida por la envidia y el fuego. Su piel, aún pálida como el mármol, ahora lleva las marcas del incendio que la consumió en la misma habitación de Lady Clarendon. Su voz, antaño clara y pura, es un susurro gélido que persigue, una lamentación sin remordimiento por el destino de Lady Clarendon, a quien empujó del balcón por celos del heredero de Hawton Mere. Ella arde, atrapada por las llamas accidentales que la encerraron, condenada a revivir su final."
                    </p>
                </div>

                <!-- Container for Sir Stephen's ghost -->
                <div id="stephenGhostContainer" class="hidden mt-8 p-4 bg-gray-800 border border-green-700 rounded-lg text-center">
                    <h3 class="text-2xl creepster-font text-green-400 mb-3">El Fantasma de Sir Stephen <span class="ghost-figure ghost-stephen">✂️</span></h3>
                    <p class="text-gray-400 text-sm italic">
                        "Sir Stephen Clarendon, el guardián de Hawton Mere, vaga como una sombra desgarrada. Su mano, tan fría como siempre, recuerda la hoja de las tijeras que su propia hermana, Charlotte, le clavó por la espalda, descubriendo su crimen contra Lady Clarendon. Sus ojos hundidos reflejan la traición y el dolor por la muerte de su amada esposa, y el futuro perdido de su linaje. Su presencia es el lamento silencioso de una justicia nunca alcanzada, un recordatorio de los crímenes que mancharon esta casa por dentro y por fuera, ambos muertos en la habitación de Lady Clarendon."
                    </p>
                </div>
            </section>

            <!-- Interactive Buttons (moved down) -->
            <div class="flex flex-col md:flex-row justify-center gap-4 mb-6">
                <button id="exploreButton"
                        class="bg-red-700 hover:bg-red-800 text-white font-bold py-3 px-6 rounded-lg transition-all duration-300 button-glow">
                    Explorar la Mansión
                </button>
                <button id="revealSecretButton"
                        class="bg-gray-800 hover:bg-red-900 text-red-300 font-bold py-3 px-6 rounded-lg transition-all duration-300 border border-red-900">
                    Revelar un Secreto
                </button>
            </div>

            <!-- Container for the general ghost -->
            <div id="ghostContainer" class="hidden mt-8 text-center">
                <p class="text-xl text-red-400 mb-4 shudder">¡Se siente una presencia helada!</p>
                <div class="text-7xl md:text-9xl ghost-appear">👻</div>
                <p class="text-sm text-gray-500 mt-2">No se está solo...</p>
            </div>

             <!-- Contenedor para el secreto revelado: Historia de Hawton Mere -->
            <div id="secretRevealContainer" class="hidden mt-8 p-4 bg-gray-800 border border-red-900 rounded-lg">
                <h3 class="text-2xl creepster-font text-red-500 mb-3">Los Horrores Ocultos de Hawton Mere</h3>
                <p class="text-gray-400 text-sm italic">
                    La mansión guarda un terrible secreto. Se descubrió un antiguo pacto con el demonio, una criatura gestada por la crueldad, destinada a que Sir Stephen asumiera la culpa. Durante años, el demonio lo atormentó, y ahora viene por él. Hay una presencia infantil, un fantasma que no es de un muerto, sino de un niño cuyo dolor es tan intenso que su espíritu se manifiesta como una entidad extraña y aterradora. Se siente una profunda rabia y dolor, mezclados con una extraña mezcla de criaturas. La oscuridad de Hawton Mere parece cobrar vida, y se experimentan horrores indescriptibles.
                </p>
            </div>

            <!-- Story or Description Section with Challenge (moved down) -->
            <section class="mt-10">
                <h2 class="text-3xl md:text-4xl creepster-font text-red-600 mb-4">HAWTON MERE: El Desafío Final</h2>
                <p class="text-gray-400 leading-relaxed mb-6">
                    <span class="creepster-font text-2xl text-red-500">¿Se atreve a enfrentarse a los horrores que residen aquí?</span>
                    <br>
                    <span class="text-xl font-bold text-red-400">¡AGUANTA UN MES EN ESTA CASA Y GANA ¡300.000!</span>
                    <br>
                    <span class="text-lg text-gray-300">¿PODRÁ HACERLO?</span>
                </p>
            </section>


            <!-- Section for Experiences and Contact -->
            <section class="mt-10 p-6 bg-gray-800 rounded-lg border border-red-700">
                <h2 class="text-3xl md:text-4xl creepster-font text-red-600 mb-4">Experiencias y Contacto</h2>
                <p class="text-gray-400 leading-relaxed mb-6">
                    Adéntrese en la oscuridad de Hawton Mere, donde criaturas y ruidos inusuales invadirán sus sentidos. Nunca se sabe lo que depara el siguiente pasillo. ¿Está listo para enfrentarlos?
                </p>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
                    <div class="p-4 bg-gray-900 rounded-lg border border-red-800 text-center">
                        <h3 class="text-xl creepster-font text-red-400 mb-2">Aventura Estándar</h3>
                        <p class="text-white text-3xl font-bold mb-2">$5.000 <span class="text-sm text-gray-400">POR PERSONA</span></p>
                        <p class="text-gray-400 text-sm">Sustos inolvidables garantizados.</p>
                    </div>
                    <div class="p-4 bg-gray-900 rounded-lg border border-red-800 text-center">
                        <h3 class="text-xl creepster-font text-red-400 mb-2">Desafío Extremo</h3>
                        <p class="text-white text-3xl font-bold mb-2">$8.000 <span class="text-sm text-gray-400">POR PERSONA</span></p>
                        <p class="text-gray-400 text-sm">Para los más valientes y atrevidos. ¡Con ofertas!</p>
                    </div>
                </div>

                <div class="text-center mt-6">
                    <h3 class="text-2xl creepster-font text-red-500 mb-3">Contacto Casas del Insomnio</h3>
                    <p class="text-gray-400 mb-2">📞 911-4234-9567</p>
                    <p class="text-gray-400 mb-2">🌐 <a href="http://www.casasdelinsomnio.com.ar" target="_blank" class="text-red-300 hover:text-red-500 transition-colors">www.casasdelinsomnio.com.ar</a></p>
                    <p class="text-gray-400">📧 <a href="mailto:Atraccionesdeterror@gmail.com" class="text-red-300 hover:text-red-500 transition-colors">Atraccionesdeterror@gmail.com</a></p>
                </div>
            </section>

            <!-- Section for exploring the mansion with text details -->
            <section class="mt-10">
                <h2 class="text-3xl md:text-4xl creepster-font text-red-600 mb-4">Un Recorrido por Hawton Mere</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    <!-- Living Room -->
                    <div class="p-4 bg-gray-800 rounded-lg border border-gray-700">
                        <h3 class="text-xl creepster-font text-red-400 mb-2">El Salón Lúgubre</h3>
                        <p class="text-gray-400 text-sm room-description">
                            "En uno de los lados del salón había una imponente chimenea ennegrecida por el hollín. Al otro lado se levantaba una gran escalera. El piso estaba enchapado de incrustaciones de mármol en diferentes tonos, puestas en un patrón de mosaico que generaba la inquietante ilusión de ser docenas de cubos sólidos. El efecto era tan convincente que uno se encontraba queriendo saltar de uno a otro, aunque el piso era, de hecho, completamente plano."
                        </p>
                    </div>

                    <!-- The Kitchen -->
                    <div class="p-4 bg-gray-800 rounded-lg border border-gray-700">
                        <h3 class="text-xl creepster-font text-red-400 mb-2">La Antigua Cocina</h3>
                        <p class="text-gray-400 text-sm room-description">
                            "La cocina era una habitación enorme y abovedada donde brillaban ollas de cobre y utensilios de todo tipo, y las paredes estaban repletas de estanterías con platos. Había un gran centro de cocción en una de las esquinas y una hoguera al costado. La iluminación la proporcionaban en su totalidad unas velas y unas lámparas de aceite que brindaban poca luz, y parecía más bien que aumentaban la negrura de las sombras. La comodidad moderna del gas, al parecer, no había llegado aún a Hawton Mere."
                        </p>
                    </div>

                    <!-- The Hallway -->
                    <div class="p-4 bg-gray-800 rounded-lg border border-gray-700">
                        <h3 class="text-xl creepster-font text-red-400 mb-2">El Corredor Helado</h3>
                        <p class="text-gray-400 text-sm room-description">
                            "Tan pronto se entraba por esa puerta se sentía: una energía extraña inundaba el aire y brillaba como una luz negra desde cada sombra. Un murmullo subía y bajaba de volumen, aunque en realidad se percibía, más que oírlo. Todos los sentidos indicaban que había peligro —peligro mortal—, y sin embargo no se veía nada extraño, excepto por un sombrío y poco agradable corredor."
                        </p>
                    </div>

                    <!-- The Bathroom -->
                    <div class="p-4 bg-gray-800 rounded-lg border border-gray-700">
                        <h3 class="text-xl creepster-font text-red-400 mb-2">El Cuarto de Aseo Inesperado</h3>
                        <p class="text-gray-400 text-sm room-description">
                            "Para sorpresa de uno, el cuarto de aseo contenía un lavabo muy moderno, con un cuenco lujosamente decorado. Parecía sorprendentemente fuera de lugar frente a las lúgubres decoraciones interiores de la casa. Pero cuando se tiraba de la cadena, la tubería antigua gemía y sonaba como si fuera a explotar en cualquier momento."
                        </p>
                    </div>

                    <!-- The Mirror -->
                    <div class="p-4 bg-gray-800 rounded-lg border border-gray-700 md:col-span-2">
                        <h3 class="text-xl creepster-font text-red-400 mb-2">El Espejo Olvidado y su Voz</h3>
                        <p class="text-gray-400 text-sm room-description">
                            "Se encontraba un espejo enorme, con un marco dorado. El decorado del marco estaba gastado y el espejo tenía manchas en los bordes. Era como mirarse en una piscina congelada. -De niño, ese espejo aterrorizaba -dijo una voz a espaldas del observador."
                        </p>
                    </div>
                </div>
            </section>
        </section>
    </main>

    <!-- Footer -->
    <footer class="mt-8 text-center text-gray-600 text-sm">
        <p>&copy; 2025 La Mansión del Lamento. Todos los derechos reservados... a los espíritus.</p>
    </footer>

    <script>
        // Get DOM elements
        const exploreButton = document.getElementById('exploreButton');
        const revealSecretButton = document.getElementById('revealSecretButton');
        const ghostContainer = document.getElementById('ghostContainer');
        const secretRevealContainer = document.getElementById('secretRevealContainer');
        const invokeCharlotteButton = document.getElementById('invokeCharlotteButton');
        const invokeStephenButton = document.getElementById('invokeStephenButton');
        const charlotteGhostContainer = document.getElementById('charlotteGhostContainer');
        const stephenGhostContainer = document.getElementById('stephenGhostContainer');

        // Function to show the general ghost
        exploreButton.addEventListener('click', () => {
            ghostContainer.classList.toggle('hidden');
            if (!ghostContainer.classList.contains('hidden')) {
                // Reset animation if already visible
                ghostContainer.querySelector('div').style.animation = 'none';
                void ghostContainer.querySelector('div').offsetWidth; // Force reflow
                ghostContainer.querySelector('div').style.animation = null;
            }
            secretRevealContainer.classList.add('hidden'); // Hide the secret
            charlotteGhostContainer.classList.add('hidden'); // Hide specific ghosts
            stephenGhostContainer.classList.add('hidden');
        });

        // Function to reveal the secret
        revealSecretButton.addEventListener('click', () => {
            secretRevealContainer.classList.toggle('hidden');
            ghostContainer.classList.add('hidden'); // Hide the general ghost
            charlotteGhostContainer.classList.add('hidden'); // Hide specific ghosts
            stephenGhostContainer.classList.add('hidden');
        });

        // Function to invoke Charlotte
        invokeCharlotteButton.addEventListener('click', () => {
            charlotteGhostContainer.classList.toggle('hidden');
            // Reset animation if already visible
            if (!charlotteGhostContainer.classList.contains('hidden')) {
                // Select the span element with the ghost-charlotte class inside the container
                const charlotteFigure = charlotteGhostContainer.querySelector('.ghost-charlotte');
                if (charlotteFigure) {
                    charlotteFigure.style.animation = 'none';
                    void charlotteFigure.offsetWidth; // Force reflow
                    charlotteFigure.style.animation = null;
                }
            }
            ghostContainer.classList.add('hidden');
            secretRevealContainer.classList.add('hidden');
            stephenGhostContainer.classList.add('hidden'); // Hide Stephen
        });

        // Function to invoke Sir Stephen
        invokeStephenButton.addEventListener('click', () => {
            stephenGhostContainer.classList.toggle('hidden');
             // Reset animation if already visible
            if (!stephenGhostContainer.classList.contains('hidden')) {
                // Select the span element with the ghost-stephen class inside the container
                const stephenFigure = stephenGhostContainer.querySelector('.ghost-stephen');
                if (stephenFigure) {
                    stephenFigure.style.animation = 'none';
                    void stephenFigure.offsetWidth; // Force reflow
                    stephenFigure.style.animation = null;
                }
            }
            ghostContainer.classList.add('hidden');
            secretRevealContainer.classList.add('hidden');
            charlotteGhostContainer.classList.add('hidden'); // Hide Charlotte
        });

        // Ensure the body has the correct height to center content
        document.body.style.minHeight = '100vh';
        document.body.style.display = 'flex';
        document.body.style.flexDirection = 'column';
        document.body.style.alignItems = 'center';
        document.body.style.justifyContent = 'center';
    </script>
</body>
</html>
