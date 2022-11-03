<template>
  <div>
    <Nav />
    <Footer />
  </div>
</template>

<script>
export default {
  async created() {
    this.products = await this.$content("products").fetch();
    this.sale_items = await this.$content("products")
      .where({ onSale: true })
      .fetch();
  },
  data() {
    return {
      //key: value
      products: null,
      sale_items: null,
    };
  },
};
</script>

<style></style>
