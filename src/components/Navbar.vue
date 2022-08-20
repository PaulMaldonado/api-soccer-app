<template>
  <div>
      <nav class="navbar navbar-expand-lg navbar-light bg-light border-bottom p-4">
          <div class="container">
            <router-link to="/" class="navbar-brand">Soccer App</router-link>

            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>

            <div class="collapse navbar-collapse justify-content-end" id="navbarSupportedContent">
                <ul class="navbar-nav">
                    <li class="nav-item">
                        <router-link to="/" class="nav-link">Inicio</router-link>
                    </li>

                    <li class="nav-item">
                        <router-link to="/about" class="nav-link">Sobre nosotros</router-link>
                    </li>
                </ul>
            </div>
          </div> 
      </nav>
  </div>
</template>

<script>
export default {
    name: 'Navigation'
}
</script>

<style scoped>
    .bg-light {
        background-color: #ffffff !important;
    }

    .navbar-brand {
        color: black !important;
        font-weight: bold;
    }

    .nav-link {
        color: black !important;
        font-weight: bold;
    }
</style>