<template>

<div class="flex justify-center mt-6" style="padding-right: 100px;">

<div class="email-card" style="max-width: 480px; width: 100%;">
  <div class="email-header">
    <div class="email-dot"></div>
    <div class="email-dot"></div>
    <div class="email-dot"></div>
    <span class="ml-2 opacity-50 text-xs">Gelen Kutusu</span>
  </div>
  <div class="email-body">
    <p class="mb-2 opacity-60 text-xs">Konu: Proje Teslim Tarihi</p>
    <p>
      Merhaba,<br><br>
      <span v-click="1" class="flag flag-1">Sanırım sen de herkes gibi</span>
      son teslim tarihini kaçırdın.<br><br>
      <span v-click="2" class="flag flag-2">Bu iş sende olmasa</span>
      ekip daha hızlı ilerlerdi.<br><br>
      Bugün içinde bitirirsen sevinirim.<br><br>
      İyi çalışmalar.
    </p>
  </div>

  <div v-click="1" class="tag tag-1">⚠ Küçümseyici</div>
  <div v-click="2" class="tag tag-2">⚠ Baskılayıcı</div>
</div>

</div>

</template>
<style>
.email-card {
  position: relative;
  background: white;
  border-radius: 12px;
  box-shadow: 0 20px 40px rgba(0,0,0,0.15);
  font-size: 0.85rem;
  color: #333;
}
.email-header {
  display: flex;
  align-items: center;
  gap: 6px;
  padding: 10px 14px;
  background: #f3f3f3;
  border-bottom: 1px solid #e5e5e5;
  border-radius: 12px 12px 0 0;
}
.email-dot {
  width: 10px; height: 10px; border-radius: 50%;
  background: #ddd;
}
.email-dot:nth-child(1) { background: #ff5f57; }
.email-dot:nth-child(2) { background: #febc2e; }
.email-dot:nth-child(3) { background: #28c840; }
.email-body {
  padding: 20px;
  line-height: 1.8;
  border-radius: 0 0 12px 12px;
}
.flag {
  padding: 1px 4px;
  border-radius: 4px;
  transition: all 0.4s ease;
}
.flag-1, .flag-2 {
  background: rgba(239, 68, 68, 0.15);
  color: #dc2626;
  font-weight: 600;
  box-shadow: 0 0 0 1px rgba(239,68,68,0.3);
}
.tag {
  position: absolute;
  right: -40px;
  background: #dc2626;
  color: white;
  font-size: 0.85rem;
  padding: 5px 14px;
  border-radius: 20px;
  box-shadow: 0 4px 10px rgba(220,38,38,0.4);
  animation: pop 0.35s ease;
}
.tag-1 { top: 78px; }
.tag-2 { top: 132px; }
@keyframes pop {
  from { transform: scale(0); opacity: 0; }
  to { transform: scale(1); opacity: 1; }
}
</style>