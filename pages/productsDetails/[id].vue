<template>
  <div v-if="product" class="product">
    <div class="product-img">
      <img :src="product.image" alt="Product image" />
    </div>
    <div class="product-info">
      <div class="product-title">{{ product.title }}</div>
      <div class="product-price"> ${{ product.price }}</div>
      <p class="product-description">{{ product.description }}</p>
      <div v-show="showing" class="added"> Added</div>
      <button class="add-to-cart-btn" @click="show">Add to Cart</button>
    </div>
  </div>
</template>

<script setup>

const { id } = useRoute().params

const url = `https://fakestoreapi.com/products/${id}`

const { data: product } = await useFetch(url, { key: id })

const showing = ref(false)
function show(){
  showing.value = true
  
  setTimeout(() => {
    showing.value = false;
  }, 2000);
 
}
</script>

<style scoped>
.product {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 1rem;
  padding: 1rem;
  max-width: 1200px;
  margin: 0 auto;
}

.product-img img {
  width: 100%;
  height: auto;
  border-radius: 8px;
  object-fit: cover;
}

.product-info {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.product-title {
  font-size: 1.8rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
}

.product-price {
  font-size: 1.5rem;
  color: #ff6f61;
  margin-bottom: 1rem;
}

.product-description {
  font-size: 1rem;
  line-height: 1.5;
  margin-bottom: 1rem;
}

.add-to-cart-btn {
  padding: 0.75rem 1.5rem;
  background-color: #ff6f61;
  color: #fff;
  border: none;
  border-radius: 5px;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.3s;
}

.add-to-cart-btn:hover {
  background-color: #ff4d4d;
}

.added{
color: green;
margin-bottom: 1rem;

}


</style>
