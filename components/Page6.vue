<template>
  <div class="stage-area">
    <div class="pipeline" v-click.hide="4">
      <div class="stage" v-click="1">
        <div class="box box-source">Claude + ChatGPT</div>
        <div class="arrow">↓</div>
        <div class="box box-source">Metin Üretimi</div>
      </div>

      <div class="stage" v-click="2">
        <div class="arrow">↓</div>
        <div class="review-box">
          <div class="review-title">İnsan İncelemesi</div>
          <div class="review-item">Doğallık kontrolü</div>
          <div class="review-item">Bağlam kontrolü</div>
          <div class="review-item">Tekrar kontrolü</div>
          <div class="review-item">Etiketleme</div>
        </div>
      </div>

      <div class="stage" v-click="3">
        <div class="arrow">↓</div>
        <div class="box box-final">Veri Seti</div>
      </div>
    </div>

    <div class="center-badge" v-click="4">
      BDM üretimi ≠ otomatik kabul
    </div>
  </div>
</template>

<style scoped>
.stage-area {
  position: relative;
  min-height: 420px;
  margin-top: 1.5rem;
}

.pipeline {
  position: absolute;
  inset: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.stage {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.box {
  padding: 0.7rem 2rem;
  border-radius: 10px;
  font-size: 1.1rem;
  font-weight: 600;
  min-width: 220px;
  text-align: center;
}

.box-source {
  background: rgba(120, 120, 120, 0.08);
  border: 1px solid rgba(120, 120, 120, 0.25);
  opacity: 0.85;
}

.box-final {
  background: #7c3aed;
  border: 1px solid #7c3aed;
  color: white;
  font-size: 1.2rem;
}

.arrow {
  font-size: 1.3rem;
  color: #7c3aed;
  opacity: 0.55;
  line-height: 1.5;
}

.review-box {
  padding: 1rem 1.8rem;
  border-radius: 14px;
  background: rgba(124, 58, 237, 0.1);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid rgba(124, 58, 237, 0.4);
  text-align: center;
  min-width: 240px;
}

.review-title {
  font-weight: 800;
  font-size: 1.1rem;
  color: #7c3aed;
  margin-bottom: 0.6rem;
}

.review-item {
  font-size: 0.95rem;
  opacity: 0.85;
  padding: 0.2rem 0;
}

.center-badge {
  position: absolute;
  inset: 0;
  margin: auto;
  width: fit-content;
  height: fit-content;
  padding: 1.2rem 2.4rem;
  border-radius: 999px;
  background: rgba(220, 38, 38, 0.08);
  border: 1px solid rgba(220, 38, 38, 0.3);
  color: #dc2626;
  font-weight: 700;
  font-size: 1.4rem;
  text-align: center;
  max-width: 560px;
}
</style>