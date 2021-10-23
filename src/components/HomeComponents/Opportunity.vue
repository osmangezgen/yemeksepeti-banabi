<template>
  <div class="opportunity">
    <h3>
      Fırsat Reyonu <span>Tüm Fırsatlar <i class="fas fa-chevron-right"></i></span>
    </h3>
    <div>
      <div
        id="carouselExampleControls"
        class="carousel slide"
        data-bs-ride="carousel"
        data-bs-interval="false"
      >
        <div class="carousel-inner">
          <div class="carousel-item active">
            <div class="opportunity-card">
              <div
                v-for="item in opportunityItem"
                :key="item.id"
                class="itemSelected-menu-hover"
              >
                <span v-if="item.basketStatus == true" class="add-item-count"
                  >{{ item.total }}
                </span>
                <span class="itemSelected-menu" v-if="item.basketStatus == true">
                  <div @click="deleteItem(item)" v-if="item.total == 1">
                    <i class="fas fa-trash-alt me-1 itemSelected-menu-icon"></i>
                  </div>
                  <div v-else @click="itemMinus(item.id)">
                    <i class="fas fa-minus me-1 itemSelected-menu-icon"></i>
                  </div>
                  <div class="itemSelected-menu-text">
                    <span>{{ item.total }}</span>
                  </div>
                  <div @click="itemPlus(item.id)">
                    <i class="fas fa-plus ms-1 itemSelected-menu-icon"></i>
                  </div>
                </span>
                <div :class="item.basketStatus ? itemSelected : null">
                  <div class="d-flex justify-content-center">
                    <span class="flag"
                      ><img src="images/flag.svg" alt="" width="61" height="55"
                    /></span>
                    <span
                      v-if="item.basketStatus == false"
                      class="add-item"
                      @click="addItem(item)"
                      ><i class="fas fa-plus"></i
                    ></span>
                    <img :src="item.imageUrl" alt="" width="122" height="65" />
                  </div>
                  <h5>{{ item.title }}</h5>
                  <span class="price">
                    <small>{{ item.oldPrice }}</small>
                    <div>{{ item.price }}</div>
                  </span>
                </div>
              </div>
            </div>
          </div>
          <div class="carousel-item">
            <div class="opportunity-card">
              <div
                v-for="item in opportunityItem"
                :key="item.id"
                class="itemSelected-menu-hover"
              >
                <span v-if="item.basketStatus == true" class="add-item-count"
                  >{{ item.total }}
                </span>
                <span class="itemSelected-menu" v-if="item.basketStatus == true">
                  <div @click="deleteItem(item)" v-if="item.total == 1">
                    <i class="fas fa-trash-alt me-1 itemSelected-menu-icon"></i>
                  </div>
                  <div v-else @click="itemMinus(item.id)">
                    <i class="fas fa-minus me-1 itemSelected-menu-icon"></i>
                  </div>
                  <div class="itemSelected-menu-text">
                    <span>{{ item.total }}</span>
                  </div>
                  <div @click="itemPlus(item.id)">
                    <i class="fas fa-plus ms-1 itemSelected-menu-icon"></i>
                  </div>
                </span>
                <div :class="item.basketStatus ? itemSelected : null">
                  <div class="d-flex justify-content-center">
                    <span class="flag"
                      ><img src="images/flag.svg" alt="" width="61" height="55"
                    /></span>
                    <span
                      v-if="item.basketStatus == false"
                      class="add-item"
                      @click="addItem(item)"
                      ><i class="fas fa-plus"></i
                    ></span>
                    <img :src="item.imageUrl" alt="" width="122" height="65" />
                  </div>
                  <h5>{{ item.title }}</h5>
                  <span class="price">
                    <small>{{ item.oldPrice }}</small>
                    <div>{{ item.price }}</div>
                  </span>
                </div>
              </div>
            </div>
          </div>
        </div>
        <button
          class="carousel-control-prev"
          type="button"
          data-bs-target="#carouselExampleControls"
          data-bs-slide="prev"
          id="carousel-control"
        >
          <span class="carousel-icon-prev"><i class="fas fa-chevron-left"></i></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button
          class="carousel-control-next"
          type="button"
          data-bs-target="#carouselExampleControls"
          data-bs-slide="next"
          id="carousel-control"
        >
          <span class="carousel-icon-next"><i class="fas fa-chevron-right"></i></span>
          <span class="visually-hidden">Next</span>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["itemSelected"],
  data() {
    return {
      opportunityItem: [
        {
          id: 1,
          imageUrl: "images/store1.jpeg",
          title: "Lay's & Lipton Ice Tea & Nogger Paketi",
          oldPrice: 15.5,
          price: 12.4,
          total: 1,
          basketStatus: false,
        },
        {
          id: 2,
          imageUrl: "images/store2.jpeg",
          title: "Eti Popkek Mini Muzlu",
          oldPrice: 5.2,
          price: 2.9,
          total: 1,
          basketStatus: false,
        },
        {
          id: 3,
          imageUrl: "images/store3.jpeg",
          title: "Eti Paykek Şekl-i Şahane Çikolata Soslu Fındıklı Kek",
          oldPrice: 8.2,
          price: 6,
          total: 1,
          basketStatus: false,
        },
        {
          id: 4,
          imageUrl: "images/store4.jpeg",
          title: "3xNestle Kitkat Paketi",
          oldPrice: 15,
          price: 12.4,
          total: 1,
          basketStatus: false,
        },
        {
          id: 5,
          imageUrl: "images/store5.jpeg",
          title: "Algida Milka Cup & Cornetto Milka Paketi",
          oldPrice: 10,
          price: 15.5,
          total: 1,
          basketStatus: false,
        },
      ],
    };
  },
  methods: {
    addItem(item) {
      setTimeout(() => {
        item.basketStatus = true;
      }, 50);
      this.$emit("basket-item", item);
    },
    deleteItem(item) {
      item.basketStatus = false;
      this.$emit("delete-item", item.id);
    },
    itemPlus(id) {
      this.$emit("item-plus", id);
    },
    itemMinus(id) {
      this.$emit("item-minus", id);
    },
  },
  watch: {
    itemSelected() {
      this.opportunityItem.forEach((element) => {
        element.basketStatus = false;
      });
    },
  },
};
</script>

<style scoped>
#carousel-control {
  opacity: 1;
  width: 0;
}
.carousel-icon-prev {
  width: 28px;
  height: 28px;
  border-radius: 4px;
  border: 1px solid #ddd;
  background-color: #fff;
  padding: 6px;
  transition: all 0.3s;
  position: absolute;
  left: 0;
  display: flex;
  align-items: center;
  color: grey;
  opacity: 0.6;
  box-shadow: 0 2px 4px #d5d5d5;
}
.carousel-icon-next {
  width: 28px;
  height: 28px;
  border-radius: 4px;
  border: 1px solid #ddd;
  background-color: #fff;
  padding: 6px;
  transition: all 0.3s;
  position: absolute;
  right: 0;
  display: flex;
  align-items: center;
  color: grey;
  opacity: 0.6;
  box-shadow: 0 2px 4px #d5d5d5;
}
.carousel-icon-prev:hover,
.carousel-icon-next:hover {
  color: #fa0050;
  opacity: 1;
}
.carousel-icon-prev .fa-chevron-left,
.carousel-icon-next .fa-chevron-right {
  font-size: 15px;
}
</style>
