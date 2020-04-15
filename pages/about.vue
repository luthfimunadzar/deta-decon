<template>
  <div>    
    <Header />

    <div class="about-wrap">
      <b-container>
        <b-row>
          <b-col md="12" lg="7">
            <div class="info">
              <h4>Board</h4>

              <div class="board-item">
                <span class="image" style="background-image: url('/profile.png')"></span>
                <div class="text">
                  <h5>Ir. Chairul Basri Nasution</h5>
                  <h6>Direktur Utama</h6>
                </div>
              </div>
              <div class="board-item">
                <span class="image" style="background-image: url('/profile.png')"></span>
                <div class="text">
                  <h5>Ir. Mardiana Daoed</h5>
                  <h6>Direktur</h6>
                </div>
              </div>
              <div class="board-item">
                <span class="image" style="background-image: url('/profile.png')"></span>
                <div class="text">
                  <h5>Ade Nurul Safrina, SE, MSc</h5>
                  <h6>Komisaris</h6>
                </div>
              </div>
            </div>
            <div class="info">
              <h4>Profile</h4>
              <p>
                “Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
              </p>
            </div>
          </b-col>
          <b-col md="12" lg="5">
            <div class="info">
              <h4>Organization Charts</h4>
              
              <div class="charts">
                <b-row>
                  <b-col md="12">
                    <div class="name">
                      <div>
                        <h5>DIREKTUR UTAMA</h5>
                        <h6>Ir. Chairul Basri Nasution</h6>
                      </div>
                    </div>
                  </b-col>
                  <b-col md="12" class="text-center">
                    <img src="/struktur-1.png" alt="" class="tri-branch">
                  </b-col>
                  <b-col col="4">
                    <div class="name small">
                      <div>
                        <h5>DIREKTUR TEKNIS</h5>
                        <h6>Ir. Mardiana Daoed</h6>
                      </div>
                    </div>
                  </b-col>
                  <b-col col="4">
                    <div class="name small">
                      <div>
                        <h5>DIREKTUR PENGEMBANGAN BISNIS & INVESTASI</h5>
                        <h6>Satrio Rama Widyowicaksono S.Ip MSc</h6>
                      </div>
                    </div>
                  </b-col>
                  <b-col col="4">
                    <div class="name small">
                      <div>
                        <h5>DIREKTUR KEUANGAN</h5>
                        <h6>Ade Nurul Safrina SE MSc</h6>
                      </div>
                    </div>
                  </b-col>
                </b-row>
                <b-row>
                  <b-col col="4">
                    <div class="div-wrap tre">
                      <h4 class="div-item">Divisi Penelitian & Pengkajian Teknis</h4>
                      <h4 class="div-item">Divisi Perancangan & Perencanaan</h4>
                      <h4 class="div-item">Divisi Pengawasan & Manajemen Konstruksi</h4>
                    </div>
                  </b-col>
                  <b-col col="4">
                    <div class="div-wrap">
                      <h4 class="div-item">Divisi Pengembangan Bisnis</h4>
                      <h4 class="div-item">Divisi Pelelangan & Kontrak</h4>
                    </div>
                  </b-col>
                  <b-col col="4">
                    <div class="div-wrap">
                      <h4 class="div-item">Divisi Umum & Sumber Daya Manusia</h4>
                      <h4 class="div-item">Divisi Administrasi & Keuangan</h4>
                    </div>
                  </b-col>
                </b-row>
              </div>
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
