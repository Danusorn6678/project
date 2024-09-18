<template>
    <div class="products">
      <div v-for="product in products" :key="product.id" class="product-card">
        <img :src="product.image" :alt="product.name" class="product-image" />
        <h2 class="product-name">{{ product.name }}</h2>
        <p class="product-price">{{ product.price }}</p>
        <p class="product-description">{{ product.description }}</p>
      </div>
    </div>
  </template>
  
  <script setup>
  const products = [
    {
      id: 1,
      name: "เครื่อง AED",
      price: "40,000 THB",
      image: "https://www.defibshop.co.uk/pub/media/catalog/product/cache/c687aa7517cf01e65c009f6943c2b1e9/a/e/aed.jpg",
      description: "เครื่องกระตุ้นหัวใจอัตโนมัติ",
    },
    {
      id: 2,
      name: "เครื่องวัดอุณหภูมิ",
      price: "1,500 THB",
      image: "https://sc04.alicdn.com/kf/HTB1RyfBaEvrK1RjSspcq6zzSXXa3.jpg",
      description: "อุปกรณ์วัดอุณหภูมิ",
    },
    {
      id: 3,
      name: "หน้ากากอนามัย",
      price: "50 THB",
      image: "https://www.collinsdictionary.com/images/full/face-mask_592143953_1000.jpg",
      description: "หน้ากากอนามัยคุณภาพสูง",
    },
  ];
  </script>
  
  <style>
  .products {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
  }
  
  .product-card {
    border: 1px solid #ddd;
    border-radius: 8px;
    padding: 16px;
    max-width: 300px;
    text-align: center;
  }
  
  .product-image {
    width: 100%;
    height: auto;
    border-radius: 8px;
  }
  
  .product-name {
    font-size: 18px;
    margin: 10px 0;
  }
  
  .product-price {
    color: #007bff;
    font-size: 16px;
  }
  
  .product-description {
    font-size: 14px;
    color: #555;
  }
  </style>
  