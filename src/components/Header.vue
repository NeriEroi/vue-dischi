<template>
  <div>
      <div class="row">
          <div class="logo_cont">
              <img src="../assets/img/logo-small.svg" alt="spotify logo">
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style>
    .row {
        width: 100%;
        height: 10vh;
        background-color: #2E3A46;
    } .logo_cont {
        width: 5%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    } img {
        width: 60%;
        height: 60%;
        object-fit: contain;
    }
    
</style>