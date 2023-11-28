<template>
  <div class="main-container main-section-mb ft-products-grid">
    <h2 class="main-h2 text-center">{{ sectionFeaturedProducts.title }}</h2>
    <p class="text-center">{{ sectionFeaturedProducts.paragraph }}</p>
    <div class="ft-products__cards-grid">
        <div v-for="(product, index) in products" :key="index" class="ft-products__cards">
            <NuxtLink :to="`/products/${product._id.$oid}`">
                <img :src="product.gallery.find(img => img.isMain)?.url" alt="" class="ft-products__img">
                <div class="ft-products__info">
                    <div class="tag">{{ product.categories[0]?.name }}</div>
                    <h4>{{ product.name }}</h4>
                    <p>{{ product.description }}</p>
                </div>
            </NuxtLink>
        </div>
    </div>
    <a href="/products/catalog" class="main-button">{{ sectionFeaturedProducts.cta }}</a>
  </div>
</template>

<script>
export default {
    data: () => ({
        sectionFeaturedProducts: {
            title: 'Productos destacados',
            paragraph: 'Lorem ipsum dolors quis illum, ullam vitae officia quisquam quo ipsum voluptates illo quae hic iusto voluptate id quasi.',
            cta: 'Ver todos los productos',
        },
        products: [
            {
                _id: { $oid: 'product-1 '}, 
                name: 'example', 
                categories: [
                    { name: 'primera', slug: 'primera' },
                ],
                gallery: [
                    { url: '', alt: '', isMain: true },
                    { url: '', alt: '', isMain: false },
                    { url: '', alt: '', isMain: false },
                    { url: '', alt: '', isMain: false },
                ],
                price: 15.10,
                description: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Fuga itaque repellat quaerat error blanditiis dignissimos ratione ab voluptatibus est optio quod, facilis deserunt harum pariatur. Pariatur hic maiores dolores alias.' 
            },
            {
                _id: { $oid: 'product-2 '}, 
                name: 'example', 
                categories: [
                    { name: 'segunda', slug: 'segunda' },
                ],
                gallery: [
                    { url: '', alt: '', isMain: true },
                    { url: '', alt: '', isMain: false },
                    { url: '', alt: '', isMain: false },
                    { url: '', alt: '', isMain: false },
                ],
                price: 15.10,
                description: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Fuga itaque repellat quaerat error blanditiis dignissimos ratione ab voluptatibus est optio quod, facilis deserunt harum pariatur. Pariatur hic maiores dolores alias.' 
            },
            {
                _id: { $oid: 'product-3 '}, 
                name: 'example', 
                categories: [
                    { name: 'tercera', slug: 'tercera' },
                ],
                gallery: [
                    { url: '', alt: '', isMain: true },
                    { url: '', alt: '', isMain: false },
                    { url: '', alt: '', isMain: false },
                    { url: '', alt: '', isMain: false },
                ],
                price: 15.10,
                description: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Fuga itaque repellat quaerat error blanditiis dignissimos ratione ab voluptatibus est optio quod, facilis deserunt harum pariatur. Pariatur hic maiores dolores alias.' 
            },
            {
                _id: { $oid: 'product-4 '}, 
                name: 'example', 
                categories: [
                    { name: 'cuarta', slug: 'cuarta' },
                ],
                gallery: [
                    { url: '', alt: '', isMain: true },
                    { url: '', alt: '', isMain: false },
                    { url: '', alt: '', isMain: false },
                    { url: '', alt: '', isMain: false },
                ],
                price: 15.10,
                description: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Fuga itaque repellat quaerat error blanditiis dignissimos ratione ab voluptatibus est optio quod, facilis deserunt harum pariatur. Pariatur hic maiores dolores alias.' 
            },
        ]
    })
}
</script>

<style lang="scss" scoped>

.main-container{
    --main-max-width: 1500px;
}

.ft-products-grid{
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 30px;
}

.ft-products__cards-grid{
    width: 100%;
    display: grid;
    flex-wrap: wrap;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 30px;
    .ft-products__cards{
        border: 1px solid #c1c1c1;
        display: flex;
        flex-direction: column;
        background-color: var(--white);
        cursor: pointer;
        border-radius: 3px;
        .ft-products__img{
            aspect-ratio: 16/9;
            background-color: var(--main-bg);
        }
        .ft-products__info{
            padding: 10px 15px;
            display: flex;
            flex-direction: column;
            gap: 5px;
            h4{
                font-size: 16px;
                margin-block: 5px;
                text-align: left;
                overflow-wrap: break-word;
                display: -webkit-box;
                -webkit-line-clamp: 2;
                -webkit-box-orient: vertical;
                overflow: hidden;
                text-overflow: ellipsis;
                font-weight: 600;
            }
            p{
                font-size: 14px;
                text-align: left;
                overflow-wrap: break-word;
                display: -webkit-box;
                -webkit-line-clamp: 3;
                -webkit-box-orient: vertical;
                overflow: hidden;
                text-overflow: ellipsis;
            }    
        }
        &:hover{
            scale: 1.07;
            transition: scale .3s;
        }
    }
}

</style>