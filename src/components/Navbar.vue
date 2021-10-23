<template>
  <div class="sticky-top">
    <div class="navbar-m">
      <div class="navbar-back">
        <div class="header-logo">
          <div href="#">
            <img src="images/banabi-logo.svg" alt="" width="auto" height="30" />
          </div>
        </div>

        <div class="header-search">
          <img class="search" src="images/search.png" alt="" width="27" height="27" />
          <input type="text" placeholder="Banabi'de Ara" />
        </div>

        <div class="content">
          <div class="dropdown">
            <a href="">
              <span>Tüm Kategoriler</span>
              <i class="fas fa-chevron-down ms-2"></i>
            </a>
          </div>
        </div>

        <div class="offer">
          <a href="">
            <img class="me-2" src="images/campaign.svg" alt="" />
            <span>Tüm Kampanyalar</span>
          </a>
        </div>
      </div>
    </div>
  </div>
  <div class="clear"></div>
</template>

<script>
export default {};
</script>

<style scoped>
.form-control:focus {
  border: none;
  box-shadow: none;
}
input {
  border-radius: 24px;
  height: 40px;
  width: 424.14px;
  padding: 0 50px;
  border: none;
  font-size: 12px;
  font-weight: 400;
  color: #4a4a4a;
  overflow: visible;
}
.search {
  position: absolute;
  top: 7px;
  left: 15px;
  color: #4a4a4a;
  opacity: 0.6;
  font-family: "Roboto", sans-serif;
  font-weight: 400;
}
input::-webkit-input-placeholder {
  opacity: 0.6;
}
</style>
