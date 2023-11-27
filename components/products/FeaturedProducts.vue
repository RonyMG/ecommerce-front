<template>
  <div class="main-container main-section-mb ft-products-grid">
    <h2 class="main-h2 text-center">{{ sectionFeaturedProducts.title }}</h2>
    <p class="text-center">{{ sectionFeaturedProducts.paragraph }}</p>
    <div class="ft-products__cards-grid">
        <div v-for="(featuredProduct, index) in featuredProducts" :key="index" class="ft-products__cards">
            <img src="" alt="" class="ft-products__img">
            <div class="ft-products__info">
                <div class="tag">{{ featuredProduct.categorie}}</div>
                <h4>{{ featuredProduct.title }}</h4>
                <p >{{ featuredProduct.description }}</p>
            </div>
        </div>
    </div>
    <button class="main-button">{{ sectionFeaturedProducts.cta }}</button>
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
        featuredProducts: [
            { title: 'example', categorie: 'primera', href: '', src: '', description: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Fuga itaque repellat quaerat error blanditiis dignissimos ratione ab voluptatibus est optio quod, facilis deserunt harum pariatur. Pariatur hic maiores dolores alias.' },
            { title: 'example', categorie: 'primera', href: '', src: '', description: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Fuga itaque repellat quaerat error blanditiis dignissimos ratione ab voluptatibus est optio quod, facilis deserunt harum pariatur. Pariatur hic maiores dolores alias.' },
            { title: 'example', categorie: 'primera', href: '', src: '', description: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Fuga itaque repellat quaerat error blanditiis dignissimos ratione ab voluptatibus est optio quod, facilis deserunt harum pariatur. Pariatur hic maiores dolores alias.' },
            { title: 'example', categorie: 'primera', href: '', src: '', description: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Fuga itaque repellat quaerat error blanditiis dignissimos ratione ab voluptatibus est optio quod, facilis deserunt harum pariatur. Pariatur hic maiores dolores alias.' },
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