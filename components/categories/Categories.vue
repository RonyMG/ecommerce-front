<template>
    <div class="main-container main-section-mb">
        <h2 class="main-h2 text-center">{{ categories.sectionTitle}}</h2>
        <p class="text-center">{{ categories.sectionParagraph}}</p>
        <div class="categories__grid">
            <a v-for="(categoriesCard, index) in categoriesCards" :key="index" class="categories__card" :href="categoriesCard.href">
                <span class="categorie__span">{{ categoriesCard.name }}</span>
            </a>   
        </div>
        <button class="main-button">{{ categories.sectionCta }}</button>
    </div>
</template>

<script>
export default {
    data: () => ({
        categories: {
            sectionTitle: 'Categories',
            sectionParagraph: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.',
            sectionCta: 'Ver todas las categorías',
        },
        categoriesCards: [
            {name: 'Primera', href: '/'},
            {name: 'Segunda', href: '/'},
            {name: 'Tercera', href: '/'},
            {name: 'Cuarta', href: '/'},
        ]
    })
}
</script>

<style lang="scss" scoped>
.main-container{
    --main-max-width: 1100px;
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    gap: 30px;
}
.categories__grid{
    --categories-minmax: 200px;
    width: 100%;
    display: grid;
    grid-template-columns: repeat(auto-fill, (minmax(var(--categories-minmax), 1fr)));
    gap: 30px;
    @media (max-width: 575px) {
        --categories-minmax: 150px
    }
}
.categories__card{
    aspect-ratio: 1/1;
    border-radius: 5px;
    border: 1px solid #c1c1c1;
    display: flex;
    justify-content: center;
    align-items: center;
    background: var(--main-bg);
    cursor: pointer;

    .categorie__span{
    font-weight: 600;
    text-transform: uppercase;
    }
    &:hover{
        scale: 1.05;
        transition: scale .3s;
    }
}

</style>