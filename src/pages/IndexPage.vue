<template>
  <q-page class="row items-center justify-evenly">
    <div class="home-banner window-width window-height" style="overflow: hidden;">
      <q-img :src="imgBanner" class="window-height" fit="cover">
        <div class="overlay"></div>
        <h1 class="absolute-center q-mt-none window-width text-h3 text-bold text-blue-2 text-center q-px-xl" style="max-width: 700px;">
          Professional PC Repair and Shop Services for All Your Computing Needs
        </h1>
      </q-img>
    </div>
    <div class="custom-card window-width" :class="$q.screen.gt.sm ? 'custom-grid' : ''" v-for="item in cardList"
      :key="item.title">
      <q-img :src="item.imageURL">
        <div class="absolute-bottom text-subtitle1 text-center">
          {{ item.title }}
        </div>
      </q-img>
      <p class="custom-text q-pa-md text-center text-bold">{{ item.text }}</p>
    </div>
  </q-page>
</template>

<script setup lang="ts">
import { useQuasar } from 'quasar'
import imgRepair from '../images/service.jpg'
import imgServer from '../images/server.jpg'
import imgSupport from '../images/support.jpg'
import imgShop from '../images/shop.jpg'
import imgCustom from '../images/customPC.jpg'
import imgBanner from '../images/banner.jpg'

const $q = useQuasar()

const cardList = [
  {
    imageURL: imgRepair,
    text: 'At our computer service center, we specialize in providing reliable and efficient PC and laptop repair services. Our team of experienced technicians is equipped to handle a wide range of issues, from hardware failures to software glitches. Whether your device is slow, not turning on, or experiencing other technical difficulties, we have the expertise to diagnose and fix the problem promptly. We use advanced diagnostic tools and high-quality replacement parts to ensure that your PC or laptop is restored to optimal performance.',
    title: 'Fast and Reliable Repairs'
  },
  {
    imageURL: imgServer,
    text: 'When it comes to server work and creating networks, our skilled professionals are here to help. We understand the importance of a robust and secure network infrastructure for businesses of all sizes. Our team has extensive experience in designing and implementing efficient server solutions tailored to your specific needs. From setting up local area networks (LANs) to configuring file servers and managing network security, we ensure smooth operations and seamless connectivity for your organization.',
    title: 'Flawless Server Setup'
  },
  {
    imageURL: imgCustom,
    text: "Looking for a custom PC setup that perfectly suits your needs? Look no further! Our experts excel in creating customized PC solutions that deliver the ultimate computing experience. We work closely with you to understand your requirements, preferences, and budget constraints. From selecting the right components and peripherals to assembling and configuring the system, we ensure every detail is taken care of. Whether you're a gamer, a designer, or a professional requiring specialized hardware, our custom PC setups will exceed your expectations.",
    title: 'Let Your Imagination Go Wild'
  },
  {
    imageURL: imgShop,
    text: 'Discover a world of cutting-edge technology at our shop, where we offer a wide range of the latest tech pieces. From high-performance laptops and powerful desktops to innovative accessories and peripherals, we have everything you need to stay ahead in the digital realm. Our shop is stocked with top brands known for their reliability and performance. Our knowledgeable staff is always ready to assist you in finding the perfect tech pieces that align with your requirements and help you unleash your full potential.',
    title: 'Wide Offer of The Best Tech Pieces'
  },
  {
    imageURL: imgSupport,
    text: 'At our computer service center, we go beyond repairs and sales. We provide comprehensive tech support services to ensure that you receive the assistance you need, even after your purchase. Our dedicated support team is available to address any software-related issues, troubleshoot network problems, and guide you through technical challenges. We understand the frustration that arises from technology hiccups, and we are committed to providing prompt and reliable solutions to keep you up and running smoothly.',
    title: 'Reliable Tech Support'
  },

]

</script>

<style lang="scss">
.custom-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
}

.custom-grid:nth-child(odd) {


  .q-img {
    grid-column: 2;
  }

  p {
    grid-column: 1;
    grid-row: 1;
  }
}

.custom-text {
  font-size: clamp(0.9rem, calc(0.3rem + 1vw), 1.5rem);
}

.overlay {
  position: absolute;
  top:0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>
