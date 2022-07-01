<template>
  <div class="directions">
    <div class="landing__title--secondary">Направления подготовки</div>
    <div class="landing__paragraph">
      Перечень направлений подготовки и планируемые к реализации профили по
      очной форме обучения в 2022/2023 учебном году.
    </div>
    <div class="direcions__buttons">
      <div 
        class="directions__button" 
        v-for="grade in grades" 
        :key="grade.name"
        :class="choosedGrade === grade.name ? 'directions__button--choosed' : 'directions__button--unchoosed'"
        @click="chooseGrade(grade.name)"
      >
        {{ grade.name }}
      </div>
    </div>
    <div 
      class="directions__grades"
      v-for="(grade, index) in grades"
      :key="index"
      v-show="grade.name === choosedGrade"
    >
      <div 
        class="directions__extension-cards"
        v-if="['Бакалавриат', 'Специалитет'].indexOf(grade.name) !== -1"
      >
        <ExtensionCard
          class="directions__extension-card"
          v-for="(direction, index) in grade.directions"
          :key="index"
          :title="direction.name"
          :isOpen="choosedCard === index"
          @changeState="changeState(index)"
        > 
          <div class="direction">
            <div class="direction__places-group">
              <div class="direction__places">
                <img
                  class="direction__places-icon"
                  src="@/assets/icons/papers-with-pen.svg"
                />
                <div class="direction__places-title">Бюджетные места</div>
                <div class="direction__places-quantity">{{direction.budgetPlaces}}</div>
              </div>
              <div class="direction__places">
                <img
                  class="direction__places-icon"
                  src="@/assets/icons/papers-with-cash.svg"
                />
                <div class="direction__places-title">Контрактные места</div>
                <div class="direction__places-quantity">{{direction.contractPlaces}}</div>
              </div>
            </div>

            <div class="direction__profiles direction__section">
              <img 
                class="direction__section-icon"
                src="@/assets/icons/lamp.svg"
              />
              <div class="direction__section-body">
                <div class="direction__section-title">Профиль подготовки:</div>
                <div class="direction__section-list">
                  <div 
                    class="direction__section-item"
                    v-for="(program, index) in direction.programs"
                    :key="index"
                  >
                    <img 
                      class="direction__section-item-icon"
                      src="@/assets/icons/check-mark-in-circle.svg"
                    />
                    <div class="direcation__section-item-text">{{program}}</div>
                  </div>
                </div>
              </div>
            </div>

            <div class="direction__profiles direction__section">
              <img 
                class="direction__section-icon"
                src="@/assets/icons/magnifying.svg"
              />
              <div class="direction__section-body">
                <div class="direction__section-title">Стоимость обучения:</div>
                <div class="direction__section-list">
                  <div class="direction__section-item">
                    <img 
                      class="direction__section-item-icon"
                      src="@/assets/icons/check-mark-in-circle.svg"
                    />
                    <div class="direcation__section-item-text">Стоимость обучения без предоставления скидки: {{direction.price}} руб.</div>
                  </div>
                  <div class="direction__section-item">
                    <img 
                      class="direction__section-item-icon"
                      src="@/assets/icons/check-mark-in-circle.svg"
                    />
                    <div class="direcation__section-item-text"> <b>Скидки</b> на стоимость обучения <b>при сумме баллов по 3</b> конкурсным предметам:</div>
                  </div>
                </div>
                <div class="direction__discounts">
                  <div 
                    class="direction__discount"
                    v-for="(discount, index) in direction.discounts"
                    :key="index"
                  >
                    <img
                      class="direction__discount-icon"
                      src="@/assets/icons/star.svg"
                    />
                    <div class="direction__discount-text">{{discount}}</div>
                  </div>
                </div>
              </div>
            </div>

            <div class="direction__profiles direction__section">
              <img 
                class="direction__section-icon"
                src="@/assets/icons/paper-with-bachelor-hat.svg"
              />
              <div class="direction__section-body">
                <div class="direction__section-title">Перечень необходимых предметов для поступления:</div>
                <div class="direction__examination-sections">
                  <div class="direction__examination-section">
                    <div class="direction__section-title">ЕГЭ:</div>
                    <ol class="direction__examination-section-list">
                      <li 
                        class="direction__examination-section-item"
                        v-for="(trial, index) in direction.exams"
                        :key="index"
                      >{{trial}}</li>
                    </ol>
                  </div>
                  <div class="direction__examination-section">
                    <div class="direction__section-title">Испытания на базе СПО:</div>
                    <ol class="direction__examination-section-list">
                      <li 
                        class="direction__examination-section-item"
                        v-for="(trial, index) in direction.spoExams"
                        :key="index"
                      >{{trial}}</li>
                    </ol>
                  </div>
                </div>
              </div>
            </div>

          </div>
        </ExtensionCard>  
      </div>
      <div 
        class="directions__extension-cards"
        v-else-if="grade.name === 'Магистратура'"
      >
        <ExtensionCard
          class="directions__extension-card"
          v-for="(direction, index) in grade.directions"
          :key="index"
          :title="direction.name"
          :isOpen="choosedCard === index"
          @changeState="changeState(index)"
        > 
          <div class="direction">
            <div class="direction__places-group">
              <div class="direction__places">
                <img
                  class="direction__places-icon"
                  src="@/assets/icons/papers-with-pen.svg"
                />
                <div class="direction__places-title">Бюджетные места</div>
                <div class="direction__places-quantity">{{direction.budgetPlaces}}</div>
              </div>
              <div class="direction__places">
                <img
                  class="direction__places-icon"
                  src="@/assets/icons/papers-with-cash.svg"
                />
                <div class="direction__places-title">Контрактные места</div>
                <div class="direction__places-quantity">{{direction.contractPlaces}}</div>
              </div>
            </div>

            <div class="direction__profiles direction__section">
              <img 
                class="direction__section-icon"
                src="@/assets/icons/lamp.svg"
              />
              <div class="direction__section-body">
                <div class="direction__section-title">Профиль подготовки:</div>
                <div class="direction__section-list">
                  <div 
                    class="direction__section-item"
                    v-for="(program, index) in direction.programs"
                    :key="index"
                  >
                    <img 
                      class="direction__section-item-icon"
                      src="@/assets/icons/check-mark-in-circle.svg"
                    />
                    <div class="direcation__section-item-text">{{program}}</div>
                  </div>
                </div>
              </div>
            </div>

            <div class="direction__profiles direction__section">
              <img 
                class="direction__section-icon"
                src="@/assets/icons/magnifying.svg"
              />
              <div class="direction__section-body">
                <div class="direction__section-title">Стоимость обучения:</div>
                <div class="direction__section-list">
                  <div class="direction__section-item">
                    <img 
                      class="direction__section-item-icon"
                      src="@/assets/icons/check-mark-in-circle.svg"
                    />
                    <div class="direcation__section-item-text">Стоимость обучения без предоставления скидки: {{direction.price}} руб.</div>
                  </div>
                  <div class="direction__section-item">
                    <img 
                      class="direction__section-item-icon"
                      src="@/assets/icons/check-mark-in-circle.svg"
                    />
                    <div class="direcation__section-item-text"><b>Скидка</b> на стоимость обучения:</div>
                  </div>
                </div>
                <div class="direction__discounts">
                  <div 
                    class="direction__discount"
                    v-for="(discount, index) in direction.discounts"
                    :key="index"
                  >
                    <img
                      class="direction__discount-icon"
                      src="@/assets/icons/star.svg"
                    />
                    <div class="direction__discount-text">{{discount}}</div>
                  </div>
                </div>
              </div>
            </div>

            <div class="direction__profiles direction__section">
              <img 
                class="direction__section-icon"
                src="@/assets/icons/paper-with-bachelor-hat.svg"
              />
              <div class="direction__section-body">
                <div class="direction__section-title">Вступительные экзамены:</div>
                <div class="direction__examination-sections">
                  <div class="direction__examination-section">
                    <div class="direction__section-title">Комплексный экзамен по направлению подготовки:</div>
                    <ol class="direction__examination-section-list">
                      <li 
                        class="direction__examination-section-item"
                        v-for="(trial, index) in direction.exams"
                        :key="index"
                      >{{trial}}</li>
                    </ol>
                  </div>
                  <div class="direction__examination-section">
                    Форма проведения вступительных испытаний: 
                    бланковое или компьютерное тестирование
                    Минимальное количество баллов для вступительных испытаний <b>30 баллов</b>.
                  </div>
                </div>
              </div>
            </div>

          </div>
        </ExtensionCard>  
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "@vue/runtime-core";
import ExtensionCard from "@/components/ExtensionCard.vue";

export default defineComponent({
  data: () => ({
    choosedGrade: 'Бакалавриат',
    choosedCard: 0,
    grades: [
      {
        name: "Бакалавриат",
        directions: [
          {
            name: "09.03.02 Информационные системы и технологии",
            budgetPlaces: 75,
            contractPlaces: 15,
            programs: [
              "Большие данные и машинное обучение (Machine Learning & Big Data)",
              "Компьютерные науки и интеллектуальный анализ данных (Computer Science and Data Mining)",
            ],
            price: "281 600",
            exams: [
              "Математика",
              "Информатика и ИКТ или физика",
              "Русский язык",
            ],
            spoExams: [
              "Информационные технологии",
              "Архитектура аппаратных средств",
              "Русский язык",
            ],
            discounts: [
              "от 180 баллов – 30%",
              "от 201 балла – 40%",
              "от 221 балла – 50%",
            ],
          },
          {
            name: "09.03.03 Прикладная информатика",
            budgetPlaces: 52,
            contractPlaces: 8,
            programs: [
              "Системы искусственного интеллекта",
              "Прикладная информатика в экономике",
            ],
            price: "281 600",
            exams: [
              "Математика",
              "Информатика и ИКТ или физика",
              "Русский язык",
            ],
            spoExams: [
              "Информационные технологии",
              "Архитектура аппаратных средств",
              "Русский язык",
            ],
            discounts: [
              "от 180 баллов – 30%",
              "от 201 балла – 40%",
              "от 221 балла – 50%",
            ],
          },
          {
            name: "38.03.01 Экономика",
            budgetPlaces: 15,
            contractPlaces: 110,
            programs: [
              "Финансовый и управленческий учет и аудит в цифровой экономике",
              "Финансы и кредит в цифровой экономике",
              "Экономика предприятий и организаций",
              "Корпоративный учет и финансовый менеджмент",
              "Мировая экономика и внешнеэкономическая деятельность",
            ],
            price: "251 350",
            exams: [
              "Математика",
              "Обществознание или История или География или Информатика и ИКТ или Иностранный язык",
              "Русский язык",
            ],
            spoExams: ["Экономика организации", "Менеджмент", "Русский язык"],
            discounts: [
              "от 180 баллов – 30%",
              "от 201 балла – 40%",
              "от 221 балла – 50%",
            ],
          },
          {
            name: "38.03.02 Менеджмент",
            budgetPlaces: 5,
            contractPlaces: 25,
            programs: [
              "Бизнес-логистика",
              "Маркетинг в цифровой экономике",
              "Управление бизнесом",
            ],
            price: "251 350",
            exams: [
              "Математика",
              "Обществознание или История или География или Информатика и ИКТ или Иностранный язык",
              "Русский язык",
            ],
            spoExams: ["Экономика организации", "Менеджмент", "Русский язык"],
            discounts: [
              "от 180 баллов – 30%",
              "от 201 балла – 40%",
              "от 221 балла – 50%",
            ],
          },
          {
            name: "38.03.04\tГосударственное и муниципальное управление",
            budgetPlaces: 5,
            contractPlaces: 25,
            programs: ["Муниципальное управление"],
            price: "251 350",
            exams: [
              "Математика",
              "Обществознание или История или География или Информатика и ИКТ или Иностранный язык",
              "Русский язык",
            ],
            spoExams: ["Экономика организации", "Менеджмент", "Русский язык"],
            discounts: [
              "от 180 баллов – 30%",
              "от 201 балла – 40%",
              "от 221 балла – 50%",
            ],
          },
          {
            name: "42.03.01 Реклама и связи с общественностью",
            budgetPlaces: 0,
            contractPlaces: 30,
            programs: [
              "Реклама и связи с общественностью в отраслях экономики",
            ],
            price: "251 350",
            exams: [
              "Русский язык",
              "Обществознание",
              "История или Информатика и ИКТ или Иностранный язык",
            ],
            spoExams: ["Экономика организации", "Менеджмент", "Русский язык"],
            discounts: [
              "от 180 баллов – 30%",
              "от 201 балла – 40%",
              "от 221 балла – 50%",
            ],
          },
          {
            name: "43.03.02 Туризм",
            budgetPlaces: 0,
            contractPlaces: 30,
            programs: ["Организация и предоставление туристических услуг"],
            price: "251 350",
            exams: [
              "Русский язык",
              "История",
              "Обществознание или География или Иностранный язык",
            ],
            spoExams: ["Русский язык", "Психология", "Экономика организации"],
            discounts: [
              "от 180 баллов – 30%",
              "от 201 балла – 40%",
              "от 221 балла – 50%",
            ],
          },
          {
            name: "44.03.04 Профессиональное обучение (по отраслям)",
            budgetPlaces: 75,
            contractPlaces: 15,
            programs: [
              "Экономика и управление",
              "Информационные технологии в образовании",
            ],
            price: "251 350",
            exams: [
              "Математика",
              "Обществознание или История или География или Информатика и ИКТ или Иностранный язык",
              "Русский язык",
            ],
            spoExams: ["Педагогика", "Психология", "Русский язык"],
            discounts: [
              "от 180 баллов – 30%",
              "от 201 балла – 40%",
              "от 221 балла – 50%",
            ],
          },
        ],
      },
      {
        name: "Специалитет",
        directions: [
          {
            name: "38.05.01 Экономическая безопасность",
            budgetPlaces: 10,
            contractPlaces: 50,
            programs: [
              "Экономико-правовое обеспечение экономической безопасности",
            ],
            price: "251 350",
            exams: [
              "Математика",
              "Обществознание или История или География или Информатика и ИКТ или Иностранный язык",
              "Русский язык",
            ],
            spoExams: ["Экономика организации", "Менеджмент", "Русский язык"],
            discounts: [
              "от 180 баллов – 30%",
              "от 201 балла – 40%",
              "от 221 балла – 50%",
            ],
          },
        ],
      },
      {
        name: "Магистратура",
        directions: [
          {
            name: "09.04.02 Информационные системы и технологии",
            budgetPlaces: 25,
            contractPlaces: 5,
            programs: [
              "Науки о данных (Data Science)",
            ],
            price: "301 350",
            exams: [
              "09.04.02 Информационные системы и технологии",
            ],
            discounts: [
              "от 80 баллов – 35%",
            ],
          },
          {
            name: "09.04.03 Прикладная информатика",
            budgetPlaces: 40,
            contractPlaces: 4,
            programs: [
              "Информационные системы в логистике", 
              "Цифровые технологии в экономике",
            ],
            price: "301 350",
            exams: [
              "09.04.03 Прикладная информатика",
            ],
            discounts: [
              "от 80 баллов – 35%",
            ],
          },
          {
            name: "38.04.01 Экономика",
            budgetPlaces: 10,
            contractPlaces: 20,
            programs: [
              "Корпоративный учет и налогообложение в цифровой экономике",
              "Экономика и управление",
              "Инновационное развитие экономики АПК",
              "Внутренний аудит и анализ бизнес-процессов в цифровой экономике",
              "Международные аграрные рынки",
              "Оценка бизнеса и корпоративные финансы в цифровой экономике",
            ],
            price: "269 800",
            exams: [
              "38.04.01 Экономика",
            ],
            discounts: [
              "от 80 баллов – 35%",
            ],
          },
          {
            name: "38.04.02 Менеджмент",
            budgetPlaces: 5,
            contractPlaces: 15,
            programs: [
              "Управление цепями поставок в цифровой экономике",
              "Управление проектами",
              "Управленческий консалтинг",
              "Управление устойчивым развитием отраслей и предприятий",
            ],
            price: "269 800",
            exams: [
              "38.04.02 Менеджмент",
            ],
            discounts: [
              "от 80 баллов – 35%",
            ],
          },
          {
            name: "44.04.04 Профессиональное обучение (по отраслям)",
            budgetPlaces: 45,
            contractPlaces: 2,
            programs: [
              "Информатизация профессионального образования",
            ],
            price: "269 800",
            exams: [
              "44.04.04 Профессиональное обучение",
            ],
            discounts: [
              "от 80 баллов – 35%",
            ],
          },
        ],
      },
    ],
  }),
  methods: {
    chooseGrade(gradeName : string) {
      this.choosedCard = 0
      this.choosedGrade = gradeName
    },
    changeState(index : number) {
      if (this.choosedCard === index) {
        this.choosedCard = -1
      }
      else {
        this.choosedCard = index
      }
    }
  },
  components: { ExtensionCard },
});
</script>

<style scoped>
.directions {
  margin-top: 64px;
  width: 100%;
  max-width: 1100px;
  padding: 0px 15px;
}
.direcions__buttons {
  display: flex;
  justify-content: center;
  gap: 16px;
  margin-bottom: 50px;
  margin-top: 40px;
}
.directions__button {
  width: 240px;
  font-size: 32px;
  line-height: 58px;
  display: flex;
  flex-direction: column;
  align-items: center;
  transition: all 1s;
  color: #AC8754;
}
.directions__button--choosed {
  font-weight: 700;
  color: var(--dark-green-text);
}
.directions__button--unchoosed {
  font-weight: 700;
  color: #AC8754;
}
.directions__button::after {
  content: '';
  height: 2px;
  width: 60%;
  border-radius: 2px;
  transition: all .3s;
}
.directions__button--choosed::after {
  background: var(--dark-green-text);
}
.directions__button--unchoosed::after {
  background: rgba(0, 0, 0, 0);
}
.directions__extension-cards {
  display: flex;
  flex-direction: column;
  gap: 32px;
}
.direction__places-group {
  justify-content: center;
  display: flex;
  gap: 15%;
  margin-bottom: 48px;
}
.direction__places {
  display: grid;
  grid-template-columns: 54px 1fr;
  column-gap: 16px;
  align-items: center;
}
.direction__places-icon {
  grid-row: 1 / 3;
}
.direction__places-title {
  font-weight: 500;
  font-size: 16px;
  line-height: 28px;
}
.direction__places-quantity {
  font-weight: 700;
  font-size: 24px;
  line-height: 28px;
} 
.direction__profiles {
  margin-bottom: 42px;
}
.direction__section {
  display: grid;
  grid-template-columns: 110px auto;
  gap: 48px;
}
.direction__section-body {
  padding-top: 16px;
}
.direction__section-title {
  font-weight: 700;
  font-size: 16px;
  line-height: 28px;
  margin-bottom: 8px;
}
.direction__section-list {
  display: flex;
  flex-direction: column;
  gap: 8px;
}
.direction__section-item {
  display: grid;
  grid-template-columns: 24px auto;
  gap: 16px;
  align-items: center;
  font-weight: 500;
  font-size: 16px;
  line-height: 28px;
}
b {
  font-weight: 700;
}
.direction__discounts {
  margin-top: 16px;
  padding-left: 40px;
  display: flex;
  flex-direction: column;
  gap: 8px;
}
.direction__discount {
  display: grid;
  grid-template-columns: 24px auto;
  gap: 16px;
  align-items: center;
}
.direction__examination-sections {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
}
.direction__examination-section-list {
  padding-left: 20px;
}
.direction__examination-section-item {
  font-weight: 500;
  font-size: 16px;
  line-height: 36px;
}
@media (max-width: 500px) {
.direcions__buttons {
  flex-direction: column;
  align-items: center;
}
  
}
</style>