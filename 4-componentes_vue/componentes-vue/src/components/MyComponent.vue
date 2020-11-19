<template>
  <div class="hero">
      <div class="hero-inner">          
          <h1 class="hero-title">{{title}}</h1>
          <div class="hero-description">
              <p>{{message}}</p>
          </div>
          <div class="hero-actions mt-4">
              <div class="btn btn-primary mr-3">
                  <BaseButton 
                    v-if="primaryCallToAction"
                    v-bind:text="primaryCallToAction.text"
                    v-bind:btnOnClick="primaryCallToAction.btnOnClick"
                    type="primary"
                    extraClass="mr-3"
                  />

                  <BaseButton 
                    v-if="secondaryCallToAction"
                    v-bind:text="secondaryCallToAction.text"
                    v-bind:btnOnClick="secondaryCallToAction.btnOnClick"
                    type="secondary"
                  />
              </div>
          </div>
      </div>
      <img class="hero-img" src="../assets/logo.png" alt="Logo Vue">
  </div>
</template>

<script>
import BaseButton from './BaseButton'

export default {
    name: 'MyComponent',
    props: {
        title: {
            type: String,
            required: true,
        },
        message: {
            type: String,
            default: '',
        },
        primaryCallToAction: Object,
        secondaryCallToAction: Object
    },
    components: {
        BaseButton
    },    
};
</script>

<style scoped>
    .hero {
        background: #282c34;
        display: flex;
        justify-content: flex-end;
        align-items: center;        
        font-weight: 700;
        height: 50vh;
        widows: 100vw;
        color: white;
    }

    .hero-inner {
        text-align: right;
        margin-right: 50px;
        width: 50%;
    }

    .hero-img {
        position: absolute;
        left: 0;
        right: 0;
        margin-left: 200px;
    }

    @media (prefers-reduced-motion: no-preference) {
        .hero-img {
            animation: App-logo-spin infinite 5s linear;
        }
    }

    @keyframes App-logo-spin {
        10% {
            transform: rotateX(180deg);
        }
        30% {
            transform: rotateX(0deg);
        }
        70% {
            transform: rotateX(0deg);
        }
        90% {
            transform: rotateX(180deg);
        }
    }

    .hero-title {
        font-size: 50px;
        text-transform: uppercase;
    }

    .hero-description {
        font-size: 20px;
        line-height: 25px;
    }

    .mr-3 {
        margin-right: 1rem !important;
    }

    .mt-4,
    .my-4 {
        margin-top: 1.5rem !important;
    }
</style>