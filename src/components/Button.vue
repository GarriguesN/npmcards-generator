<script setup>
import { onMounted } from 'vue';

const props = defineProps({
    label:{
        type: String,
        required: true
    },
    type: {
      type: String,
      default: 'button'
    }
})

onMounted(() => {
    function rippleEffect(event) {
    const btn = event.currentTarget;
    
        const circle = document.createElement("span");
        const diameter = Math.max(btn.clientWidth, btn.clientHeight);
        const radius = diameter / 2;

        circle.style.width = circle.style.height = `${diameter}px`;
        circle.style.left = `${event.clientX - (btn.offsetLeft + radius)}px`;
        circle.style.top = `${event.clientY - (btn.offsetTop + radius)}px`;
        circle.classList.add("ripple");

        const ripple = btn.getElementsByClassName("ripple")[0];

        if (ripple) {
            ripple.remove();
        }

        btn.appendChild(circle);
    }

    const btns = document.getElementsByClassName("bt");
    for (let i = 0; i < btns.length; i++) {
        btns[i].addEventListener("click", rippleEffect);
    }
});

</script>

<template>
    <div class="flex">
        <div>
            <button :type="type" class="bt rounded px-2 py-1 min-w-max font-bold overflow-hidden shadow-sm relative bg-green-600 box-border border-floridaRed text-white hover:bg-opacity-90
            mobile:px-5
            mobile:py-2">
                {{ label ? label : 'DEFAULT' }}
            </button>  
        </div>

    </div>
</template>

<style>
    span.ripple {
        position: absolute;
        border-radius: 50%;
        transform: scale(0);
        animation: ripple 600ms linear;
        background-color: rgba(255, 255, 255, 0.7);
    }
    @keyframes ripple {
    to {
        transform: scale(4);
        opacity: 0;
    }
    }
</style>
