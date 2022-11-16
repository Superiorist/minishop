<template>
  <div class="contact-form" id="contact-form">

   
	<div class="contact-form__ul">

		<button class="close__btn" @click="$emit('close')">X</button>
	
		<input class="contact-form__input" placeholder="Товар" disabled :value="data.title"/>

		<div class="contact-form-1__ul">
			<div class="contact-form-1__container">
				
				<input class="contact-form__input" v-model="user.name" placeholder="Имя"/>
			</div>
			<div class="contact-form-1__container">
				
				<input class="contact-form__input" v-model="user.phone" placeholder="Телефон"/>
			</div>
		</div>
		<button class="contact-form__button" @click="checkPhone()">Send Message</button>
	</div>


  </div>
</template>



<script>

export default {
  name: 'contactForm',
  props: ['data'],
  components: {
   
  },
  data() {
  	return {
  		user: {
  			name: 'Асет',
  			phone: '89253879344',
        	title: '',
  		}
  	}
  },
  methods: {
    
    checkPhone() {
      let regex = /^(\+7|7|8)?[\s\-]?\(?[489][0-9]{2}\)?[\s\-]?[0-9]{3}[\s\-]?[0-9]{2}[\s\-]?[0-9]{2}$/;
      let phone = '89000000000';
    	if (!regex.test(this.user.phone) || this.user.name == ''){
       alert('Ошибка при вводе данных!');
       } else{
       ym(91198556,'reachGoal','clickSend')
       alert('Отлично!');
      } 
       console.log (this.user.name)
    },
 }
}
</script>


<style scoped>
span {
	cursor: pointer;
}
.contact-form__ul {
	max-width: 436px;
	margin: 0 auto;
}
textarea {
	max-width: 436px;
	min-height: 107px;
}
.contact-form-1__container {
	width: 100%;
}
.contact-form-1__container:nth-child(1) {
	padding-right: 20px;
}
.contact-form__label {
	color: #656E75;
	text-align:left;
	margin-bottom: 4px;
	margin-top: 16px;
}
h3 {
	margin-top: 32px;
	margin-bottom: 16px;
	color: #5816F1;
}
h1 {
	margin-bottom: 16px;
}
span {
	color: #5816F1;
}
p {
	color: black;
}
.contact-form__p {
	margin-bottom: 56px;

}

.close__btn {
	background-color: white;
    border: none;
    font-weight: bold;
    transform: translate(198px, -23px);
    font-size: 19px;
	cursor: pointer;
}
.contact-form {
	background-color: #00000075;
    width: 100%;
    height: 100vh;
    position: fixed;
    top: 0;
    left: 0;
}
.contact-form__input {
	display: block;
	width: 100%;
	height: 48px;
	font-style: normal;
	font-weight: 400;
	font-size: 15px;
	line-height: 22px;
	margin-bottom: 32px;
	

	background-clip: padding-box;
	border: 1px solid #656E75;
	border-radius: 0;
	box-shadow: none;
	transition: all .2s linear;
	padding: 8px;
	box-sizing: border-box;
}
.contact-form__input::placeholder {
	color: #212529;
	opacity: 0.4;
}
.contact-form__input:focus {
	border: 1px solid #656E75;
	border-radius: 0;
	outline: 0;
}
.contact-form__ul {
	position: absolute;
	transform: translate(-50%, -50%);
	top: 50%;
	left: 50%;
	background-color: white;
	box-sizing: border-box;
	padding: 40px;	
	min-width: 430px;
}
.contact-form-1__ul {
	display: flex;
    flex-direction: row;
    justify-content: space-between;
}
.contact-form__button {
	padding: 9px 34px;
  	background: var(--contact-button-color);
  	color: var(--contact-text-button-color);
  	font-style: normal;
	font-weight: 700;
	font-size: 15px;
	line-height: 22px;
	transition: all 0.3s ease;
	cursor: pointer;
}
.contact-form__button:hover {
	background-color: var(--contact-button-hover-color)
}
.contact-form__button:active {
	background-color: var(--contact-button-active-color)
}
@media (max-width: 650px) {
	.contact-form__p {
	    font-weight: 700;
	    font-size: 14px;
	    line-height: 20px;
	    margin-bottom: 34px;
	}
	.contact-form-1__ul {
		display: flex;
    	flex-direction: column;
	}
	.contact-form__input {
		margin-bottom: 24px;
	}
	h3 {
		margin-top: 24px;
		margin-bottom: 16px;
	}
	.contact-form-1__container {
		padding-right: 0 !important;
	}
}
</style>











