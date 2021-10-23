<template>
  <div class="slider">
    <div id="carouselExampleIndicators" class="carousel slide" data-bs-ride="carousel">
      <div class="carousel-indicators">
        <button
          type="button"
          data-bs-target="#carouselExampleIndicators"
          data-bs-slide-to="0"
          class="active"
          aria-current="true"
          aria-label="Slide 1"
        ></button>
        <button
          type="button"
          data-bs-target="#carouselExampleIndicators"
          data-bs-slide-to="1"
          aria-label="Slide 2"
        ></button>
      </div>
      <div class="carousel-inner">
        <div class="carousel-item active">
          <img
            src="images/slider1.webp"
            class="responsive"
            alt="..."
            width="745"
            height="276"
          />
        </div>
        <div class="carousel-item">
          <img
            src="images/slider2.webp"
            class="responsive"
            alt="..."
            width="745"
            height="276"
          />
        </div>
      </div>
      <div class="carousel-control-back">
        <button
          class="carousel-control-prev"
          type="button"
          data-bs-target="#carouselExampleIndicators"
          data-bs-slide="prev"
        >
          <span class="carousel-icon-prev"><i class="fas fa-chevron-left"></i></span>
          <span class="visually-hidden">Previous</span>
        </button>
      </div>
      <button
        class="carousel-control-next"
        type="button"
        data-bs-target="#carouselExampleIndicators"
        data-bs-slide="next"
      >
        <span class="carousel-icon-next"><i class="fas fa-chevron-right"></i></span>
        <span class="visually-hidden">Next</span>
      </button>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.carousel-indicators button {
  width: 12px;
  height: 12px;
  border: 1px solid #d7d7d7;
  background-color: #fff;
  border-radius: 50%;
  margin: 0 8px;
  opacity: 1;
}
.carousel-indicators .active {
  background-color: #fa0050;
}

.carousel-icon-prev {
  padding: 11px 6px;
  background-color: rgba(0, 0, 0, 0.4);
  box-shadow: none;
  border: none;
  border-radius: 0 4px 4px 0;
  position: absolute;
  left: 0;
  display: flex;
  align-items: center;
}
.carousel-icon-next {
  padding: 11px 6px;
  background-color: rgba(0, 0, 0, 0.4);
  box-shadow: none;
  border: none;
  border-radius: 4px 0 0 4px;
  position: absolute;
  right: 0;
  display: flex;
  align-items: center;
}
.carousel-icon-prev:hover,
.carousel-icon-next:hover {
  color: #fa0050;
}
.carousel-icon-prev .fa-chevron-left,
.carousel-icon-next .fa-chevron-right {
  font-size: 10px;
}
</style>
