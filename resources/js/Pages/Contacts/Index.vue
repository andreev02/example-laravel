<script setup>
import { Head, Link } from '@inertiajs/vue3'
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import PaginationLayout from '@/Layouts/PaginationLayout.vue';
import SearchFilterLayout from '@/Layouts/SearchFilterLayout.vue';

defineProps({
  filters: {
    type: Object,
  },
  contacts: {
    type: Object,
  },
})

</script>

<template>
  <div>

    <Head title="Contacts" />

    <AuthenticatedLayout>
      <template #header>
        <h2 class="font-semibold text-xl text-gray-800 dark:text-gray-200 leading-tight">Contacts</h2>
      </template>

      <div class="py-12 max-w-7xl mx-auto sm:px-6 lg:px-8">

        <SearchFilterLayout :filters="filters"/>

        <div class="bg-white rounded-md shadow overflow-x-auto">
          <div class="relative overflow-x-auto shadow-md sm:rounded-lg">
            <table class="w-full text-sm text-left rtl:text-right text-gray-500 dark:text-gray-400">
              <caption
                class="p-5 text-lg font-semibold text-left rtl:text-right text-gray-900 bg-white dark:text-white dark:bg-gray-800">
                Our contacts
                <p class="mt-1 text-sm font-normal text-gray-500 dark:text-gray-400">Browse a list of Flowbite products
                  designed to help you work and play, stay organized, get answers, keep in touch, grow your business, and
                  more.</p>
              </caption>
              <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
                <tr>
                  <th scope="col" class="px-6 py-3">
                    Name
                  </th>
                  <th scope="col" class="px-6 py-3">
                    Phone
                  </th>
                  <th scope="col" class="px-6 py-3">
                    City
                  </th>
                  <th scope="col" class="px-6 py-3">
                    Organization
                  </th>
                  <th scope="col" class="px-6 py-3">
                    <span class="sr-only">Edit</span>
                  </th>
                </tr>
              </thead>
              <tbody>
                <tr v-if="contacts" v-for="contact in contacts.data" :key="contact.id"
                  class="bg-white border-b dark:bg-gray-800 dark:border-gray-700">
                  <th scope="row" class="px-6 py-4 font-medium text-gray-900 whitespace-nowrap dark:text-white">
                    {{ contact.name }}
                  </th>
                  <td class="px-6 py-4">
                    {{ contact.phone }}
                  </td>
                  <td class="px-6 py-4">
                    {{ contact.city }}
                  </td>
                  <td class="px-6 py-4">
                    {{ contact.organization?.name }}
                  </td>
                  <td class="px-6 py-4 text-right">
                    <a :href="`/contacts/${contact.id}/edit`"
                      class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Edit</a>
                  </td>
                </tr>
                <tr v-if="!contacts" class="bg-white border-b dark:bg-gray-800 dark:border-gray-700">
                  <td class="px-6 py-4 font-medium text-gray-900 whitespace-nowrap dark:text-white" colspan="5">No
                    contacts found.</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>

        <div class="pt-12">
          <Link
            class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 me-2 mt-10 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800"
            href="/contacts/create">
          <span>Create</span>
          <span class="hidden md:inline">&nbsp;Contact</span>
          </Link>
        </div>
      
      </div>

      <div class="pb-16 flex justify-center">
        <PaginationLayout v-if="contacts" :links="contacts.links" />
      </div>

    </AuthenticatedLayout>
  </div>
</template>
