<script setup>
import { onMounted, ref } from "vue";

// example components
import DefaultNavbar from "@/examples/navbars/NavbarDefault.vue";
import Header from "@/examples/Header.vue";
import iconoPerf from "@/assets/img/iconoPerfil.png"

//Vue Material Kit 2 components
import MaterialButton from "@/components/MaterialButton.vue";

// material-input
import setMaterialInput from "@/assets/js/material-input";

onMounted(() => {
  setMaterialInput();
});

const compatibleProfile = ref({
  name: "María Gómez",
  age: 68,
  image: "../assets/img/iconoPerfil.jpg", // asegúrate de tener esta imagen en la carpeta public
  interests: ["Paseos al atardecer", "Lectura", "Jardinería", "Música clásica"],
});
</script>

<template>
  <DefaultNavbar transparent />
  <Header>
    <div
      class="page-header align-items-start min-vh-100"
      :style="{ backgroundImage: 'url(/fondo.jpg)' }"
      loading="lazy"
    >
      <span class="mask bg-gradient-dark opacity-6"></span>
      <div class="container my-auto">
        <div class="row justify-content-center">
          <div class="col-lg-6 col-md-8 col-12">
            <div class="card z-index-0 fadeIn3 fadeInBottom text-center">
              <div class="card-header bg-gradient-primary text-white py-3">
                <h4 class="mb-0 text-white">Perfil Compatible</h4>
              </div>
              <div class="card-body">
                <img
                  :src="img6"
                  alt="Foto de perfil"
                  class="rounded-circle shadow"
                  style="width: 150px; height: 150px; object-fit: cover; margin-bottom: 1rem;"
                />
                <h5 class="font-weight-bold mb-1">{{ compatibleProfile.name }}</h5>
                <p class="text-secondary mb-3">{{ compatibleProfile.age }} años</p>
                <h6 class="text-info">Intereses en común:</h6>
                <ul class="list-unstyled">
                  <li v-for="(interest, i) in compatibleProfile.interests" :key="i">
                    🌿 {{ interest }}
                  </li>
                </ul>
                <MaterialButton color="primary" class="mt-3">Conectar</MaterialButton>
              </div>
            </div>
          </div>
        </div>
      </div>

    </div>
  </Header>
</template>