<template>
  <div class="">
    <Header/>


            <div class="header-two">
          <h2 class="header-two__header-title">Каталог</h2>
          <div class="header-two__sort">
            <p>Сортировать по </p>
            <select v-model="selected">
              <option value="По популярности">{{selected}}</option>
                <option v-for="(item, index) in sortItems" :key="index" :value="item.text">
                {{ item.text }} 
              </option>
            </select>
              <!-- <span>Выбрано: {{ selected }}</span> -->
          </div>
        </div>

    <div class="wrapper-main-content">
      <div class="wrapper-main-content__left-bar">
        <LeftBar/>
      </div>

      <div class="wrapper-main-content__main-content">
            <Nuxt />
            <ItemBackpack/>
      </div>
    </div>

    <RightSidebar/>
  </div>
</template>

<script>
import Header from "@/components/Header.vue"
import RightSidebar from "@/components/RightSidebar.vue"
import LeftBar from "@/components/LeftBar.vue"
// для теста
import ItemBackpack from '@/components/backpack/ItemBackpack.vue'
export default {
components:{
  Header,
  RightSidebar,
  LeftBar,
  ItemBackpack
},
data() {
  return {
    sortItems:[
      { text: 'По цене', value: 'По цене' },
      // { text: 'По популярности', value: 'По популярности' },
    ],
    selected: 'По популярности'
  }
}
}
</script>
<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.wrapper-main-content {
  display: flex;
  padding-left: 105px;
  padding-right: 105px;

  &__left-bar {
background: pink;
width:20%;
  }

  &__main-content {
// background: blue;
width:80%;
  }
}

.header-two {
  display: flex;
  justify-content: space-between;
  padding-left: 105px;
  padding-right: 105px;
  padding-top: 20px;
  padding-bottom: 20px;

  &__sort {
    display: flex;
    align-items: center;
  }
}
</style>
