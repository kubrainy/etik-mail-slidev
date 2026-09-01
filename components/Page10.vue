<template>
  <div class="demo-wrap">
    <div class="mail-client">
      <div class="mail-header">Etik Model Kontrolü</div>
      <div class="mail-field">
        <span class="field-label">Kime:</span>
        <span class="field-value">ekip@sirket.com</span>
      </div>
      <div class="mail-field">
        <span class="field-label">Konu:</span>
        <span class="field-value">Rapor Hk.</span>
      </div>
      <div class="mail-body">
        "Bu işi hâlâ bitirmediğinizi görüyorum..."
      </div>
      <div class="send-btn" :class="{ blocked: showBlocked }">
        {{ showBlocked ? 'Gönderim Engellendi' : 'GÖNDER' }}
      </div>
    </div>

    <div class="flow-col">
      <v-click @click="stage = 1">
        <div class="flow-step" :class="{ active: stage >= 1 }">
          <span class="dot" /> Analiz Ediliyor
        </div>
      </v-click>

      <v-click @click="stage = 2">
        <div class="flow-step step-warn" :class="{ active: stage >= 2 }">
          <span class="dot dot-warn" /> Etik Dışı
        </div>
      </v-click>

      <v-click @click="stage = 3">
        <div class="flow-step step-block" :class="{ active: stage >= 3 }">
          <span class="dot dot-block" /> Gönderim Engellendi
        </div>
      </v-click>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const stage = ref(0)
const showBlocked = computed(() => stage.value >= 3)
</script>

<style scoped>
.demo-wrap {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 3rem;
  margin-top: 1.5rem;
  flex-wrap: wrap;
}

.mail-client {
  width: 320px;
  padding: 1.2rem;
  border-radius: 14px;
  background: rgba(124, 58, 237, 0.05);
  border: 1px solid rgba(124, 58, 237, 0.2);
  text-align: left;
}

.mail-header {
  font-weight: 700;
  font-size: 1.05rem;
  margin-bottom: 0.8rem;
  opacity: 0.85;
}

.mail-field {
  display: flex;
  gap: 0.5rem;
  font-size: 0.9rem;
  padding: 0.3rem 0;
  border-bottom: 1px solid rgba(120, 120, 120, 0.15);
}

.field-label {
  opacity: 0.5;
  min-width: 3.5rem;
}

.field-value {
  opacity: 0.85;
}

.mail-body {
  margin-top: 0.7rem;
  padding: 0.7rem 0.8rem;
  border-radius: 8px;
  background: rgba(120, 120, 120, 0.06);
  font-size: 0.9rem;
  font-style: italic;
  opacity: 0.8;
  line-height: 1.4;
}

.send-btn {
  margin-top: 1rem;
  padding: 0.6rem;
  border-radius: 8px;
  background: #7c3aed;
  color: white;
  font-weight: 700;
  text-align: center;
  font-size: 0.95rem;
  transition: background 500ms ease, color 500ms ease;
}

.send-btn.blocked {
  background: rgba(220, 38, 38, 0.12);
  color: #dc2626;
  border: 1px solid rgba(220, 38, 38, 0.4);
}

.flow-col {
  display: flex;
  flex-direction: column;
  gap: 0.9rem;
}

.flow-step {
  display: flex;
  align-items: center;
  gap: 0.7rem;
  padding: 0.7rem 1.4rem;
  border-radius: 10px;
  background: rgba(120, 120, 120, 0.06);
  border: 1px solid rgba(120, 120, 120, 0.2);
  font-weight: 600;
  font-size: 1.05rem;
  opacity: 0.5;
  min-width: 240px;
}

.flow-step.active {
  opacity: 1;
}

.dot {
  width: 0.6rem;
  height: 0.6rem;
  border-radius: 50%;
  background: #7c3aed;
}

.step-warn.active {
  background: rgba(217, 119, 6, 0.1);
  border-color: rgba(217, 119, 6, 0.35);
  color: #d97706;
}

.dot-warn {
  background: #d97706;
}

.step-block.active {
  background: rgba(220, 38, 38, 0.1);
  border-color: rgba(220, 38, 38, 0.4);
  color: #dc2626;
}

.dot-block {
  background: #dc2626;
}
</style>