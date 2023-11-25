<template>
  <div>
    <Navbar></Navbar>
    <div class="content-container first-section">
      <NuxtPage/>
    </div>
    <Footer :menuItems="menuItems"></Footer>
  </div>
</template>

<script>
export default {
  provide(){
    return{
      menuItems: this.menuItems
    }
  },
  data: () => ({
      menuItems: ['Home', 'About us', 'Locations', 'Terms and conditions']
  }),
}
</script>

<style>
.content-container{
  min-height: calc(100vh - var(--footer-height));
}
</style>
