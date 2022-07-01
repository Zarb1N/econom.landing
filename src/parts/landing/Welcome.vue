<template>
  <div class="welcome">
    <div class="welcome__card">
      <div class="welcome__card-text">
        <div class="welcome__title">Институт экономики и <br/> управления АПК</div>
        <div class="welcome__hint">Приемная кампания 2022</div>
      </div>
    </div>
  </div>
</template>


<style scoped>
.welcome {
  height: 800px;
  background-image: url('../../assets/background.png');
  background-size: cover;
  background-position: center;
  display: flex;
  justify-content: center;
  align-items: center;
}
.welcome__card {
  max-width: 910px;
  max-height: 423px;
  width: 100%;
  height: 100%;
  background: url('../../assets/welcome-card.svg') center;
}
.welcome__card-text {
  padding: 107px 30px 76px 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 32px;
}
.welcome__title {
  font-weight: 700;
  font-size: 48px;
  line-height: 90px;
  text-align: center
}
.welcome__hint {
  font-weight: 500;
  font-size: 32px;
  line-height: 28px;
}
@media (max-width: 500px) {
  .welcome__title {
    font-size: 32px; 
    line-height: 50px;
  }
  .welcome__hint {
    font-size: 24px;
    line-height: 25px;
  }
}
</style>