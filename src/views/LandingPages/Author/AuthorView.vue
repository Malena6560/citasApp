<script setup>
import { onMounted } from "vue";

// example components
import DefaultNavbar from "@/examples/navbars/NavbarDefault.vue";
import Header from "@/examples/Header.vue";

//Vue Material Kit 2 components
import MaterialInput from "@/components/MaterialInput.vue";
import MaterialSwitch from "@/components/MaterialSwitch.vue";
import MaterialButton from "@/components/MaterialButton.vue";


// material-input
import setMaterialInput from "@/assets/js/material-input";
onMounted(() => {
  setMaterialInput();
});
</script>

<template>
  <DefaultNavbar transparent />
  <Header>
    <div
      class="page-header align-items-start min-vh-100"
      :style="{
        backgroundImage: 'url(/fondo.jpg)'
      }"
      loading="lazy"
    >
      <span class="mask bg-gradient-dark opacity-6"></span>
      <div class="container my-auto">
        <div class="row">
          <div class="col-lg-4 col-md-8 col-12 mx-auto">
            <div class="card z-index-0 fadeIn3 fadeInBottom">
              <div class="card-header p-0 position-relative mt-n4 mx-3 z-index-2">
                <div class="bg-gradient-primary shadow-primary border-radius-lg py-3 pe-1">
                  <h4 class="text-white font-weight-bolder text-center mt-2 mb-0">
                    Crear Cuenta
                  </h4>
                </div>
              </div>
              <div class="card-body">
                <form role="form" class="text-start">
                  <MaterialInput
                    id="name"
                    class="input-group-outline my-3"
                    :label="{ text: 'Nombre completo', class: 'form-label' }"
                    type="text"
                  />
                  <MaterialInput
                    id="email"
                    class="input-group-outline mb-3"
                    :label="{ text: 'Correo Electrónico', class: 'form-label' }"
                    type="email"
                  />
                  <MaterialInput
                    id="password"
                    class="input-group-outline mb-3"
                    :label="{ text: 'Contraseña', class: 'form-label' }"
                    type="password"
                  />
                  <MaterialInput
                    id="confirmPassword"
                    class="input-group-outline mb-3"
                    :label="{ text: 'Confirmar Contraseña', class: 'form-label' }"
                    type="password"
                  />

                  <MaterialSwitch
                    class="d-flex align-items-center mb-3"
                    id="terms"
                    labelClass="mb-0 ms-3"
                  >
                    Acepto los términos y condiciones
                  </MaterialSwitch>

                  <div class="text-center">
                    <MaterialButton
                      class="my-4 mb-2"
                      variant="gradient"
                      color="primary"
                      fullWidth
                    >
                      Registrarse
                    </MaterialButton>
                  </div>
                  <p class="mt-4 text-sm text-center">
                    Ya tienes una cuenta?
                    <a
                      href="../SignIn/BasicView.vue"
                      class="text-primary text-gradient font-weight-bold"
                    >
                      Inicia sesión
                    </a>
                  </p>
                </form>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </Header>
</template>
