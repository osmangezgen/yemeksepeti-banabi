<template>
  <div class="content-navbar" style="display: flex">
    <div class="available-adress">
      <img src="images/home.png" alt="" width="19" />
      <div>
        <div>Ev</div>
        <span>İstanbul (Beşiktaş..</span>
      </div>
      <a href="">Değiştir</a>
    </div>
    <div class="package-info">
      <div class="package-box">
        <img src="images/delivery-time.svg" alt="" />
        <div>
          <h4>Teslimat Süresi</h4>
          <span>8 DK</span>
        </div>
      </div>
      <div class="package-box">
        <img src="images/basket-amoun.svg" alt="" />
        <div>
          <h4>Min. Sepet Tutarı</h4>
          <span>25,00 TL</span>
        </div>
      </div>
      <div class="package-box">
        <img src="images/delivery.svg" alt="" />
        <div>
          <h4 class="d-flex">
            <div>Gönderim Ücreti</div>
            <img class="info" src="images/info.png" alt="" width="16" height="16" />
            <div class="dropdown">
              <div class="package-tooltip">
                <h2>Gönderim Ücreti</h2>
                <div class="tooltip-description">
                  Sepet tutarınız arttıkça gönderim ücreti azalır. 100,00 TL ve üzeri
                  alışverişlerinizde ise gönderim ücreti ödemezsiniz.
                </div>
                <hr />
                <div class="row">
                  <div class="col">
                    <h5>Sepet Ücreti</h5>
                    <div>
                      <p>0,00 TL - 4,99 TL</p>
                      <p>50,00 TL - 74,99 TL</p>
                      <p>75,00 TL - 99,99 TL</p>
                      <p>100,00 TL ve üzeri</p>
                    </div>
                  </div>
                  <div class="col">
                    <h5>Gönderim Ücreti</h5>
                    <div>
                      <p>4,99 TL</p>
                      <p>3,99 TL</p>
                      <p>2,99 TL</p>
                      <p>Ücretsiz</p>
                    </div>
                  </div>
                </div>
                <div class="arrow">
                  <i class="fas fa-sort-up"></i>
                </div>
              </div>
            </div>
          </h4>
          <span>0,00 - 4,99 TL</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style></style>
