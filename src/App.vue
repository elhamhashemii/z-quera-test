<template>
   <MainLayout>
     <RouterView />
   </MainLayout>
 </template>

<script setup>
import { RouterView } from 'vue-router'
import MainLayout from "./components/layout/MainLayout.vue"

document.onclick = () => applyCursorRippleEffect(event); 

function applyCursorRippleEffect(e) {
   const ripple = document.createElement("div");

   ripple.className = "ripple";
   document.body.appendChild(ripple);

  ripple.style.left = `${e.clientX}px`;
  ripple.style.top = `${e.clientY}px`; 

   ripple.style.animation = "ripple-effect .4s  linear";
   ripple.onanimationend = () => document.body.removeChild(ripple);

}
</script>

<style>
.ripple {
   width: 10px;
   height: 10px;
   background-color: transparent;
   position: fixed;
   border-radius: 50%;
   border: 1px solid #ef394e5e;
}

@keyframes ripple-effect {
   to {
      transform:scale(5);
      opacity: 0.01;
   }
}
</style>