<template>
<div v-if="loading" width="100%" height="100%">
  <article>
    <Lottie :options='lottieOptions' :loading="loading"></Lottie>
  </article>
</div>
<article v-else>
  <Navi />
  <Top />
  <div class="under-water">
    <v-container>
      <Profile id="profile" />
    </v-container>
  </div>
  <div class="top_padding">
    <BlogCard />
  </div>

  <div class="top_padding under-water">
    <v-container>
      <SkillsCarousel />
    </v-container>
  </div>
  <div class="top_padding">
    <v-container>
      <Products id="product" />
    </v-container>
  </div>
  <ContactModal />
</article>
</template>

<script>
import Navi from '~/components/nav/navbar.vue'
import Lottie from '~/components/animation/loading-lottie.vue'
import Top from '~/components/profile/profile-top-image.vue'
import Profile from '~/components/profile/profile-contents.vue'
import Products from '~/components/product/product.vue'
import SkillsCarousel from '~/components/skill/skills-carousel.vue'
import BlogCard from '~/components/profile/profile-blog-card.vue'
import ContactModal from '~/components/contact/contact-modal.vue'


export default {
  components: {
    Navi,
    Lottie,
    Top,
    Profile,
    Products,
    SkillsCarousel,
    BlogCard,
    ContactModal
  },
  data() {
    return {
      loading: true,
    }
  },
  asyncData() {
    return {
      lottieOptions: {
        animationData: require(`~/assets/animation/loadingAnimation.json`)
      }
    }
  },
}
</script>

<style media="screen">
.top_padding {
  padding-top: 20px;
}

.under-water {
  background: radial-gradient(1.5em 6.28571em at 1.95em, rgba(255, 255, 255, 0) 50%, rgba(255, 255, 255, 0.25) 50%, rgba(255, 255, 255, 0.25) 55%, rgba(255, 255, 255, 0) 55%) 0 0, radial-gradient(1.5em 6.28571em at -0.45em, rgba(255, 255, 255, 0) 50%, rgba(255, 255, 255, 0.25) 50%, rgba(255, 255, 255, 0.25) 55%, rgba(255, 255, 255, 0) 55%) 1.5em 5.5em, radial-gradient(2.3em 4.57143em at 2.99em, rgba(255, 255, 255, 0) 50%, rgba(255, 255, 255, 0.3) 50%, rgba(255, 255, 255, 0.3) 55%, rgba(255, 255, 255, 0) 55%) 0 0, radial-gradient(2.3em 4.57143em at -0.69em, rgba(255, 255, 255, 0) 50%, rgba(255, 255, 255, 0.3) 50%, rgba(255, 255, 255, 0.3) 55%, rgba(255, 255, 255, 0) 55%) 2.3em 4em, radial-gradient(3.5em 6.28571em at 4.55em, rgba(255, 255, 255, 0) 50%, rgba(255, 255, 255, 0.25) 50%, rgba(255, 255, 255, 0.25) 55%, rgba(255, 255, 255, 0) 55%) 0 0, radial-gradient(3.5em 6.28571em at -1.05em, rgba(255, 255, 255, 0) 50%, rgba(255, 255, 255, 0.25) 50%, rgba(255, 255, 255, 0.25) 55%, rgba(255, 255, 255, 0) 55%) 3.5em 5.5em, radial-gradient(#15ffa5, #00ced1);
  background-color: mediumspringgreen;
  background-size: 1.5em 11em, 1.5em 11em, 2.3em 8em, 2.3em 8em, 3.5em 11em, 3.5em 11em, 100% 100%;
  background-repeat: repeat;
}
</style>
