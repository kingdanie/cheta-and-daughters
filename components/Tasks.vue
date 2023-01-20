<template>
    <div class="w-full">
        <div class="bg-cyan-500 p-2">
            <h4 class="text-white font-semibold">Task</h4>
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
                  <span v-if="tab.count" :class="[tab.current ? 'text-cyan-600' : 'text-gray-900', 'hidden ml-2 font-medium md:inline-block']">{{ tab.count }}</span>
                </a>
              </nav>
            </div>
          </div>
          


            <div class="p-4">
                        <!-- Stacked list -->
        <ul role="list" class="mt-5 divide-y divide-gray-200 border-t border-gray-200 sm:mt-0 sm:border-t-0">
          <!-- <li v-for="candidate in candidates" :key="candidate.email"> -->
        <li v-for="candidate in 24" :key="candidate">

            <a href="#" class="group block">
              <div class="flex items-center py-5 px-4 sm:py-6 sm:px-0">
                <div class="flex min-w-0 flex-1 items-center">
                  <div class="flex-shrink-0">
                    <div class="bg-cyan-600 rounded-full text-white p-2 h-10 w-10  group-hover:opacity-75">
                        <PlusIcon class="h-5 w-5 m-auto" />
                    </div>
                    <small>Assign
                        Agents 
                    </small>

                  </div>
                  <div class="min-w-0 flex-1 px-4">
                    <div>
                      <p class="truncate text-sm font-medium">{{ candidates.name }}</p>
                      <p class="mt-2 flex items-center text-sm text-gray-500">
                        <BuildingOffice2Icon class="mr-1.5 h-5 w-5 flex-shrink-0 text-gray-700" aria-hidden="true" />
                        <span class="truncate">{{ candidates.adress }}</span>
                      </p>
                      <p class="text-gray-500 text-sm">
                        {{candidates.company}}
                      </p>
                      <p class="text-sm text-blue-400">
                          <time :datetime="candidates.appliedDatetime">{{ candidates.applied }}</time>
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


import { BuildingOffice2Icon, ChevronRightIcon, PlusIcon} from '@heroicons/vue/24/outline'

const Tasks = [
  { name: 'Unassigned', href: '#', count: '24', current: true },
  { name: 'Assigned', href: '#', count: '12', current: false },
  { name: 'Completed', href: '#', count: '30', current: false },
]

const candidates =
  {
    name: 'Emily Selman',
    adress: '12b Emmanuel Street, Surulere Lagos',
    company: "Sterling Bank Plc",
    appliedDatetime: '2020-07-01T15:34:56',

  }


export default {
        name: "Tasks",
        components: { BuildingOffice2Icon, ChevronRightIcon, PlusIcon },

data() {
    return {
        tabs: Tasks,
        candidates: candidates,
    }
}
}
</script>