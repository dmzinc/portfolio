<template>
    <section class="bg-light" id="portfolio">
      <div class="container">
        <div class="row">
          <div class="col-lg-12 text-center">
            <h2 class="section-heading text-uppercase">Portfolio</h2>
            <h3 class="section-subheading text-muted">Project Sample</h3>
          </div>
        </div>
        <div class="row">
          
            <div class="col-md-4 col-sm-6 portfolio-item" v-for="(obj, key) in portfolioJSON" :key="key">
                <a class="portfolio-link" data-toggle="modal" href="#portfolioModal2">
                    <div class="portfolio-hover">
                        <div class="portfolio-hover-content">
                            <i class="fas fa-plus fa-3x"></i>
                        </div>
                    </div>
                    <img class="img-fluid" src="img/portfolio/02-thumbnail.jpg" alt="">
                </a>
                <div class="portfolio-caption">
                    <h4>{{ obj.caption }}</h4>
                    <p class="text-muted">{{ obj.title }}</p>
                </div>
            </div>
        </div>
      </div>
    </section>
</template>

<script>
export default {
    data: () => ({
        portfolioJSON: [
            {
                img: 'src/assets/img/devio1.png',
                caption: 'Perptual Academy',
                title: 'Web Design'
            },
            {
                img: '/something/random/img.jpg',
                caption: 'Finish',
                title: 'Identify'
            },
            {
                img: '/something/random/img.jpg',
                caption: 'Lines',
                title: 'Branding'
            },
            {
                img: '/something/random/img.jpg',
                caption: 'Southwest',
                title: 'Website Design'
            },
            {
                img: '/something/random/img.jpg',
                caption: 'Window',
                title: 'Photography'
            },
            {
                img: '/something/random/img.jpg',
                caption: 'Coffee',
                title: 'Drink a Lot!' 
            },
            {
                img: '/something/random/img.jpg',
                caption: 'Pizza',
                title: 'I Ate some Pizza!'
            }
        ]
    })
}
</script>

<style lang="css">

</style>


