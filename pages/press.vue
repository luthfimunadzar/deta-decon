<template>
  <div>    
    <Header />

    <div class="about-wrap">
      <b-container>
        <b-row>
          <b-col lg="12">
            <div class="info">
              <h4>Press</h4>

              <div class="awards-item" v-for="data in awards" :key="data.id">
                <b-row>
                  <b-col md="3">
                    <div class="img" :style="{ backgroundImage: 'url(' + data.img + ')'}"></div>
                  </b-col>
                  <b-col md="9" class="d-flex align-items-center">
                    <div class="wrap">
                      <h5>{{ data.title }}</h5>
                      <p>{{ data.text }}</p>
                      <a :href="data.link" target="_blank">Read More</a>
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
      awards: [
        {
          id: 1,
          img: 'https://cdn1.katadata.co.id/media/images/temp/2018/01/17/2018_01_17-10_01_00_abe0245fd667d43642de627b52e98c92.jpg',
          title: 'Wajah Baru Gelora Bung Karno',
          text: 'Sementara konsultan manajemen konstruksi adalah PT Deta Decon dan PT Multi Karadiguna Jasa dengan nilai kontrak Rp 10,2 miliar.',
          link: 'https://katadata.co.id/infografik/2018/01/17/wajah-baru-gelora-bung-karno'
        },
        {
          id: 2,
          img: 'https://img-k.okeinfo.net/content/2016/08/15/470/1464327/renovasi-gbk-kementerian-pupr-gandeng-9-perusahaan-konstruksi-fMsqqD3Bou.jpg',
          title: 'Renovasi GBK, Kementerian PUPR Gandeng 9 Perusahaan Konstruksi',
          text: 'Stadion Utama GBK oleh PT Deta Decon Rp9,5 miliar, Stadion Renang Aquatic PT Sangkuriang dengan nilai kontrak Rp4 miliar, ...',
          link: 'https://economy.okezone.com/read/2016/08/15/470/1464327/renovasi-gbk-kementerian-pupr-gandeng-9-perusahaan-konstruksi'
        },
        {
          id: 3,
          img: 'https://static.republika.co.id/uploads/images/inpicture_slide/dirjen-pendidikan-islam-kamaruddin-amin-_141222133638-623.jpg',
          title: 'IsDB Biayai Pembangunan 4 Kampus PTKIN pada 2017',
          text: 'Konsultasn PT Deta Decon akan menangani paket 1 dan paket 2 di UIN Sumatera Utara dan Raden Fatah Palembang. PT Ciriajasa Cipta ...',
          link: 'https://www.republika.co.id/berita/pendidikan/dunia-kampus/16/11/23/oh3d9e396-isdb-biayai-pembangunan-4-kampus-ptkin-pada-2017'
        },
        {
          id: 4,
          img: 'https://netizen.media/wp-content/uploads/2018/01/megah-nan-mewah-750x430.jpg',
          title: 'GBK Jakarta Kalahkan Stadion Wembley London',
          text: 'Sedangkan konsultan manajemen konstruksinya PT Deta Decon dan PT Multi Karadiguna Jasa KSO dengan nilai kontrak Rp10,2 Miliar ...',
          link: 'https://netizen.media/2018/01/14/gbk-jakarta-kalahkan-stadion-wembley-london/'
        },
        {
          id: 5,
          img: 'http://lombokita.com/wp-content/uploads/2017/07/wisma-atlet-kemayoran.jpg',
          title: 'Pemerintah Optimistis Wisma Atlet Selesai 2017',
          text: 'Lalu Konsultan Manajemen Konstruksi untuk C2 adalah PT Yodya Karya dan untuk D10 adalah PT Bina Karya, PT Deta Decon dan PT ...',
          link: 'http://lombokita.com/pemerintah-optimistis-wisma-atlet-selesai-2017/'
        },
      ]
    }
  },
  head () {
    return {
      title: 'Press | Deta Decon',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'description', name: 'description', content: 'PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the 26-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. ' },
        { hid: 'og:title', name: 'og:title', content: 'Deta Decon' },
        { hid: 'og:description', name: 'og:description', content: 'PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the 26-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. ' },
      ]
    }
  },
}
</script>
