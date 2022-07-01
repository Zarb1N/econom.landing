<template>
  <div class="landing">
    <div class="landing__header header">
      <div class="header__content">
        <img 
          class="header__logo"
          src="@/assets/uni-logo.svg"
        />
        <div class="header__navigation">
          <a 
            class="header__navigation-item"
            v-for="item in navigationItems"
            :key="item.goTo"
            :href="`#${item.goTo}`"
          >
            {{item.name}}
          </a>
          <a 
            class="header__navigation-item header__navigation-item--button"
            href="#ask-a-question"
          >Задать вопрос </a>
        </div>
      </div>
    </div>
    <Welcome/>
    <AboutUs 
      class="landing__about-us"
      id="about-us"
    />
    <div class="landing__button--primary">Задать вопрос</div>
    <PreparationDirections 
      class="landing__preparation-directions"
      id="directions"
    />
    <Futher/>
    <QuestionForm
      id="ask-a-question"
    />
    <Alumnuses
      id="alumnuses"
    />
    <Call/>
    <Footer
      id="contacts"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "@vue/runtime-core";
import Welcome from '../parts/landing/Welcome.vue'
import AboutUs from '../parts/landing/AboutUs.vue'
import PreparationDirections from "@/parts/landing/PreparationDirections.vue"
import CompaniesAndInternationPrograms from "@/parts/landing/CompaniesAndInternationPrograms.vue";
import QuestionForm from "@/parts/landing/QuestionForm.vue";
import Alumnuses from "@/parts/landing/Alumnuses.vue";
import Call from '@/parts/landing/Call.vue'
import Footer from '@/parts/landing/Footer.vue'


export default defineComponent({
  data: () => ({
    navigationItems: [
      {
        name: 'О нас',
        goTo: 'about-us'
      },
      {
        name: 'Направление',
        goTo: 'directions'
      },
      {
        name: 'Выпускники',
        goTo: 'alumnuses'
      },
      {
        name: 'Контакты',
        goTo: 'contacts'
      },
    ]
  }),
  components: {
    Welcome,
    AboutUs,
    PreparationDirections,
    Futher: CompaniesAndInternationPrograms,
    QuestionForm,
    Alumnuses,
    Call,
    Footer,
  }
})
</script>

<style>
.landing {
  width: 100%;
  display: flex;
  flex-direction: column;
  overflow-x: hidden;
  scroll-behavior: smooth;
}
.landing__header {
  position: fixed;
  top: 0px;
  background: rgba(255, 255, 255, 0.41);
  backdrop-filter: blur(100px);
  z-index: 100;
}
.header {
  width: 100%;
  height: 70px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.header__content {
  width: 100%;
  max-width: 1100px;
  padding: 0 15px;
  display: grid;
  grid-template-columns: min-content auto;
}
.header__navigation {
  justify-self: end;
  display: flex;
  align-items: center;
  gap: 32px;
}
.header__navigation-item {
  display: block;
}
.header__navigation-item:visited {
  color: var(--dark-green-text);
}
.header__navigation-item--button {
  background: #E82525;
  box-shadow: inset 0px 0px 4px #FFFFFF;
  border-radius: 18px;
  color: white;
  margin-left: 12px;
  width: 190px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.header__navigation-item--button:visited {
  color: white;
}
.landing__title--secondary {
  font-weight: 700;
  font-size: 32px;
  line-height: 58px;
}
.landing__title--tertiary {
  font-weight: 700;
  font-size: 24px;
  line-height: 58px;
}
.landing__paragraph {
  font-weight: 500;
  font-size: 16px;
  line-height: 28px;
}
.landing__button--primary {
  background: var(--red-primary);
  box-shadow: inset 0px 0px 4px #FFFFFF;
  border-radius: 18px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  cursor: pointer;
}
</style>
<style scoped>
.landing__button--primary {
  height: 56px;
  width: 410px;
  font-weight: 600;
  font-size: 24px;
  line-height: 28px;
  align-self: center;
}
.landing__preparation-directions, .landing__about-us {
  align-self: center;
}
.landing__preparation-directions {
  margin-bottom: 80px;
}
@media (max-width: 500px) {
  .header {
    display: none;
  }
}
</style>