<template>
  <div class="container max-w-3xl mx-auto">
    <div class="w-full py-5 pl-5 mx-auto mb-16 text-center bg-gray-700 rounded-lg shadow-inner">
      <p class="mt-5 text-2xl font-medium text-white">
        Here are some example projects I've had the chance to work on.
      </p>
      
      <transition
        appear
        appear-active-class="ease-in-out transform"
        appear-class="scale-x-0"
        appear-to-class="scale-x-100"
      >
        <div class="inline-block w-32 border-b-2 border-gray-400 shadow-md" :style="{ transitionDuration: (initialDelay*0.618)+'ms' }"></div>
      </transition>
    </div>

    <transition-group
      class="max-w-2xl mx-auto space-y-10"
      tag="div"
      enter-active-class="transition duration-1000 transform"
      enter-class="-translate-x-6 opacity-0"
      enter-to-class="translate-x-0 opacity-100"
    >
      <div
        v-for="item in items"
        :key="item.title"
        class="flex p-5 space-x-6 border border-gray-200 rounded-md shadow-md"
      >
        <!-- Project image -->
        <img class="w-24 h-24 my-auto rounded-sm" :src="item.image" />

        <div>
          <div class="flex flex-wrap items-center space-x-5">
            <!-- Project title -->
            <span class="text-3xl font-medium">{{ item.title }}</span>

            <!-- Project type pill -->
            <span class="px-2 py-1 text-sm text-white bg-gray-600 rounded-full">{{ item.type }}</span>

            <!-- Social icons -->
            <div class="flex space-x-3">
              <!-- GitHub -->
              <a class="text-gray-700 transition duration-200 hover:text-gray-800" v-if="item.github" :href="item.github" target="_blank">
                <svg class="fill-current" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                  <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                </svg>
              </a>

              <!-- Twitter -->
              <a class="text-gray-700 transition duration-200 hover:text-gray-800" v-if="item.twitter" :href="item.twitter" target="_blank">
                <svg class="fill-current" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                  <path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/>
                </svg>
              </a>

              <!-- Website -->
              <a class="text-gray-700 transition duration-200 hover:text-gray-800" v-if="item.website" :href="item.website" target="_blank">
                <svg class="fill-current" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                  <path d="M6.188 8.719c.439-.439.926-.801 1.444-1.087 2.887-1.591 6.589-.745 8.445 2.069l-2.246 2.245c-.644-1.469-2.243-2.305-3.834-1.949-.599.134-1.168.433-1.633.898l-4.304 4.306c-1.307 1.307-1.307 3.433 0 4.74 1.307 1.307 3.433 1.307 4.74 0l1.327-1.327c1.207.479 2.501.67 3.779.575l-2.929 2.929c-2.511 2.511-6.582 2.511-9.093 0s-2.511-6.582 0-9.093l4.304-4.306zm6.836-6.836l-2.929 2.929c1.277-.096 2.572.096 3.779.574l1.326-1.326c1.307-1.307 3.433-1.307 4.74 0 1.307 1.307 1.307 3.433 0 4.74l-4.305 4.305c-1.311 1.311-3.44 1.3-4.74 0-.303-.303-.564-.68-.727-1.051l-2.246 2.245c.236.358.481.667.796.982.812.812 1.846 1.417 3.036 1.704 1.542.371 3.194.166 4.613-.617.518-.286 1.005-.648 1.444-1.087l4.304-4.305c2.512-2.511 2.512-6.582.001-9.093-2.511-2.51-6.581-2.51-9.092 0z"/>
                </svg>
              </a>
            </div>
          </div>

          <p class="text-lg" v-html="item.description"></p>
        </div>
      </div>
    </transition-group>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

type PortfolioItemType = 'website' | 'web application'

interface PortfolioItem {
  title: string
  type: string
  image: string
  description: string
  github?: string
  website?: string
}

const items: PortfolioItem[] = [
  {
    title: 'Screening',
    type: 'web application',
    image: '/provq-logo-q.svg',
    description: `
      Enables ProVQ to accept apprenticeship applications and screen applicants automatically.
      Tests are fully customisable, providing a CMS-like system.
    `,
    website: 'https://screening.provq.com',
  },
  {
    title: 'CryptoBase',
    type: 'website',
    image: '/cryptobase.png',
    description: `
      Informative website for the upcoming platform.
      CryptoBase aims to be the central hub for all things cryptocurrency related.
      Learn, trade, automate, share, earn and gain insights from one place.
    `,
    github: 'https://github.com/james2mid/cryptobase-www',
    website: 'https://cryptobase.cc',
  },
  {
    title: 'JM',
    type: 'website',
    image: '/logo.svg',
    description: `
      Professional website showcasing past projects and the services I offer.
    `,
    github: 'https://github.com/james2mid/jamesmiddleton-www',
    // website: 'https://jamesmiddleton.me',
  },
  {
    title: 'Eden Labs',
    type: 'website',
    image: '#',
    description: `
      Organisation aiming to better the world through technology.
    `,
    github: 'https://github.com/edenlabs/edenlabs-www',
    website: 'https://edenlabs.dev',
  },
]

@Component({

})
export default class Portfolio extends Vue {
  initialDelay = 2000
  interval = this.initialDelay / (1.618 ^ 2)

  created () {
    const staggerNext = () => {
      const currentIndex = this.items.length
      const currentItem = items[currentIndex]

      this.items.push(currentItem)

      if (this.items.length < items.length) {
        setTimeout(staggerNext, this.interval)
      }
    }

    setTimeout(staggerNext, this.initialDelay)
  }

  items: PortfolioItem[] = []
}
</script>
