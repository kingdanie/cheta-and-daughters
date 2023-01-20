<template>
    <div class="w-full">
        <div class="bg-cyan-500 p-2 flex justify-between">
            <h4 class="text-white font-semibold">Agents</h4>
            <button> <MagnifyingGlassIcon class="h-5 w-5 text-white" /></button>
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
              <nav class="flex space-x-3" aria-label="Tabs">
                <a v-for="tab in tabs" :key="tab.name" :href="tab.href" :class="[tab.current ? 'border-cyan-500 text-cyan-600' : 'border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-200', 'pl-5 whitespace-nowrap py-4 px-1 border-b-2 font-medium text-sm']">
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
                  <div class="flex-shrink-0">
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
  { name: 'All', href: '#', current: true },
  { name: 'Online', href: '#', current: false },
  { name: 'Offline', href: '#', current: false },
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
    }
}
}
</script>