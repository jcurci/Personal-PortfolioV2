<template>
    <v-container>
      <h1 align="center">Apresentation</h1>
      <v-row>
        <v-col cols="12" md="4">
          <v-card>
            <v-card-title class="card-h1">About me</v-card-title>
            <v-card-text>
                I’m always looking to grow, take on new responsibilities, 
                and challenge myself in software development. My goal is 
                to be part of a collaborative team where I can contribute 
                my skills, learn from my teammates, and keep evolving as 
                a professional while delivering high-quality results. 
                I'm constantly seeking knowledge and improvement to enhance 
                my work and contribute to the team's and company's success.
                <br>
                I have experience and a strong interest in the following technologies: Vue.js, Vuetify, JavaScript, Angular, TypeScript, and Agile methodologies.
              </v-card-text>
  
              <v-card-title class="card-h1">Education & Experience</v-card-title>
              <div v-for="experience in Experiences" :key="experience.name" class="experience">
              <v-card-text>
                <h3 class="card-h3">{{ experience.name }}</h3>
                <v-card-subtitle>{{  experience.duration }}</v-card-subtitle>
                <p>{{ experience.description }}</p>
                <p>{{ experience.location }}</p>
              </v-card-text>
              </div>
          </v-card>
        </v-col>
        
  
        <v-col cols="12" md="4">
          <v-card>
            <v-card-title class="card-h1">Skills</v-card-title>
            <v-card-text>
              <div v-for="skill in skills" :key="skill.name" class="skill">
                <p>{{ skill.name }} - {{ skill.value }}%</p>
                <v-progress-linear
                  :value="skill.value"
                  color="amber"
                  height="10"
                  :model-value= skill.value
                  striped
                ></v-progress-linear>
              </div>
            </v-card-text>
  
            <v-card-title>Languages</v-card-title>
            <v-card-text>
              <div v-for="language in languages" :key="language.name" class="skill">
                <p>{{ language.name }} - {{ language.value }}%</p>
                <v-progress-linear
                  :value="language.value"
                  color="amber"
                  height="10"
                  :model-value= language.value
                  striped
                ></v-progress-linear>
              </div>
            </v-card-text>
          </v-card>
        </v-col>
  
        <v-col cols="12" md="4">
          <v-card>
            <v-card-title class="card-h1">Resume</v-card-title>
            <v-card-text>
              <p>Dowload my resume clicking in the button bellow: </p>
              <v-spacer></v-spacer>
              <v-btn 
                class="dowload-btn"
                @click="downloadResume">
                Dowload Resume
              </v-btn>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script>
  export default {
    name: 'Portfolio',
    data() {
      return {
        skills: [
          { name: 'Vue.js', value: 60},
          { name: 'Vuetify', value: 45 },
          { name: 'React', value: 20 },
          { name: 'Angular', value: 10 },
          { name: 'JavaScript', value: 70 },
          { name: 'Python', value: 30},
          { name: 'HTML & CSS', value: 85 },
          { name: 'Git & GitHub', value:  90},
          { name: 'UX/UI', value: 65 }
        ],
        languages: [
        { name: 'English', value: 70},
        { name: 'Spanish', value: 40},
        { name: 'Portuguese / Native', value: 100}
        ],
        Experiences: [
          { name: 'RS Serviços', 
          description: 'IT Intern',
          duration: '07.2023 - 12.2023',
          location: 'São Paulo - Brazil'
          },
  
          { name: 'MDS Group', 
          description: 'Web developer Intern',
          duration: '04.2024 - 02.2025',
          location: 'São Paulo - Brazil'
          },
          { name: 'Bachelor: Software Engineering', 
          duration: '2023 - 2026',
          location: 'FIAP | São Paulo - Brazil'
          },
          { name: 'Courses', 
          description: 'Completed courses about development, blockchain, scrum and sustainability.',
          duration: 'Fiap | Alura | Origamid'
          }
  
        ]
      };
    },
    methods: {
    downloadResume() {
      const link = document.createElement('a');
      link.href = '@/Downloads/CV-JhonatanCurci.pdf';
      link.setAttribute('download', 'JhonatanResume.pdf');
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
    }
  }
  
  
  
  }
  </script>
  
  <style scoped>
  h1 {
    padding: 18px;
    font-size: 42px;
    font-family: "Lora", serif;
    text-decoration: underline #FFEA00;
  }
  .card-h1 {
    font-size: 32px;
    font-family: "Lora", serif;
  }
  .card-h3 {
    font-size: 20px;
    font-family: "Lora", serif;
    text-decoration: underline #FFEA00;
  }
  .v-card-subtitle{
    margin-left: -15px;
  }
  
  .skill {
    margin-bottom: 20px;   
  }
  .dowload-btn{
    transform: scale(1);
    border: 1.5px solid #FFEA00;
    border-radius: 10px;
    margin-top: 15px; 
    transition: all 0.3s ease; 
  }
  
  .dowload-btn:hover {
    border-color: #FFEA00; 
    transform: translateY(-3px);
    background-color: #312d018e;
    box-shadow: 0 2px 15px #FFEA00;
  }
  .v-card{
    border-radius: 10px;
    transition: transform 0.5s, box-shadow 0.2s;
    border: 2px solid #FFEA00;
  }
  .v-card:hover{
    transform: translateY(-5px);
  }
  </style>
  