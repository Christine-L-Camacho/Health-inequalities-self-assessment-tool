<template>
  <!--   <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <NavBar :page="activePage" @changePage="changePage"/>

    <div v-if="activePage === 'Instructions'" class="SiteBanner" style="background-image:url(https://nhsproviders.org/media/689135/web-hero-transformation-4.png);">
      <a class="" >
          <div class="SiteContainer">
              <div class="SiteBanner-inner">
                  <h1>Health Inequalities Self-Assessment Tool</h1>
              </div>
          </div>
      </a>
  </div>

  <BreadCrumb :page="activePage"/>

  <div class="SiteContainer">
    <div class="standard-grid">
      <div v-if="activePage === 'Instructions'">
        <InstructionsPage @changePage="changePage"/>
      </div>

      <div v-if="activePage === 'Section 1'" class="row">
        <QuestionSection :sect="'1'" :theme="'1 - Building public health capacity & capability'" :questions="section1" :existingselection="section1Scores" @changeScore="updateScoresSection1"/>
      </div>
      <div v-if="activePage === 'Section 2'" class="row">
        <QuestionSection :sect="'2'" :theme="'2 - Data, insight, evidence and evaluation'" :questions="section2" :existingselection="section2Scores" @changeScore="updateScoresSection2"/>
      </div>
    </div>
  </div>
  <footer class="SiteSubFooter">
    <div class="SiteContainer">
      <div class="SiteSubFooter-copyright">© NHS Providers 2024</div>
      <div class="SiteSubFooter-charity">Registered Charity 1140900 | Registered in England No 07525114</div>
    </div>
  </footer>
</template>

<script>
import InstructionsPage from './components/InstructionsPage.vue'
import questionsections from './questions.js'
import NavBar from './components/NavBar.vue'
import BreadCrumb from './components/BreadCrumb.vue'
import QuestionSection from './components/QuestionSection.vue'

export default {
  name: 'App',
  components: {
    InstructionsPage,
    NavBar,
    BreadCrumb,
    QuestionSection,
  },
  data() {
    return {
      activePage: "Instructions",
      section1: questionsections.section1,
      section1TotalScore: 0,
      section1Scores: {},
      section2: questionsections.section2,
      section2TotalScore: 0,
      section2Scores: {},
    };
  },
  methods: {
    changePage: function (page) {
      this.activePage=page;

    },
    updateScoresSection1: function([q_num, score]) {
      this.section1Scores[q_num] = score;
      this.section1TotalScore = 0;
      for (var key in this.section1Scores) {
        this.section1TotalScore += parseInt(this.section1Scores[key])
      }
      console.log('Section 1 total score: ' + this.section1TotalScore)
    },
    updateScoresSection2: function([q_num, score]) {
      this.section2Scores[q_num] = score;
      this.section2TotalScore = 0;
      for (var key in this.section2Scores) {
        this.section2TotalScore += parseInt(this.section2Scores[key])
      }
      console.log('Section 2 total score: ' + this.section2TotalScore)
    },
  },
}
</script>

<style>

</style>
