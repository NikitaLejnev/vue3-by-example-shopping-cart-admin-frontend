<template>
  <TopBar />
  <h1>Shop Items</h1>
  <button @click="showDialog = true">Add Item to Shop</button>
  <div v-for="shopItem of shopItems"
    :key="shopItem.shop_item_id">
    <h2>{{ shopItem.name }}</h2>
    <p>Description: {{ shopItem.description }}</p>
    <p>Price: {{ shopItem.price }}</p>
    <img :src="shopItem.image_url" :alt="shopItem.name" />
    <br />
    <button type="button" @click="deleteItem(shopItem)">
      Delete Item from Shop
    </button>
  </div>
</template>
