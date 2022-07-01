<template>
  <div class="form-section">
    <div class="form-section__form form">
      <div class="form__input">
        <img
          class="form__input-icon"
          src="@/assets/icons/person.svg"
        />
        <input
          class="form__input-field" 
          type="text"
          placeholder="Ваше имя"
          v-model="name"
        />
      </div>
      <div class="form__input">
        <img
          class="form__input-icon"
          src="@/assets/icons/mail.svg"
        />
        <input
          class="form__input-field" 
          type="text"
          placeholder="Ваш почтовый адрес"
          v-model="email"
        />
      </div>
      <textarea 
        class="form__textarea"
        placeholder="Задайте нам любой вопрос, который Вас интересует"
        v-model="question"
      ></textarea>
      <div 
        class="form__submit-btn landing__button--primary"
        @click="sendFormData()"
      >Задать вопрос </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "@vue/runtime-core";

export default defineComponent({
  // В данной переменной хранятся данные, которые пользователи вводят на клиенте. Сюда надо прикрутить скрипт на пыхе,
  // чтобы он отправлял данные из этой переменной на почту Фоминой / Мырксиной.
  data: () => ({
    name: '',
    email: '',
    question: ''
  }),
  methods: {
    async sendFormData() {
      const res = await fetch('ссылка на сервер', {
        method: 'POST',
        headers: { 
          'Content-type': 'application/json' 
        },
        body: JSON.stringify({
          name: this.name,
          email: this.email,
          question: this.question
        })
      }) 
    }
  }
})
</script>

<style scoped>
.form-section {
  background-image: url('../../assets/form-background.png');
  background-size: cover;
  background-position: center;
  height: 960px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 80px;
}
.form {
  height: 500px;
  width: 500px;
  background: url('../../assets/form-background.svg');
  background-position: center;
  background-size: contain;
  padding: 64px 86px;
}
.form__input {
  margin-bottom: 8px;
  display: grid;
  grid-template-columns: 0px auto;
  align-items: center;
}
.form__input-icon {
  z-index: 10;
  margin-left: 20px;
}
.form__input-field, .form__textarea {
  width: 100%;
  background: #FFFFFF;
  border: 1px solid #D5D5D5;
  box-shadow: inset 3px 5px 4px rgba(0, 0, 0, 0.17);
  border-radius: 34px;
  font-weight: 500;
  font-size: 16px;
  line-height: 28px;
  color: #A38255;
}
.form__input-field::placeholder, .form__textarea::placeholder {
  font-weight: 500;
  font-size: 16px;
  line-height: 28px;
  color: #A38255;
}
.form__input-field {
  height: 56px;
  padding: 14px 14px 14px 60px;
}
.form__textarea {
  margin-top: calc(24px - 8px);
  min-height: 160px;
  padding: 14px 20px;
  resize: none;
}
.form__submit-btn {
  margin-top: 24px;
  height: 40px;
}
</style>