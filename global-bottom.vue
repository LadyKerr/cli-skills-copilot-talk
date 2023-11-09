<template>
    <footer class="absolute bottom-0 left-0 right-0 w-full z-9">
        <div class="flex w-full p-2" :class="{
            'justify-start': $slidev.configs.globalBottomPosition === 'left',
            'justify-end': !$slidev.configs.globalBottomPosition,
        }">
            <div class="flex flex-col gap-2 bg-light-background dark:bg-dark-background bg-opacity-60 p-2 rounded-md">
                <span class="text-sm"><logos-twitter class="mr-1" />@itsthatladydev</span>
            </div>
        </div>
        <!-- <div class="border-bar"></div> -->
    </footer>
</template>
  
<style>
footer {
    display: none !important;
}
</style>