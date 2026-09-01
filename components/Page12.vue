<template>
  <div class="closing-stage">
    <v-click>
      <div class="line">
        Etik dışı dil yalnızca <span class="dim">sosyal medyada</span> ortaya çıkmaz.
      </div>
    </v-click>

    <v-click>
      <div class="line">
        İş hayatındaki iletişimde de <span class="highlight">görünür</span>.
      </div>
    </v-click>

    <v-click>
      <div class="line line-final">
        Ve yapay zekâ, bunu <span class="highlight">gerçekleşmeden önce</span>
        fark etmemize yardımcı olabilir.
      </div>
    </v-click>
  </div>

  <v-click>
    <div class="footer">
      <div class="footer-title">
        Türkçe Kurumsal E-Postalarda Etik Dışı Dil Tespiti
      </div>

      <div class="thanks-row">
        <img src="/tubitak-logo.png" class="tubitak-logo" alt="TÜBİTAK logosu" />
        <div class="footer-thanks">
          Bu çalışma TÜBİTAK 2209-A Üniversite Öğrencileri Araştırma
          Projeleri Destekleme Programı kapsamında desteklenmiştir.
        </div>
      </div>
    </div>
  </v-click>
</template>

<style scoped>
.closing-stage {
  min-height: 260px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 1.6rem;
  margin-top: 1rem;
}

.line {
  font-size: 1.6rem;
  font-weight: 600;
  max-width: 760px;
  line-height: 1.5;
  opacity: 0.85;
}

.line-final {
  font-size: 1.9rem;
  font-weight: 700;
  opacity: 1;
}

.dim {
  opacity: 0.55;
}

.highlight {
  color: #7c3aed;
}

.footer {
  margin-top: 2.5rem;
  padding-top: 1.5rem;
  border-top: 1px solid rgba(120, 120, 120, 0.2);
  text-align: center;
}

.footer-title {
  font-size: 1rem;
  font-weight: 700;
  opacity: 0.6;
  margin-bottom: 0.7rem;
}

.thanks-row {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  max-width: 560px;
  margin: 0 auto;
  padding: 0.4rem 0.8rem;
  border-radius: 999px;
  background: rgba(120, 120, 120, 0.05);
}

.tubitak-logo {
  width: 120px;
  height: auto;
  flex-shrink: 0;
}

.footer-thanks {
  font-size: 0.78rem;
  opacity: 0.5;
  line-height: 1.4;
  text-align: left;
}
</style>