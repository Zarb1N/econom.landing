<template>
  <div class="futher">
    <div class="landing__title--tertiary">Компании для трудоутройства</div>
    <div 
      class="futher__grid"
      style="margin-bottom: 80px"
    >
      <div 
        class="futher__grid-item"
        v-for="company in companies"
        :key="company"
      >
        <img
          class="futher__logo"
          :src="require(`@/assets/companies-icons/${company}`)"
        />
      </div>
    </div>
    <div class="landing__title--tertiary">Программы международного взаимодействия</div>
    <div class="futher__grid">
      <div 
        class="futher__grid-item"
        v-for="uni in programs"
        :key="uni"
      >
        <img
          class="futher__logo"
          :src="require(`@/assets/international-unis-icons/${uni}`)"
        />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "@vue/runtime-core";

export default defineComponent({
  data: () => ({
    companies: [
      'Rectangle 547.png',
      'vtb 1.png',
      'Гленкор.png',
      'загружено 1.png',
      'лого-1.png',
      'лого-2.png',
      'лого-3.png',
      'лого-4.png',
      'лого-5.png',
      'лого-6.png',
      'лого-7.png',
      'лого.png',
      'Микоян-1.png',
      'Микоян-2.png',
      'Микоян.png',
    ],
    programs: [
      'Rectangle 547-1.png',
      'Rectangle 547.png',
      'Гленкор-1.png',
      'Гленкор-2.png',
      'Гленкор.png',
      'лого-1.png',
      'лого-2.png',
      'лого-3.png',
      'лого-4.png',
      'лого-5.png',
      'лого-6.png',
      'лого-7.png',
      'лого-8.png',
      'лого-9.png',
      'лого-10.png',
      'лого-11.png',
      'лого-12.png',
      'лого-13.png',
      'лого-14.png',
      'лого-15.png',
      'лого.png',
      'Микоян-1.png',
      'Микоян-2.png',
      'Микоян.png',
      'фон.png',
    ],
  }),
})
</script>

<style scoped>
.futher {
  width: 100%;
  max-width: 1100px;
  padding: 0px 15px;
  margin-bottom: 80px;
  align-self: center;
}
.futher__grid {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  grid-template-columns: repeat(auto-fill, 160px);
  justify-content: center;
  gap: 64px;
}
.futher__grid-item {
  border: 1px solid #1C372B;
  padding: 6px;
  border-radius: 25px;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 160px;
  width: 160px;
}
.futher__logo {
  max-width: 100%;
  max-height: 100%;
}
.landing__title--tertiary {
  margin-bottom: 35px;
}
</style>