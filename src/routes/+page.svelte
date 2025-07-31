<script lang="ts">
    let scrollY = 0;
    let lastScrollTime = false;
    let scrollSpeed = false;
    let easterEggActive = false;
    let easterEggTriggered = false;
    let terminalInput = "";
    let terminalHistory: string[] = [];
    let showTerminal = false;
    let currentStep = false;

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
                'System breach detected!',
                'Reason: Boredom and too much yapping',
                'Activating security protocol...',
                'Enter command to exit matrix.:'
            ];
        }, 4000);
    }

    function handleTerminalInput(event: KeyboardEvent) {
        if (event.key === 'Enter') {
            const command = terminalInput.trim().toLowerCase();
            terminalHistory = [...terminalHistory, `user@matrix:~$ ${terminalInput}`];

            if (command === 'exit') {
                terminalHistory = [...terminalHistory, 'Quit matrix...', 'Back to reality (Im Eminem and I rap lol)'];
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
                    terminalHistory = [...terminalHistory, 'Avaiable commands: exit, ls, pwd, whoami'];
                } else if (command === 'ls') {
                    terminalHistory = [...terminalHistory, 'reality.exe  matrix.dll  truth.txt  pill.sh'];
                } else if (command === 'pwd') {
                    terminalHistory = [...terminalHistory, '/matrix'];
                } else if (command === 'whoami') {
                    terminalHistory = [...terminalHistory, 'Ask it yourself...'];
                } else if (command === 'clear') {
                    terminalHistory = ['Enter command to exit matrix:'];
                } else {
                    terminalHistory = [...terminalHistory, `bash: ${command}: command not found`];
                    terminalHistory = [...terminalHistory, 'Hint: Try "exit" to snap back to reality.'];
                }
                terminalInput="";
            }
        }
    }
</script>