<template>
  <div>    
    <Header />
    <b-carousel
      id="carousel-1"
      v-model="slide"
      :interval="4000"
      indicators
      background="#73030D"
    >
      <b-carousel-slide img-src="/hero.jpg">
        <h2>Architecture Planning and Design</h2>
      </b-carousel-slide>
      <b-carousel-slide img-src="/hero.jpg">
        <h2>Architecture Planning and Design</h2>
      </b-carousel-slide>
      <b-carousel-slide img-src="/hero.jpg">
        <h2>Architecture Planning and Design</h2>
      </b-carousel-slide>
    </b-carousel>

    <div class="masonry">
      <b-container>
        <b-row no-gutters>
          <b-col md="12" lg="8">
            <b-row no-gutters>
              <b-col md="6">
                <div class="box red">
                  <div>
                    <h4>“Lorem ipsum dolor sit amet, consectetur adipiscing elit.”</h4>
                    <a href="#" class="download">Download</a>
                  </div>
                </div>
              </b-col>
              <b-col md="6">
                <div class="box yellow">
                  <h3>Architecture Planning and Design</h3>
                </div>
              </b-col>
              <b-col md="12">
                <div class="box image">
                  <div class="image-wrap" style="background-image: url('/home-2.jpg')"></div>
                  <h4>DEDC IAIN Sulthan<br/>Thaha Saifuddin Jambi (2017)</h4>
                </div>
              </b-col>
            </b-row>
          </b-col>
          <b-col md="12" lg="4">
            <b-row no-gutters>
              <b-col md="6" lg="12">
                <div class="box image">
                  <div class="image-wrap" style="background-image: url('/home-4.jpg')"></div>
                  <h4>Project Management and Supervision Consultant (PMSC) Sunan Ampel</h4>
                </div>
              </b-col>
              <b-col md="6" lg="12">
                <div class="box yellow">
                  <h3>Supervision and Construction Management</h3>
                </div>
              </b-col>
            </b-row>
          </b-col>
          <b-col md="4">
            <div class="box image short">
              <div class="image-wrap" style="background-image: url('/home-3.jpg')"></div>
              <h4>Perencanaan Struktur Pembangunan Gedung Bank Indonesia Jakarta</h4>
            </div>
          </b-col>
          <b-col md="8">
            <div class="box red text-left">
              <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
            </div>
          </b-col>
          <b-col md="4">
            <div class="box yellow">
              <h3>Investigation and Building Audits</h3>
            </div>
          </b-col>
          <b-col md="8">
            <div class="box image short">
              <div class="image-wrap" style="background-image: url('/home-1.jpg')"></div>
              <h4>Perencana Struktur Gedung Kelapa Gading Sport Plaza</h4>
            </div>
          </b-col>
        </b-row>
      </b-container>
    </div>
    
    <Footer />
  </div>
</template>

<script>
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'

export default {
  components: {
    Header,
    Footer
  },
  data() {
    return {
      slide: 0
    }
  }
}
</script>
