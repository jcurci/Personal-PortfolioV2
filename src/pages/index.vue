<template>
  <v-container id="welcomeMsg">
    <img
      class="front-icon"
      src="@/assets/img/Frontend-icon.png"
      align="right"
      alt="Front-End Icon"
    />
    <div
      class="offset-md-1"
    >
      <v-col cols="12" md="6" xs="10">
        <div id="textbox">
          <div>
            <h2 id="typeWriter">
              Hello World, Welcome!
              <div id="border"></div>
            </h2>
          </div>
          <h1>My name is Jhonatan Curci.</h1>
          <h2>
            I am a <span id="highlight">Web Developer</span>
            actually working on <a class="highlight-btn" href="https://www.mdsgroup.com.br/pt/" target="_blank">MDS BRASIL.</a>
          </h2>
        </div>
      </v-col>
      <v-btn 
        class="about-btn"
        to="/resumo"
      ><v-icon>mdi-human-greeting-variant</v-icon> About me</v-btn>
    </div>
  </v-container>
</template>

<style scoped>
#welcomeMsg{
  padding-top: 50px;;
}
#welcomeMsg h1,
h2 {
  color: #ffffff;
  letter-spacing: 2px;
  line-height: 32px;
  font-family: "Lora", serif;
}
.highlight-btn {
  color: #FFEA00;
  text-decoration: underline #FFEA00;
}
#welcomeMsg h1 {
  font-size: 35px;
  font-weight: 400;
  cursor: default;
  line-height: 1.5;
}
#welcomeMsg h2 {
  font-size: 20px;
  font-weight: 300;
  cursor: default;
}
#textbox {
  margin-top: 80px;
}

.about-btn{
  transform: scale(1);
  box-shadow: 0 2px 15px rgba(219, 187, 4, 0.5);
  border: 1.5px solid #FFEA00;
  font-size: 14px;
  border-radius: 10px;
  margin-left: 10px; 
  transition: all 0.3s ease; 
}
.about-btn:hover{
  border-color: #FFEA00; 
  transform: translateY(-3px);
  background-color: #312d018e;
  box-shadow: 0 2px 15px #FFEA00;
}

#typeWriter {
  height: 40px;
  white-space: nowrap;
  overflow: hidden;
  position: relative;
  animation: animated-text 2s steps(25, end) 1s 1 normal both;
}
#border {
  border-bottom: solid 3px #FFEA00;
  position: absolute;
  right: -7px;
  width: 20px;
  animation: animated-cursor 1050ms steps(25, end) infinite;
}
#highlight {
  box-shadow: inset 0 -7px 0 #ffea0436;
}
.front-icon{
  padding: 70px;
  margin-right: 30px;
}
@keyframes animated-text {
  from {
    width: 0;
  }
  to {
    width: 230px;
  }
}
@keyframes animated-cursor {
  from {
    border-bottom-color: #FFEA00;
  }
  to {
    border-bottom-color: transparent;
  }
}
</style>
