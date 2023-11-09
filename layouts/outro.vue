<template>
    <div class="slidev-layout outro">
        <div class="absolute inset-0 z-1">
            <img src="../assets/cli-outro.svg" alt="" />
        </div>
        <div class="flex flex-col justify-center items-center w-full h-full">
            <slot></slot>
        </div>
    </div>
</template>
  
<style>
.slidev-layout.outro {
    h1+p {
        @apply text-4xl;
    }
}
</style>