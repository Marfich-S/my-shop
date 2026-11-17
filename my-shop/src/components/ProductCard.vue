<template>
    <div class="product-car">
        <img :src="image" :alt="name" class = "product-image" />
        <h2>{{ name }}</h2>
        <p>{{ description }}</p>
        <p class="price">{{ price }} грн</p>
        <button class="by-button">Купити</button>
    </div>
</template>

<script>
export default{
    props:{
        name: String,
        description: String,
        price: Number,
        image: String
    }

};
</script>

<style scoped>
    .product-card {
        border: 1px solid #ccc;
        border-radius: 5px;
        padding: 10px;
        text-align: center;
        width: 200px;
    }
    .product-image {
        width: 100%;
        height: 200px;
        object-fit: cover;
    }
    .price{
        font-size: 18px;
        font-weight: bold;
        color: #28a745;
    }
    .by-button {
        background-color: #007bff;
        color: white;
        border: none;
        padding: 10px 20px;
        border-radius: 5px;
        cursor: pointer;
        margin-bottom: 10px;
    }
    .by-button:hover {
        background-color: #0056b3;
    }
</style>