<template>
  <div class="about-us">
    <div class="landing__title--secondary">О нас</div>
    <div class="about-us__wrapper">
      <div class="about-us__description">
        <img 
          class="about-us__description-first-image"
          src="@/assets/ректорат_вид_сверху.png"
        />
        <div class="landing__paragraph">
          Становление и развитие российской науки во многом связано со 155-летней 
          историей Российского государственного аграрного университета – 
          МСХА имени К.А.Тимирязева  и именами таких выдающихся ученых, как 
          Тимирязев К.А., Прянишников Д.Н., Чаянов А.В., Кондратьев  Н.Д., Вавилов Н.И., 
          Вильямс В.Р., Немчинов В.С. и др. Сегодня это ведущий учебный, научный, 
          методический и консультационный центр мирового уровня. В Тимирязевке обучаются 
          более 15000 студентов из  всех регионов России и стран дальнего зарубежья. 
          Выпускники Академии обладают профессиональными компетенциями, востребованными
          на отечественном и международном рынке труда.
        </div>
        <img 
          class="about-us__description-second-image"
          src="@/assets/2корпус.png"
        />
        <div class="landing__paragraph">
          Выдающимися достижениями в обучении, науке, творчестве отличаются студенты 
          лидера в агроэкономическом образовании  – института экономики и управления АПК. 
          Институт готовит бакалавров, магистров и аспирантов в сфере экономики, менеджмента, 
          экономической безопасности, информационных систем и технологий, прикладной 
          информатики, педагогики  и другим направлениям.  Имеет длительный опыт реализации 
          совместных программ обучения с вузами Европы и Азии.
          <br/><br/>
          Институт экономики и управления АПК может предложить Вам:
          <br/> - Военную кафедру
          <br/> - Стажировки и практики в крупнейших компаниях агробизнеса и финансово-кредитной сферы
          <br/> - Участие в именных стипендиальных программах 
          <br/> - Общежития, расположенные в шаговой доступности от учебных корпусов 
          <br/> - Развитие в науке, спорте и творчестве
          <br/> - Скидки на оплату обучения
        </div>
        
      </div>
    </div>
    <div class="about-us__uni-in-numbers">
      <div class="landing__title--tertiary">Институт в цифрах</div>
      <div class="about-us__uni-in-numbers-items">
        <div 
          class="about-us__uni-in-numbers-item"
          v-for="(item, index) in uniInNumbers"
          :key="index"
        >
          <div 
            class="about-us__uni-in-numbers-item-title"
            :style="{backgroundImage: `url(${require('@/assets/closed-lines-' + (index + 1) + '.svg')})`}"
          >{{item.title}}</div>
          <div 
            class="about-us__uni-in-numbers-item-subtitle"
            v-html="item.subtitle"
          ></div>
        </div>
      </div>
    </div>
    <div class="abous-us__about-director">
      <div class="landing__title--tertiary">Директор Института экономики и управления АПК</div>
      <div class="abous-us__about-director-body">
        <div class="landing__paragraph">
          Хоружий Людмила Ивановна, доктор экономических наук, профессор, директор 
          Института экономики и управления АПК РГАУ-МСХА им. К.А. Тимирязева, член 
          Общественного совета Минфина России, Председатель Совета по стандартам 
          бухгалтерского учета при Минфине России, член Научно-технического совета 
          Минсельхоза России, президент Института профессиональных бухгалтеров и 
          аудиторов России.
          <br/>
          <br/>
          Подготовленные под ее руководством студенты и аспиранты добивались высочайших 
          результатов: неоднократно становились призерами Всероссийских и региональных 
          студенческих научных конференций, лауреатами стипендий Президента и 
          Правительства РФ, призерами НТТМ, конкурсов научных работ Вольного 
          экономического общества и др.
        </div>
        <img
          class="about-us__about-director-image"
          src="@/assets/Фото_Хоружий.png"
        />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "@vue/runtime-core";


export default defineComponent({
  data: () => ({
    uniInNumbers: [
      {
        title: '2000+',
        icon: '',
        subtitle: 'студентов'
      },
      {
        title: '35',
        icon: '',
        subtitle: 'образовательных программ'
      },
      {
        title: '71',
        icon: '',
        subtitle: 'cредний балл ЕГЭ'
      },
      {
        title: '18',
        icon: '',
        subtitle: '12 - выпускающих и <br/> 6 - базовых кафедр'
      },
    ]
  }),
  methods: {
    getImageURL(path: string) {
      // return new URL(`../assets/${path}`, import.meta.url).href;
    }
  }
})
</script>


<style scoped>
.about-us {
  width: 100%;
  max-width: 1100px;
  padding: 80px 15px;
}
.about-us__wrapper {
}
.landing__title--secondary, .landing__title--tertiary {
  margin-bottom: 40px;
}
.about-us__description {
  display: grid;
  grid-template-columns: repeat(2, calc(50% - 15px));
  grid-template-rows: auto auto 1fr;
  column-gap: 30px;
  row-gap: 50px;
  margin-bottom: 80px;
}
.about-us__description-first-image {
  justify-self: flex-end;
  grid-row: 1 / 3;
}
.about-us__description-second-image {
  grid-row: 2 / 4;
}
.about-us__uni-in-numbers {
  margin-bottom: 80px;
}
.about-us__uni-in-numbers-items {
  display: flex;
  justify-content: space-between;
}
.about-us__uni-in-numbers-item {
  width: 190px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 36px;
}
.about-us__uni-in-numbers-item-title {
  width: 190px;
  height: 190px;
}
.about-us__uni-in-numbers-item-title {
  background-position: center;
  background-size: cover;
  display: flex;
  align-items: center;
  justify-content: center;
  font-style: italic;
  font-weight: 500;
  font-size: 56px;
  line-height: 28px;
  text-shadow: 0px 11px 3px rgba(28, 55, 43, 0.17);
}
.abous-us__about-director-body {
  display: grid;
  grid-template-columns: repeat(2, calc(50% - 15px));
  gap: 30px;
  margin-bottom: 40px;
}
.abous-us__about-director-body img {
  width: 100%;
}
@media (max-width: 500px) {
  .about-us__description {
    display: flex;
    flex-direction: column;
  }
  .about-us__description > div {
    grid-column: 1 / 2;
  }
  .about-us__uni-in-numbers-items {
    flex-wrap: wrap;
  }  
  .abous-us__about-director-body {
    display: flex;
    flex-direction: column-reverse;
  }
}
</style>

