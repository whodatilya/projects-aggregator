<template>
  <div class="main">
    <div class="header flex">
      <div
        class="header__wrapper wrap row justify-end items-center"
        v-for="component in components"
        :key="component.id"
      >
        <div class="header__item" @click="switchComponent(component.component)">
          {{ component.title }}
        </div>
      </div>
    </div>
    <div class="content">
      <div class="content__wrapper">
        <component
          class="content__item"
          :is="currentComponent + 'Component'">
        </component>
      </div>
    </div>
    <div class="footer flex">
      <div class="footer__wrapper row full-width justify-end items-center justify-end">
        <div class="footer__info">
          Ilya Gordeev,
          <span> 2023</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import AboutComponent from 'components/AboutComponent.vue';
import ContactsComponent from 'components/ContactsComponent.vue';
import ProjectsComponent from 'components/ProjectsComponent.vue';
export default defineComponent({
  name: 'IndexPage',
  components: {
    AboutComponent,
    ContactsComponent,
    ProjectsComponent
  },
  data () {
    return {
      currentComponent: 'Projects',
      components: [
        {
          id: 0,
          title: 'Projects',
          component: 'Projects'
        },
        {
          id: 1,
          title: 'About Me',
          component: 'About'
        },
        {
          id: 2,
          title: 'Contacts',
          component: 'Contacts'
        }
      ]
    }
  },
  methods: {
    switchComponent (component) {
      this.currentComponent = component
    }
  }
})
</script>
<style scoped lang="sass">
.header
  height: 9vh
  background: #9C27B0
  &__item
    padding: 0 24px
    font-family: "Gotham Pro", serif
    font-weight: 500
    &:hover
      cursor: pointer
.content
  height: 82vh
  background: #21BA45
.footer
  height: 9vh
  background: red
  &__info
    padding: 0 24px
</style>
