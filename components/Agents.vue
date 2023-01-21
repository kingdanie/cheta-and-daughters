<template>
    <div class="w-full">
        <div class="bg-cyan-500 p-2 flex items-center justify-between">
            <h4 class="text-white font-semibold">Agents</h4>
            
              <div v-if="showSearch" class="w-full px-2 lg:px-5">
              <label for="search" class="sr-only">Search agents</label>
              <div class="relative text-white focus-within:text-white">
                      <input id="search-agent" name="search-agent" 
                                class="
                                        block w-full rounded-md border border-transparent 
                                        bg-white bg-opacity-25 px-3 leading-5 
                                        text-white placeholder-gray-400 focus:bg-gray-200 
                                        focus:text-gray-900 focus:placeholder-gray-600 
                                        focus:outline-none focus:ring-0 sm:text-sm
                                " 
                                placeholder="Search agents" 
                                type="search" 
                                autocomplete="off"
                        />
              </div>
            </div>
            
            <button @click="toggleSearch()"> <MagnifyingGlassIcon class="h-5 w-5 text-white hover:text-cyan-200" /></button>
        </div>

        <div class="bg-white">

          <div class="sm:hidden">
            <label for="tabs" class="sr-only">Select a tab</label>
            <!-- Use an "onChange" listener to redirect the user to the selected tab URL. -->
            <select id="tabs" name="tabs" class="block w-full border-gray-300 py-2 pl-3 pr-10 text-base focus:border-cyan-500 focus:outline-none focus:ring-cyan-500 sm:text-sm">
              <option v-for="tab in tabs" :key="tab.name" :selected="tab.current">{{ tab.name }}</option>
            </select>
          </div>

          <div class="hidden sm:block">
            <div class="border-b border-gray-200">
              <nav class="flex flex justify-between" aria-label="Tabs">
                <a v-for="tab in tabs" :key="tab.name" :href="tab.href" :class="[tab.current ? 'border-cyan-500 text-cyan-600' : 'border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-200', 'pr-5 whitespace-nowrap py-4 px-1 border-b-2 font-medium text-sm']">
                  <span v-if="tab.name !== 'All'" :class="[tab.bgColor, 'w-5 h-5 rounded-full']" aria-hidden="true"> _ </span>
                  {{ tab.name }}
                </a>
              </nav>
            </div>
          </div>
          


            <div class="p-4">
                        <!-- Stacked list -->
        <ul role="list" class="mt-5 divide-y divide-gray-200 border-t border-gray-200 sm:mt-0 sm:border-t-0">
          <!-- <li v-for="candidate in agents" :key="candidate.email"> -->
        <li v-for="candidate in 24" :key="candidate">

            <a href="#" class="group block">
              <div class="flex items-center py-5 px-4 sm:py-6 sm:px-0">
                <div class="flex min-w-0 flex-1 items-center">
                  <div class="flex-shrink-0 md:place-self-start">
                    <img class="h-12 w-12 rounded-full group-hover:opacity-75" :src="agents.imageUrl" alt="" />
                  </div>
                  <div class="min-w-0 flex-1 px-4">
                    <div>
                      <p class="truncate text-sm font-medium">{{ agents.name }}</p>
                      <p class="mt-2 flex items-center text-sm text-gray-500">
                        <span class="truncate">{{ agents.phone }}</span>
                      </p>
                      <p class="text-gray-500 text-sm">
                        {{agents.location}}
                      </p>
                    </div>
                  </div>
                </div>
                <div>
                  <ChevronRightIcon class="h-5 w-5 text-gray-400 group-hover:text-gray-700" aria-hidden="true" />
                </div>
              </div>
            </a>
          </li>
        </ul>
            </div>

        </div>

    </div>
</template>

<script>
import { BuildingOffice2Icon, ChevronRightIcon } from '@heroicons/vue/24/outline'
import { MagnifyingGlassIcon } from "@heroicons/vue/24/solid";
const Tasks = [
  { name: 'All', href: '#', current: true,  bgColor: '' },
  { name: 'Online', href: '#', current: false,  bgColor: 'bg-green-600' },
  { name: 'Offline', href: '#', current: false, bgColor: 'bg-red-600' },
]

const agents =
  {
    name: 'Adebayo Adeboye Emmanuel',
    phone: '08069786754',
    location: "Akure",
    imageUrl:
      'https://images.unsplash.com/photo-1502685104226-ee32379fefbe?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',

  }


export default {
        name: "Agents",
        components: { MagnifyingGlassIcon, BuildingOffice2Icon, ChevronRightIcon },
data() {
    return {
        tabs: Tasks,
        agents: agents,
        showSearch: false,
    }
},
methods: {
    toggleSearch() {
      this.showSearch = !this.showSearch;
    },
  },
}
</script>