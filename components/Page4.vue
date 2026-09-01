<template>
  <div class="pipeline">
    <v-click>
      <div class="stage">
        <div class="box">3.222 Türkçe Metin</div>
        <div class="arrow">↓</div>
        <div class="box">İnsan Gözetimi</div>
      </div>
    </v-click>

    <v-click>
      <div class="stage">
        <div class="arrow arrow-connector">↓</div>
        <div class="box box-model">BERTürk</div>
        <div class="arrow">↓</div>
        <div class="box box-model">Fine-tuning</div>
      </div>
    </v-click>

    <v-click>
      <div class="stage">
        <div class="arrow arrow-connector">↓</div>
        <div class="box">Etik / Etik Dışı</div>
        <div class="arrow">↓</div>
        <div class="box box-final">Web Tabanlı Sistem</div>
      </div>
    </v-click>
  </div>
</template>

<style scoped>
.pipeline {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 1rem;
}

.stage {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.box {
  padding: 0.70rem;
  border-radius: 10px;
  background: rgba(124, 58, 237, 0.07);
  border: 1px solid rgba(124, 58, 237, 0.25);
  font-size: 1.15rem;
  font-weight: 600;
  min-width: 260px;
  text-align: center;
}

.box-model {
  background: rgba(124, 58, 237, 0.12);
  border-color: rgba(124, 58, 237, 0.4);
  color: #7c3aed;
}

.box-final {
  background: #7c3aed;
  border-color: #7c3aed;
  color: white;
  font-size: 1.25rem;
}

.arrow {
  font-size: 1.3rem;
  color: #7c3aed;
  opacity: 0.55;
}

.arrow-connector {
  margin-top: -0.1rem;
}
</style>