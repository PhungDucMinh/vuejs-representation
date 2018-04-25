<template>
  <table style="margin: 0 auto;">
        <thead>
          <tr>
            <th>Name</th>
            <th>Price</th>
          </tr>
        </thead>
        <tbody>
        	<product-row v-for="product in products" :key="product.name" :product="product"></product-row>
        </tbody>
      </table>
</template>
<script>
import ProductRow from "./ProductRow";
export default {
  name: "ProductTable",
  components: { ProductRow },
  props: {
    products: {
      type: Array
    }
  },
  data: function() {
    return {
      productCategories: []
    };
  },
  created: function() {}
};
</script>
