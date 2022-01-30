<template>
   
    <div
      class="d-flex flex-column flex-shrink-0 p-3 text-white bg-dark"
      style="max-width:100%; height:100vh; position:fixed"
    >
    
      <a
        href="/"
        class="d-flex align-items-center mb-3 mb-md-0 me-md-auto text-white text-decoration-none"
      >
       
        <span class="fs-4">Скоропись</span>
      </a>
      <hr />
      <ul class="nav nav-pills flex-column mb-auto">
        <li class="nav-item">
          <router-link to="/" class="nav-link text-white" aria-current="page">
            <svg class="bi me-2" width="16" height="16">
              
            </svg>
            Home
          </router-link>
        </li>
        <li>
          <router-link to="/about" class="nav-link text-white">
            <svg class="bi me-2" width="16" height="16">
              
            </svg>
            Dashboard
          </router-link>
        </li>
      </ul>
      <hr />
      <div class="dropdown">
        <img
          src="https://github.com/mdo.png"
          alt=""
          width="32"
          height="32"
          class="rounded-circle me-2"
        />
        <strong>Иван Иванов</strong>
      </div>
    </div>
</template>

<script>
export default {
    name: 'Nav',

}
</script>

<style>

</style>