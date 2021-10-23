<template>
  <div class="sidebar">
    <div class="user-panel" role="button" :class="userPanel" @click="userPanelClick">
      <div class="user-profile">
        <img src="images/user.png" alt="" width="36" height="36" />
        <span>OSMAN GEZGEN</span>
        <i class="fas fa-chevron-down"></i>
      </div>

      <div class="user-profile-menu">
        <div><a href="">Bilgilerim</a></div>
        <div><a href="">Önceki Siparişlerim</a></div>
        <div><a href="">Favorilerim</a></div>
        <div><a href="">Adreslerim</a></div>
        <div><a href="">Kuponlarım</a></div>
        <div class="user-logout"><a href="">Çıkış Yap</a></div>
      </div>
    </div>

    <div class="basket">
      <div class="header">
        <span
          >SEPETİM
          <span
            v-if="basketItemsSide.length > 0"
            style="font-size: 12px; font-weight: 400"
            >({{ basketItemsSide.length }} Ürün)</span
          >
          <span
            v-if="basketItemsSide.length > 0"
            @click="deleteItemAll"
            style="position: absolute; right: 10px; cursor: pointer"
            ><i class="fas fa-trash-alt me-1"></i></span
        ></span>
      </div>
      <div class="location">İstanbul (Beşiktaş Mah.)</div>
      <div class="list">
        <div v-if="basketItemsSide.length > 0">
          <div class="basket-item" v-for="item in basketItemsSide" :key="item.id">
            <img :src="item.imageUrl" alt="" height="40" />
            <h3>{{ item.title }}</h3>
            <div class="basket-action">
              <div @click="deleteItem(item.id)" v-if="item.total == 1">
                <i class="fas fa-trash-alt me-1"></i>
              </div>
              <div v-else @click="itemMinus(item.id)">
                <i class="fas fa-minus me-1"></i>
              </div>
              <span>{{ item.total }}</span>
              <div @click="itemPlus(item.id)"><i class="fas fa-plus ms-1"></i></div>
            </div>
            <div class="basket-price">
              <h3>{{ (item.oldPrice * item.total).toFixed(2) }} TL</h3>
              <h3>{{ (item.price * item.total).toFixed(2) }} TL</h3>
            </div>
          </div>
          <div class="basket-allPrice">
            <div>
              <span>Toplam Tutar:</span>
              <span>{{ allOldPrice.toFixed(2) }} TL</span>
            </div>
            <div>
              <span>İndirimli Tutar:</span>
              <span>{{ allPrice.toFixed(2) }} TL</span>
            </div>
            <button :class="minBasket > 0 ? null : 'greenBasket'">Sepeti Onayla</button>
            <div class="basket-message" v-if="minBasket > 0">
              Minimum sepet tutarının altındasınız. Siparişinizi tamamlamak için
              sepetinize
              <b>{{ minBasket.toFixed(2) }}</b> değerinde daha ürün eklemeniz
              gerekmektedir.
            </div>
          </div>
        </div>
        <div class="empty" v-else>
          <img src="images/empty.svg" alt="" />
          <span>Sepetiniz henüz boş.</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["basketItemsSide"],
  data() {
    return {
      userPanel: null,
      basketItems: [
        {
          id: 1,
          imageUrl: "images/store4.jpeg",
          title: "3xNestle Kitkat Paketi",
          oldPrice: 8.1,
          price: 6.5,
        },
        {
          id: 3,
          imageUrl: "images/store4.jpeg",
          title: "3xNestle Kitkat Paketi",
          oldPrice: 8.1,
          price: 5.2,
        },
      ],
      test: [],
    };
  },
  methods: {
    userPanelClick() {
      if (this.userPanel == null) this.userPanel = "user-panel-active";
      else this.userPanel = null;
    },
    deleteItem(id) {
      this.$emit("delete-item", id);
    },
    deleteItemAll() {
      this.$emit("delete-item-all");
    },
    itemPlus(id) {
      this.$emit("item-plus", id);
    },
    itemMinus(id) {
      this.$emit("item-minus", id);
    },
  },
  computed: {
    allPrice() {
      let result = 0;
      this?.basketItemsSide.forEach((element) => {
        result = result + element.price * element.total;
      });
      return result;
    },
    allOldPrice() {
      let result = 0;
      this?.basketItemsSide.forEach((element) => {
        result = result + element.oldPrice * element.total;
      });
      return result;
    },
    minBasket() {
      let result = 25;
      result = result - this.allPrice;
      return result;
    },
  },
};
</script>

<style></style>
