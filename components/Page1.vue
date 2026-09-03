<script setup>
import { useSlideContext } from '@slidev/client'
const { $clicks: clicks } = useSlideContext()
</script>

<template>
  <div class="slide-wrap">
    <div class="email-card">
      <div class="email-header">
        <div class="email-dot"></div>
        <div class="email-dot"></div>
        <div class="email-dot"></div>
        <span class="ml-2 opacity-50 text-xs">Gelen Kutusu</span>
      </div>
      <div class="email-body">
        <p class="mb-2 opacity-60 text-xs">Konu: Dosya Teslimi</p>
        <p>
          Merhaba,<br><br>
          Dosyayı yeniden gönderdim.
          <span class="flag" :class="{ 'flag--on': clicks >= 1 }">Umarım bu kez gözden kaçmaz</span>
          ve
          <span class="flag" :class="{ 'flag--on': clicks >= 2 }">süreci tekrar hatırlatmak zorunda kalmam.</span><br><br>
          İyi çalışmalar.
        </p>
      </div>

      <div v-click="1" class="tag tag-1">⚠ Pasif-agresif</div>
      <div v-click="2" class="tag tag-2">⚠ Baskılayıcı</div>
    </div>

    <div class="subtext">
      Hakaret yok. Küfür yok.
    </div>

    <div class="question">
      Peki etik mi?
    </div>
  </div>
</template>

<style scoped>
.slide-wrap {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.4rem;
}
.subtext {
  font-size: 1.1rem;
  opacity: 0.7;
}
.question {
  font-size: 1.4rem;
  font-weight: 700;
}
.email-card {
  position: relative;
  max-width: 420px;
  margin-left: auto;
  margin-right: auto;
  background: white;
  border-radius: 12px;
  box-shadow: 0 20px 40px rgba(0,0,0,0.15);
  font-size: 0.8rem;
  color: #333;
  text-align: left;
}
.email-header {
  display: flex;
  align-items: center;
  gap: 6px;
  padding: 8px 12px;
  background: #f3f3f3;
  border-bottom: 1px solid #e5e5e5;
}
.email-dot {
  width: 10px; height: 10px; border-radius: 50%;
  background: #ddd;
}
.email-dot:nth-child(1) { background: #ff5f57; }
.email-dot:nth-child(2) { background: #febc2e; }
.email-dot:nth-child(3) { background: #28c840; }
.email-body {
  padding: 16px 18px;
  line-height: 1.7;
}
.flag {
  padding: 1px 4px;
  border-radius: 4px;
  transition: all 0.4s ease;
}
.flag--on {
  background: rgba(239, 68, 68, 0.15);
  color: #dc2626;
  font-weight: 600;
  box-shadow: 0 0 0 1px rgba(239,68,68,0.3);
}
.tag {
  position: absolute;
  right: -64px;
  white-space: nowrap;
  background: #dc2626;
  color: white;
  font-size: 0.7rem;
  padding: 3px 10px;
  border-radius: 20px;
  box-shadow: 0 4px 10px rgba(220,38,38,0.4);
  animation: pop 0.35s ease;
}
.tag-1 { top: 96px; }
.tag-2 { top: 140px; }
@keyframes pop {
  from { transform: scale(0); opacity: 0; }
  to { transform: scale(1); opacity: 1; }
}
</style>
