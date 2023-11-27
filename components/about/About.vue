<template>
  <div class="main-container main-section-mb about-grid" :class="[`about-grid--${aboutUs.sectionAlign}`]">
    <h2 class="main-h2">{{aboutUs.sectionTitle}}</h2>
    <p>{{ aboutUs.sectionParagraph }}</p>
  <button class="main-button" :href="aboutUs.sectionHref">{{ aboutUs.sectionCta }}</button>
  </div>
</template>

<script>
export default {
  data: ()=>({
    aboutUs: {
      sectionAlign: 'center',
      sectionTitle: 'About us', 
      sectionParagraph: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Modi dolorem enim exercitationem tempora iusto numquam ullam repellendus earum ducimus hic! A ad minima magni quod, ab ducimus dolore odio deserunt', 
      sectionCta: 'Read more',
      sectionHref: '/about-us'
    }    
  })
}
</script>

<style lang="scss" scoped>
.main-container{
  --main-max-width: 1200px;

}
.about-grid{
  display: flex;
  flex-direction: column;
  gap: 30px;
  align-items: center;
  text-align: center;
}
.about-grid--left{
  align-items: start;
  text-align: left;
  margin-left: 0;
}
.about-grid--center{
  align-items: center;
  text-align: center;
}
.about-grid--right{
  align-items: end;
  text-align: right;
  margin-right: 0;
}
</style>