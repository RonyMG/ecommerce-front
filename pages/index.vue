<template>
    <div>
        <MainBanner></MainBanner>
        <About></About>
        <Categories></Categories>
        <FeaturedProducts></FeaturedProducts>
    </div>
</template>
  
<script>

import MainBanner from '../components/Banners/MainBanner'
import About from '../components/about/About'
import Categories from '../components/categories/Categories'
import FeaturedProducts from '../components/products/FeaturedProducts'

export default {
    components: { MainBanner, About, Categories, FeaturedProducts },
}
</script>

<style lang="scss">
    div{
        p{
            color: black;
        }
    }
</style>