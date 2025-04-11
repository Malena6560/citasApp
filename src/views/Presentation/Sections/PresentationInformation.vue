<script setup>
import RotatingCard from "../../../examples/cards/rotatingCards/RotatingCard.vue";
import RotatingCardFront from "../../../examples/cards/rotatingCards/RotatingCardFront.vue";
import RotatingCardBack from "../../../examples/cards/rotatingCards/RotatingCardBack.vue";
import DefaultInfoCard from "../../../examples/cards/infoCards/DefaultInfoCard.vue";
import vueImgCard from "@/assets/img/cardFondo.jpg";
import vueImgCard2 from "@/assets/img/cardFondo2.jpg";
</script>
<template>
  <section class="my-5 py-5">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-lg-4 ms-auto me-auto p-lg-4 mt-lg-0 mt-4">
          <RotatingCard>
            <!-- Tarjetas de personas -->
            <RotatingCardFront
             :style="`background-image: url(${vueImgCard})`"
              icon="touch_app"
              title="No te rindas! </br> Tu futuro espera"
              description="Charla, comparte, y deja que la vida te sorprenda con nuevas amistades o un gran amor."
            />

            <RotatingCardBack
             :style="`background-image: url(${vueImgCard2})`"
              title="Descubre Mas!"
              description="El amor y la amistad no tienen edad, solo necesitan una oportunidad."
            />
          </RotatingCard>
        </div>
        <div class="col-lg-6 ms-auto">
          <div class="row justify-content-start">
            <DefaultInfoCard
              title="El amor que esperas"
              description="Regístrate gratis y da el primer paso hacia nuevas experiencias y emociones."
            />
            <DefaultInfoCard
              title="La chispa no se apaga…"
              description="¡solo se enciende con más estilo!"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>