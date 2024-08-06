<template>
   <div class="grids" >
  
    <Product v-for="p in products" :product="p" :key="p.id" />
  
   </div>
 </template>
 
 <script setup>
 const { data: products } = await useFetch('https://fakestoreapi.com/products')

 </script>
 
 <style scoped>
 .grids {
   display: grid;
   gap: 1rem;
   grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
   padding: 1rem;
 }
 
 
 </style>
 