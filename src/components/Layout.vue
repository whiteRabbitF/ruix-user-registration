<template>
  <div>
    <div class="split-screen">

      <div class="layout-container">
        
      <header>
        <div class="logo">
          <img src="/assets/rubik-logo.png" alt="">
        </div>

        <div class="lang-list">
          <label for="languages"></label>
            
          <div class="custom-select">
    <div class="selected-option" @click="toggleDropdown">
      <span>{{ dropdownOpen ? '' : `${selectedLanguageValue}` }}</span>
      <img :src="`/assets/flags/${selectedLanguage}.png`" :alt="`${selectedLanguage} flag`" class="flag-icon" />
    </div>
    <div v-show="dropdownOpen" class="options">
      <div v-for="language in languages" :key="language.value" @click="selectLanguage(language.value)">
        <h3 v-if="dropdownOpen">{{ language.label }}</h3>
        <img :src="`/assets/flags/${language.value}.png`" :alt="`${language.label} flag`" class="flag-icon" />
      </div>
    </div>
    </div>


    <main>
    <div class="welcome-msgs">
      <h1>WELCOME RUIX</h1>
      <h2 class="msg-2">Welcome to Ruix. dashboard Community</h2>
    </div>

    <div class="google">
      <button class="google-btn">
        <img src="/assets/google-icon.png" alt="">
        <div>Continue With Google</div>
      </button>
    </div>

    <div class="or">
      <div class="horizontal-line-1"></div>
    <p>Or</p>
      <div class="horizontal-line-2"></div>
    </div>

    <div class="registration">
      

      <input type="name" placeholder="Name" required>
      <input type="email" placeholder="Email" required>
      <input type="password" placeholder="Password" required>

      <div class="remember">
        <input type="checkbox" id="rememberCheckbox">
        <label for="rememberCheckbox">Remember Me</label>
      </div>


      <button class="reg-btn">Register</button>

      <div class="log-in">
        <p>Already have an account?</p>
        <button class="log-in-btn">Log in</button>
      </div>
    </div>
  </main>

    </div>
  </header>
</div>

    <div class="image-container">
    </div>

    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedLanguage: 'english',
      selectedLanguageValue: 'EN', // Добавлено для хранения значения выбранного языка
      dropdownOpen: false,
      languages: [
        { value: 'english', label: 'EN' },
        { value: 'spanish', label: 'SP' },
        { value: 'french', label: 'FR' },
      ],
    };
  },
  methods: {
    toggleDropdown() {
      this.dropdownOpen = !this.dropdownOpen;
    },
    selectLanguage(language) {
      this.selectedLanguage = language;
      this.selectedLanguageValue = this.languages.find(lang => lang.value === language)?.label || '';
      this.dropdownOpen = false;
    },
  },
};
</script>

<style scoped>
.split-screen {
  display: flex;
  height: 100vh;
  width: 100vw;
  margin: 0;
  padding: 0;
}

.image-container,
.layout-container {
  flex: 2;
  overflow: hidden;
  position: relative;
}

.logo img{
  width: 160px;
  height: auto;
}

.logo{
  position: absolute;
  top: 30px;
  left: 80px;
}

.lang-list{
  position: absolute;
  top: 30px;
  left: 800px;
}

.image-container {
  background: url('./assets/dynamics-pic.png') center/cover no-repeat;
}

.layout-container {
  display: flex;
  justify-content: center;
  align-items: center;
  background: #f4f4f4;
  color: black;
  font-size: 36pt;
}

.selected-option img {
  width: 40px;
}

.selected-option {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  font-size: 20pt;
  gap: 20px;
}

.options img{
  width: 40px;
}

.custom-select{
  /* display: grid;
  grid-template-columns: repeat(2, 1fr); */
  width: 100px;
  height: 40px;
  padding: 15px;
  border: 1px solid black;
  border-radius: 20px;
  cursor: pointer;
  font-family: 'Urbanist', sans-serif;
}

.custom-select:hover{
  background-color: #a1826649;
  border: none;
}

.options h3{
  font-size: 12pt;
}

.options {
  /* display: grid;
  grid-template-rows: repeat(1, 2fr); */
  font-size: 16pt;
  width: 100px;
  height: 40px;
  padding: 15px;
  margin-top: 20px;
  font-family: 'Urbanist', sans-serif;
}

.lang-list select {
  border-radius: 20px;
  font-size: 14pt;
  padding-left: 20px;
  padding: 20px;
  height: 40px;
}

.welcome-msgs{
  position: absolute;
  display: block;
  width: 500px;
  height: 50px;
  top: 40px;
  left: -500px;
  font-size: 14pt;
  margin-top: 100px;
  font-weight: 300;
  text-align: center;
  
}

.msg-2{
  display: block;
  width: 500px;
  height: 30px;
  font-size: 16pt;
  font-weight: 100;
  text-align: center;
  top: 50px;
  position: absolute;
  font-family: 'Urbanist', sans-serif;
}
.google img{
  width: 20px;
  position: absolute;
  left: 80px;
}
.google{
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 220px;
  left: -450px;
  font-size: 14pt;
  margin-top: 80px;
}

.or{
  position: absolute;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  top: 380px;
  left: -250px;
}

.or p{
  font-size: 18pt;
  color: #AFA8A8;
  font-family: 'Urbanist', sans-serif;
}

.horizontal-line-1 {
  width: 50px;
  height: 2px;
  background-color: #AFA8A8;
  top: 35px;
  left: 30px;
  position: absolute;
}
.horizontal-line-2 {
  width: 50px;
  height: 2px;
  background-color: #AFA8A8;
  top: 35px;
  left: -55px;
  position: absolute;
}

.google button {
  background: transparent;
  cursor: pointer;
  border-radius: 10px;
  border: 1px solid black;
  height: 70px;
  width: 400px;
  font-family: 'Urbanist', sans-serif;
}

.registration{
  position: absolute;
  top: 450px;
  left: -450px;
  font-size: 14pt;
  display: grid;
  grid-template-rows: repeat(6, 1fr);
  width: 400px;
  height: 100px;
  gap: 20px;
}

.registration input{
  display: block;
  width: 380px;
  height: 30px;
  border-radius: 15px;
  border: 1px solid black;
  padding: 15px;
  font-family: 'Urbanist', sans-serif;
}

.remember{
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  flex-direction: column;
  position: absolute;
  width: 500px;
  top: 250px;
  left: -220px;
  font-size: 14pt;
  font-weight: 300;
  font-family: 'Urbanist', sans-serif;
}

.remember input[type="checkbox"] {
  margin-left: 230px;
  width: 15px;
  height: 15px;
}

.reg-btn{
  background: transparent;
  position: absolute;
  width: 400px;
  height: 55px;
  top: 300px;
  left: 0px;
  border-radius: 20px;
  border: 1px solid black;
  background-color: black;
  color: azure;
  font-family: 'Urbanist', sans-serif;
  cursor: pointer;
}

.reg-btn:hover {
  background-color: rgb(61, 57, 57);
}

.log-in{
  display: flex;
  flex-direction: row;
  position: absolute;
  width: 500px;
  top: 350px;
  left: 50px;
  gap: 10px;
  font-size: 16pt;
  text-align: center;
  font-family: 'Urbanist', sans-serif;
}

.log-in-btn{
  background: transparent;
  border: transparent;
  color: #FEC00F;
  cursor: pointer;
  font-family: 'Urbanist', sans-serif;
}
</style>
