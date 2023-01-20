<template>
        <!-- <div>Hello World, greetings for Nuxt</div> -->
   <!-- Navbar -->
   <Disclosure as="nav" class="flex-shrink-0" >

      <div class="mx-auto px-2 sm:px-4 lg:px-8 shadow">
        <div class="relative flex h-16 items-center justify-between">
          <!-- Logo section -->
          <div class="flex justify-between px-2 lg:px-0 md:w-40 xl:w-48">
            <div class="flex-shrink-0">
                <NuxtLink to="/">
                        <img class="h-8 w-auto" src="/img/youverify.png" alt="Chetas & Daughters Ltd" />
                </NuxtLink>
            </div>
            <NuxtLink to="#">
                <ArrowLeftCircleIcon class="h-8 w-8 text-cyan-700" />
            </NuxtLink>
          </div>

          <!-- Search section -->
          <div class="flex flex-1 justify-center lg:justify-between">
            <div class="w-full px-2 lg:px-6">
              <label for="search" class="sr-only">Search projects</label>
              <div class="relative text-gray-200 focus-within:text-gray-400">
                      <input id="search" name="search" 
                                class="
                                        block w-full rounded-md border border-transparent 
                                        bg-gray-300 bg-opacity-25 py-2 pl-10 pr-3 leading-5 
                                        text-gray-100 placeholder-gray-400 focus:bg-gray-200 
                                        focus:text-gray-900 focus:placeholder-gray-600 
                                        focus:outline-none focus:ring-0 sm:text-sm font-semibold
                                " 
                                placeholder="Search for anything here" type="search" 
                        />
                      <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center pr-3">
                        <MagnifyingGlassIcon class="h-5 w-5 text-gray-500 hover:text-gray-400" aria-hidden="true" />
                      </div>
              </div>
            </div>
          </div>
          <div class="flex lg:hidden">
            <!-- Mobile menu button -->
            <DisclosureButton class="inline-flex items-center justify-center rounded-md bg-cyan-600 p-2 text-cyan-400 hover:bg-cyan-600 hover:text-white focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-cyan-600">
              <span class="sr-only">Open main menu</span>
              <Bars3CenterLeftIcon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
              <XMarkIcon v-else class="block h-6 w-6" aria-hidden="true" />
            </DisclosureButton>
          </div>
          <!-- Links section -->
          <div class="hidden lg:block md:w-48 space-x-5">
            <div class="flex items-center justify-between">
              <div class="flex rounded-lg p-2 bg-cyan-50 hover:bg-cyan-100">
                <BellIcon class="h-6 w-6 text-cyan-400 "/>
              </div>
              <!-- Profile dropdown -->
              <Menu as="div" class="relative ml-4 flex-shrink-0">
                <div>
                  <MenuButton class="flex rounded-full bg-cyan-700 text-sm text-white focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-cyan-700">
                    <span class="sr-only">Open user menu</span>
                    <img class="h-8 w-8 rounded-full" src="https://images.unsplash.com/photo-1517365830460-955ce3ccd263?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=256&h=256&q=80" alt="" />
                  </MenuButton>
                </div>
                <!-- <transition enter-active-class="transition ease-out duration-100" enter-from-class="transform opacity-0 scale-95" enter-to-class="transform opacity-100 scale-100" leave-active-class="transition ease-in duration-75" leave-from-class="transform opacity-100 scale-100" leave-to-class="transform opacity-0 scale-95">
                  <MenuItems class="absolute right-0 z-10 mt-2 w-48 origin-top-right rounded-md bg-white py-1 shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none">
                    <MenuItem v-for="item in userNavigation" :key="item.name">
                      <a :href="item.href" :class="[active ? 'bg-gray-100' : '', 'block px-4 py-2 text-sm text-gray-700']">{{ item.name }}</a>
                    </MenuItem>
                  </MenuItems>
                </transition> -->
              </Menu>
              <div class="flex items-center space-x-3">
                <small class="font-medium text-cyan-800">Solomon</small>
                <NuxtLink to="#">
                        <ChevronDownIcon class="h-4 w-4 font-medium text-cyan-800"/>
                </NuxtLink>
                </div>
            </div>
          </div>
        </div>
      </div>

      <DisclosurePanel class="lg:hidden">

        <div class="space-y-1 px-2 pt-2 pb-3">
          <DisclosureButton v-for="item in navigation" :key="item.name" as="a" :href="item.href" :class="[item.current ? 'text-white bg-cyan-800' : 'text-cyan-200 hover:text-cyan-100 hover:bg-cyan-600', 'block px-3 py-2 rounded-md text-base font-medium']" :aria-current="item.current ? 'page' : undefined">{{ item.name }}</DisclosureButton>
        </div>
        <div class="border-t border-cyan-800 pt-4 pb-3">
          <div class="space-y-1 px-2">
            <DisclosureButton v-for="item in userNavigation" :key="item.name" as="a" :href="item.href" class="block rounded-md px-3 py-2 text-base font-medium text-cyan-200 hover:bg-cyan-600 hover:text-cyan-100">{{ item.name }}</DisclosureButton>
          </div>
        </div>
      </DisclosurePanel>
    </Disclosure>
</template>
  
<script>
import { Disclosure, DisclosureButton, DisclosurePanel, Menu, MenuButton, MenuItem, MenuItems } from '@headlessui/vue'
import {
  MagnifyingGlassIcon,
  ChevronDownIcon,
  BellIcon
} from '@heroicons/vue/20/solid'
import { Bars3CenterLeftIcon, XMarkIcon, ArrowLeftCircleIcon,  } from '@heroicons/vue/24/outline'

const userNavigation = [
  { name: 'Your Profile', href: '#' },
  { name: 'Settings', href: '#' },
  { name: 'Sign out', href: '#' },
]
const navigation = [
  {name: "dashboard", current: true},
    {name: "agents",  current: false},
    {name: "tasks",  current: false},
    {name: "teams",  current: false},
    {name: "users",  current: false},
    {name: "settings",  current: false}
]

export default {
name: "TopBars",
components: { Bars3CenterLeftIcon, XMarkIcon, MagnifyingGlassIcon, ArrowLeftCircleIcon, ChevronDownIcon, BellIcon},

data() {
    return {
        navigation: navigation,
        userNavigation: userNavigation,
        open: false,
        active: false
    }
}
}
</script>