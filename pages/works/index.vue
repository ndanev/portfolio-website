<template>
  <div class="work">
    <div class="hero">
      <div class="container">
        <div class="row">
          <div class="col-md-12">
            <h1 class="hero-title">
              {{ worksContent.heroTitle }}
            </h1>
            <p class="hero-lead">
              <span>{{ worksContent.heroSubtitleAddition }}</span>
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="section">
      <div class="container">
        <div class="row">
          <div v-for="project in projects" :key="project.id" class="col-md-12 mb-5 project">
            <div class="row">
              <div class="col-md-6 mb-3 mb-md-0">
                <img
                  :src="project.image"
                  class="img-fluid"
                  width="402"
                  height="313"
                  :alt="project.title"
                  :title="project.title"
                >
              </div>
              <div class="col-md-6 d-flex flex-column justify-content-center">
                <h3 class="project-title">
                  {{ project.title }}
                </h3>
                <div class="project-subtitle">
                  {{ project.subtitle }}
                </div>
                <p class="project-desc">
                  {{ project.desc }} <br>
                  {{ project.technologies }} <br>
                  <em>{{ project.responsive }}</em>
                </p>
                <div v-if="project.githubLink" class="mb-1">
                  - <a :href="project.githubLink" class="project-link" target="_blank">Github Link <i class="fas fa-external-link-alt" /></a>
                </div>
                <div v-if="project.githubLink_2" class="mb-1">
                  - <a :href="project.githubLink_2" class="project-link" target="_blank">Github Link - Backend <i class="fas fa-external-link-alt" /></a>
                </div>
                <div v-if="project.website">
                  - <a :href="project.website" class="project-link" target="_blank">Website <i class="fas fa-external-link-alt" /></a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import mqttSportsScore from '@/assets/images/mqtt-sports-score.png';
import northPark from '@/assets/images/northpark.png';
import phillipsPlace from '@/assets/images/phillips-place.png';
import carVertu from '@/assets/images/auto_pregled.png';

const worksContent = {
  heroTitle: 'Portfolio',
  heroSubtitle: 'Personal',
  heroSubtitleAddition: 'Projects'
}

const projects = [
  {
    id: 0,
    title: 'North Park Shopping Center',
    subtitle: '(Online Real-Time Sports Score Update Systems)',
    image: northPark,
    desc: "- Real-time sports (football, basketball ...) update system. Created an admin interface for uploading scores and match details, a viewer interface for watching live updates, and a backend that uses MQTT to broadcast changes instantly to every connected client.",
    technologies: '- The technologies used include Vue, NodeJS (Express), MQTT portocol',
    responsive: '- Full Responsive',
    githubLink: '',
    githubLink_2: '',
    website: 'https://northparkcenter.com/' //
  },
  {
    id: 1,
    title: 'Phillips Place',
    subtitle: '(Online Real-Time Sports Score Update Systems)',
    image: phillipsPlace,
    desc: "- Real-time sports (football, basketball ...) update system. Created an admin interface for uploading scores and match details, a viewer interface for watching live updates, and a backend that uses MQTT to broadcast changes instantly to every connected client.",
    technologies: '- The technologies used include Vue, NodeJS (Express), MQTT portocol',
    responsive: '- Full Responsive',
    githubLink: '',
    githubLink_2: '',
    website: 'https://phillipsplacecharlotte.netlify.app/' //
  },
  {
    id: 2,
    title: 'Car Vertu',
    subtitle: '(Online Real-Time Sports Score Update Systems)',
    image: carVertu,
    desc: "- Real-time sports (football, basketball ...) update system. Created an admin interface for uploading scores and match details, a viewer interface for watching live updates, and a backend that uses MQTT to broadcast changes instantly to every connected client.",
    technologies: '- The technologies used include Vue, NodeJS (Express), MQTT portocol',
    responsive: '- Full Responsive',
    githubLink: 'https://github.com/ndanev/car-review',
    githubLink_2: '',
    website: 'https://auto-pregled.netlify.app/' //
  },
  {
    id: 3,
    title: 'MQTT Sports Score',
    subtitle: '(Online Real-Time Sports Score Update Systems)',
    image: mqttSportsScore,
    desc: "- Real-time sports (football, basketball ...) update system. Created an admin interface for uploading scores and match details, a viewer interface for watching live updates, and a backend that uses MQTT to broadcast changes instantly to every connected client.",
    technologies: '- The technologies used include Vue, NodeJS (Express), MQTT portocol',
    responsive: '- Full Responsive',
    githubLink: 'https://github.com/ndanev/mqtt-sports-score-frontend',
    githubLink_2: 'https://github.com/ndanev/mqtt-sports-score-backend',
    website: '' //
  }
]
</script>

<style>
.work .hero-title {
  padding-bottom: 0;
  margin-bottom: 1rem;
}

.work .hero-lead {
  margin-bottom: 40px;
}

.work .hero-lead span {
  color: #f33c7a;
}

.project img {
  border: 1px solid #d9d9d9;
}

.project-link {
  color: #2d1948;
  font-weight: bold;
  -webkit-transition: all .25s;
  -o-transition: all .25s;
  transition: all .25s;
}

.project-link i {
  color: #f33c7a;
}

.project-link:hover {
  color: #f33c7a;
}

.project-subtitle {
  font-size: 1rem;
  margin-bottom: .8rem;
  font-weight: 500;
}
</style>