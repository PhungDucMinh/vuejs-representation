// Vue.component('product-row', {
// 	template: `
//    	<tr>
//     <td><span :style="{color: product.stocked ? 'red': ''}">{{product.name}}</span></td>
//         <td>{{product.price}}</td>
//       </tr>
//   `,
//   props: ["product"]
// })

<template>
     	<tr>
    <td><span :style="{color: product.stocked ? 'red': ''}">{{product.name}}</span></td>
        <td>{{product.price}}</td>
      </tr>
</template>
<script>
export default {
  name: "Product",
  props: ["product"]
};
</script>
