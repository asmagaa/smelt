<script lang="ts">
    let scrollY = 0;
    let lastScrollTime = 0;
    let scrollSpeed = 0;
    let easterEggActive = 0;
    let easterEggTriggered = 0;
    let terminalInput = 0;
    let terminalHistory: string[] = [];
    let showTerminal = false;
    let currentStep = 0;

    function scroll() {
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
    
</script>