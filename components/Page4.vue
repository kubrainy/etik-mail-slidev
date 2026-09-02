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
  animation: stage-in 0.6s cubic-bezier(0.22, 1, 0.36, 1) both;
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
  animation: box-in 0.5s ease both;
}

.box-model {
  background: rgba(124, 58, 237, 0.12);
  border-color: rgba(124, 58, 237, 0.4);
  color: #7c3aed;
  animation:
    box-in 0.5s ease both,
    glow-pulse 2.4s ease-in-out infinite 0.6s;
}

.box-final {
  background: #7c3aed;
  border-color: #7c3aed;
  color: white;
  font-size: 1.25rem;
  animation:
    box-in 0.5s ease both,
    final-pop 0.5s cubic-bezier(0.34, 1.56, 0.64, 1) 0.35s both;
}

.arrow {
  font-size: 1.3rem;
  color: #7c3aed;
  opacity: 0.55;
  animation: arrow-flow 1.4s ease-in-out infinite;
}

.arrow-connector {
  margin-top: -0.1rem;
}

@keyframes stage-in {
  from {
    opacity: 0;
    transform: translateY(24px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes box-in {
  from {
    opacity: 0;
    transform: scale(0.92);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

@keyframes arrow-flow {
  0%, 100% {
    transform: translateY(0);
    opacity: 0.4;
  }
  50% {
    transform: translateY(3px);
    opacity: 0.9;
  }
}

@keyframes glow-pulse {
  0%, 100% {
    box-shadow: 0 0 0 rgba(124, 58, 237, 0);
  }
  50% {
    box-shadow: 0 0 18px rgba(124, 58, 237, 0.35);
  }
}

@keyframes final-pop {
  0% {
    transform: scale(0.85);
  }
  60% {
    transform: scale(1.06);
  }
  100% {
    transform: scale(1);
  }
}
</style>