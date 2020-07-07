<template>
  <div>    
    <Header />

    <div class="contact-wrap">
      <b-container>
        <b-row>
          <b-col md="7">
            <div class="info">
              <h4>Contact Us</h4>
              <p>
                Telp: (021) 864 9905 <br/>
                E-mail: detadecon94@yahoo.com 
              </p>
            </div>
            <div class="info">
              <h4>Visit</h4>
              <p>
                Perkantoran Pondok Kelapa Blok C No. 1<br/>
                Jl. Pondok Kelapa Raya, Duren Sawit,<br/>
                Jakarta – 13450, Indonesia.
              </p>
            </div>
            <div class="info">
              <h4>Follow</h4>
              <a href="https://www.facebook.com/DetaDecon/" target="_blank" class="socmed"><i class="fab fa-facebook-f"></i></a>
              <a href="https://www.linkedin.com/company/deta-decon" target="_blank" class="socmed"><i class="fab fa-linkedin-in"></i></a>
              <a href="https://www.instagram.com/deta_decon/" target="_blank" class="socmed"><i class="fab fa-instagram"></i></a>
              <a href="mailto:detadecon94@yahoo.com" class="socmed"><i class="far fa-envelope"></i></a>
            </div>
          </b-col>
          <b-col md="5">
            <div class="info">
              <h4>Maps</h4>
              
              <GmapMap
              :center="{lat:-6.237972, lng:106.934897}"
              :zoom="19"
              map-type-id="terrain"
              >
                  <GmapMarker  :position="{lat:-6.237972, lng:106.934897}"/>
              </GmapMap>
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
    }
  },
  head () {
    return {
      title: 'Deta Decon - Contact',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'description', name: 'description', content: 'PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the 26-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. ' },
        { hid: 'og:title', name: 'og:title', content: 'Deta Decon - Contact' },
        { hid: 'keywords', name: 'keywords', content: 'Deta Decon, PT Deta Decon, Deta, Decon, Construction, Civil, Indonesia'},
        { hid: 'og:description', name: 'og:description', content: 'PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the 26-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. ' },
      ]
    }
  },
}
</script>
