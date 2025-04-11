<script setup>
import { ref, onMounted } from "vue";

// example components
import DefaultNavbar from "@/examples/navbars/NavbarDefault.vue";
import Header from "@/examples/Header.vue";

//Vue Material Kit 2 components
import MaterialInput from "@/components/MaterialInput.vue";
import MaterialButton from "@/components/MaterialButton.vue";

// material-input
import setMaterialInput from "@/assets/js/material-input";

onMounted(() => {
  setMaterialInput();
});

const messages = ref([
  { user: "Juan", text: "Hola, ¿cómo estás?" },
  { user: "Tú", text: "Todo bien, ¿y tú?" },
]);

const newMessage = ref("");

function sendMessage() {
  if (newMessage.value.trim() !== "") {
    messages.value.push({ user: "Tú", text: newMessage.value });
    newMessage.value = "";
  }
}
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
            <div class="card z-index-0 fadeIn3 fadeInBottom">
              <div class="card-header bg-gradient-primary text-center py-3">
  <h4 class="mb-0 text-white">Sala de Chat</h4>
</div>
              <div class="card-body" style="max-height: 400px; overflow-y: auto;">
                <div v-for="(msg, index) in messages" :key="index" class="mb-3">
                  <div
                    :class="[
                      'p-3 rounded',
                      msg.user === 'Tú'
                        ? 'bg-gradient-info text-white text-end ms-auto'
                        : 'bg-light text-dark me-auto'
                    ]"
                    style="max-width: 75%;"
                  >
                    <strong>{{ msg.user }}:</strong> {{ msg.text }}
                  </div>
                </div>
              </div>
              <div class="card-footer">
                <div class="d-flex">
                  <input
                    v-model="newMessage"
                    type="text"
                    placeholder="Escribe un mensaje..."
                    class="form-control me-2"
                    @keyup.enter="sendMessage"
                  />
                  <MaterialButton color="primary" @click="sendMessage">Enviar</MaterialButton>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <footer class="footer position-absolute bottom-2 py-2 w-100">
        <div class="container">
          <div class="row align-items-center justify-content-lg-between">
            <div class="col-12 col-md-6 my-auto">
              <div class="copyright text-center text-sm text-white text-lg-start">
                © {{ new Date().getFullYear() }}, hecho con
                <i class="fa fa-heart" aria-hidden="true"></i> por
                <a
                  href="https://www.creative-tim.com"
                  class="font-weight-bold text-white"
                  target="_blank"
                >
                  Creative Tim
                </a>
              </div>
            </div>
            <div class="col-12 col-md-6">
              <ul class="nav nav-footer justify-content-center justify-content-lg-end">
                <li class="nav-item">
                  <a href="https://www.creative-tim.com" class="nav-link text-white" target="_blank">
                    Creative Tim
                  </a>
                </li>
                <li class="nav-item">
                  <a href="https://www.creative-tim.com/presentation" class="nav-link text-white" target="_blank">
                    About Us
                  </a>
                </li>
                <li class="nav-item">
                  <a href="https://www.creative-tim.com/blog" class="nav-link text-white" target="_blank">
                    Blog
                  </a>
                </li>
                <li class="nav-item">
                  <a href="https://www.creative-tim.com/license" class="nav-link pe-0 text-white" target="_blank">
                    License
                  </a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </footer>
    </div>
  </Header>
</template>
