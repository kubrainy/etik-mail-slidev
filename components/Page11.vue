<template>
  <div class="split-wrap">
    <div class="contrib-col">
      <div class="col-title">Katkımız</div>

      <v-clicks>
        <div class="contrib-item">
          <span class="num">01</span>
          <span class="text">Türkçe kurumsal iletişime özgü veri seti</span>
        </div>
        <div class="contrib-item">
          <span class="num">02</span>
          <span class="text">BERTürk tabanlı etik dil sınıflandırması</span>
        </div>
        <div class="contrib-item">
          <span class="num">03</span>
          <span class="text">Pasif-agresif / örtük dil tespiti</span>
        </div>
        <div class="contrib-item">
          <span class="num">04</span>
          <span class="text">Gerçek zamanlı prototip</span>
        </div>
      </v-clicks>
    </div>

    <div class="col-divider" />

    <v-click>
      <div class="next-col">
        <div class="col-title next-title">Sonraki Adım</div>
        <div class="next-item">Daha geniş gerçek dünya verisi</div>
        <div class="next-item">Farklı sektörler</div>
        <div class="next-item">Çok sınıflı etik dışı dil</div>
        <div class="next-item">Bağımsız veri kümeleri</div>
      </div>
    </v-click>
  </div>
</template>

<style scoped>
.split-wrap {
  display: flex;
  align-items: flex-start;
  justify-content: center;
  gap: 3rem;
  margin-top: 1.5rem;
}

.col-title {
  font-weight: 800;
  font-size: 1.2rem;
  margin-bottom: 1.1rem;
  color: #7c3aed;
}

.contrib-col {
  min-width: 380px;
}

.contrib-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 0.6rem 0;
  border-bottom: 1px solid rgba(120, 120, 120, 0.15);
  text-align: left;
}

.num {
  font-size: 1.3rem;
  font-weight: 800;
  color: #7c3aed;
  opacity: 0.5;
  min-width: 2.2rem;
}

.text {
  font-size: 1.05rem;
  font-weight: 600;
}

.col-divider {
  width: 1px;
  align-self: stretch;
  background: rgba(120, 120, 120, 0.2);
}

.next-col {
  min-width: 220px;
  text-align: left;
  opacity: 0.85;
}

.next-title {
  font-size: 1rem;
  opacity: 0.6;
  color: inherit;
}

.next-item {
  font-size: 0.9rem;
  padding: 0.35rem 0;
  opacity: 0.75;
}

.next-item::before {
  content: "· ";
  opacity: 0.5;
}
</style>