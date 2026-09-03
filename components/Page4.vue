<template>
  <div class="pipeline">
    <v-click>
      <div class="stage">
        <div class="stage-visual">
          <div class="doc-cluster">
            <span v-for="n in 15" :key="n" class="doc" :class="{ alt: n % 2 === 0 }" />
          </div>
        </div>
        <div class="stage-cap">3.222 Türkçe Kurumsal Metin</div>
        <div class="stage-sub">Etik / Etik dışı · dengeli veri seti</div>
      </div>
    </v-click>

    <v-click>
      <div class="flow">
        <div class="flow-arrow">→</div>
        <div class="stage">
          <div class="stage-visual">
            <div class="bert-logo">
              <svg class="bert-rings" viewBox="0 0 200 200" aria-hidden="true">
                <defs>
                  <marker
                    id="p4ah"
                    markerUnits="userSpaceOnUse"
                    markerWidth="26"
                    markerHeight="26"
                    viewBox="0 0 14 14"
                    refX="6"
                    refY="7"
                    orient="auto"
                  >
                    <path d="M0,0 L14,7 L0,14 Z" fill="#c6cad0" />
                  </marker>
                </defs>
                <path
                  d="M26.71 73.32 A 78 78 0 0 1 173.29 73.32"
                  fill="none"
                  stroke="#c6cad0"
                  stroke-width="13"
                  stroke-linecap="round"
                  marker-end="url(#p4ah)"
                />
                <path
                  d="M173.29 126.68 A 78 78 0 0 1 26.71 126.68"
                  fill="none"
                  stroke="#c6cad0"
                  stroke-width="13"
                  stroke-linecap="round"
                  marker-end="url(#p4ah)"
                />
              </svg>
              <div class="bert-word">
                <span class="bw-inner"><span style="color: #4285f4">B</span><span style="color: #ea4335">E</span><span style="color: #fbbc05">R</span><span style="color: #34a853">T</span></span>
              </div>
            </div>
          </div>
          <div class="stage-cap">BERTürk</div>
          <div class="stage-sub">Fine-tune edilmiş sınıflandırıcı</div>
        </div>
      </div>
    </v-click>

    <v-click>
      <div class="flow">
        <div class="flow-arrow">→</div>
        <div class="stage">
          <div class="stage-visual">
            <div class="webui">
              <div class="webui-bar">
                <span class="dot" /><span class="dot" /><span class="dot" />
                <div class="webui-url">etikmail.kubrainy.me</div>
              </div>
              <div class="webui-body">
                <div class="webui-field">Merhaba, dosyayı tekrar gönderiyorum…</div>
                <div class="webui-row">
                  <span class="webui-chip">Etik Dışı</span>
                  <span class="webui-send">Gönder</span>
                </div>
              </div>
            </div>
          </div>
          <div class="stage-cap">Web Tabanlı Sistem</div>
          <div class="stage-sub">Çalışan canlı prototip</div>
        </div>
      </div>
    </v-click>
  </div>
</template>

<style scoped>
.pipeline {
  display: flex;
  align-items: flex-start;
  justify-content: center;
  gap: 0.75rem;
  margin-top: 1.5rem;
}

.flow {
  display: flex;
  align-items: flex-start;
  gap: 0.75rem;
}

.stage {
  display: flex;
  flex-direction: column;
  align-items: center;
  animation: stage-in 0.55s cubic-bezier(0.22, 1, 0.36, 1) both;
}

.stage-visual {
  height: 190px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.stage-cap {
  margin-top: 1rem;
  font-size: 1.1rem;
  font-weight: 700;
  text-align: center;
}

.stage-sub {
  margin-top: 0.25rem;
  font-size: 0.8rem;
  opacity: 0.6;
  text-align: center;
}

.flow-arrow {
  height: 190px;
  display: flex;
  align-items: center;
  font-size: 2rem;
  color: #7c3aed;
  opacity: 0.55;
  animation: arrow-flow 1.6s ease-in-out infinite;
}

/* --- veri kümesi --- */
.doc-cluster {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 7px;
  width: 178px;
  padding: 14px;
  border: 1px dashed rgba(124, 58, 237, 0.35);
  border-radius: 14px;
  background: rgba(124, 58, 237, 0.05);
}

.doc {
  position: relative;
  width: 26px;
  height: 32px;
  border-radius: 3px;
  background: #fff;
  border: 1px solid rgba(124, 58, 237, 0.3);
  box-shadow: 0 1px 3px rgba(124, 58, 237, 0.12);
  transform: rotate(-2deg);
  animation: box-in 0.4s ease both;
}
.doc.alt {
  transform: rotate(2.5deg);
  background: rgba(124, 58, 237, 0.06);
}
.doc::after {
  content: "";
  position: absolute;
  left: 4px;
  right: 4px;
  top: 7px;
  height: 2px;
  background: rgba(124, 58, 237, 0.4);
  box-shadow: 0 5px 0 rgba(124, 58, 237, 0.4), 0 10px 0 rgba(124, 58, 237, 0.4);
}

/* --- BERT logosu (dönen oklar) --- */
.bert-logo {
  position: relative;
  width: 150px;
  height: 150px;
  animation: box-in 0.5s ease both;
}
.bert-rings {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  animation: spin 16s linear infinite;
}
.bert-word {
  position: absolute;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}
.bw-inner {
  white-space: nowrap;
  font-size: 1.7rem;
  font-weight: 800;
  letter-spacing: 0.02em;
}

/* --- web arayüzü --- */
.webui {
  width: 232px;
  border-radius: 12px;
  overflow: hidden;
  background: #fff;
  border: 1px solid rgba(124, 58, 237, 0.25);
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.14);
  animation:
    box-in 0.5s ease both,
    final-pop 0.5s cubic-bezier(0.34, 1.56, 0.64, 1) 0.3s both;
}
.webui-bar {
  display: flex;
  align-items: center;
  gap: 5px;
  padding: 7px 10px;
  background: #f3f0fb;
  border-bottom: 1px solid rgba(124, 58, 237, 0.15);
}
.dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #cbb9f0;
}
.webui-url {
  margin-left: 8px;
  font-size: 0.62rem;
  color: #8b7fb0;
}
.webui-body {
  padding: 12px 12px 14px;
}
.webui-field {
  font-size: 0.72rem;
  color: #444;
  padding: 8px 10px;
  border: 1px solid rgba(124, 58, 237, 0.2);
  border-radius: 8px;
  background: rgba(124, 58, 237, 0.03);
  line-height: 1.4;
}
.webui-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 10px;
}
.webui-chip {
  font-size: 0.7rem;
  font-weight: 700;
  color: #d64545;
  background: #fdecec;
  border: 1px solid #f3c9c9;
  border-radius: 999px;
  padding: 3px 10px;
}
.webui-send {
  font-size: 0.72rem;
  font-weight: 700;
  color: #fff;
  background: #7c3aed;
  border-radius: 8px;
  padding: 5px 14px;
}

@keyframes stage-in {
  from { opacity: 0; transform: translateY(24px); }
  to   { opacity: 1; transform: translateY(0); }
}
@keyframes box-in {
  from { opacity: 0; transform: scale(0.92); }
  to   { opacity: 1; transform: scale(1); }
}
@keyframes arrow-flow {
  0%, 100% { transform: translateX(0);   opacity: 0.4; }
  50%      { transform: translateX(4px); opacity: 0.9; }
}
@keyframes spin { to { transform: rotate(360deg); } }
@keyframes final-pop {
  0%   { transform: scale(0.85); }
  60%  { transform: scale(1.06); }
  100% { transform: scale(1); }
}
</style>
