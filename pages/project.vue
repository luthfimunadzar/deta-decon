<template>
  <div>
    <Header />

    <div class="opt-project">
      <b-container>
        <b-row>
          <b-col>
            <div class="title">
              Project Section
            </div>
            <div class="dropdown-group">
              <b-dropdown right>
                <template v-slot:button-content>
                  <span class="d-md-block d-none"
                    >Investigation, Building <br />Audits, Renovation</span
                  >
                  <span class="d-md-none d-block"
                    >Investigation, Building Audits, Renovation</span
                  >
                </template>
                <b-dropdown-item @click="filtered('Structure Investigation')"
                  >Structure Investigation</b-dropdown-item
                >
                <b-dropdown-item @click="filtered('Building Audit')"
                  >Building Audit</b-dropdown-item
                >
                <b-dropdown-item
                  @click="filtered('Structure Strengthening & Renovation')"
                  >Structure Strengthening & Renovation</b-dropdown-item
                >
              </b-dropdown>
              <b-dropdown right>
                <template v-slot:button-content>
                  <span class="d-md-block d-none"
                    >Supervision and<br />Construction Management</span
                  >
                  <span class="d-md-none d-block"
                    >Supervision and Construction Management</span
                  >
                </template>
                <b-dropdown-item
                  @click="
                    filtered('Project Management & Supervision Consultant')
                  "
                  >Project Management & Supervision Consultant</b-dropdown-item
                >
                <b-dropdown-item @click="filtered('Construction Management')"
                  >Construction Management</b-dropdown-item
                >
                <b-dropdown-item @click="filtered('Supervision Consultant')"
                  >Supervision Consultant</b-dropdown-item
                >
              </b-dropdown>
              <b-dropdown right>
                <template v-slot:button-content>
                  <span class="d-md-block d-none"
                    >Architecture Planning<br />and Design</span
                  >
                  <span class="d-md-none d-block"
                    >Architecture Planning and Design</span
                  >
                </template>
                <b-dropdown-item @click="filtered('Detail Engineering Design')"
                  >Detail Engineering Design</b-dropdown-item
                >
                <b-dropdown-item @click="filtered('Architecture Design')"
                  >Architecture Design</b-dropdown-item
                >
                <b-dropdown-item @click="filtered('Structure Design')"
                  >Structure Design</b-dropdown-item
                >
                <b-dropdown-item
                  @click="
                    filtered('Mechanical, Electrical and Plumbing Design')
                  "
                  >Mechanical, Electrical and Plumbing Design</b-dropdown-item
                >
              </b-dropdown>
            </div>
          </b-col>
        </b-row>
      </b-container>
    </div>

    <b-container>
      <b-row>
        <b-col md="4">
          <iframe
            src="https://www.youtube.com/embed/B8suluOznjU"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
            class="video-project"
          ></iframe>
        </b-col>
        <b-col md="4">
          <iframe
            src="https://www.youtube.com/embed/BqaUuCYlsJQ"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
            class="video-project"
          ></iframe>
        </b-col>
        <b-col md="4">
          <iframe
            src="https://www.youtube.com/embed/AjWVhnk0-2w"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
            class="video-project"
          ></iframe>
        </b-col>
      </b-row>
    </b-container>

    <div class="search">
      <b-container>
        <b-row>
          <b-col>
            <b-form inline class="form-search" @submit.prevent="formSearch()">
              <label for="" class="mr-3">Filter Project</label>
              <b-form-input
                v-model="search"
                placeholder="Cari Berdasarkan Nama Project"
              ></b-form-input>
              <b-button variant="primary" type="submit">Cari</b-button>
            </b-form>
          </b-col>
        </b-row>
      </b-container>
    </div>

    <div class="project-wrap">
      <b-container>
        <b-row v-if="dataShow.length != 0">
          <b-col md="4" sm="6" v-for="data in dataShow" :key="data.id">
            <div
              class="image"
              :style="{ backgroundImage: 'url(' + data.img + ')' }"
              @click="openGallery(data.id)"
            >
              <div class="wrap">
                <span>{{ data.year }}</span>
                <h5>{{ data.nama }}</h5>
                <h6>{{ data.cat }}</h6>
              </div>
            </div>
          </b-col>
        </b-row>
        <b-row v-else>
          <b-col class="text-center">
            <h5 class="mb-0">
              Hasil Pencarian "{{ this.keyword }}" Tidak Ditemukan
            </h5>
          </b-col>
        </b-row>
      </b-container>
    </div>

    <Footer />

    <client-only>
      <light-box
        ref="lightbox"
        :media="image"
        :show-caption="true"
        :show-light-box="false"
        :show-thumbs="false"
      />
    </client-only>
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
      dataShow: [],
      keyword: "",
      image: [
        {
          thumb: "",
          src: "",
          caption: ""
        }
      ],
      dataProject: [
        // old
        {
          id: 75,
          nama: "Tugu Nol Kalimantan",
          year: "2023",
          cat: "Detail Engineering Design, Architecture Design, Structure Design, Mechanical, Electrical and Plumbing Design",
          img: "/project-75.jpeg"
        },
        {
          id: 74,
          nama: "Rumah Sakit Umum Persahabatan Rawamangun Jakarta Timur",
          year: "2023",
          cat: "Detail Engineering Design, Architecture Design, Structure Design, Mechanical, Electrical and Plumbing Design",
          img: "/project-74.jpeg"
        },
        {
          id: 73,
          nama: "Rumah Susun ASN, Ibu Kota Nusantara",
          year: "2023",
          cat: "Detail Engineering Design, Architecture Design, Structure Design, Mechanical, Electrical and Plumbing Design",
          img: "/project-73.jpeg"
        },
        {
          id: 72,
          nama: "Universitas Negeri Jakarta",
          year: "2022",
          cat: "Project Management & Supervision Consultant",
          img: "/project-72.jpg"
        },
        {
          id: 71,
          nama: "Rumah Sakit Pelni",
          year: "2022",
          cat: "Architecture Design",
          img: "/project-71.jpeg"
        },
        {
          id: 1,
          nama: "Gelora Bung Karno (GBK)",
          year: "2017-2018",
          cat: "Construction Management",
          img: "/project-1.jpg"
        },
        {
          id: 2,
          nama: "Athlete Villages Kemayoran",
          year: "2017-2018",
          cat: "Construction Management",
          img: "/project-2.jpg"
        },
        {
          id: 3,
          nama: "Islamic University of Sultan Syarif Kasim",
          year: "2006-2008",
          cat: "Project Management & Supervision Consultant",
          img: "/project-3.jpg"
        },
        {
          id: 4,
          nama: "UIN Raden Fatah Palembang",
          year: "2017-2020",
          cat: "Project Management & Supervision Consultant",
          img: "/project-4.jpg"
        },
        {
          id: 5,
          nama: "UIN Sumatera Utara",
          year: "2017-2020",
          cat: "Project Management & Supervision Consultant",
          img: "/project-5.jpg"
        },
        {
          id: 6,
          nama: "UIN Sunan Ampel",
          year: "2013-2015",
          cat: "Project Management & Supervision Consultant",
          img: "/project-6.jpg"
        },
        {
          id: 7,
          nama: "UIN Sultan Taha Jambi",
          year: "2018",
          cat: "Detail Engineering Design",
          img: "/project-7.jpg"
        },
        {
          id: 8,
          nama: "KOPEBI Building, Bank Indonesia",
          year: "2008",
          cat: "Detail Engineering Design",
          img: "/project-8.jpg"
        },
        {
          id: 9,
          nama: "Islamic Development Center",
          year: "2010-2011",
          cat: "Supervision Consultant",
          img: "/project-9.jpg"
        },
        {
          id: 10,
          nama: "Semarang State University",
          year: "2013",
          cat: "Detail Engineering Design",
          img: "/project-10.jpg"
        },
        {
          id: 11,
          nama: "State Islamic University Of Sunan Gunung Djati Bandung",
          year: "2010",
          cat: "Detail Engineering Design",
          img: "/project-11.jpg"
        },
        {
          id: 12,
          nama: "University of Alauddin Makassar",
          year: "2007-2008",
          cat: "Detail Engineering Design",
          img: "/project-12.jpg"
        },
        {
          id: 13,
          nama: "STAIN Malang Project",
          year: "2005",
          cat: "Detail Engineering Design",
          img: "/project-13.jpg"
        },
        {
          id: 14,
          nama:
            "Auditorium/Multipurpose Building of The State University of Gorontalo",
          year: "2011",
          cat: "Detail Engineering Design",
          img: "/project-14.jpg"
        },
        {
          id: 15,
          nama: "Islamic Centre Jakarta",
          year: "2005, 2006, 2007",
          cat: "Detail Engineering Design",
          img: "/project-15.jpg"
        },
        {
          id: 16,
          nama: "Menteng Park, Central Jakarta",
          year: "2006",
          cat: "Detail Engineering Design",
          img: "/project-16.jpg"
        },
        {
          id: 17,
          nama:
            "Training Centre (Pusdiklat Pajak), Ministry of Finance Republic of Indonesia",
          year: "2014",
          cat: "Detail Engineering Design",
          img: "/project-17.jpg"
        },
        {
          id: 18,
          nama: "Hotel Grandhika Iskandarsyah",
          year: "2013-2014",
          cat: "Construction Management",
          img: "/project-18.jpg"
        },
        {
          id: 19,
          nama: "Class III Hospital Building, RSUD Arifin Achmad",
          year: "2013",
          cat: "Construction Management",
          img: "/project-19.jpg"
        },
        {
          id: 20,
          nama: "Annex Building Renovation Project and Mosque PT. ASKES",
          year: "2010",
          cat: "Construction Management",
          img: "/project-20.jpg"
        },
        {
          id: 21,
          nama:
            "Regional Office, Directorate General of Customs and Excise, Ministry of Finance Republic of Indonesia",
          year: "2010",
          cat: "Construction Management",
          img: "/project-21.jpg"
        },
        {
          id: 22,
          nama: "PPM Building",
          year: "2009-2010",
          cat: "Construction Management",
          img: "/project-22.jpg"
        },
        {
          id: 23,
          nama: "Madrasa International Indramayu",
          year: "2009",
          cat: "Construction Management",
          img: "/project-23.jpg"
        },
        {
          id: 24,
          nama: "East Jakarta Mayor Office",
          year: "2007-2009",
          cat: "Construction Management",
          img: "/project-24.jpeg"
        },
        {
          id: 25,
          nama: "Riau Main Stadium",
          year: "2008",
          cat: "Construction Management",
          img: "/project-25.jpg"
        },
        {
          id: 26,
          nama:
            "Simple Flats in 26 Locations spread across Sumatra, Java, Kalimantan and Sulawesi",
          year: "2007-2008",
          cat: "Construction Management",
          img: "/project-26.jpg"
        },
        {
          id: 27,
          nama: "Simple Flats (Rusunawa) and PSD Marunda, DKI Jakarta",
          year: "2004-2006",
          cat: "Construction Management",
          img: "/project-27.jpg"
        },
        {
          id: 28,
          nama:
            "JFA Puskin Building Puslitbang, Pusinfowas, Representative of BPKP DKI II and Inspectorate",
          year: "2003-2007",
          cat: "Construction Management",
          img: "/project-28.jpg"
        },
        {
          id: 29,
          nama: "Blok G Building as a Green Building",
          year: "2011",
          cat: "Construction Management",
          img: "/project-29.jpg"
        },
        {
          id: 30,
          nama: "Marunda Cluster B Block I and II",
          year: "2009",
          cat: "Construction Management",
          img: "/project-30.jpg"
        },
        {
          id: 31,
          nama:
            "Regional Office of DPJ in South Sumatra and the Bangka Belitung Islands and the Tax Service Office",
          year: "2007-2008",
          cat: "Construction Management",
          img: "/project-31.jpg"
        },
        {
          id: 32,
          nama: "DKI Jakarta Provincial Archives Building",
          year: "2004-2006",
          cat: "Construction Management",
          img: "/project-32.jpg"
        },
        {
          id: 33,
          nama: "Budhi Asih Hospital Building Jakarta",
          year: "2003-2005",
          cat: "Construction Management",
          img: "/project-33.jpg"
        },
        {
          id: 34,
          nama: "Sarinah Building Jakarta",
          year: "2004-2005",
          cat: "Structure Investigation, Structure Strengthening & Renovation",
          img: "/project-34.jpg"
        },
        {
          id: 35,
          nama: "The State University of Jakarta (UNJ)",
          year: "2011-2013",
          cat: "Project Management & Supervision Consultant",
          img: "/project-35.jpg"
        },
        {
          id: 36,
          nama: "Riau Province Development Office",
          year: "2012-2013",
          cat: "Project Management & Supervision Consultant",
          img: "/project-36.jpg"
        },
        {
          id: 37,
          nama: "Rusunawa Supervision Development Work - 2 (PP10-17)",
          year: "2010-2011",
          cat: "Supervision Consultant",
          img: "/project-37.jpg"
        },
        {
          id: 38,
          nama: "Arcadia Apartment and Office Buildings.",
          year: "2008",
          cat: "Building Audit",
          img: "/project-38.jpg"
        },
        {
          id: 39,
          nama: "MAPOLDA SUMBAR Building",
          year: "2012",
          cat: "Detail Engineering Design",
          img: "/project-39.jpg"
        },
        {
          id: 40,
          nama: "Rental Flats Based on Prototype T-24 (90 TB)",
          year: "2011",
          cat: "Detail Engineering Design",
          img: "/project-40.jpg"
        },
        {
          id: 41,
          nama: "Rusunawa-Based Prototype T - 24 in 43 Locations",
          year: "2010",
          cat: "Detail Engineering Design",
          img: "/project-41.jpg"
        },
        {
          id: 42,
          nama:
            'Building Process Renovation Advanced Stage, Archives, Telematics, Supporting, Main PPPTMGB "LEMIGAS"',
          year: "2007",
          cat: "Detail Engineering Design",
          img: "/project-42.jpg"
        },
        {
          id: 43,
          nama: "Simple Flats in the University of Muhammadiyah Surakarta",
          year: "2007",
          cat: "Detail Engineering Design",
          img: "/project-43.jpg"
        },
        {
          id: 44,
          nama: "Low-Cost Rental Apartments (rusunawa) in Bandung",
          year: "2006",
          cat: "Detail Engineering Design",
          img: "/project-44.jpg"
        },
        {
          id: 45,
          nama:
            "The Construction and Equipment of Two Orphan Centers in Aceh Province, Indonesia (Ind 103a-SCC 0001)",
          year: "2006",
          cat: "Detail Engineering Design",
          img: "/project-45.jpg"
        },
        {
          id: 46,
          nama: "UNPAD Rusunawa Development Location of Sumedang Regency",
          year: "2006",
          cat: "Detail Engineering Design",
          img: "/project-46.jpg"
        },
        {
          id: 47,
          nama: "Cipayung High Level Flat",
          year: "2006",
          cat: "Detail Engineering Design",
          img: "/project-47.jpg"
        },
        {
          id: 48,
          nama: "Pasar Atas Bukit Tinggi",
          year: "2018-2019",
          cat: "Supervision and Construction Management",
          img: "/project-48.jpg"
        },
        {
          id: 49,
          nama: "RUSUN MK Sumatra Region 3",
          year: "2016",
          cat: "Supervision and Construction Management",
          img: "/project-49.jpg"
        },
        {
          id: 50,
          nama: "RUSUN MK, West Java Region",
          year: "2017",
          cat: "Supervision and Construction Management",
          img: "/project-50.jpg"
        },
        {
          id: 51,
          nama: "Faculty of Economics and Islamic Business IAIN Batusangkar",
          year: "2017",
          cat: "Construction Management",
          img: "/project-51.jpg"
        },
        {
          id: 52,
          nama: "RUSUNAMI Sukaramai Medan",
          year: "2016",
          cat: "Construction Management",
          img: "/project-52.jpg"
        },
        {
          id: 53,
          nama: "Public Flat, Jakabaring Palembang",
          year: "2016",
          cat: "Supervision and Construction Management",
          img: "/project-53.jpg"
        },
        {
          id: 54,
          nama: "Universitas Tanjungpura Pontianak (UNTAN)",
          year: "2017-2018",
          cat: "Project Management & Supervision Consultant",
          img: "/project-54.jpg"
        },
        {
          id: 55,
          nama: "Universitas Lambung Mangkurat Banjarmasin (UNLAM)",
          year: "2017-2018",
          cat: "Project Management & Supervision Consultant",
          img: "/project-55.jpg"
        },
        {
          id: 56,
          nama: "Gedung A, B and Graha PGAS - Head Office",
          year: "2017-2018",
          cat: "Building Audit",
          img: "/project-56.jpg"
        },
        {
          id: 57,
          nama: "PT. Sarinah (Persero)",
          year: "2017-2018",
          cat: "Supervision Consultant",
          img: "/project-57.jpg"
        },
        {
          id: 58,
          nama: "Rusunami Kalimas Residence",
          year: "2015-2016",
          cat:
            "Architecture Design, Structure Design, Mechanical, Electrical and Plumbing Design",
          img: "/project-58.jpg"
        },
        {
          id: 59,
          nama: "Tax Court Secretariat Office",
          year: "2012",
          cat:
            "Architecture Design, Structure Design, Mechanical, Electrical and Plumbing Design",
          img: "/project-59.jpg"
        },
        {
          id: 60,
          nama: "Riau Province Ipdn Campus Building In Rokan Hilir District",
          year: "2010-2011",
          cat:
            "Architecture Design, Structure Design, Mechanical, Electrical and Plumbing Design",
          img: "/project-60.jpg"
        },
        {
          id: 61,
          nama: "District Hospital Sungai Dareh",
          year: "2010",
          cat:
            "Architecture Design, Structure Design, Mechanical, Electrical and Plumbing Design",
          img: "/project-61.jpg"
        },
        {
          id: 62,
          nama: "Muhammadiyah Hospital in Jakarta",
          year: "2009",
          cat:
            "Architecture Design, Structure Design, Mechanical, Electrical and Plumbing Design",
          img: "/project-62.jpg"
        },
        {
          id: 63,
          nama: "General Hospital of Gandul Medika",
          year: "2008",
          cat:
            "Architecture Design, Structure Design, Mechanical, Electrical and Plumbing Design",
          img: "/project-63.jpg"
        },
        {
          id: 64,
          nama: "Sports Stadium, East Lampung",
          year: "2008",
          cat:
            "Architecture Design, Structure Design, Mechanical, Electrical and Plumbing Design",
          img: "/project-64.jpg"
        },
        {
          id: 65,
          nama:
            "Office Building for the Republic of Indonesia State Code Agency",
          year: "2007",
          cat:
            "Architecture Design, Structure Design, Mechanical, Electrical and Plumbing Design",
          img: "/project-65.jpg"
        },
        {
          id: 66,
          nama: "Jayapura State Government Building (GKN)",
          year: "2019",
          cat: "Structure Design",
          img: "/project-66.jpg"
        },
        {
          id: 67,
          nama: "Pasar Atas Bukit Tinggi",
          year: "2019",
          cat: "Construction Management",
          img: "/project-67.jpg"
        },
        {
          id: 68,
          nama: "UIN Sumatera Utara Medan",
          year: "2020",
          cat: "Project Management & Supervision Consultant",
          img: "/project-68.jpeg"
        },
        {
          id: 69,
          nama: "Rumah Susun Pasar Jumat",
          year: "2018-2020",
          cat: "Construction Management",
          img: "/project-69.jpg"
        },
        {
          id: 70,
          nama: "Polda Maluku",
          year: "2020",
          cat: "Construction Management",
          img: "/project-70.jpeg"
        }
      ],
      search: ""
    };
  },
  created() {
    this.dataShow = this.dataProject;
  },
  methods: {
    filtered(params) {
      let tempFiltered = this.dataProject.filter(e =>
        e.cat.toLowerCase().includes(params.toLowerCase())
      );
      this.keyword = params;

      this.dataShow = tempFiltered;
    },
    formSearch() {
      this.keyword = this.search;
      let tempSearch = this.dataProject.filter(obj =>
        obj.nama.toLowerCase().includes(this.search.toLowerCase())
      );

      this.dataShow = tempSearch;
    },
    openGallery(params) {
      let tempImage = this.dataProject.filter(obj => obj.id === params);

      this.image[0].thumb = tempImage[0].img;
      this.image[0].src = tempImage[0].img;
      this.image[0].caption =
        tempImage[0].year +
        " " +
        tempImage[0].nama +
        "<br/>" +
        tempImage[0].cat;
      this.$refs.lightbox.showImage(0);
    }
  },
  head() {
    return {
      title: "Deta Decon - Project",
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: "description",
          name: "description",
          content:
            `PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the ${new Date().getFullYear() - 1994 }-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. `
        },
        { hid: "og:title", name: "og:title", content: "Deta Decon - Project" },
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
