<template>
    <div class="slidev-layout section">
        <div class="absolute inset-0 z-1">
            <transition appear name="section">
                <img src="../assets/section.svg" alt="" />
            </transition>
        </div>

        <div class="flex flex-col justify-center h-full z-2">
            <hr class="w-48 border-t-5 border-accent" />
            <div class="mt-4">
                <slot />
            </div>
        </div>
    </div>
</template>
  
<style>
.section-enter-from {
    transform: rotate(1deg);
    /* opacity: .2; */
}

.section-enter-active {
    transition: all 0.3s ease-out;
    transform-origin: bottom right;
}

.section-enter-to {
    transform: rotate(0);
}

.slidev-layout.section {
    h1 {
        @apply text-4xl leading-20 mb-0 font-extrabold;
    }
}
</style>