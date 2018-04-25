<template>
  <div>
        <search-bar 
            v-on:show-product-change="handleIsShowStockProductChange" 
            v-on:filter-text-change="handleFilterTextChange">
        </search-bar>
        <product-table v-bind:products="filteredProducts"></product-table>
	</div>
</template>

<script>
import SearchBar from "./SearchBar";
import ProductTable from "./ProductTable";

export default {
  name: "FilterableProductTable",
  components: { SearchBar, ProductTable },
  data() {
    return {
      products: [],
      isShowStockProduct: false,
      filterText: ""
    };
  },
  mounted: function() {
    this.products = [
      {
        category: "Sporting Goods",
        price: "$49.99",
        stocked: true,
        name: "Football"
      },
      {
        category: "Sporting Goods",
        price: "$9.99",
        stocked: true,
        name: "Baseball"
      },
      {
        category: "Sporting Goods",
        price: "$29.99",
        stocked: false,
        name: "Basketball"
      },
      {
        category: "Electronics",
        price: "$99.99",
        stocked: true,
        name: "iPod Touch"
      },
      {
        category: "Electronics",
        price: "$399.99",
        stocked: false,
        name: "iPhone 5"
      },
      {
        category: "Electronics",
        price: "$199.99",
        stocked: true,
        name: "Nexus 7"
      }
    ];
  },
  methods: {
    handleIsShowStockProductChange: function(isShowStockProduct) {
      this.isShowStockProduct = isShowStockProduct;
    },
    handleFilterTextChange: function(filterText) {
      this.filterText = filterText;
    }
  },
  computed: {
    filteredProducts: function() {
      return this.products.reduce(
        function(cummulator, currentProduct) {
          if (
            (!this.filterText ||
              currentProduct.name
                .toLowerCase()
                .indexOf(this.filterText.toLowerCase()) !== -1) &&
            (this.isShowStockProduct ? currentProduct.stocked === true : true)
          ) {
            cummulator.push(currentProduct);
          }

          return cummulator;
        }.bind(this),
        []
      );
    }
  }
};
</script>
