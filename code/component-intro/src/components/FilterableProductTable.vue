<template>
  <div>
        <search-bar></search-bar>
        <product-table v-bind:products="products"></product-table>
	</div>
</template>

<script>
import SearchBar from './SearchBar';
import ProductTable from './ProductTable';

export default {
  name: "FilterableProductTable",
  components: {SearchBar, ProductTable},
  data() {
    return {
      msg: "Welcome to Your Tech Talk",
      products: []
    };
  },
  created: function() {
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
  }
};
</script>

// Vue.component('product-row', {
// 	template: `
//    	<tr>
//     <td><span :style="{color: product.stocked ? 'red': ''}">{{product.name}}</span></td>
//         <td>{{product.price}}</td>
//       </tr>
//   `,
//   props: ["product"]
// })


// Vue.component('search-bar', {
//   template: `
// 	<form>
//         <input type="text" placeholder="Search..." />
//         <p>
//           <input type="checkbox" />
//           Only show products in stock
//         </p>
//       </form>
//   `
// })

// Vue.component('product-table', {
//   template: `
// 	<table>
//         <thead>
//           <tr>
//             <th>Name</th>
//             <th>Price</th>
//           </tr>
//         </thead>
//         <tbody>
//         	<product-row v-for="product in products" :key="product.name" :product="product"></product-row>
//         </tbody>
//       </table>
//   `,
//   props: {
//   	products: {
//     	type: Array
//     }
//   },
//   data: function() {
//   	return {
//     	productCategories: [],
//     }
//   },
//   created: function() {
  	
//   }
// })


