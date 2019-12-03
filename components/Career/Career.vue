<template>
  <div class="career">
    <h1 class="career__title">Career</h1>
    <div class="career__content">
      <div class="career__picture-content">
        <img class="career__picture" src="~/assets/career.svg" />
      </div>
      <div class="career__list">
        <Experience
          v-for="item in experiences"
          :key="item.post"
          :post="item.post"
          :company="item.company"
          :location="item.location"
          :startDate="item.startDate"
          :endDate="item.endDate"
          :description="item.description"
          :objective="item.objective"
          :environment="item.environment"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Experience from "./Experience.vue";

export default {
  components: {
    Experience
  },
  head: {
    link: [
      {
        rel: "stylesheet",
        href: "https://fonts.googleapis.com/css?family=Roboto"
      }
    ]
  },
  data() {
    return {
      name: "career",
      experiences: [
        {
          post: "Full Stack Developer on Aurélia / C#",
          company: "Apside / Berger Levrault",
          location: "Toulouse, France",
          startDate: "March 2019",
          endDate: "September 2019",
          description:
            "Projet de fin d'étude (PFE) au sein de l'ESN Apside, en mission chez le client Berger-Levrault.",
          objective:
            "Conception et réalisation de solutions techniques sur une plateforme web médico-sociale (Dossier administratif, Facturation, Dossier de soins, Planning, Prescription, Connecteur …).",
          environment: "HTML, CSS, TypeScript, Aurelia, C# and REST API."
        },
        {
          post:
            "Project Manager, Integrator and Developer Full Stack JavaScript",
          company: "Armatis-Lc",
          location: "Calais, France",
          startDate: "September 2018",
          endDate: "March 2019",
          description:
            "Projet Innovation et Conception (PIC) réalisé au sein de l'entreprise Armatis-lc accompagné de deux collègues élèves-ingénieurs : Jean-Christophe Meyer et Ulysse Pirlot.",
          objective:
            "Conception d'une solution digitale accompagnant le téléconseiller dans le but de simplifier sa tâche quotidienne et lui offrir des moyens d’agrémenter sa conversation avec le client en prenant appui sur les fichiers de prospection en base et en allant sourcer sur le web des informations pertinentes et géolocalisées.",
          environment: "Node.Js, HTML, CSS, Javascript and C#."
        },
        {
          post: "Intern in Web development under AGILE method",
          company: "U-Need Consulting",
          location: "Toulouse, France",
          startDate: "June 2018",
          endDate: "August 2018",
          description:
            "Stage d'assistant ingénieur au sein de l'entreprise U-Need.",
          objective:
            "Intervention sur l’évolution et l’optimisation d'une application web de gestion. Digitalisation du système de facturation de l’entreprise. Pilotage et réalisation du projet par la mise en place d'une méthode AGILE.",
          environment: "PHP, SQL, Javascript, JQuery, CSS, HTML."
        },
        {
          post: "Integrator, designer and web developer",
          company: "2ST-CI and Wake Up Africa",
          location: "Abidjan, Côte d'Ivoire",
          startDate: "June 2016",
          endDate: "August 2016",
          description:
            "Stage au sein de l'ENS 2ST-CI et l'association Wake Up Africa, association créée par des ivoiriens dans le but de développer les domaines de la santé et de l'éducation en Côte d'Ivoire et, plus globalement, en Afrique.",
          objective:
            "Développement d'une plateforme web d'échange de données médicales ayant pour objectif de faciliter les diagnostics médicaux et de les rendre accessibles dans tout le pays. Création du site officiel de l'association Wake Up Africa.",
          environment: "CSS, HTML, PHP, MySQL, Bootstrap and jQuery."
        }
      ]
    };
  }
};
</script>

<style lang="scss">

$primary-color: #11467f;
$border-color: #cfdae5;

.career {
  background-color: $primary-color;
  padding: 3%;

  &__title {
    text-align: center;
    font-size: 110px;
    color: #ffffff;
    margin: 0 17% 20px 0;
    font-family: Woodchuck-Regular;
    letter-spacing: 3px;
  }

  &__content {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
  }

  &__picture-content {
    width: 36%;
  }

  &__picture {
    width: 100%;
  }

  &__list {
    border-left: 9px solid $border-color;
    margin: auto;
    width: 55%;
    padding-left: 71px;
  }
}
</style>
