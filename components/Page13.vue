<template>
  <div class="qr-wrap">
    <div class="qr-stage">
      <div class="qr-block">
        <div class="qr-heading">
          <span class="qr-kicker">QR KODU TARAYIN</span>
          <span class="qr-action">Modeli deneyin</span>
        </div>
        <img src="/qr-demo.png" class="qr-img" alt="Canlı sistem QR kodu" />
        <div class="qr-url">etikmail.kubrainy.me</div>
      </div>

      <div class="qr-block">
        <div class="qr-heading">
          <span class="qr-kicker">QR KODU TARAYIN</span>
          <span class="qr-action"> Benimle iletişime geçin</span>
        </div>
        <img src="/kubrainy-me.png" class="qr-img" alt="İletişim QR kodu" />
        <div class="qr-url">kubrainy.me</div>
      </div>
    </div>

    <div class="resources">
      <div class="resource-title">Kaynaklar</div>
      <div class="resource-item">Veri seti · huggingface.co/datasets/kubrainy/etik-mail-dataset</div>
      <div class="resource-item">Model · huggingface.co/kubrainy/etik-mail-toxic-model</div>
      <div class="resource-item">Kod · github.com/kubrainy/etikmail</div>
    </div>
  </div>
</template>

<style scoped>
.qr-wrap {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2.5rem;
}

.qr-stage {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  gap: 5rem;
}

.qr-block {
  width: 260px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.qr-heading {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.35rem;
  margin-bottom: 1.2rem;
}

.qr-kicker {
  font-size: 0.8rem;
  font-weight: 700;
  letter-spacing: 0.16em;
  color: #9b8bd0;
}

.qr-action {
  font-size: 1.7rem;
  font-weight: 800;
  line-height: 1.2;
  white-space: nowrap;
}

.qr-img {
  width: 240px;
  height: 240px;
  border-radius: 16px;
  border: 1px solid rgba(124, 58, 237, 0.25);
  padding: 0.8rem;
  background: white;
}

.qr-url {
  margin-top: 0.5rem;
  font-size: 1.05rem;
  font-weight: 600;
  color: #7c3aed;
}

.resources {
  text-align: center;
  opacity: 0.45;
}

.resource-title {
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  margin-bottom: 0.3rem;
}

.resource-item {
  font-size: 0.68rem;
  line-height: 1.5;
}
</style>
