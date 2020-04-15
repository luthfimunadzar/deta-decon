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
              <a href="#" class="socmed"><i class="fab fa-facebook-f"></i></a>
              <a href="#" class="socmed"><i class="fab fa-instagram"></i></a>
              <a href="#" class="socmed"><i class="fab fa-whatsapp"></i></a>
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
  }
}
</script>
