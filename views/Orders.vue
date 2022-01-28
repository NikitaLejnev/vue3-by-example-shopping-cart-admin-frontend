<template>
  <TopBar />
  <h1>Orders</h1>
  <div v-for="order of orders" :key="order.order_id">
    <h2>Order ID: {{ order.order_id }}</h2>
    <p>Name: {{ order.name }}</p>
    <p>Address: {{ order.address }}</p>
    <p>Phone: {{ order.phone }}</p>
    <div>
      <h3>Ordered Items</h3>
      <div
        v-for="orderedItems of order.ordered_items"
        :key="orderedItems.shop_item_id"
      >
        <h4>Name: {{ orderedItems.name }}</h4>
        <p>Description: {{ orderedItems.description }}</p>
        <p>Price: {{ orderedItems.price }}</p>
      </div>
    </div>
    <p>
      <b>Total: ${{ calcTotal(order.ordered_items) }}</b>
    </p>
    <button type="button" @click="deleteOrder(order)">Delete
      Order</button>
  </div>
</template>
