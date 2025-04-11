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
                  <MaterialButton color="primary" @click="sendMessage" >Enviar</MaterialButton>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

    </div>
  </Header>
</template>
