<template>
    <div class="faqs-section main-section-mb">
        <div class="main-container">
            <h2 class="main-h2 text-center">{{ sectionFAQS.title }}</h2>
            <p class="text-center">{{ sectionFAQS.paragraph }}</p>
            <div class="accordion" id="accordionExample">
                <div class="accordion-item" v-for="(faq, index) in faqs" :key="index">
                    <h2 class="accordion-header" :id="`heading${index}`">
                    <button class="accordion-button" type="button" data-bs-toggle="collapse" :data-bs-target="`#collapse${index}`" aria-expanded="true" :aria-controls="`collapse${index}`">
                        {{ faq.title }}
                    </button>
                    </h2>
                    <div :id="`collapse${index}`" class="accordion-collapse collapse" :class="{'show' : index === 0}" :aria-labelledby="`heading${index}`" data-bs-parent="#accordionExample">
                        <div class="accordion-body">
                            {{ faq.answer }}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data: () => ({
        sectionFAQS: {
            title: 'Frecuent Questions',
            paragraph: 'Lorem ipsum dolors quis illum, ullam vitae officia quisquam quo ipsum voluptates illo quae hic iusto voluptate id quasi.',
        },
        faqs: [
            {title: 'Question 1', answer: 'This is the first item s accordion body. It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. Its also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.'},
            {title: 'Question 2', answer: 'This is the first item s accordion body. It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. Its also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.'},
            {title: 'Question 3', answer: 'This is the first item s accordion body. It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. Its also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.'},
            {title: 'Question 4', answer: 'This is the first item s accordion body. It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. Its also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.'}
        ]
    })
}
</script>

<style lang="scss" scoped>
.main-container{
    --main-max-width: 1100px;
    gap: 30px;
    display: flex;
    flex-direction: column;
}

</style>