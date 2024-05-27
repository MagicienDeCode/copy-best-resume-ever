<template>
  <div class="resume">
    <div class="banner">
      <div class="banner__fullname">{{ person.name.first }} {{ person.name.middle }} {{ person.name.last }}</div>
      <div class="banner__position">{{ person.position }}</div>
      
      <div v-if="person.birth" class="banner__location">{{ lang.born }} {{person.birth.year}} {{ lang.bornIn }} {{person.birth.location}}</div>
      <br/>
      <div class="banner__position">{{ 'Kotlin, Python3, Java' }}</div>
    </div>

    <div class="content">
      <div class="content__left">

        <div class="section">
          <div class="section-headline">
            {{ lang.contact }}
          </div>

          <div class="section-content section-content--plain">
            <div class="section-link">
              <i class="section-link__icon material-icons">business</i>{{ person.contact.street }}
            </div>

            <a
              class="section-link link"
              :href="contactLinks.email">
              <i class="section-link__icon material-icons">mail</i>{{ person.contact.email }}
            </a>
            <!--
            <div class="section-link">
              <i class="section-link__icon material-icons">phone</i>{{ person.contact.phone }}
            </div>
            -->
            <a
              target="_blank"
              v-if="person.contact.website"
              class="section-link link"
              :href="person.contact.website">
              <i class="section-link__icon fa fa-globe"></i>{{ person.contact.website }}
            </a>

            <a
              target="_blank"
              v-if="person.contact.linkedin"
              class="section-link link"
              :href="contactLinks.linkedin">
              <i class="section-link__icon fa fa-linkedin"></i>{{ person.contact.linkedin }}
            </a>

            <a
              target="_blank"
              v-if="person.contact.github"
              class="section-link link"
              :href="contactLinks.github">
              <i class="section-link__icon fa fa-github"></i>{{ person.contact.github }}
            </a>

            <a
              v-if="person.contact.medium"
              class="section-link link"
              :href="contactLinks.medium">
              <i class="section-link__icon fa fa-medium"></i>{{ person.contact.medium }}
            </a>
          </div>
        </div>

         <div
          v-if="person.skills"
          class="section">
          <div class="section-headline">
            {{ lang.skills }}
          </div>

          <div class="section-content-grid">
            <a
              v-for="(skill, index) in person.skills"
              class="grid-item"
              :key="index"
              :class="{ link: skill.url !== undefined}"
              :href="skill.url">
              <span class="squarred-grid-item">
                {{ skill.name }}
              </span>
            </a>
          </div>
        </div>

        <div class="section">
          <div class="section-headline">
            {{ lang.about }}
          </div>

          <div class="section-content section-content--plain">
            {{ person.about }}
            <br/>
            <br/>
            {{ person.about2 }}
            <br/>
            <br/>
             {{ person.about3 }}
            <br/>
            <br/>
             {{ person.about4 }}
            <br/>
          </div>
        </div>

        <div class="section">
          <div class="section-headline">
            {{ 'Language' }}
          </div>

          <div class="section-content section-content--plain">
            {{ 'English   -   French   -   Chinese' }}
          </div>
        </div>

      </div>

      <div class="content__right">
        <div class="section">
          <div class="section-headline">
            <i class="section-headline__icon material-icons">work</i>{{ lang.experience }}
          </div>

          <div class="section-content">
            <a
              target="_blank"
              class="section-content__item"
              :class="{ link: true}"
              :href="'https://www.slimpay.com/fr/'">
              <span class="section-content__header"><img class="company-icon-1"/>{{ '(Full time) Tech Lead' }}</span>


              <span class="section-content__subheader">
                {{ 'SlimPay' }}
                <span class="section-content__plain">{{ 'France' }}</span>
                <span class="section-content__plain--times">{{ 'October 2018 - now (~6 years)' }}</span>
              </span>
              <br/>
              <span class="section-content__text--light--bold">{{ '➡︎ Since 2023, Tech Lead ' }}</span>
              <br/>
              <span class="section-content__text--light">{{ '- Design and develop new open banking products, guiding team members, propose technical improvements.' }}</span>
              <br/>
              <span class="section-content__text--light">{{ '- Integration with Trustly products, new version of SlimCollects (PIS/AIS)' }}</span>
              <br/>
              <span class="section-content__text--light">{{ '- Webhook projects' }}</span>
              <br/>
              <span class="section-content__text--light">{{ '- Instant Payment solution' }}</span>
              
              <br/>
              <span class="section-content__text--light--bold">{{ '➡︎ Since 2021, Full Stack Software Engineer ' }}</span>
              <br/>
              <span class="section-content__text--light">{{ '- PIS team, design and develop new SlimCollect(PIS) ecosystem, springboot, axon framework CQRS, domain driven design, event sourcing.' }}</span>
              <br/>
              <span class="section-content__text--light">{{ '- PaymentFactory team, 1.Resolve balance problems, 2.Help Financial team to prepare ACPR audit, 3.Develop a kotlin based project with SQL native (improve daily reconciliation of balance from 4 days to 1 hour average).' }}</span>
              <br/>
              <span class="section-content__text--light--bold">{{ '➡︎ Since 2018, Junior Software Engineer ' }}</span>
              <br/>
              <span class="section-content__text--light">{{ '- Innovation team, one of the pioneers for Kotlin and open-banking (PSD2) product. 1.Proof of Concept with Kotlin, connect to sandbox of bank. 2.ETL system with Kotlin(Extract-Transform-Load).' }}</span>
              <br/>
              <br/>
              <span class="section-content__text--light--bold">{{ 'SpringBoot, Kotlin, Java, Domain Driven Design, Event Sourcing, CQRS, AxonFramework, Kafka, DynamoDB, PostgreSQL, Docker' }}</span>
              <!--
              <br/>
              <span class="section-content__text--light">{{ '- Develop new feautres in legacy systems in Java(8 and 11), maintaining different microservices.' }}</span>
              -->
            </a>
            <br/>
            <a
              target="_blank"
              class="section-content__item"
              :class="{ link: true}"
              :href="'https://monbanquet.fr/'">

              <span class="section-content__header"><img class="company-icon-2"/>{{ '(Internship) Full Stack Developer' }}</span>
              <span class="section-content__subheader">
                {{ 'Monbanquet.fr' }}
                <span class="section-content__plain">{{ 'France' }}</span>
                <span class="section-content__plain--times2">{{ 'April 2018 - September 2018 (6 months)' }}</span>
              </span>

              <br/>
              <span class="section-content__text--light">{{ '- Refactoring back office, participate in the development of new features' }}</span>
              <br/>
              <span class="section-content__text--light">{{ '- Learn and create microservices for delivery service, billing service' }}</span>
              <br/>
              <span class="section-content__text--light">{{ '- Participate in the design and development for the site monbanquet.fr' }}</span>
              <br/>
              <span class="section-content__text--light">{{ '- Monitoring and maintaining of all microservices using AWS Kubernetes' }}</span>
              <br/>
              <br/>
              <span class="section-content__text--light--bold">{{ 'Java, SpringBoot, MongoDB, Kubernetes, React, Angular, Kafka' }}</span>
            </a>
            <br/>
            <!--
            <a
              target="_blank"
              v-for="(experience, index) in person.experience"
              :key="index"
              class="section-content__item"
              :class="{ link: experience.website !== undefined}"
              :href="experience.website">

              <span class="section-content__header">{{ experience.position }}</span>
              <span class="section-content__subheader">
                {{ experience.company }}
                <span class="section-content__plain">{{ experience.location }}</span>
              </span>

              <div class="section-content__text">{{ experience.timeperiod }}</div>
              <span class="section-content__text--light">{{ experience.description }}</span>
            </a>
            -->
          </div>
        </div>

        <div class="section">
          <div class="section-headline">
            <i class="section-headline__icon material-icons">school</i>{{ lang.education }}
          </div>

          <div class="section-content">
            <a
              v-for="(education, index) in person.education"
              class="section-content__item"
              :key="index"
              :class="{ link: education.website !== undefined}"
              :href="education.website">

              <span class="section-content__header"> {{  education.school }} </span>
              <span class="section-content__subheader">{{ education.degree }}</span>
              <span class="section-content__text"> {{ education.timeperiod }} </span>
              <span class="section-content__text--light"> {{ education.description }} </span>
            </a>
          </div>
        </div>
     
      <!--
        <div
          v-if="person.projects"
          class="section">
          <div class="section-content-grid">
            <a v-for="(project, index) in person.projects" :key="index"
              target="_blank"
              class="section-content__item-grid"
              :class="{ link: project.url !== undefined}"
              :href="project.url">
              <span class="section-content__header"> {{ project.name }} - {{ project.platform }} </span>
              <span class="section-content__subheader"></span>
              <span class="section-content__text"> {{ project.description }} </span>
            </a>
          </div>
        </div>
        -->
        <!--
        <div
          v-if="person.projects"
          class="section">
          <div class="section-headline">
            <i class="section-headline__icon material-icons">code</i>{{ lang.projects }}
          </div>

          <div class="section-content-grid">
            <a v-for="(project, index) in person.projects" :key="index"
              target="_blank"
              class="section-content__item-grid"
              :class="{ link: project.url !== undefined}"
              :href="project.url">
              <span class="section-content__header"> {{ project.name }} </span>
              <span class="section-content__subheader">{{ project.platform }}</span>
              <span class="section-content__text"> {{ project.description }} </span>
            </a>
          </div>
        </div>
        -->

        <div class="section">
          <div class="section-headline">
            <i class="section-headline__icon material-icons">local_library</i>{{ 'Lifelong learning' }}
          </div>

          <div class="section-content">
            <a
              target="_blank"
              class="section-content__item"
              :class="{ link: true}"
              :href="'https://leetcode.com/MagicienDeCode/'">

              <span class="section-content__text--light--bold">➡︎ Algorithm Training: LeetCode, 1001 solved</span>
            </a>
          </div>
        </div>
        <!--
        <div class="section">

          <div class="section-content-grid">
            <a
              target="_blank"
              class="section-content__item-grid"
              :class="{ link: true}"
              href="https://github.com/MagicienDeCode/images/blob/master/certificates/eCertificate_xiang_java6.pdf">
              <span class="section-content__header"> {{ 'ORACLE Certified Professional' }} </span>
              <span class="section-content__text"> {{ 'Java SE 6 Programmer, July 25, 2014' }} </span>
            </a>
          </div>
        </div>

        
        <div
          v-if="person.contributions"
          class="section">
          <div class="section-headline">
            <i class="section-headline__icon fa fa-heart"></i>{{lang.contributions}}
          </div>

          <div class="section-content-grid">
            <a
              v-for="(contribution, index) in person.contributions"
              class="section-content__item-grid"
              :key="index"
              :class="{ link: contribution.url !== undefined}"
              :href="contribution.url">
              <span class="section-content__header"> {{ contribution.name }} </span>
              <span class="section-content__text"> {{ contribution.description }} </span>
              <span class="section-content__text--light" style="word-break: break-all;">
                {{ contribution.url }}
              </span>
            </a>
          </div>
        </div>
         -->
      </div>
    </div>
    <img class="qr-code"/>
    <img class="picture"/>
  </div>
</template>

<script>
import Vue from 'vue';
import { getVueOptions } from './options';

const name = 'cool';

export default Vue.component(name, getVueOptions(name));
</script>

<style lang="less" scoped>
@accent-color: #34495E;
@banner-color: #42b883;
@banner-height: 120px;
@picture-size: 120px;
@picture-offset: 35px;
@base-padding: 30px;
@left-column-width: 240px;

.link {
  color: inherit;
  cursor: pointer;
  text-decoration-line: none;

  &:visited {
    color: inherit;
  }
}

.resume {
  position: relative;
  font-family:'Roboto' !important;
  font-size: 0.9em;
}

.company-icon-1{
  height: 20px;
  width: 20px;
  content: url('../../resume/slimpay.jpg');
  margin-right: 10px;
}
.company-icon-2{
  height: 20px;
  width: 20px;
  content: url('../../resume/mb.jpg');
  margin-right: 10px;
}

.picture {
  position: absolute;
  top: @banner-height - @picture-offset;
  left: @left-column-width + @base-padding * 2 - @picture-size / 2;
  height: @picture-size;
  width: @picture-size;
  border-radius: 50%;
  border: 5px solid @accent-color;
  content: url('../../resume/lixiang.jpg');
  z-index: 2;
}

.qr-code{
  position: absolute;
  height: 100px;
  width: 100px;
  top: 40px;
  right: 40px;
  content: url('../../resume/qr2.png');
  border: 5px solid white;
}

.banner {
  width: calc(100% - @base-padding * 2);
  height: @banner-height;
  padding: @base-padding;
  background-color: purple;
  /*
    background-image: url('../../resume/banner.png');
    background-repeat: no-repeat;
    background-size: cover;
  */
  color: white;

  &__fullname {
    font-size: 32px;
  }

  &__position {
    font-size: 16px;
  }

  &__location {
    font-size: 12px;
  }
}

.content {
  display: flex;
  width: 100%;
  height: 100%;

  &__left,
  &__right {
    height: 100%;
    padding: @base-padding;
  }

  &__left {
    width: @left-column-width;
    color: rgba(255, 255, 255, 0.59);
    background-color: @accent-color;

    .section-headline {
      color: white;
    }
  }

  &__right {
    flex: 1;
  }
}

.section {
  margin: 20px 0;
}

.section-link,
.section-headline {
  display: flex !important;
  align-items: center;
  color: @accent-color;
  display: inline-block;
  font-size: 1.2em;
  margin: 8px 0;

  &__icon {
    margin-right: 8px;
    font-size: 1.4em;
  }
}

.section-link {
  font-size: 1.1em;
  color: rgba(255, 255, 255, 0.59) !important;

  &__icon {
    color: white;
  }
}

.section-content {
  margin-top: 5px;
  padding-left: 32px;
  font-size: 14px;

  &__item {
    display: block;
    margin-bottom: 5px;
  }

  &__header {
    display: block;
    font-size: 1.1em;
    font-weight: 500;
  }

  &__subheader {
    display: block;
    font-weight: 400;
  }

  &__plain,
  &__text {
    display: block;
    font-size: 12px;

    &--light {
      font-size: 12px;
    }
    &--bold {
      font-weight: bold;
    }
    &--times{
      font-size: 12px;
      padding-left: 140px;
    }
    &--times2{
      font-size: 12px;
      padding-left: 50px;
    }
  }

  &__plain {
    display: inline;
    font-weight: 300;
  }

  &__item-grid {
    flex: 1 1 0;
    margin-bottom: 5px;
    padding-right: 5px;
  }

  &--plain {
    padding: 0;
  }
}

.section-content-grid {
  display: flex;
  flex-wrap: wrap;
  margin-top: 5px;
  margin-bottom: 5px;
}

.grid-item {
  padding-right: 5px;
}

.squarred-grid-item {
  display: block;
  border: 1px solid white;
  color: white;
  margin-top: 5px;
  padding: 5px;
}
</style>
