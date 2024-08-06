<template>
   <nav class="navBar">
     <NuxtLink to="/" class="logo">Nuxt</NuxtLink>
    
   </nav>
 </template>
 
 <script setup>

 </script>
 
 <style scoped>
 .navBar {
   position: fixed;
   top: 0;
 right: 0;
 left: 0;
   background-color: #ff6f61; 
   padding: 1rem 1.5rem; 
   
   align-items: center;
   z-index: 2;
 }
 
 .logo {
   color: white;
   font-size: 1.5rem;
   text-decoration: none;
 }
 
 .cart {
   color: white;
   font-size: 1.5rem;
   text-decoration: none;
 }
 </style>
 