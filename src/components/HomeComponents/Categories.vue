<template>
  <div class="categories">
    <h3>Kategoriler</h3>
    <div>
      <div class="categories-card">
        <div class="favorites">
          <span>Favorilerim</span>
        </div>
        <div
          class="d-flex align-items-center"
          v-for="item in categoryItem"
          :key="item.id"
        >
          <img :src="item.imageUrl" alt="" width="96" height="106" />
          <span>{{ item.title }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      categoryItem: [
        {
          id: 1,
          imageUrl: "images/categoryNew.jpeg",
          title: "Yeni Ürünler",
        },
        {
          id: 2,
          imageUrl: "images/category1.jpeg",
          title: "Su",
        },
        {
          id: 3,
          imageUrl: "images/category2.jpeg",
          title: "Atıştırmalık",
        },
        {
          id: 9,
          imageUrl: "images/category3.jpeg",
          title: "Dondurma",
        },
        {
          id: 5,
          imageUrl: "images/category4.jpeg",
          title: "İçecek",
        },
        {
          id: 6,
          imageUrl: "images/category5.jpeg",
          title: "Süt & Kahvaltılık",
        },
        {
          id: 7,
          imageUrl: "images/category6.jpeg",
          title: "Meyve & Sebze",
        },
        {
          id: 4,
          imageUrl: "images/category7.jpeg",
          title: "Fırından",
        },
        {
          id: 8,
          imageUrl: "images/category8.webp",
          title: "Hazır & Donuk Gıda",
        },
        {
          id: 10,
          imageUrl: "images/category10.jpeg",
          title: "Taze Yemek",
        },
        {
          id: 11,
          imageUrl: "images/category11.jpeg",
          title: "Temel Gıda",
        },
        {
          id: 12,
          imageUrl: "images/category12.jpeg",
          title: "Fit & Form",
        },
        {
          id: 13,
          imageUrl: "images/category13.jpeg",
          title: "Kişisel Bakım",
        },
        {
          id: 14,
          imageUrl: "images/category14.jpeg",
          title: "Ev Bakım",
        },
        {
          id: 15,
          imageUrl: "images/category15.jpeg",
          title: "Evcil Hayvan",
        },
      ],
    };
  },
};
</script>

<style></style>
