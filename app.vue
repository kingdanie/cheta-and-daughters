<template>
  <div class="min-h-full">
    <TopBar />
    <main class="mx-auto lg:grid lg:grid-cols-12">
      <NavBar />
      <div class="lg:col-span-10 w-full h-full bg-red-200 mt-7">
        <div class="grid md:grid-cols-2 lg:grid-cols-3">
          <Tasks />
          <Maps />
         <Agents />
        </div>
      </div>
    </main>
  </div>
</template>
