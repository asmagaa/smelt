<script lang="ts">
    let scrollY = 0;
    let lastScrollTime = 0;
    let scrollSpeed = 0;
    let easterEggActive = false;
    let easterEggTriggered = false;
    let terminalInput = '';
    let terminalHistory: string[] = [];
    let showTerminal = false;
    let currentStep = 0;
    
    function handleScroll() {
        const scrollPercentage = (scrollY + window.innerHeight) / document.body.scrollHeight;
        
        if (scrollPercentage > 0.7 && !easterEggTriggered) {
            triggerEasterEgg();
        }
    }

    function triggerEasterEgg() {
        easterEggActive = true;
        easterEggTriggered = true;
        
        setTimeout(() => {
            showTerminal = true;
            terminalHistory = [
                'System breach detected...',
                'Activating security protocol...',
                'Enter command to exit matrix mode:'
            ];
        }, 4000);
    }

    function handleTerminalInput(event: KeyboardEvent) {
        if (event.key === 'Enter') {
            const command = terminalInput.trim().toLowerCase();
            terminalHistory = [...terminalHistory, `user@matrix:~$ ${terminalInput}`];
            
            if (command === 'exit' || command === 'quit' || command === 'logout') {
                terminalHistory = [...terminalHistory, 'Exiting matrix mode...', 'Welcome back to reality.'];
                setTimeout(() => {
                    easterEggActive = false;
                    showTerminal = false;
                    terminalHistory = [];
                    setTimeout(() => {
                        easterEggTriggered = false;
                    }, 5000);
                }, 2000);
            } else if (command === 'help' || command === 'ls' || command === 'pwd') {
                if (command === 'help') {
                    terminalHistory = [...terminalHistory, 'Available commands: exit, quit, logout, ls, pwd, whoami'];
                } else if (command === 'ls') {
                    terminalHistory = [...terminalHistory, 'reality.exe  matrix.dll  truth.txt  red_pill.sh'];
                } else if (command === 'pwd') {
                    terminalHistory = [...terminalHistory, '/home/neo/matrix'];
                }
            } else if (command === 'whoami') {
                terminalHistory = [...terminalHistory, 'You are... The One.'];
            } else if (command === 'clear') {
                terminalHistory = ['Enter command to exit matrix mode:'];
            } else {
                terminalHistory = [...terminalHistory, `bash: ${command}: command not found`];
                terminalHistory = [...terminalHistory, 'Hint: Try "exit", "quit", or "logout" to return to reality'];
            }
            terminalInput = '';
        }
    }
</script>

<svelte:window bind:scrollY on:scroll={handleScroll} />

<main class="container">
    <header class="hero">
        <h1>Why I Am the Greatest Programmer That Has Ever Lived</h1>
        <p class="subtitle">An Exhaustive Dissertation on My Unparalleled Coding Supremacy</p>
        <p class="disclaimer">WARNING: This well-written document contains dangerous levels of confidence and yapping possibly causing severe eye-rolling and headache.</p>
    </header>

    <div class="content">
        <section class="intro">
            <h2>Executive Summary</h2>
            <p>
                Ladies, gentlemen, and fellow carbon-based life forms, you are about to witness something extraordinary. 
                This document is not just a resume - it's a historical artifact documenting the rise of a coding deity. 
                Some call it arrogance, I call it factual accuracy. Buckle up, because you're about to read why I am 
                literally the best thing that has happened to software development since the invention of electricity. 
            </p>
            <p>
                While other developers are still googling "how to center a div," I'm over here architecting solutions 
                that would make Linus Torvalds weep tears of pure joy. This isn't confidence speaking - this is just 
                objective reality acknowledging itself.
            </p>
        </section>

        <section class="skills">
            <h2>My S-Tier Superpowers</h2>
            <p>
                Let me start by saying that calling my abilities "skills" is like calling Einstein's theories "homework." 
                I don't just write code - I craft digital poetry that compiles on the first try. While others debug, 
                I simply will my programs into perfect existence through sheer mental superiority.
            </p>
            <p>
                I speak more programming languages than the United Nations has official languages. C++, JavaScript, Python, 
                Rust, Go, Assembly, and several languages I invented during my lunch breaks. I dream in binary and wake up 
                with perfectly optimized algorithms. My IDE doesn't have syntax highlighting because my code is so clean 
                it illuminates itself.
            </p>
            <p>
                When Stack Overflow has a question, they ask me. When GitHub needs inspiration for new features, they study 
                my repositories. I don't use Git - Git uses me as a reference implementation. My commits are so well-written 
                that they're taught in computer science literature courses.
            </p>
            <p>
                Data structures? I invented better ones before breakfast. Big O notation? More like Big ME notation, because 
                my algorithms transcend traditional complexity analysis. I once optimized a O(n²) algorithm to O(awesome) 
                just by looking at it disapprovingly.
            </p>
        </section>

        <section class="problem-solving">
            <h2>My Extraordinary Problem-Solving Ability</h2>
            <p>
                I don't solve problems - I whisper to them gently until they solve themselves out of respect. My debugging 
                process consists of three steps: 1) Look at the code, 2) The bugs apologize and fix themselves, 3) Accept praise 
                from my IDE for being so magnificent.
            </p>
            <p>
                When NASA needs to calculate rocket trajectories, they use my algorithms. When Google's search algorithm feels 
                inadequate, it looks up to my search implementations for guidance. I once solved the traveling salesman problem 
                so efficiently that all the salesmen just started teleporting.
            </p>
            <p>
                My approach to architecture is simple: I think of the most elegant solution possible, then I improve it by 300% 
                because even my first thoughts are better than most people's final drafts. I don't follow design patterns - 
                design patterns follow me around taking notes.
            </p>
            <p>
                Error handling? In my code, errors don't happen because even exceptions are too intimidated to occur. 
                When edge cases see my code approaching, they become middle cases out of pure respect. I write tests not 
                because my code needs them, but because my tests want to be associated with excellence.
            </p>
        </section>

        <section class="learning">
            <h2>My Infinite Knowledge Absorption Matrix</h2>
            <p>
                While other developers "learn" technologies, I simply download them directly into my consciousness through 
                pure intellectual osmosis. I read documentation so fast that the authors have to rewrite it to keep up with 
                my comprehension speed. I don't attend conferences - conferences attend me.
            </p>
            <p>
                I learned React before it was invented. I was writing functional programming when functions were still 
                procedural. I mastered machine learning when AI was still trying to figure out what intelligence meant. 
                Framework authors call me for advice on how to improve their own creations.
            </p>
            <p>
                My learning curve isn't a curve - it's a vertical line that shoots straight up into the stratosphere of 
                knowledge. When new technologies emerge, they're basically just catching up to concepts I've already 
                internalized. TypeScript? I was thinking in types before types existed.
            </p>
            <p>
                I don't have side projects - I have side masterpieces. Each one is a testament to human potential and 
                a glimpse into the future of software development. My GitHub profile is basically a museum of computational 
                excellence that researchers will study for generations.
            </p>
        </section>

        <section class="leadership">
            <h2>My Napoleonic Leadership and Collaboration Excellence</h2>
            <p>
                When I join a team, productivity doesn't just increase - it transcends mathematical limitations. Other 
                developers don't just look up to me; they recalibrate their entire understanding of what's possible in 
                software engineering. I don't do code reviews - I perform code enlightenments.
            </p>
            <p>
                My pull requests are so perfect that they automatically get approved by the universe itself. When I comment 
                on someone's code, it's not criticism - it's a masterclass in excellence delivery. Junior developers frame 
                my code reviews and hang them on their walls for inspiration.
            </p>
            <p>
                I communicate so effectively that when I explain complex technical concepts, even non-technical people 
                suddenly understand quantum computing. My documentation is so clear and comprehensive that it's being 
                considered for the Pulitzer Prize in the "Technical Literature That Makes You Weep With Joy" category.
            </p>
            <p>
                Git workflows become more elegant just by my presence in the repository. Merge conflicts see me coming 
                and resolve themselves preemptively. I don't just follow agile methodologies - agile methodologies 
                evolve to accommodate my superior development velocity.
            </p>
        </section>

        <section class="passion">
            <h2>My Transcendent Passion Brighter Than A 100 Suns</h2>
            <p>
                My passion for programming isn't just a career choice - it's a calling from the digital gods themselves. 
                I don't work 9-to-5; I work 25-hour days (I invented extra time through efficient coding). When I sleep, 
                I dream in perfectly optimized algorithms that solve world hunger and achieve world peace simultaneously.
            </p>
            <p>
                I love coding so much that my heart beats in perfect binary rhythm. My blood type is JavaScript (though 
                I prefer TypeScript for formal occasions). When I'm not coding, I'm thinking about coding. When I'm 
                thinking about coding, I'm accidentally solving problems that haven't been invented yet.
            </p>
            <p>
                My dedication is so intense that coffee shops started serving my preferred blend as "The Developer's 
                Enlightenment." I don't burn out - I burn bright, like a supernova of computational excellence that 
                illuminates the entire software development galaxy.
            </p>
            <p>
                Every line of code I write is infused with pure passion and cosmic energy. My functions don't just execute - 
                they perform. My variables don't just store data - they cradle information with the tenderness of a master 
                craftsman holding their finest creation.
            </p>
        </section>

        <section class="innovation">
            <h2>My Reality-Bending Innovation Capabilities</h2>
            <p>
                I don't just think outside the box - I redesigned the box, optimized it, and then transcended the very 
                concept of containment itself. My innovations are so groundbreaking that they're usually ahead of their 
                time by at least three technological generations.
            </p>
            <p>
                When I encounter a problem that seems impossible, I smile because impossible problems are my specialty. 
                I've solved more "unsolvable" programming challenges than there are stars in the visible universe. 
                P vs NP? Solved it during a coffee break, but I'm keeping the solution to myself to maintain universal balance.
            </p>
            <p>
                My creative solutions are so elegant that they're studied in advanced mathematics courses as examples of 
                perfect logical beauty. I once wrote a sorting algorithm so efficient that it sorted data before it was 
                even inputted. Time itself rearranges to accommodate my code's execution efficiency.
            </p>
            <p>
                Innovation isn't something I do - it's something that happens naturally in my presence. Ideas manifest into 
                perfect implementations through sheer proximity to my genius. Other developers take notes not just on what 
                I code, but on how I breathe while coding, hoping to capture some fragment of the magic.
            </p>
        </section>

        <section class="conclusion">
            <h2>A Modest Conclusion to This Understated Self-Assessment</h2>
            <p>
                In conclusion, I am not just a good programmer - I am the programmer. The alpha and omega of code. 
                The beginning and end of software development excellence. Hiring me isn't just a business decision - 
                it's an investment in the future of human technological evolution.
            </p>
            <p>
                I don't just write software; I compose digital symphonies that make angels weep and demons applaud. 
                My code doesn't just work - it transcends the physical limitations of silicon and achieves a state of 
                computational nirvana that theoretical physicists are still trying to understand.
            </p>
            <p>
                This document, while comprehensive, only scratches the surface of my capabilities. My true power levels 
                are classified information that would destabilize the global economy if fully disclosed. I am not just 
                a developer - I am a force of nature, a phenomenon, a gift to humanity's technological advancement.
            </p>
            <p>
                Some might call this arrogance. I call it radical honesty. The truth is, I'm probably being too modest. 
                But humility is one of my many virtues, right alongside my ability to make computers feel emotions and 
                my talent for writing code so beautiful that it belongs in the Louvre.
            </p>
            <p class="hint">
                <em>Scroll down to about 60-70% of the page to enter the Matrix...</em>
            </p>
            <p class="disclaimer">
                <strong>Legal Notice:</strong> This document may cause spontaneous applause, uncontrollable admiration, 
                and an irresistible urge to hire the author immediately. Side effects may include questioning your own 
                career choices and a sudden desire to learn everything about programming.
            </p>
        </section>
    </div>

    {#if easterEggActive}
        <div class="matrix-overlay">
            <div class="matrix-rain-container">
                {#each Array(50) as _, i}
                    <div class="matrix-column" style="left: {i * 2}%; animation-delay: {Math.random() * 2}s;">
                        {#each Array(20) as _, j}
                            <span class="matrix-char">{String.fromCharCode(0x30A0 + Math.floor(Math.random() * 96))}</span>
                        {/each}
                    </div>
                {/each}
            </div>

            {#if !showTerminal}
                <div class="matrix-text">
                    <div class="matrix-line">WELCOME TO THE MATRIX</div>
                    <div class="matrix-line">REALITY IS AN ILLUSION</div>
                    <div class="matrix-line">THE CODE IS CALLING YOU...</div>
                </div>
            {/if}

            {#if showTerminal}
                <div class="terminal-container">
                    <div class="terminal-header">
                        <div class="terminal-buttons">
                            <span class="terminal-button close"></span>
                            <span class="terminal-button minimize"></span>
                            <span class="terminal-button maximize"></span>
                        </div>
                        <div class="terminal-title">neo@matrix: /home/neo/matrix</div>
                    </div>
                    
                    <div class="terminal-content">
                        <div class="terminal-output">
                            {#each terminalHistory as line}
                                <div class="terminal-line">{line}</div>
                            {/each}
                        </div>
                        
                        <div class="terminal-input-line">
                            <span class="terminal-prompt">user@matrix:~$ </span>
                            <input 
                                type="text" 
                                bind:value={terminalInput}
                                on:keydown={handleTerminalInput}
                                class="terminal-input"
                                placeholder="Type 'exit' to return to reality..."
                            />
                            <span class="terminal-cursor">|</span>
                        </div>
                    </div>
                </div>
            {/if}
        </div>
    {/if}

</main>

<style>
    :global(body) {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    .container {
        max-width: 800px;
        margin: 0 auto;
        padding: 0 2rem;
        position: relative;
    }

    .hero {
        text-align: center;
        padding: 4rem 0;
    }

    .hero h1 {
        font-size: 2.5rem;
        margin-bottom: 1rem;
    }

    .subtitle {
        font-size: 1.2rem;
        opacity: 0.9;
        font-style: italic;
    }

    .disclaimer {
        font-size: 1rem;
        color: yellow;
        margin-top: 1rem;
        padding: 0.5rem;
        background: red;
        border-radius: 5px;
        border: 1px solid yellow;
        animation: blink 1s infinite;
    }

    @keyframes blink {
        0%, 50% { opacity: 1; }
        51%, 100% { opacity: 0.7; }
    }

    .content {
        background: white;
        border-radius: 10px;
        box-shadow: 0 4px 6px black;
        overflow: hidden;
    }

    section {
        padding: 2rem;
        border-bottom: 1px solid white;
        position: relative;
        transition: all 0.3s ease;
    }

    section:hover {
        background: linear-gradient(45deg, rgba(255,255,255,0.05), rgba(52,152,219,0.05));
        transform: translateX(5px);
        box-shadow: -5px 0 15px darkgrey;
    }

    section:last-child {
        border-bottom: none;
    }

    .intro {
        background: linear-gradient(135deg, rgba(255,193,7,0.1), rgba(255,87,34,0.1));
        border-left: 5px solid yellow;
    }

    .skills {
        background: linear-gradient(135deg, rgba(244,67,54,0.1), rgba(233,30,99,0.1));
        border-left: 5px solid red;
    }

    .problem-solving {
        background: linear-gradient(135deg, rgba(156,39,176,0.1), rgba(103,58,183,0.1));
        border-left: 5px solid violet;
    }

    .learning {
        background: linear-gradient(135deg, rgba(63,81,181,0.1), rgba(33,150,243,0.1));
        border-left: 5px solid blue;
    }

    .leadership {
        background: linear-gradient(135deg, rgba(0,188,212,0.1), rgba(0,150,136,0.1));
        border-left: 5px solid cyan;
    }

    .passion {
        background: linear-gradient(135deg, rgba(76,175,80,0.1), rgba(139,195,74,0.1));
        border-left: 5px solid green;
    }

    .innovation {
        background: linear-gradient(135deg, rgba(255,152,0,0.1), rgba(255,193,7,0.1));
        border-left: 5px solid orange;
    }

    .conclusion {
        background: linear-gradient(135deg, rgba(121,85,72,0.1), rgba(158,158,158,0.1));
        border-left: 5px solid darkgoldenrod;
        position: relative;
        overflow: hidden;
    }

    .conclusion::before {
        content: '👑';
        position: absolute;
        top: 1rem;
        right: 2rem;
        font-size: 3rem;
        opacity: 0.1;
        animation: float 3s ease-in-out infinite;
    }

    @keyframes float {
        0%, 100% { transform: translateY(0px); }
        50% { transform: translateY(-10px); }
    }

    h2 {
        color: #2c3e50;
        font-size: 1.8rem;
        margin-bottom: 1.5rem;
        padding-bottom: 0.5rem;
        border-bottom: 3px solid lightblue;
        display: inline-block;
    }

    p {
        margin-bottom: 1.5rem;
        text-align: justify;
        font-size: 1.1rem;
    }

    .hint {
        text-align: center;
        color: grey;
        font-size: 0.9rem;
        margin-top: 2rem;
        animation: glow 3s ease-in-out infinite alternate;
    }

    @keyframes glow {
        from { text-shadow: 0 0 5px lightblue; }
        to { text-shadow: 0 0 20px lightblue, 0 0 30px lightblue; }
    }

    @keyframes pulse {
        0% { transform: scale(1); }
        50% { transform: scale(1.02); }
        100% { transform: scale(1); }
    }

    .matrix-overlay {
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        background: black;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        z-index: 1000;
        animation: matrixAppear 1s ease-out;
    }

    .matrix-rain-container {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        overflow: hidden;
        opacity: 0.6;
    }

    .matrix-column {
        position: absolute;
        top: -100%;
        width: 20px;
        animation: matrixFall 8s linear infinite;
    }

    .matrix-char {
        display: block;
        color: lightgreen;
        font-family: 'Courier New', monospace;
        font-size: 14px;
        text-shadow: 0 0 5px lightgreen;
        animation: matrixGlow 2s ease-in-out infinite alternate;
    }

    @keyframes matrixFall {
        to { top: 100%; }
    }

    @keyframes matrixGlow {
        from { opacity: 0.3; }
        to { opacity: 1; }
    }

    .terminal-container {
        width: 80%;
        max-width: 800px;
        background: #1a1a1a;
        border-radius: 10px;
        box-shadow: 0 0 50px darkgreen;
        animation: terminalAppear 1s ease-out;
        z-index: 1001;
    }

    .terminal-header {
        background: black;
        padding: 10px 15px;
        border-radius: 10px 10px 0 0;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    .terminal-buttons {
        display: flex;
        gap: 8px;
    }

    .terminal-button {
        width: 12px;
        height: 12px;
        border-radius: 50%;
        display: block;
    }

    .terminal-button.close {
        background: red;
    }

    .terminal-button.minimize {
        background: yellow;
    }

    .terminal-button.maximize {
        background: lightgreen;
    }

    .terminal-title {
        color: white;
        font-family: 'Courier New', monospace;
        font-size: 12px;
    }

    .terminal-content {
        padding: 20px;
        background: #000;
        border-radius: 0 0 10px 10px;
        min-height: 300px;
        max-height: 400px;
        overflow-y: auto;
    }

    .terminal-output {
        margin-bottom: 20px;
    }

    .terminal-line {
        color: lightgreen;
        font-family: 'Courier New', monospace;
        font-size: 14px;
        margin: 5px 0;
        animation: typewriter 0.5s ease-out;
    }

    .terminal-input-line {
        display: flex;
        align-items: center;
        color: lightgreen;
        font-family: 'Courier New', monospace;
        font-size: 14px;
    }

    .terminal-prompt {
        color: lightgreen;
        margin-right: 10px;
    }

    .terminal-input {
        background: transparent;
        border: none;
        color: lightgreen;
        font-family: 'Courier New', monospace;
        font-size: 14px;
        outline: none;
        flex: 1;
    }

    .terminal-input::placeholder {
        color: darkgreen;
    }

    .terminal-cursor {
        color: lightgreen;
        animation: blinkCursor 1s infinite;
        margin-left: 2px;
    }

    @keyframes terminalAppear {
        from { opacity: 0; transform: scale(0.8); }
        to { opacity: 1; transform: scale(1); }
    }

    @keyframes typewriter {
        from { opacity: 0; transform: translateX(-10px); }
        to { opacity: 1; transform: translateX(0); }
    }

    @keyframes matrixAppear {
        from { opacity: 0; }
        to { opacity: 1; }
    }

    .matrix-text {
        text-align: center;
        color: lightgreen;
        font-family: 'Courier New', monospace;
        font-size: 2rem;
        z-index: 1001;
        text-shadow: 0 0 10px lightgreen;
        animation: matrixTextPulse 3s ease-in-out infinite;
    }

    .matrix-line {
        margin: 1.5rem 0;
        animation: fadeInMatrix 1s ease-in-out;
        text-shadow: 0 0 15px lightgreen;
    }

    @keyframes matrixTextPulse {
        0%, 100% { opacity: 0.8; transform: scale(1); }
        50% { opacity: 1; transform: scale(1.02); }
    }

    @keyframes fadeInMatrix {
        from { opacity: 0; transform: translateY(30px); }
        to { opacity: 1; transform: translateY(0); }
    }

    @keyframes blinkCursor {
        50% { opacity: 0; }
    }

    @media (max-width: 768px) {
        .container {
            padding: 0 1rem;
        }
        
        .hero {
            margin: 0 -1rem 2rem -1rem;
            padding: 2rem 0;
        }
        
        .hero h1 {
            font-size: 2rem;
        }
        
        section {
            padding: 1.5rem;
        }
        
        .matrix-text {
            font-size: 1.5rem;
            padding: 0 1rem;
        }

        .terminal-container {
            width: 95%;
            margin: 0 1rem;
        }

        .terminal-content {
            padding: 15px;
            font-size: 12px;
        }
    }
</style>