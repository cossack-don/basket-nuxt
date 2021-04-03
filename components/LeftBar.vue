<template>
<div class="left-bar">
      <ul class="left-bar__list-items">
      <li class="left-bar__item" v-for="(item, index) in listLeftBar" :key="index">
          <nuxt-link :to="item.url">{{item.nameCategory}}</nuxt-link>
      </li>
  </ul>
</div>

</template>

<script>
export default {
data() {
    return {
        listLeftBar:[
            {
                url:'/backpack',
                nameCategory:'Рюкзаки'
            },
                        {
                url:'/t-shirts',
                nameCategory:'Футболки'
            },
                        {
                url:'/shirts',
                nameCategory:'Рубашки'
            }
        ]
    }
}
}
</script>

<style>
ul {
    list-style-type: none;
}

.left-bar__item {
    margin-bottom: 15px;
}
</style>