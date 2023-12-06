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
                    <div
                      class="img"
                      :style="{ backgroundImage: 'url(' + data.img + ')' }"
                    ></div>
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
import Header from "~/components/Header.vue";
import Footer from "~/components/Footer.vue";

export default {
  components: {
    Header,
    Footer
  },
  data() {
    return {
      awards: [
        {
          id: 16,
          img:
            "https://cdn.rri.co.id/berita/13/images/1695205682852-2/1695205682852-2.jpeg",
          title:
            "Pembangunan Pasar Raya Fase VII Ditargetkan Tuntas Juli 2024",
          text:
            "Perkembangan pembangunan gedung Pasar Raya Fase VII Kota Padang telah mencapai 7,3 persen. Pembangunan ditargetkan tuntas pada Juli 2024 ...",
          link:
            "https://www.rri.co.id/padang/daerah/366722/pembangunan-pasar-raya-fase-vii-ditargetkan-tuntas-juli-2024?utm_source=news_main&utm_medium=internal_link&utm_campaign=general_campaign"
        },
        {
          id: 16,
          img:
            "https://asset.kompas.com/crops/3wxcRo2YnLvIHgbSpL4gZ6Xy8gs=/143x0:1493x900/750x500/data/photo/2023/06/09/648310c4766a5.jpeg",
          title:
            "Topping Off, Tim SFD UNJ Usung Konsep 'Smart and Green Building' untuk UNJ Phase-2",
          text:
            "Universitas Negeri Jakarta (UNJ) menjadi salah satu perguruan tinggi negeri yang mendapatkan pinjaman Pemerintah Kerajaan Saudi Arabia melalui Saudi Fund for Development (SFD) ...",
          link:
            "https://www.kompas.com/edu/read/2023/06/09/210000671/topping-off-tim-sfd-unj-usung-konsep-smart-and-green-building-untuk-unj"
        },
        {
          id: 14,
          img:
            "https://static.republika.co.id/uploads/images/inpicture_slide/universitas-negeri-jakarta-unj-mendapatkan-kunjungan-dari-pemerintah_220314194841-851.jpeg",
          title:
            "Bangun Fasilitas Kampus, UNJ Jalin Kerja Sama dengan Pemerintah Saudi",
          text:
            "Universitas Negeri Jakarta (UNJ) mendapatkan kunjungan dari Pemerintah Kerajaan Saudi Arabia terkait The Development and ...",
          link:
            "https://republika.co.id/berita/r8qjlm291/bangun-fasilitas-kampus-unj-jalin-kerja-sama-dengan-pemerintah-saudi"
        },
        {
          id: 13,
          img:
            "https://beritabeta.com/storage/img/2020/09/polda-maluku-ok-19686.jpg",
          title: "Pembangunan Gedung Polda Maluku Telan Dana Rp 172 Miliar",
          text:
            "Gedung baru Polda Maluku mulai dibangun  oleh PT Adhikarya  Beyond Cunstruction. Pembangunan gedung yang berlokasi  di Tantui ...",
          link:
            "https://beritabeta.com/pembangunan-gedung-polda-maluku-telan-dana-rp-172-miliar"
        },
        {
          id: 12,
          img:
            "http://lassernewstoday.com/wp-content/uploads/2020/09/IMG_20200918_202933_469-1024x576.jpg",
          title: "Gubernur Hadiri Pemancangan Tiang Kantor Polda Maluku",
          text:
            "Gubernur Maluku, Murad Ismail, Jumat (18/09/2020) menghadiri acara pemancangan tiang pertama pembangunan konstruksi gedung ...",
          link:
            "http://lassernewstoday.com/berita/nasional/gubernur-hadiri-pemancangan-tiang-kantor-polda-maluku/"
        },
        {
          id: 11,
          img:
            "https://cdn.medcom.id/dynamic/content/2020/06/18/1155683/2yaVXALmn6.jpg?w=1024",
          title: "Pasa Ateh Bukittinggi Dibangun dengan Konsep Green Building",
          text:
            "Kementerian Pekerjaan Umum dan Perumahan Rakyat (PUPR) telah menyelesaikan pembangunan kembali (rekonstruksi).",
          link:
            "https://www.medcom.id/properti/news-properti/eN40zV1N-pasa-ateh-bukittinggi-dibangun-dengan-konsep-green-building"
        },
        {
          id: 15,
          img:
            "https://foto.wartaekonomi.co.id/files/arsip_foto_2018_03_15/infrastruktur_2018_03_15_102135_big.webp",
          title: "Jokowi Tinjau Rusun Ponpes An-Nawawi Tanara Banten",
          text:
            "Presiden Joko Widodo didampingi Menteri Pekerjaan Umum dan Perumahan Rakyat (PUPR) Basuki Hadimuljono meninjau Rumah Susun.",
          link:
            "https://www.wartaekonomi.co.id/read173775/jokowi-tinjau-rusun-ponpes-an-nawawi-tanara-banten"
        },
        {
          id: 1,
          img:
            "https://cdn1.katadata.co.id/media/images/temp/2018/01/17/2018_01_17-10_01_00_abe0245fd667d43642de627b52e98c92.jpg",
          title: "Wajah Baru Gelora Bung Karno",
          text:
            "Sementara konsultan manajemen konstruksi adalah PT Deta Decon dan PT Multi Karadiguna Jasa dengan nilai kontrak Rp 10,2 miliar.",
          link:
            "https://katadata.co.id/infografik/2018/01/17/wajah-baru-gelora-bung-karno"
        },
        {
          id: 9,
          img:
            "https://www.indopos.co.id/wp-content/uploads/2022/03/Agus-Harimurti-Yudhoyono-750x375.jpg",
          title: "Presiden Jokowi Tinjau Rusun Ponpes An-Nawawi Tanara Banten",
          text:
            "Presiden Joko Widodo didampingi Menteri Pekerjaan Umum dan Perumahan Rakyat (PUPR) Basuki Hadimuljono meninjau Rumah Susun ...",
          link:
            "https://indopos.co.id/read/2018/03/14/131130/presiden-jokowi-tinjau-rusun-ponpes-an-nawawi-tanara-banten/"
        },
        {
          id: 3,
          img:
            "https://static.republika.co.id/uploads/images/inpicture_slide/dirjen-pendidikan-islam-kamaruddin-amin-_141222133638-623.jpg",
          title: "IsDB Biayai Pembangunan 4 Kampus PTKIN pada 2017",
          text:
            "Konsultasn PT Deta Decon akan menangani paket 1 dan paket 2 di UIN Sumatera Utara dan Raden Fatah Palembang. PT Ciriajasa Cipta ...",
          link:
            "https://www.republika.co.id/berita/pendidikan/dunia-kampus/16/11/23/oh3d9e396-isdb-biayai-pembangunan-4-kampus-ptkin-pada-2017"
        },
        {
          id: 5,
          img:
            "http://lombokita.com/wp-content/uploads/2017/07/wisma-atlet-kemayoran.jpg",
          title: "Pemerintah Optimistis Wisma Atlet Selesai 2017",
          text:
            "Lalu Konsultan Manajemen Konstruksi untuk C2 adalah PT Yodya Karya dan untuk D10 adalah PT Bina Karya, PT Deta Decon dan PT ...",
          link:
            "http://lombokita.com/pemerintah-optimistis-wisma-atlet-selesai-2017/"
        },
        {
          id: 10,
          img:
            "https://img.okeinfo.net/content/2017/10/18/43/1797588/selain-museum-olahraga-ini-fasilitas-lain-yang-ditawarkan-stadion-utama-gelora-bung-karno-pVYDSgIAsJ.jpg",
          title:
            "Dilengkapi Fasilitas Canggih, Kemegahan SUGBK Angkat Citra Bangsa",
          text:
            "Stadion Utama Gelora Bung Karno (SUGBK) terus berpacu dengan waktu demi tampil cantik pada Asian Games 2018. Ajang olahraga ...",
          link:
            "https://sports.sindonews.com/berita/1249384/51/dilengkapi-fasilitas-canggih-kemegahan-sugbk-angkat-citra-bangsa"
        },
        {
          id: 6,
          img:
            "https://asset.kompas.com/data/photo/2016/08/29/1607445Preview-Renovasi-GBK780x390.jpg",
          title: "Menanti Wajah Baru Kompleks Gelora Bung Karno Senayan",
          text:
            "Dalam rangka menyukseskan perhelatan Asian Games 2018 di Jakarta dan Palembang, sejumlah proyek pembangunan fasilitas utama ...",
          link:
            "https://properti.kompas.com/read/2016/08/29/070000521/menanti.wajah.baru.kompleks.gelora.bung.karno.senayan?page=all"
        },
        {
          id: 7,
          img:
            "https://asset.kompas.com/data/photo/2016/07/28/1445225logo21780x390.jpg",
          title: "Pembangunan Wisma Atlet Kemayoran Masih 11 Persen",
          text:
            "ementerian Pekerjaan Umum dan Perumahan Rakyat (PUPR) merilis progres pembangunan Wisma Atlet Kemayoran, Jakarta Pusat ...",
          link:
            "https://properti.kompas.com/read/2016/08/10/220000721/Pembangunan.Wisma.Atlet.Kemayoran.Masih.11.Persen."
        },
        {
          id: 8,
          img:
            "https://images.solopos.com/2016/11/Ilustrasi-kampus-Universitas-Islam-Negeri-UIN-Walisongo.-walisongo.ac_.id_.jpg",
          title:
            "KAMPUS DI SEMARANG : Kontrak Pembangunan UIN Semarang Ditandatangani, Terealisasi 2017?",
          text:
            "Proyek pembangunan empat kampus Perguruan Tinggi Keagamaan Islam Negeri (PTKIN) di lingkungan Kementerian Agama (Kemenag) ...",
          link:
            "https://www.solopos.com/kampus-di-semarang-kontrak-pembangunan-uin-semarang-ditandatangani-terealisasi-2017-771491"
        },
        {
          id: 2,
          img:
            "https://img-k.okeinfo.net/content/2016/08/15/470/1464327/renovasi-gbk-kementerian-pupr-gandeng-9-perusahaan-konstruksi-fMsqqD3Bou.jpg",
          title:
            "Renovasi GBK, Kementerian PUPR Gandeng 9 Perusahaan Konstruksi",
          text:
            "Stadion Utama GBK oleh PT Deta Decon Rp9,5 miliar, Stadion Renang Aquatic PT Sangkuriang dengan nilai kontrak Rp4 miliar, ...",
          link:
            "https://economy.okezone.com/read/2016/08/15/470/1464327/renovasi-gbk-kementerian-pupr-gandeng-9-perusahaan-konstruksi"
        }
      ]
    };
  },
  head() {
    return {
      title: "Deta Decon - Press",
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: "description",
          name: "description",
          content:
            `PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the ${new Date().getFullYear() - 1994 }-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. `
        },
        { hid: "og:title", name: "og:title", content: "Deta Decon - Press" },
        {
          hid: "keywords",
          name: "keywords",
          content:
            "Deta Decon, PT Deta Decon, Deta, Decon, Construction, Civil, Indonesia"
        },
        {
          hid: "og:description",
          name: "og:description",
          content:
            `PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the ${new Date().getFullYear() - 1994 }-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. `
        }
      ]
    };
  }
};
</script>
