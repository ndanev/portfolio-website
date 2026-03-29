<template>
  <div class="home">
    <div class="hero-home">
      <div class="container h-100">
        <div class="row h-100">
          <div class="col-md-7 offset d-flex justify-content-center flex-column">
            <h2 class="hero-home-title animate-4">
              Hi, I’m Nemanja 👋 <br>
              <span> Frontend Developer</span>
            </h2>
            <p class="hero-lead mb-4 animate-6">
              {{ homeContent.heroSubtitle }}
            </p>
            <div class="hero-button-wrapper animate-8">
              <nuxt-link class="button button-primary d-inline-block me-3 mb-3 mb-md-0" to="#projects">
                {{ homeContent.heroProjectsButton }}
              </nuxt-link>
              <a class="button button-secondary d-inline-block" download href="../assets/files/Nemanja_Danev_CV.pdf">
                {{ homeContent.heroDownloadButton }}
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
    <section class="section section-about">
      <div class="container">
        <div class="row">
          <div class="col-md-12 text-left text-md-center">
            <h2 class="section-title">
              <span>
                {{ homeContent.aboutTitle }}
              </span>
            </h2>
          </div>
        </div>
        <div class="row">
          <div class="col-md-6 d-flex flex-column justify-content-center">
            <h2 class="section-subtitle">
              Turning complex ideas into
              <br>
              <span>Great User Experiences</span>
            </h2>
            <p class="section-lead">
              {{ homeContent.aboutContent }}
            </p>
          </div>
          <div class="col-md-6 text-center">
            <img
              src="@/assets/images/home-about.webp"
              width="500"
              height="500"
              class="img-fluid"
              alt="Creative Agency"
              title="Creative Agency"
            >
          </div>
        </div>
      </div>
    </section>
    <section class="section section-skills">
      <div class="container">
        <div class="row justify-content-center mb-5">
          <div class="col-md-6 text-center">
            <h2 class="section-title">
              <span>
                {{ homeContent.skillsTitle }}
              </span>
            </h2>
          </div>
        </div>
        <div class="row">
          <div v-for="(skill, index) in skills" :key="index" class="col-6 col-md-3">
            <SkillCard :title="skill.title" :image="skill.image" />
          </div>
        </div>
      </div>
    </section>
    <section class="section section-works" id="projects">
      <div class="container-fluid">
        <div class="row justify-content-center mb-5">
          <div class="col-md-4 text-center">
            <h2 class="section-title">
              <span>
                {{ homeContent.worksTitle }}
              </span>
            </h2>
          </div>
        </div>
        <div class="row justify-content-center">
          <div v-for="work in works" :key="work.id" class="col-12 col-sm-6 col-md-3">
            <nuxt-link to="/works">
              <WorkCard :title="work.workTitle" :image="work.img" />
            </nuxt-link>
          </div>
        </div>
      </div>
    </section>
    <section class="section section-process">
      <div class="container">
        <div class="row justify-content-center mb-5">
          <div class="col-md-6 text-center">
            <h2 class="section-title">
              <span>
                {{ homeContent.processTitle }}
              </span>
            </h2>
          </div>
        </div>
        <div class="row">
          <div v-for="(process, index) in workProcess" :key="index" class="col-12 col-sm-6 col-md-4">
            <ProcessCard :title="process.title" :desc="process.desc" />
          </div>
        </div>
      </div>
    </section>
    <section class="section section-contact">
      <div class="container">
        <div class="row justify-content-center mb-5">
          <div class="col-md-6 text-center">
            <h2 class="section-title">
              <span>
                {{ homeContent.contactTitle }}
              </span>
            </h2>
            <p class="section-lead">
              {{ homeContent.contactSubtitle }}
            </p>
          </div>
        </div>
        <div class="row">
          <div class="col-md-12">
            <form class="home-form" @submit.prevent="sendMessage">
              <div class="row">
                <div class="col-md-4">
                  <div class="form-group">
                    <label>{{ homeContent.contactLabelTitle }}</label>
                    <input type="text" class="form-control" :placeholder="homeContent.contactPlaceholderTitle">
                  </div>
                </div>
                <div class="col-md-4">
                  <div class="form-group">
                    <label>{{ homeContent.contactLabelName }}</label>
                    <input type="text" class="form-control" :placeholder="homeContent.contactPlaceholderName">
                  </div>
                </div>
                <div class="col-md-4">
                  <div class="form-group">
                    <label>{{ homeContent.contactLabelEmail }}</label>
                    <input type="text" class="form-control" :placeholder="homeContent.contactPlaceholderEmail">
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12">
                  <div class="form-colntrol">
                    <label>{{ homeContent.contactLabelMessage }}</label>
                    <textarea class="form-group w-100" rows="10" />
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12">
                  <button type="submit" class="button button-primary">
                    {{ homeContent.contactButton }}
                  </button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>


<script setup>
import ProcessCard from '~/components/ProcessCard.vue';
import SkillCard from '~/components/SkillCard.vue';
import WorkCard from '~/components/WorkCard.vue';

// IMAGES
import jobLoop from '@/assets/images/jobloop.webp';
import userFinder from '@/assets/images/user-finder.webp';
import tastyland from '@/assets/images/tastyland.webp';
import mqttSportsScore from '@/assets/images/mqtt-sports-score.png';

import html from '@/assets/images/html.jpg';
import css from '@/assets/images/css.jpg';
import javascript from '@/assets/images/javascript.jpg';
import typescript from '@/assets/images/typescript.png';
import vuejs from '@/assets/images/vuejs.jpg';
import nuxt from '@/assets/images/nuxt.png';
import react from '@/assets/images/react.png';
import next from '@/assets/images/next.png';
import angular from '@/assets/images/angular.png';
import tailwind from '@/assets/images/tailwind.jpg';
import bootstrap from '@/assets/images/bootstrap.jpg';
import nodejs from '@/assets/images/nodejs-logo.webp';

const homeContent = {
  heroSubtitle: 'Several years of experience building high-performance, production-ready applications, working with APIs, dashboards and modern frontend tools.',
  heroDownloadButton: 'Download CV',
  heroProjectsButton: 'Projects',
  aboutTitle: 'About Me',
  aboutContent: 'Over the past 5+ years, I’ve been building web applications with a strong focus on frontend architecture and user experience. Most of my work revolves around Vue.js and Nuxt, where I’ve developed scalable dashboards, integrations with APIs and complex UI systems. I care about writing clean and maintainable code, but also about delivering real value to users through smooth and intuitive interfaces. I’m always looking to improve and stay up to date with modern frontend practices.',
  skillsTitle: 'Skills & Expertise',
  worksTitle: 'Projects',
  processTitle: 'How I Work',
  contactTitle: 'Contact',
  contactSubtitle: 'If you have any question or you want to contact us, feel free to send us an email. We’re here to help you!',
  contactLabelTitle: 'Your Title',
  contactPlaceholderTitle: 'Enter Your Title',
  contactLabelName: 'Your Name',
  contactPlaceholderName: 'Enter Your Name',
  contactLabelEmail: 'Your Email',
  contactPlaceholderEmail: 'Enter Your Email',
  contactLabelMessage: 'Your Message',
  contactButton: 'Send'
}

const skills = [
  {
    title: 'HTML',
    image: html
  },
  {
    title: 'CSS',
    image: css
  },
  {
    title: 'Javascript',
    image: javascript
  },
  {
    title: 'Typescript',
    image: typescript
  },
  {
    title: 'Vue',
    image: vuejs
  },
  {
    title: 'Nuxt',
    image: nuxt
  },
  {
    title: 'React',
    image: react
  },
  {
    title: 'Next',
    image: next
  },
  {
    title: 'Angular',
    image: angular
  },
  {
    title: 'Bootstrap',
    image: bootstrap
  },
  {
    title: 'Tailwind',
    image: tailwind
  },
  {
    title: 'Node (Express)',
    image: nodejs
  }
]

const works = [
  {
    id: 1,
    workTitle: 'MQTT Sports Score',
    img: mqttSportsScore
  },
  {
    id: 2,
    workTitle: 'Job Loop',
    img: jobLoop
  },
  {
    id: 3,
    workTitle: 'Github User Finder',
    img: userFinder
  },
  {
    id: 4,
    workTitle: 'Natural Tasty',
    img: tastyland
  }
]

const workProcess = [
  {
    id: 1,
    title: 'Requirements & Analysis',
    desc: 'Understanding business needs and user goals'
  },
  {
    id: 2,
    title: 'Architecture & Planning',
    desc: 'Structuring scalable and maintainable solutions'
  },
  {
    id: 3,
    title: 'Development',
    desc: 'Building features with clean, reusable code'
  },
  {
    id: 4,
    title: 'Performance & UX',
    desc: 'Optimizing speed and user experience'
  },
  {
    id: 5,
    title: 'Testing & Delivery',
    desc: 'Ensuring quality and production readiness'
  }
]
</script>

<style>
.hero-home {
  background-image: url("@/assets/images/hero-home.webp");
  background-color: rgba(45, 25, 72, 1);
  background-repeat: no-repeat;
  background-size: cover;
  height: calc(100vh - 30px - 85px);
  width: 100%;
}

.hero-home-title {
  color: #ffffff;
  font-size: 4rem;
  font-weight: bold;
  text-transform: uppercase;
  -webkit-animation: .4s ease-out 0s 1 slideInFromLeft;
          animation: .4s ease-out 0s 1 slideInFromLeft;
}

.hero-home-title span {
  color: #f33c7a;
}

.hero-lead {
  color: #ffffff;
  font-size: 1.6rem;
}

.section-about {
  background-color: #2d1948;
}

.section-skills {
  background-color: #1b0c30;
}

.section-skills .section-title {
  margin-bottom: 2rem;
}

.section-works {
  background-color: #2d1948;
}

.section-works .section-title {
  margin-bottom: 2rem;
}

.section-process {
  background-image: url("@/assets/images/work-process-bg.webp");
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

.section-process .section-title {
  margin-bottom: 2rem;
}

.section-contact {
  background-image: url("@/assets/images/contact-bg.webp");
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  position: relative;
  z-index: 1;
}

.section-contact::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(27, 12, 48, .35);
  z-index: -1;
}

.section-contact .section-title {
  margin-bottom: 2rem;
}

.home-form label {
  color: #fff;
  font-weight: bold;
}

.home-form .form-control {
  background-color: #2d1948;
  color: #fff;
  border-radius: 0;
  border: 0;
  height: 45px;
}

.home-form .form-control::-webkit-input-placeholder {
  color: #fff;
}

.home-form .form-control::-moz-placeholder {
  color: #fff;
}

.home-form .form-control:-ms-input-placeholder {
  color: #fff;
}

.home-form .form-control::-ms-input-placeholder {
  color: #fff;
}

.home-form .form-control::placeholder {
  color: #fff;
}

.home-form textarea {
  background-color: #2d1948;
  color: #fff;
  border-radius: 0;
  border: 0;
  padding: 1rem;
}

@-webkit-keyframes slideInFromLeft {
  0% {
    -webkit-transform: translateX(-100%);
            transform: translateX(-100%);
  }
  100% {
    -webkit-transform: translateX(0);
            transform: translateX(0);
  }
}

@keyframes slideInFromLeft {
  0% {
    -webkit-transform: translateX(-100%);
            transform: translateX(-100%);
  }
  100% {
    -webkit-transform: translateX(0);
            transform: translateX(0);
  }
}

.animate-8 {
  -webkit-animation: .8s ease-out 0s 1 slideInFromLeft;
          animation: .8s ease-out 0s 1 slideInFromLeft;
}

.animate-6 {
  -webkit-animation: .6s ease-out 0s 1 slideInFromLeft;
          animation: .6s ease-out 0s 1 slideInFromLeft;
}

.animate-4 {
  -webkit-animation: .4s ease-out 0s 1 slideInFromLeft;
          animation: .4s ease-out 0s 1 slideInFromLeft;
}

@media (max-width: 991px) {
  .hero-home {
    background-position: 75%;
  }
}

@media (max-width: 767px) {
  .hero-lead {
    font-size: 1.2rem;
  }

  .hero-home-title {
    font-size: 2.4rem;
  }
}
</style>