<script setup lang="ts">
// import TheWelcome from '../components/TheWelcome.vue'
import { Button } from "@/components/ui/button"
import TheHeader from "@/components/Layout/TheHeader.vue"
import { Icon } from '@iconify/vue';
import { Card, CardContent, CardFooter, CardHeader, CardTitle } from '@/components/ui/card'
import QuoteForm from '@/components/QuoteForm.vue'

type Services = {
  id: number;
  title: string;
  description: string;
  icon: string;
  color: string;
}

type Customer = {
  id: number;
  name: string;
  body: string;
  icon: string;
  color: string;
}

const services:Services [] = [
  {
    id:1,
    title: 'Analyse your product',
    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magnam. ',
    icon: 'el:headphones',
    color: 'bg-blue-100 p-2 rounded text-blue-600'
  },
  {
    id:2,
    title: 'Analyse your product',
    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magnam. ',
    icon:"material-symbols-light:content-paste-rounded",
    color:'bg-green-100 p-2 rounded text-green-600'
  },
  {
    id:3,
    title: 'Analyse your product',
    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magnam. ',
    icon:'et:chat',
    color:'bg-red-100 p-2 rounded text-red-600'
  }
]


const customers:Customer [] = [
  {
    id:1,
    name: 'Peter Nkole',
    body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magnam. ',
    icon: 'el:headphones',
    color: 'bg-blue-100 p-2 rounded text-blue-600'
  },
  {
    id:2,
    name: 'Mulenga Musamba',
    body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magnam. ',
    icon:"material-symbols-light:content-paste-rounded",
    color:'bg-green-100 p-2 rounded text-green-600'
  },
  {
    id:3,
    name: 'Clinton Daka',
    body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magnam. ',
    icon:'et:chat',
    color:'bg-red-100 p-2 rounded text-red-600'
  },
  {
    id:4,
    name: 'Isaac Tembo',
    body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magnam. ',
    icon:'et:chat',
    color:'bg-yellow-100 p-2 rounded text-yellow-600'
  },
  {
    id:5,
    name: 'Precious Nyirenda',
    body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magnam. ',
    icon:'et:chat',
    color:'bg-teal-100 p-2 rounded text-teal-600'
  },
  {
    id:6,
    name: 'Bupe Nyense',
    body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magnam. ',
    icon:'et:chat',
    color:'bg-pink-100 p-2 rounded text-pink-600'
  }
]

</script>

<template>
  <TheHeader />

  <main class="my-16 flex flex-col gap-y-10 items-center ">
    <!-- <TheWelcome /> -->
    <div class="flex justify-between ">
      <div class="flex items-center flex-col justify-end w-[100%]">
        <div class="mx-auto w-96 flex flex-col gap-5 ">
          <h3 class="font-bold text-2xl text-gray-800 max-w-max">
            Find influencers for your products
          </h3>
          <p class="text-sm text-gray-500">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magnam.
          </p>
          <Button class="bg-blue-600 rounded-2xl font-semibold flex-initial w-40 " size="default">
            Offered Services
          </Button>
        </div>



      </div>
      <div class="w-[50%]">
          <img
            src="/images/header-image.png"
            alt="Header Image"
            class="w-auto  mt-10 mx-auto"
          />
      </div>
    </div>

    <div class="flex items-center flex-col justify-end w-[100%] gap-y-4">
      <h3 class="font-bold text-2xl text-gray-800 max-w-max">
        Explore our services
      </h3>

      <div id="services" class="grid grid-cols-3 gap-6 ">
        <Card class="w-[350px]" v-for="service in services" :key="service.id">
          <CardHeader>
            <Icon
                  :icon="service.icon" :ssr="true" class="text-4xl mb-2 "
                  :class="service.color" />

            <CardTitle>
              {{ service.title }}
            </CardTitle>

          </CardHeader>
          <CardContent class="text-sm text-gray-600">
            {{ service.description}}
          </CardContent>
          <CardFooter class="flex-col">
            <Button variant="outline">
              Learn more
              <Icon icon="mdi:arrow-right" :ssr="true" />
            </Button>
          </CardFooter>

        </Card>
      </div>
    </div>

    <div class="flex ">
      <div class="w-[50%]">
        <img
          src="/images/details-1.png"
          alt="Header Image"
          class="w-auto   mx-auto"
        />
      </div>
      <div class="mx-auto w-[50%] flex flex-col gap-5 items-center ">
        <h5 class="text-red-500 font-semibold">WHAT WE DO</h5>
        <h3 class="font-bold text-3xl text-gray-800 w-96">
          The right influencer can boost your conversion
        </h3>
        <p class="text-sm text-gray-500 w-96">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magnam.
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim aeque doleamus.
        </p>
        <Button class="bg-blue-600 rounded-2xl font-semibold w-40 " size="default">
          Get Quote
        </Button>
      </div>
    </div>

    <div id="features" class="bg-[url('/images/features-background.jpg')] bg-cover h-svh w-full flex flex-col gap-y-10 items-center text-white text-sm">
      <h3 class="font-bold text-3xl mt-10">
        Online Service features
      </h3>
      <p class="w-[700px]">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim aeque doleamus.
      </p>
      <div class="flex flex-row-reverse ">
        <div class="w-[50%]">
          <img
            src="/images/features-dashboard.png"
            alt="Header Image"
            class="w-auto   mx-auto"
          />
        </div>
        <div  class="mx-auto w-[50%] flex flex-col gap-5 items-center ">
          <div v-for="service in services" :key="service.id">

            <h3 class="font-black">
              <Icon
                :icon="service.icon" :ssr="true" class="text-4xl mb-2 inline"
                :class="service.color" />
              {{ service.title }}
            </h3>
            <p class="text-sm  w-96 ">
              {{service.description}}
            </p>
          </div>

        </div>
      </div>


    </div>

    <div id="testimonials" class="grid grid-cols-3 gap-6 ">
      <h1 class="col-span-3 text-center font-bold text-3xl text-gray-800">
        Customer's Testimonials
      </h1>
      <Card class="w-[350px]" v-for="customer in customers" :key="customer.id">
        <CardHeader class="">
          <Icon
            icon="fontisto:quote-a-left" :ssr="true" class="text-4xl mb-2 mx-auto"
            :class="customer.color" />



        </CardHeader>
        <CardContent class="text-sm text-gray-600">
          {{ customer.body}}
        </CardContent>
        <CardTitle class="text-center">
          {{ customer.name }}
        </CardTitle>
        <CardFooter class="flex-col">

          <Button variant="outline">
            Learn more
            <Icon icon="mdi:arrow-right" :ssr="true" />
          </Button>
        </CardFooter>

      </Card>
    </div>
    <div>
      <h3 class=" font-semibold">Trusted over by <span class="text-blue-600">5000</span> people worldwide</h3>
      <div class="flex  gap-5 items-center ">

      </div>
    </div>

    <div class="flex justify-between w-full ">
      <div class="mx-auto w-[50%] flex flex-col gap-5 items-center ">
        <h5 class="text-red-500 font-semibold">GET A QUOTE</h5>
        <h3 class="font-bold text-3xl text-gray-800 w-96">
          Submit for a quote
        </h3>
        <p class="text-sm text-gray-500 w-96">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magnam.
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim aeque doleamus.
        </p>
      </div>
      <div class="w-[50%]">
        <QuoteForm />
      </div>
    </div>




  </main>
</template>
