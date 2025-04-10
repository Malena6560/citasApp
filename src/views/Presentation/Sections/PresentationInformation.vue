<script setup>
import RotatingCard from "../../../examples/cards/rotatingCards/RotatingCard.vue";
import RotatingCardFront from "../../../examples/cards/rotatingCards/RotatingCardFront.vue";
import RotatingCardBack from "../../../examples/cards/rotatingCards/RotatingCardBack.vue";
import DefaultInfoCard from "../../../examples/cards/infoCards/DefaultInfoCard.vue";
import vueImgCard from "@/assets/img/cardPrincipal.jpg"; 
import vueImgCard2 from "@/assets/img/cardPrincipal2.jpg"; 

</script>
<template>
  <section class="my-5 py-5">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-lg-4 ms-auto me-auto p-lg-4 mt-lg-0 mt-4">
          <!-- Card de la Pantalla Principal -->
          <RotatingCard>
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
              icon="content_copy"
              title="El amor que esperas"
              description="Regístrate gratis y da el primer paso hacia nuevas experiencias y emociones."
            />
            <DefaultInfoCard
              icon="flip_to_front"
              title="Bootstrap 5 Ready"
              description="The world’s most popular front-end open source toolkit,
                  featuring Sass variables and mixins."
            />
          </div>
          <div class="row justify-content-start mt-5">
            <DefaultInfoCard
              class="mt-3"
              icon="price_change"
              title="Save Time & Money"
              description="Creating your design from scratch with dedicated designers can
                be very expensive. Start with our Design System."
            />
            <DefaultInfoCard
              class="mt-3"
              icon="devices"
              title="Fully Responsive"
              description="Regardless of the screen size, the website content will
                  naturally fit the given resolution."
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
