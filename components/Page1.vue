<template>
  <div class="slide-wrap">
    <div class="email-quote">
      "Sanırım herkes gibi sen de son teslim tarihini kaçırdın.
      Tabii senden zaten fazlasını beklemiyordum.<br><br>
      Bu iş sende olmasa belki ekip daha hızlı ilerlerdi."
    </div>

    <div class="subtext">
      Hakaret yok. Küfür yok.
    </div>

    <div class="question">
      Peki etik mi?
    </div>

    <div class="tags-slot">
      <v-click>
        <div class="tags">
          <span class="topic-tag">Pasif-agresif</span>
          <span class="topic-tag">Baskılayıcı</span>
          <span class="topic-tag">Küçümseyici</span>
        </div>
      </v-click>
    </div>
  </div>
</template>

<style scoped>
.slide-wrap {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}
.email-quote {
  font-size: 1.3rem;
  font-style: italic;
  max-width: 780px;
  padding: 1.4rem 2rem;
  border-left: 4px solid #7c3aed;
  background: rgba(124, 58, 237, 0.07);
  border-radius: 8px;
  line-height: 1.5;
}
.subtext {
  font-size: 1.1rem;
  opacity: 0.7;
}
.question {
  font-size: 1.4rem;
  font-weight: 700;
}
.tags-slot {
  min-height: 3rem;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
}
.tags {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  gap: 0.75rem;
  justify-content: center;
  align-items: center;
}
.topic-tag {
  position: static;
  display: inline-flex;
  white-space: nowrap;
  padding: 0.5rem 1rem;
  border-radius: 14px;
  background: rgba(124, 58, 237, 0.1);
  border: 1px solid rgba(124, 58, 237, 0.3);
  color: #7c3aed;
  font-weight: 600;
  font-size: 0.95rem;
}
</style>