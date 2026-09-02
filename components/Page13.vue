<template>
  <div class="qr-stage">
      <div class="qr-block" v-click="1">
        <img src="/qr-demo.png" class="qr-img" alt="Canlı sistem QR kodu" />
        <div class="qr-url">etikmail.kubrainy.me</div>
      </div>
  </div>

  <div class="resources" v-click="1">
    <div class="resource-title">Kaynaklar</div>
    <div class="resource-item">Veri seti · huggingface.co/datasets/kubrainy/etik-mail-dataset</div>
    <div class="resource-item">Model · huggingface.co/kubrainy/etik-mail-toxic-model</div>
    <div class="resource-item">Kod · github.com/kubrainy/etikmail</div>
  </div>
</template>

<style scoped>
.qr-stage {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 300px;
  margin-top: 1rem;
}

.qr-block {
  text-align: center;
}

.qr-img {
  width: 220px;
  height: 220px;
  border-radius: 16px;
  border: 1px solid rgba(124, 58, 237, 0.25);
  padding: 0.8rem;
  background: white;
}

.qr-label {
  margin-top: 1.2rem;
  font-size: 1.3rem;
  font-weight: 700;
}

.qr-url {
  margin-top: 0.3rem;
  font-size: 1.05rem;
  font-weight: 600;
  color: #7c3aed;
}

.resources {
  margin-top: 1.5rem;
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