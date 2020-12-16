<template>
  <div class="form-wrap">
    <form v-show='!submitted' class="form" @submit.prevent="submit">
      <h1 class="form-header">Форма заявки</h1>
      <div class="form-name flex">
        <label class="label" for="name">ФИО</label>
        <input class="name" type="text" name="name" id="name" v-model="name.value">
        <p v-show="!name.value">Обязательное поле</p>
      </div>            

      <div class="form-email flex">
        <label class="label" for="email">Email</label>
        <input class="email" type="email" name="email" id="email" v-model="email.value">
        <p v-show="!email.value">Обязательное поле</p>
      </div>

      <div class="form-tel flex">
        <label class="label" for="tel">Телефон</label>
        <input class="tel" type="tel" name="tel" id="tel" v-model="tel.value">
        <p v-show="!tel.value">Обязательное поле</p>
      </div>

      <div class="form-comment flex">
        <label class="label" for="textarea">Комментарий</label>
        <textarea class="comment" name="textarea" id="textarea" v-model="comment.value"></textarea>
      </div>

      <div class="form-legacy">
        <input class="legacy" type="checkbox" id="checkbox"
          :value="legacy.value" 
          v-model="legacy.value">
        <label class="label"  for="checkbox" >Согласие на обработку персональных данных</label>
        <p v-show="!legacy.value">Обязательное поле</p>
      </div>

      <div class="form-btn flex">
        <button type='submit' class="btn">Отправить заявку</button>
      </div>
    </form>
    <div v-show='submitted' class="form-success">
      <div class="succes">
        <h1>Ваша заявка успешно отправлена.</h1>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Form',
    data() {
      return {
        name: {
          value: '',
        },
        email: {
          value: "",
        },
        tel: {
          value: "",
        },
        legacy: {
          value: '',
        },
        comment: {
          value: '',
        },
        submitted: false,
      }
    },
    methods: {
      submit() {
        if (this.name.value && this.email.value && this.tel.value&& this.legacy.value){
          this.submitted = true;
        }
        else 
          alert('Заполните все обязательные поля');
      }
    }
}
</script>

<style scoped>
  .form,
  .form-success {
    max-width: 600px;
    padding: 50px;
    padding-top: 0;
    margin: 0 auto;
    font-size: 20px;
    border: 1px #da711d solid;
  }

  .flex {
    display: flex;
    flex-direction: column;
    justify-content: left;
    align-items: left;
  }

  div {
    margin-bottom: 10px;
  }

  input,
  textarea {
    font-size: 17px;
    border: 1px #da711d solid;
  }

  input:hover,
  textarea:hover {
    border: 1px #ef891c solid;
  }

  label {
    margin-bottom: 5px;
    margin-right: 5px;
  } 

  textarea {
    height: 60px;
    resize: vertical;
  }

  .btn {
    padding: 10px;
    background-color: #ef831c;
    font-weight: 700;
    color: white;
    border: 1px #da711d solid;
  }

  .btn:active,
  .btn:hover {
    background-color: white;
    color: #ef831c;
  }

  p {
    font-size: 13px;
    color: #ef831c;
    margin: 0;
    padding: 5px;
  }
</style>