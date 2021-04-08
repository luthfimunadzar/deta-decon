<template>
  <div>
    <Header />

    <div class="about-wrap">
      <b-container>
        <b-row>
          <b-col lg="12">
            <div class="info">
              <h4>Who we are</h4>

              <p>
                We are a collective of engineers, developers, architects, and
                planners working together to build a better future. Our firm,
                Deta Decon, is responsible for some of the Indonesia's most
                technically and environmentally advanced buildings and
                significant public spaces. Through mastery in Technical
                Expertise, our firm has maintaned its well-acknowledged
                reputation by succesfully provided the structural design for
                500+ of the government buildings, airports, state / grant
                universities, schools, apartments, residences, and corporate
                buildings throughout the land of Indonesia.
              </p>
            </div>

            <div class="info">
              <h4 class="text-center red">Board of Directors</h4>

              <div class="wrap-people gray">
                <b-row class="justify-content-center">
                  <b-col
                    cols="6"
                    md="4"
                    lg="2"
                    v-for="people in bod"
                    :key="people.id"
                  >
                    <div class="board-item">
                      <span
                        class="image"
                        :style="{ backgroundImage: 'url(' + people.img + ')' }"
                      ></span>
                      <div class="text">
                        <h5>{{ people.nama }}</h5>
                        <h6>{{ people.jabatan }}</h6>
                        <!-- <span>Exp. {{ people.exp }}</span> -->
                      </div>
                    </div>
                  </b-col>
                </b-row>
              </div>

              <div class="wrap-people gray">
                <h6 class="people-divide">Technical Experts</h6>
                <b-row>
                  <b-col
                    cols="6"
                    md="4"
                    lg="2"
                    v-for="people in peoples"
                    :key="people.id"
                  >
                    <div class="board-item">
                      <span
                        class="image"
                        :style="{ backgroundImage: 'url(' + people.img + ')' }"
                      ></span>
                      <div class="text">
                        <h5>{{ people.nama }}</h5>
                        <h6>{{ people.jabatan }}</h6>
                        <span>Exp. {{ people.exp }}</span>
                      </div>
                    </div>
                  </b-col>
                </b-row>
              </div>

              <div class="wrap-people">
                <h6 class="people-divide">Finance & Administration</h6>
                <b-row>
                  <b-col
                    cols="6"
                    md="4"
                    lg="2"
                    v-for="people in finance"
                    :key="people.id"
                  >
                    <div class="board-item">
                      <span
                        class="image"
                        :style="{ backgroundImage: 'url(' + people.img + ')' }"
                      ></span>
                      <div class="text">
                        <h5>{{ people.nama }}</h5>
                        <h6>{{ people.jabatan }}</h6>
                        <span>Exp. {{ people.exp }}</span>
                      </div>
                    </div>
                  </b-col>
                </b-row>
              </div>

              <div class="wrap-people gray">
                <h6 class="people-divide">Operation and Logistics</h6>
                <b-row>
                  <b-col
                    cols="6"
                    md="4"
                    lg="2"
                    v-for="people in operation"
                    :key="people.id"
                  >
                    <div class="board-item">
                      <span
                        class="image"
                        :style="{ backgroundImage: 'url(' + people.img + ')' }"
                      ></span>
                      <div class="text">
                        <h5>{{ people.nama }}</h5>
                        <h6>{{ people.jabatan }}</h6>
                        <span>Exp. {{ people.exp }}</span>
                      </div>
                    </div>
                  </b-col>
                </b-row>
              </div>
            </div>

            <div class="info">
              <h4>In Memoriam</h4>
              <p>
                PT Deta Decon was founded in Jakarta in 1994 by Ir. Chairul
                Basri Nasution. With a portfolio spanning hundreds of projects
                across the country, Deta Decon is one of the most significant &
                highly respected construction consultant firm in Indonesia.
              </p>
              <img src="/banner-duka.jpg" class="w-100" alt="" />
            </div>

            <div class="info">
              <h4>Career</h4>
              <p>
                DetaDecon offers a rewarding career experience, a collaborative
                interdisciplinary environment, and the opportunity to work on
                some of Indonesia’s most exciting and transformative
                engineering, and planning projects.
              </p>
              <p>
                Mail to:
                <a href="mailto:detadecon94@yahoo.com">detadecon94@yahoo.com</a>
                or <a href="mailto:detadc@gmail.com">detadc@gmail.com</a>
              </p>
              <p>Subject: Name_Job Application</p>
              <p>Stay updated regarding our Job Vacancy through:</p>
              <p>
                LinkedIn Page:
                <a
                  href="https://www.linkedin.com/company/deta-decon"
                  target="_blank"
                  >https://www.linkedin.com/company/deta-decon</a
                >
              </p>
              <p>
                Facebook Page:
                <a href="https://www.facebook.com/DetaDecon/" target="_blank"
                  >https://www.facebook.com/DetaDecon/</a
                >
              </p>
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
      bod: [
        {
          id: 1,
          img: "/people2.jpg",
          nama: "Ir. Mardiana Daoed",
          jabatan: "President Director"
          // exp: "38 Years"
        },
        {
          id: 2,
          img: "/people43.png",
          nama: "Satrio Rama Widyowicaksono S.Ip., M.Sc",
          jabatan: "Managing Director"
          // exp: "40 Years"
        }
      ],
      peoples: [
        // {
        //   id: 1,
        //   img: '/people1.jpg',
        //   nama: 'Ir. Chairul Basri Nasution',
        //   jabatan: 'President Director',
        //   exp: '40 Years'
        // },
        // {
        //   id: 2,
        //   img: "/people2.jpg",
        //   nama: "Ir. Mardiana Daoed",
        //   jabatan: "Director",
        //   exp: "38 Years"
        // },
        {
          id: 19,
          img: "/people26.jpg",
          nama: "Ir. Wuryan Irianto",
          jabatan: "Head of Construction Supervision and Management",
          exp: "35 Years"
        },
        {
          id: 24,
          img: "/people40.jpeg",
          nama: "Budiyanto",
          jabatan: "Lighting and Power Installation Engineer",
          exp: "39 Years"
        },
        {
          id: 3,
          img: "/people3.jpg",
          nama: "Ir. Azwar Muchtasar",
          jabatan: "Structural Expert, Construction Management Expert",
          exp: "35 Years"
        },
        {
          id: 23,
          img: "/people39.jpeg",
          nama: "Asnawi Lubis",
          jabatan: "Network Installation Technician",
          exp: "35 Years"
        },
        {
          id: 12,
          img: "/people8.jpg",
          nama: "Ir. Fayandi Zakir",
          jabatan: "Architectural Expert",
          exp: "31 Years"
        },
        {
          id: 15,
          img: "/people16.jpeg",
          nama: "Ir. Djadjuli Hasjim",
          jabatan: "Mechanical Expert",
          exp: "30 Years"
        },
        {
          id: 4,
          img: "/people6.jpg",
          nama: "Ir. Sudiro",
          jabatan: "Estimator Expert",
          exp: "30 Years"
        },
        {
          id: 5,
          img: "/people5.jpg",
          nama: "Ir. Farida Ansuria",
          jabatan: "Structural Expert",
          exp: "27 Years"
        },
        {
          id: 7,
          img: "/people12.jpg",
          nama: "Ir. Endang Mahyudin",
          jabatan: "Structural Expert",
          exp: "26 Years"
        },
        {
          id: 6,
          img: "/people9.jpg",
          nama: "Ir. Yusuf Munawar",
          jabatan: "Construction Management experts",
          exp: "25 Years"
        },
        {
          id: 13,
          img: "/people4.jpg",
          nama: "Ir. Devy Kartika",
          jabatan: "Architectural Expert",
          exp: "25 Years"
        },
        {
          id: 8,
          img: "/people11.jpg",
          nama: "Ir. Wahyu Raharjo",
          jabatan: "Quality Management experts",
          exp: "21 Years"
        },
        {
          id: 9,
          img: "/people13.jpg",
          nama: "Ir. Andy Arman",
          jabatan: "Structural Expert",
          exp: "19 Years"
        },
        {
          id: 10,
          img: "/people14.jpg",
          nama: "Ir. Nugroho Budianto",
          jabatan: "Structural Expert",
          exp: "18 Years"
        },
        {
          id: 16,
          img: "/people10.jpg",
          nama: "Ir. Rois",
          jabatan: "Electrical Expert",
          exp: "18 Years"
        },
        {
          id: 14,
          img: "/people17.jpg",
          nama: "Ir. Irawan Saleh",
          jabatan: "Architectural Expert",
          exp: "13 Years"
        },
        {
          id: 25,
          img: "/people41.jpeg",
          nama: "Fauzzul Musamma ST.",
          jabatan: "Occupational Safety & Health ",
          exp: "11 Years"
        },
        {
          id: 11,
          img: "/people15.jpg",
          nama: "Ir. Aiman Purohito",
          jabatan: "Structural Expert",
          exp: "11 Years"
        },
        {
          id: 17,
          img: "/people18.jpg",
          nama: "Ir. Imam Maryoko",
          jabatan: "Mechanical, Electrical & Plumbing Supervisor",
          exp: "10 Years"
        },
        {
          id: 20,
          img: "/people20.jpg",
          nama: "Muchtar",
          jabatan: "Drafter",
          exp: "8 Years"
        },
        {
          id: 21,
          img: "/people21.jpg",
          nama: "Nurhidayah, ST",
          jabatan: "Architect & Drafter",
          exp: "7 Years"
        },
        {
          id: 22,
          img: "/people37.jpeg",
          nama: "M. Nasirudin",
          jabatan: "Architect & Drafter",
          exp: "7 Years"
        },
        {
          id: 29,
          img: "/people38.jpeg",
          nama: "Ir. Kandiyas Sakta Oihual",
          jabatan: "Building Engineering Expert",
          exp: "7 Years"
        },
        {
          id: 26,
          img: "/people42.jpeg",
          nama: "Rio Rahmadhani, ST",
          jabatan: "Civil Engineer",
          exp: "6 Years"
        },
        {
          id: 18,
          img: "/people19.jpg",
          nama: "Dedeh Setiawan, ST",
          jabatan: "Supervisor",
          exp: "6 Years"
        },
        {
          id: 30,
          img: "/people33.jpeg",
          nama: "Ir. Rico Afriandi, ST.",
          jabatan: "Architect",
          exp: "4 Years"
        }
      ],
      finance: [
        // {
        //   id: 1,
        //   img: '/people31.jpeg',
        //   nama: 'E Tri Susilawati, B.Sc',
        //   jabatan: 'Head of Finance & Administration ',
        //   exp: '22 Years'
        // },
        {
          id: 4,
          img: "/people24.jpg",
          nama: "Deddy Rahmansyah",
          jabatan: "Administration",
          exp: "18 Years"
        },
        {
          id: 3,
          img: "/people23.jpg",
          nama: "Deni Setiawan, Amd",
          jabatan: "Administration",
          exp: "6 Years"
        },
        {
          id: 5,
          img: "/people34.jpg",
          nama: "Hadi Ismail",
          jabatan: "Administration",
          exp: "6 Years"
        },
        {
          id: 2,
          img: "/people22.jpg",
          nama: "Fitriaty K, ST.",
          jabatan: "Project Administration",
          exp: "5 Years"
        },
        {
          id: 6,
          img: "/people25.jpg",
          nama: "Shafira Salsabila, S.Kom",
          jabatan: "Administration",
          exp: "2 Years"
        }
      ],
      operation: [
        {
          id: 1,
          img: "/people32.jpeg",
          nama: "Nasrudin",
          jabatan: "Head of Operation & Logistics",
          exp: "10 Years"
        },
        {
          id: 6,
          img: "/people30.jpeg",
          nama: "Udin",
          jabatan: "Logistic Staff",
          exp: "12 Years"
        },
        {
          id: 4,
          img: "/people29.jpeg",
          nama: "Sidin",
          jabatan: "Logistic Staff",
          exp: "6 Years"
        },
        {
          id: 5,
          img: "/people36.jpeg",
          nama: "Suwarno",
          jabatan: "Logistic Staff",
          exp: "6 Years"
        },
        {
          id: 2,
          img: "/people27.jpeg",
          nama: "Rahmat",
          jabatan: "Office Administration",
          exp: "3 Years"
        },
        {
          id: 3,
          img: "/people28.jpeg",
          nama: "Andi Saputra",
          jabatan: "Office Administration",
          exp: "2 Years"
        },
        {
          id: 7,
          img: "/people35.jpeg",
          nama: "Eddy Slamet",
          jabatan: "Logistic Staff",
          exp: "2 Years"
        }
      ]
    };
  },
  head() {
    return {
      title: "Deta Decon - About",
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: "description",
          name: "description",
          content:
            "PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the 26-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. "
        },
        { hid: "og:title", name: "og:title", content: "Deta Decon - About" },
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
            "PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the 26-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. "
        }
      ]
    };
  }
};
</script>
