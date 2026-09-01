<template>
  <div class="email-quote">
    "Bu raporu hâlâ göndermemiş olmanız gerçekten kabul edilebilir değil.
    Bundan sonra tekrar hatırlatmak zorunda kalmayacağımı umuyorum."
  </div>

  <div class="mt-8 text-xl opacity-70">
    Hakaret yok. Küfür yok.
  </div>

  <div class="text-2xl font-bold mt-2">
    Peki etik mi?
  </div>

  <v-click>
    <div class="tags mt-10">
      <span class="tag">Pasif-agresif</span>
      <span class="tag">Baskılayıcı</span>
      <span class="tag">Küçümseyici</span>
    </div>
  </v-click>

</template>

<style scoped>
.email-quote {
  font-size: 1.5rem;
  font-style: italic;
  max-width: 780px;
  margin: 1rem auto 0;
  padding: 1.8rem 2.2rem;
  border-left: 4px solid #7c3aed;
  background: rgba(124, 58, 237, 0.07);
  border-radius: 8px;
  line-height: 1.55;
}
.tags {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
}
.tag {
  padding: 0.6rem 1.4rem;
  border-radius: 14px;
  background: rgba(124, 58, 237, 0.1);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid rgba(124, 58, 237, 0.3);
  color: #7c3aed;
  font-weight: 600;
  font-size: 1.05rem;
}
</style>