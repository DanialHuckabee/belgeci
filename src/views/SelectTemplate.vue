<script setup lang="ts">
import NavBar from '../components/NavBar.vue'
import router from '@/router'
import { EyeIcon, DocumentIcon } from '@heroicons/vue/20/solid'

const people = [
  {
    name: 'Okul Başvurusu',
    title: 'Okul Başvurusu için gerekli belgeler ve süreç hakkında detaylı bilgi',
    role: 'Admin',
    email: 'janecooper@example.com',
    telephone: '+1-202-555-0170',
    imageUrl: 'https://meetingtomorrow.com/wp-content/uploads/2019/08/TextDocument.png'
  },
  {
    name: 'Kuaför Ruhsatı',
    title: 'Kuaför Ruhsatı almak için gerekli belgeler ve başvuru adımları',
    role: 'User',
    email: 'johndoe@example.com',
    telephone: '+1-202-555-0110',
    imageUrl:
      'https://image.isu.pub/210917100548-70213f5503fc26a039628881a95ace2b/jpg/page_1_thumb_large.jpg'
  },
  {
    name: 'Ödeme Talebi',
    title: 'Ödeme Talebi süreci ve gerekli belgeler hakkında bilgi',
    role: 'Admin',
    email: 'alicejohnson@example.com',
    telephone: '+1-202-555-0123',
    imageUrl:
      'https://imgv2-2-f.scribdassets.com/img/document/502812084/original/4987dc4a83/1718141271?v=1'
  },
  {
    name: 'Abonelik Kapatma',
    title: 'Abonelik Kapatma işlemleri ve dikkat edilmesi gerekenler',
    role: 'User',
    email: 'michaelbrown@example.com',
    telephone: '+1-202-555-0144',
    imageUrl:
      'https://d20ohkaloyme4g.cloudfront.net/img/document_thumbnails/cfbc62a916b02ccfc8cff52e94775109/thumb_300_424.png'
  },
  {
    name: 'Bilgi Talebi',
    title: 'Bilgi Talebi başvuru süreci ve gerekli belgeler',
    role: 'Admin',
    email: 'emilydavis@example.com',
    telephone: '+1-202-555-0155',
    imageUrl:
      'https://image.isu.pub/210917100548-70213f5503fc26a039628881a95ace2b/jpg/page_1_thumb_large.jpg'
  },
  {
    name: 'Destek Başvurusu',
    title: 'Destek Başvurusu için izlenmesi gereken adımlar ve gerekli belgeler',
    role: 'User',
    email: 'davidwilson@example.com',
    telephone: '+1-202-555-0166',
    imageUrl:
      'https://image.isu.pub/210917100548-70213f5503fc26a039628881a95ace2b/jpg/page_1_thumb_large.jpg'
  }
]
</script>

<template>
  <NavBar></NavBar>

  <div class="mx-auto max-w-7xl">
    <div class="md:flex md:items-center md:justify-between py-10">
      <div class="min-w-0 flex-1">
        <h2
          class="text-2xl font-bold leading-7 text-gray-900 sm:truncate sm:text-3xl sm:tracking-tight"
        >
          Sablon seçimi
        </h2>
      </div>
      <div class="mt-4 flex md:ml-4 md:mt-0">
        <button
          type="button"
          class="inline-flex items-center rounded-md bg-white px-3 py-2 text-sm font-semibold text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 hover:bg-gray-50"
        >
          Edit
        </button>
        <button
          type="button"
          class="ml-3 inline-flex items-center rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-700 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
        >
          Publish
        </button>
      </div>
    </div>
    <ul role="list" class="grid grid-cols-1 gap-6 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5">
      <li
        v-for="person in people"
        :key="person.email"
        class="col-span-1 flex flex-col divide-y divide-gray-200 rounded-lg bg-white border text-center shadow-md"
      >
        <div class="flex flex-1 flex-col p-8">
          <img
            class="mx-auto h-32 flex-shrink-0 object-contain shadow-lg border"
            :src="person.imageUrl"
            alt=""
          />
          <h3 class="mt-6 text-sm font-medium text-gray-900">{{ person.name }}</h3>
          <dl class="mt-1 flex flex-grow flex-col justify-between">
            <dt class="sr-only">Title</dt>
            <dd class="text-sm text-gray-500">{{ person.title }}</dd>
            <dt class="sr-only">Role</dt>
            <!-- <dd class="mt-3">
              <span
                class="inline-flex items-center rounded-full bg-green-50 px-2 py-1 text-xs font-medium text-green-700 ring-1 ring-inset ring-green-600/20"
                >{{ person.role }}</span
              >
            </dd> -->
          </dl>
        </div>
        <div>
          <div class="-mt-px flex divide-x divide-gray-200">
            <div class="flex w-0 flex-1">
              <a
                :href="`mailto:${person.email}`"
                class="relative -mr-px inline-flex w-0 flex-1 items-center justify-center gap-x-3 rounded-bl-lg border border-transparent py-4 text-sm font-semibold text-gray-900"
              >
                <EyeIcon class="h-5 w-5 text-gray-400" aria-hidden="true" />

                Önizleme
              </a>
            </div>
            <div class="-ml-px flex w-0 flex-1">
              <button
                @click="router.push('about')"
                class="relative inline-flex w-0 flex-1 items-center justify-center gap-x-3 rounded-br-lg border border-transparent py-4 text-sm font-semibold text-gray-900"
              >
                <DocumentIcon class="h-5 w-5 text-gray-400" aria-hidden="true" />
                Aç
              </button>
            </div>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>
