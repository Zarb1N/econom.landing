<template>
  <div class="call">
    <div class="call__footer">
      <img src="@/assets/icons/graduates.svg" alt="">
      <div class="call__title">
        Поступай в <b>Институт экономики <br/> и управления АПК</b>!
      </div>
      <div class="call__subtitle">
        Получи профессию будущего!
      </div>
    </div>
  </div>
</template>

<style scoped>
.call {
  height: 919px;
  background-image: url('../../assets/background-3.png');
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  background-position: center;
  background-size: cover;
}
.call__footer {
  height: 424px;
  backdrop-filter: blur(20px);
  background: rgba(242, 241, 237, 0.61);
  border-radius: calc((100vw - 1000px) * 7) calc((100vw - 1000px) * 7) 0px 0px;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-items: center;
  padding-bottom: 56px;
  text-align: center;
}
.call__footer img {
  width: 256px;
  height: 256px;
  margin-bottom: 40px;
}
.call__title {
  font-weight: 700;
  font-size: 48px;
  line-height: 64px;
  color: white;
  margin-bottom: 8px;
}
b {
  color: #E82525;
}
.call__subtitle {
  font-weight: 700;
  font-size: 36px;
  line-height: 90px;
  text-align: center;
  color: #FFFFFF;
} 
@media (max-width: 500px) {
  .call__title {
    font-size: 32px;
    line-height: 40px;
  }
  .call__subtitle {
    font-size: 20px;
    line-height: 25px;
  }
}
</style>