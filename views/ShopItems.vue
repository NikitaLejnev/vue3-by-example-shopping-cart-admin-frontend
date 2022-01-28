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

  <dialog :open="showDialog" class="center">
    <h2>Add Item to Shop</h2>
    <Form :validationSchema="schema" @submit="submitForm">
      <div>
        <label for="name">Name</label>
        <br />
        <Field name="name" type="text" placeholder="Name" />
        <ErrorMessage name="name" />
      </div>
      <br />
      <div>
        <label for="description">Description</label>
        <br />
        <Field name="description" type="text" placeholder="Description" />
        <ErrorMessage name="description" />
      </div>
      <br />
      <div>
        <label for="imageUrl">Image URL</label>
        <br />
        <Field name="imageUrl" type="text" placeholder="Image URL" />
        <ErrorMessage name="imageUrl" />
      </div>
      <br />
      <div>
        <label for="price">Price</label>
        <br />
        <Field name="price" type="text" placeholder="Price" />
        <ErrorMessage name="price" />
      </div>
      <br />
      <input type="submit" />
      <button @click="showDialog = false" type="button">Cancel</button>
    </Form>
  </dialog>
</template>
