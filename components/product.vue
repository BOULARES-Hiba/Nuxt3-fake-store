<template>
   <div class="product-card">
  <NuxtLink :to="`/productsDetails/${product.id}`" class="product-link">
          <span class="title">{{ product.title }}</span>
       <div class="product-img"><img :src="product.image" class="product-img" alt="Product image"></div>  
         <div class="product-info">
           <button class="details"> View more </button>
         </div>
       </NuxtLink>
   </div>
</template>
<script setup>
const { product } = defineProps(['product'])


</script>




<style>
.product-card {
   border: 1px solid #ddd;
   border-radius: 8px;
   overflow: hidden;
   background-color: #fff;
   box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
   transition: transform 0.2s, box-shadow 0.2s;
 }
 
 .product-card:hover {
   transform: translateY(-5px);
   box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
 }
 
 .product-link {
   text-decoration: none;
   color: inherit;
 }
 .product-img{
   max-height:250px;
}
 .product-img {
   width: 100%;
   height: auto;
   object-fit: fit;
 }

 
 .product-info {
   padding: 1rem;
 }
 
 .title {
   font-size: 1.2rem;
   font-weight: bold;
   display: block;
   margin-bottom: 0.5rem;
 }
 
 .details {
   font-size: 0.9rem;
   color: #fff;
   background-color: #ff6f61;
   width: 100%;
   padding: 0.5rem;
   border: none;
   border-radius: 1rem;
 }
</style>