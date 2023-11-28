<template>
    <div>
        <MainBanner></MainBanner>
        <About></About>
        <Categories></Categories>
        <FeaturedProducts></FeaturedProducts>
        <FAQS></FAQS>
    </div>
</template>
  
<script>

import MainBanner from '../components/Banners/MainBanner'
import About from '../components/about/About'
import Categories from '../components/categories/Categories'
import FeaturedProducts from '../components/products/FeaturedProducts'
import FAQS from '../components/FAQS'

export default {
    components: { MainBanner, About, Categories, FeaturedProducts, FAQS },
}
</script>

<style lang="scss">
    div{
        p{
            color: black;
        }
    }
</style>