<template>
  <div id="slider" class="slider-lg">
      <h1 class="title-lg">{{text}}</h1>
      <p class="description-lg">El Framework JavaScript Progresivo</p>
      <a href="#" target="_blank">Comenzar</a>
      <a href="https://es.vuejs.org/" class="tutorial_link" target="_blank">
        Visita su página
        <svg
          height="12"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 4.53657 8.69699"
          class="css-b7q1rs"
        >
          <path
            d="
            M.18254,8.697a.18149.18149,0,0,1-.12886-.31034L4.09723,4.34126.05369.29954a.18149.18149,
            0,0,1,.2559-.2559L4.4838,4.21785a.18149.18149,0,0,1,0,.2559L.30958,8.648A.18149.18149,
            0,0,1,.18254,8.697Z
          "
            fill="currentColor"
          ></path>
        </svg>
      </a>
    </div>
</template>

<script>
export default {
    name: "Slider",
    props: ['text', 'home']
}
</script>