<script>
    import Globe from '$lib/assets/globe.svg';

    const stripItems = Array(8).fill('PETRICHOR');
</script>

<div class="flex items-center overflow-hidden w-screen h-10 my-4 bg-white/[0.02] backdrop-blur-[10px] border-t border-b border-white/[0.08] opacity-70">
    {#each stripItems as item, index}
        <div class="flex justify-center items-center gap-3 min-w-[max(20%,150px)] flex-shrink-0 strip1">
            <div class="inline-flex items-center">
                <img src={Globe} alt="Globe" class="w-4 h-4 invert opacity-60" />
            </div>
            <div class="inline-flex items-center">
                <span class="text-white font-medium text-sm tracking-[1.5px] opacity-80 whitespace-nowrap">&nbsp;{item}</span>
            </div>
        </div>
    {/each}
</div>

<style>
    .strip1 {
        animation: infinite-scroll 5s linear infinite;
    }

    @keyframes infinite-scroll {
        0% {
            transform: translateX(0%);
        }
        100% {
            transform: translateX(-100%);
        }
    }

    @media (max-width: 768px) {
        .strip1 {
            animation: infinite-scroll 4s linear infinite;
        }
    }
    
    @media (max-width: 480px) {
        .strip1 {
            animation: infinite-scroll 3s linear infinite;
        }
    }
</style>