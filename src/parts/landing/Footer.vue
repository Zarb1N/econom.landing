<template>
  <div class="footer">
    <div class="footer__content">
      <div class="footer__title">
        По всем вопросам о поступлении в Институт экономики и 
        управления АПК РГАУ-МСХА имени К.А Тимирязева 
        обращаться:
        <br/>
        <br/>
      </div>
      <div class="footer__subtitle">Мырксина Юлия Александровна</div>
      <div class="footer__hint"> Заместитель директора Института экономики и управления АПК <br/> <br/></div>
      <div class="footer__subtitle">+7 (926) 726-25-34</div>
      <div class="footer__subtitle">myrksina@rgau-msha.ru <br/> <br/></div>

      <div class="footer__paragraph">Институт экономики и управления АПК в социальных сетях:</div>
      <a 
        class="footer__title"
        href="https://vk.com/econom.timacad"
      >https://vk.com/econom.timacad </a>
      <a 
        class="footer__title"
        href="https://t.me/economtimacad"
      >https://t.me/economtimacad</a>
      <a 
        class="footer__title"
        href="https://www.youtube.com/channelUCO4pk7gpsBVEnMOZC3hLFOQ"
      >https://www.youtube.com/channel <br/> UCO4pk7gpsBVEnMOZC3hLFOQ</a>
    </div>
  </div>
</template>

<style scoped>
.footer {
  background: #F2F1ED;
  display: flex;
  justify-content: center;
}
.footer__content {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  width: 100%;
  max-width: 1100px;
  padding: 40px 15px;
}
.footer__title {
  font-weight: 700;
  font-size: 32px;
  line-height: 48px;
}
.footer__subtitle {
  font-weight: 700;
  font-size: 28px;
  line-height: 32px;
}
.footer__hint {
  font-weight: 400;
  font-size: 24px;
  line-height: 32px;
}
.footer__paragraph {
  font-weight: 500;
  font-size: 32px;
  line-height: 32px;
}
a.footer__title {
  margin-top: 12px;
}
@media (max-width: 500px) {
  .footer__title {
    font-size: 24px;
    line-height: 30px;
  }
  .footer__subtitle {
    font-size: 22px;
    line-height: 22px;
  }
  .footer__hint {
    font-size: 18px;
    line-height: 20px;
  }
  .footer__paragraph {
    font-size: 24px;
    line-height: 30px;
  }
}
</style>