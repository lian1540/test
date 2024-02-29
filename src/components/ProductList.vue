<template>

<div >
  <h1>第二题..... 在ProductList.vue组件中更新代码，并在商品列表中展示每个商品的名称、价格和平均评分（从reviews计算得出）</h1>

  <div class="product-list">
    <div class="product" v-for="product in products" :key="product.id">
      <h2>{{ product.name }}</h2>
      <h3>{{ product.description }}</h3>
      <p>\${{ product.price.toFixed(2) }}</p>
      <p>Average Rating: {{ averageRating(product.reviews) }}</p>
      -+--------------------------------------------------------------
    </div>
  </div>
</div>
</template>

<script>
export default {
  data() {
    return {
      products: [],
      data:{ }
    };
  },
  created() {
    this.fetchProducts();
  },
  methods: {
    fetchProducts() {
      this.data = {
        status: "success",
        data: [{
          id: 1,
          name: "Product 1",
          description: "Description for Product 1",
          price: 99.99,
          category: {
            id: 1,
            name: "Electronics"

          },
          images: ["image1.jpg", "image2.jpg"],
          reviews: [{
            id: 1,
            rating: 4,
            comment: "Great product!",
            author: "John Doe"

          },{
            id: 2,
            rating: 5,
            comment: "Great product111111!",
            author: "John Doe1111"

          }]
          
        },
        {
          id: 2,
          name: "Product 2",
          description: "Description for Product 1",
          price: 99.99,
          category: {
            id: 1,
            name: "Electronics"

          },
          images: ["image1.jpg", "image2.jpg"],
          reviews: [{
            id: 1,
            rating: 4,
            comment: "Great product!",
            author: "John Doe"

          }]
          },
          {
          id: 3,
          name: "Product 3",
          description: "Description for Product 1",
          price: 99.99,
          category: {
            id: 1,
            name: "Electronics"

          },
          images: ["image1.jpg", "image2.jpg"],
          reviews: [{
            id: 1,
            rating: 4,
            comment: "Great product!",
            author: "John Doe"

          }]
        }]
      }

this.products=this.data.data


    },
    averageRating(reviews) {
      if (!reviews || reviews.length === 0) return 'No reviews';
      const sum = reviews.reduce((accumulator, review) => accumulator + review.rating, 0);
      return (sum / reviews.length).toFixed(1);
    }
  }
};
</script>

<style></style>