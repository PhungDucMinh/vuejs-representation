<template>
  	<form>
        <input type="text" @change="handleFilterTextChange" placeholder="Search..." />
        <p>
          <input type="checkbox" @click="handleCheckBoxChange"/>
          Only show products in stock
        </p>
      </form>
</template>
<script>
export default {
  name: "SearchBar",
  data: function() {
    return {
      filterText: "",
      inStockOnly: false
    };
  },
  methods: {
    handleCheckBoxChange: function(event) {
      this.inStockOnly = event.target.checked;
      this.$emit("show-product-change", this.inStockOnly);
    },
    handleFilterTextChange: function(event) {
      this.filterText = event.target.value;
      this.$emit("filter-text-change", this.filterText);
    }
  }
};
</script>
