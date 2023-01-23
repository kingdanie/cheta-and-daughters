<template>
<nav class="hidden md:col-span-2 xl:col-span-2 lg:block" aria-label="Sidebar">
<div class="bg-cyan-700 p-5 text-cyan-100">
        <h3 class="font-bold">Cheta And Daughters Limited </h3>
        <div>RC1234689</div>
</div>

<div class="bg-cyan-600 text-white flex-1 space-y-1 h-full pt-10">
    <NuxtLink v-for="item in Menu" :key="item.name" :href="item.name" :class="[item.current ? 'bg-cyan-500 border-white text-white' : 'border-transparent text-gray-200 hover:bg-gray-50 hover:text-gray-900', 'group capitalize flex items-center px-3 py-2 text-sm font-medium border-l-4']">
          <component :is="item.icon" :class="[item.current ? 'text-gray-50' : 'text-gray-200/50 group-hover:text-gray-500', 'mr-5 flex-shrink-0 h-6 w-6']" aria-hidden="true" />
          {{ item.name }}
    </NuxtLink>
</div>
</nav>

</template>

<script>
import { BriefcaseIcon, UserGroupIcon, BuildingOffice2Icon, Cog6ToothIcon, ClipboardDocumentListIcon, CheckCircleIcon } from '@heroicons/vue/24/solid'
const Menu = [
    {name: "dashboard", icon: BriefcaseIcon, current: true},
    {name: "agents", icon: UserGroupIcon, current: false},
    {name: "task", icon: ClipboardDocumentListIcon, current: false},
    {name: "teams", icon: CheckCircleIcon, current: false},
    {name: "users", icon: BuildingOffice2Icon, current: false},
    {name: "settings", icon: Cog6ToothIcon, current: false}
]

export default {
        name: "NavBar",

        data() {
            return {
                Menu: Menu
            }
        }
}
</script>