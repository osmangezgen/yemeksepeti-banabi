<template>
  <div class="home">
    <div class="row row-design">
      <div class="col-md-3">
        <sidebar
          class="sticky-sidebar"
          :basketItemsSide="basketItems"
          @delete-item="deleteItem"
          @delete-item-all="deleteItemAll"
          @item-plus="itemPlus"
          @item-minus="itemMinus"
        ></sidebar>
      </div>
      <!-- <div class="col-md-3"></div> -->
      <div class="col-md-9">
        <div class="content-navbar">
          <available-info></available-info>
          <main-slider></main-slider>
          <opportunity
            @basket-item="basketItem"
            @delete-item="deleteItem"
            @item-plus="itemPlus"
            @item-minus="itemMinus"
            :itemSelected="itemSelected"
          ></opportunity>
          <categories></categories>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Sidebar from "@/components/HomeComponents/Sidebar.vue";
import Availableİnfo from "@/components/HomeComponents/Availableİnfo.vue";
import mainSlider from "@/components/HomeComponents/mainSlider.vue";
import Opportunity from "@/components/HomeComponents/Opportunity.vue";
import Categories from "@/components/HomeComponents/Categories.vue";

export default {
  components: {
    Sidebar,
    "available-info": Availableİnfo,
    mainSlider,
    Opportunity,
    Categories,
  },
  data() {
    return {
      basketItems: [],
      itemSelected: "itemSelected",
    };
  },
  methods: {
    basketItem(item) {
      if (this.itemSelected == "") this.itemSelected = "itemSelected";
      this.basketItems.push(item);
    },
    deleteItem(id) {
      this.basketItems = this.basketItems.filter((x) => x.id !== id);
    },
    deleteItemAll() {
      this.basketItems.forEach((element) => {
        element.total = 1;
      });
      this.basketItems = [];
    },
    itemPlus(id) {
      let memory = [];
      this.basketItems.forEach((element) => {
        if (element.id == id) {
          element.total++;
          memory.push(element);
        } else {
          memory.push(element);
        }
      });
      this.basketItems = memory;
    },
    itemMinus(id) {
      let memory = [];
      this.basketItems.forEach((element) => {
        if (element.id == id) {
          element.total--;
          memory.push(element);
        } else {
          memory.push(element);
        }
      });
      this.basketItems = memory;
    },
  },
  watch: {
    basketItems() {
      if (this.basketItems.length == 0) {
        this.itemSelected = "";
      }
    },
  },
};
</script>
