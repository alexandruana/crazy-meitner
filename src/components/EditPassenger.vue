<script setup>
import { reactive } from "vue";
import TravelDocuments from "./TravelDocuments.vue";

const passenger = reactive({
  first_name: "",
  middle_name: "",
  last_name: "",
  date_of_birth: "",
  nationality: "",
  gender: "",
});
</script>
<template>
  <div class="overflow-hidden rounded-lg bg-white shadow">
    <div class="px-4 py-5 sm:px-6 text-left">
      <h2>Passenger name</h2>
      <!-- We use less vertical padding on card headers on desktop than on body sections -->
    </div>
    <div class="px-4 py-5 sm:p-6">
      <form @submit.prevent="submit">
        <div class="space-y-12">
          <div class="border-b border-gray-900/10 pb-12">
            <h2 class="text-base font-semibold leading-7 text-gray-900">
              Personal Information
            </h2>
            <p class="mt-1 text-sm leading-6 text-gray-600">
              Use a permanent address where you can receive mail.
            </p>

            <div class="mt-10 grid grid-cols-1 gap-x-6 gap-y-8 sm:grid-cols-6">
              <div class="sm:col-span-2">
                <label
                  for="first-name"
                  class="block text-sm font-medium leading-6 text-gray-900"
                  >First name</label
                >
                <div class="mt-2">
                  <input
                    type="text"
                    name="first-name"
                    id="first-name"
                    autocomplete="given-name"
                    class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                    v-model="passenger.first_name"
                  />
                </div>
              </div>
              <div class="sm:col-span-2">
                <label
                  for="middle-name"
                  class="block text-sm font-medium leading-6 text-gray-900"
                  >Middle name</label
                >
                <div class="mt-2">
                  <input
                    type="text"
                    name="middle-name"
                    id="middle-name"
                    autocomplete="middle-name"
                    class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                    v-model="passenger.middle_name"
                  />
                </div>
              </div>
              <div class="sm:col-span-2">
                <label
                  for="last-name"
                  class="block text-sm font-medium leading-6 text-gray-900"
                  >Last name</label
                >
                <div class="mt-2">
                  <input
                    type="text"
                    name="last-name"
                    id="last-name"
                    autocomplete="family-name"
                    class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                    v-model="passenger.last_name"
                  />
                </div>
              </div>
              <div class="sm:col-span-2">
                <label
                  for="date_of_birth"
                  class="block text-sm font-medium leading-6 text-gray-900"
                  >Date of birth</label
                >
                <div class="mt-2">
                  <input
                    id="date_of_birth"
                    name="date_of_birth"
                    type="date"
                    autocomplete="bday"
                    class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                    v-model="passenger.date_of_birth"
                  />
                </div>
              </div>
              <div class="sm:col-span-2">
                <label
                  for="country"
                  class="block text-sm font-medium leading-6 text-gray-900"
                  >Nationality</label
                >
                <div class="mt-2">
                  <input
                    type="text"
                    name="country"
                    id="country"
                    autocomplete="country-name"
                    class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                    v-model="passenger.nationality"
                  />
                </div>
              </div>
              <div class="sm:col-span-2">
                <label class="block text-sm font-medium leading-6 text-gray-900"
                  >Gender</label
                >
                <fieldset class="mt-4">
                  <legend class="sr-only">Passenger gender</legend>
                  <div
                    class="space-y-4 sm:flex sm:items-center sm:space-x-10 sm:space-y-0"
                  >
                    <div class="flex items-center">
                      <input
                        id="male"
                        name="gender"
                        type="radio"
                        checked
                        class="h-4 w-4 border-gray-300 text-indigo-600 focus:ring-indigo-600"
                        value="male"
                        v-model="passenger.gender"
                      />
                      <label
                        for="male"
                        class="ml-3 block text-sm font-medium leading-6 text-gray-900"
                        >Male</label
                      >
                    </div>
                    <div class="flex items-center">
                      <input
                        id="female"
                        name="gender"
                        type="radio"
                        class="h-4 w-4 border-gray-300 text-indigo-600 focus:ring-indigo-600"
                        value="female"
                        v-model="passenger.gender"
                      />
                      <label
                        for="female"
                        class="ml-3 block text-sm font-medium leading-6 text-gray-900"
                        >Female</label
                      >
                    </div>
                  </div>
                </fieldset>
              </div>
            </div>
          </div>
        </div>
      </form>
    </div>
    <div class="px-4 py-4 sm:px-6">
      <TravelDocuments />
    </div>
  </div>
</template>
