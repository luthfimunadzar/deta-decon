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
        <h2>Construction Management & Supervision</h2>
        <h6>Gelora Bung Karno (GBK), Jakarta</h6>
      </b-carousel-slide>
      <b-carousel-slide img-src="/project-71.jpeg">
        <h2>Architecture, Planning and Design</h2>
        <h6>Rumah Sakit PELNI, Jakarta Barat</h6>
      </b-carousel-slide>
      <b-carousel-slide img-src="/hero3.jpg">
        <h2>Investigation & Building Audits</h2>
        <h6>Sarinah Building, Jakarta</h6>
      </b-carousel-slide>
    </b-carousel>

    <div class="masonry">
      <b-container>
        <b-row no-gutters>
          <!-- <b-col md="12">
            <img src="/banner-duka.jpg" class="w-100" alt="">
          </b-col> -->
          <b-col md="12" lg="8">
            <b-row no-gutters>
              <b-col md="12">
                <div class="box image short">
                  <div
                    class="image-wrap"
                    style="background-image: url('/home-5.jpg')"
                  ></div>
                  <h4>
                    Detail Engineering & Design Rumah Susun Ibu Kota Nusantara (2023-current)
                  </h4>
                </div>
              </b-col>
              <b-col md="6">
                <div class="box red">
                  <div>
                    <!-- <h4>Download DETA DECON 2020 Company Profile</h4>
                    <a href="#" class="download">Download</a> -->
                    <h3 class="mb-4">Deta Decon</h3>
                    <h4 class="mb-0">Scope of Services:</h4>
                    <!-- <h6>Scope of Services:</h6> -->
                  </div>
                </div>
              </b-col>
              <b-col md="6">
                <div class="box yellow">
                  <h3>Supervision and Construction Management</h3>
                </div>
              </b-col>
              <b-col md="12">
                <div class="box image short">
                  <div
                    class="image-wrap"
                    style="background-image: url('/home-2.jpg')"
                  ></div>
                  <h4>
                    Management Construction<br />Gelora Bung Karno (2017-2018)
                  </h4>
                </div>
              </b-col>
            </b-row>
          </b-col>
          <b-col md="12" lg="4">
            <b-row no-gutters>
              <b-col md="6" lg="12">
                <div class="box image">
                  <div
                    class="image-wrap"
                    style="background-image: url('/home-4.jpg')"
                  ></div>
                  <h4>
                    Management Construction, Design and Build<br />Athletes
                    Villages Kemayoran (2017-2018)
                  </h4>
                </div>
              </b-col>
              <b-col md="6" lg="12">
                <div class="box yellow">
                  <h3>Architecture Planning and Design</h3>
                </div>
              </b-col>
            </b-row>
          </b-col>
          <b-col md="4">
            <div class="box image short">
              <div
                class="image-wrap"
                style="background-image: url('/home-3.jpg')"
              ></div>
              <h4>
                Architectural, Planning, and Design<br />UIN Sultan Thaha Jambi
                (2018)
              </h4>
            </div>
          </b-col>
          <b-col md="8">
            <div class="box red text-left">
              <p>
                PT Deta Decon is a structural & civil consulting firm based in
                Jakarta, Indonesia. Founded in 1994, the
                {{ new Date().getFullYear() - 1994 }}-year old company has
                delivered excellence through the area of expertise in building
                structure, building skin, building performance, construction
                support services, property loss consulting and sustainability.
              </p>
            </div>
          </b-col>
          <b-col md="4">
            <div class="box yellow">
              <h3>Investigation and Building Audits</h3>
            </div>
          </b-col>
          <b-col md="8">
            <div class="box image short">
              <div
                class="image-wrap"
                style="background-image: url('/home-1.jpg')"
              ></div>
              <h3>
                and 500+ more resilient and gigantic structures all over
                Indonesia
              </h3>
            </div>
          </b-col>
        </b-row>
      </b-container>
    </div>

    <div class="media-partner">
      <b-container>
        <b-row>
          <b-col lg="8">
            <h4>Partners</h4>
            <img src="/client-1.png" alt="" class="img-mp" />
            <img src="/client-2.png" alt="" class="img-mp" />
            <img src="/client-3.png" alt="" class="img-mp" />
            <img src="/client-4.png" alt="" class="img-mp" />
            <img src="/client-5.png" alt="" class="img-mp" />
            <img src="/client-6.jpg" alt="" class="img-mp" />
            <img src="/client-9.png" alt="" class="img-mp" />
            <img src="/client-7.png" alt="" class="img-mp" />
            <img src="/client-8.jpg" alt="" class="img-mp" />
            <img src="/client-10.png" alt="" class="img-mp" />
            <img src="/client-11.jpg" alt="" class="img-mp" />
          </b-col>
          <b-col lg="4">
            <h4 class="mt-4 mt-lg-0">Media</h4>
            <img src="/media-1.png" alt="" class="img-mp" />
            <img src="/media-2.png" alt="" class="img-mp" />
            <img src="/media-3.png" alt="" class="img-mp" />
            <img src="/media-4.png" alt="" class="img-mp" />
            <img src="/media-5.png" alt="" class="img-mp" />
            <img src="/media-6.png" alt="" class="img-mp" />
            <img src="/media-7.png" alt="" class="img-mp" />
          </b-col>
          <b-col lg="12">
            <h4>Clients</h4>
            <img src="/partner-1.png" alt="" class="img-mp" />
            <img src="/partner-2.png" alt="" class="img-mp" />
            <img src="/partner-3.png" alt="" class="img-mp" />
            <img src="/partner-4.png" alt="" class="img-mp" />
            <img src="/partner-5.png" alt="" class="img-mp" />
            <img src="/partner-6.png" alt="" class="img-mp" />
            <img src="/partner-7.png" alt="" class="img-mp" />
            <img src="/partner-8.png" alt="" class="img-mp" />
            <img src="/partner-9.png" alt="" class="img-mp" />
            <img src="/partner-10.png" alt="" class="img-mp" />
            <img src="/partner-11.png" alt="" class="img-mp" />
            <img src="/partner-12.png" alt="" class="img-mp" />
            <img src="/partner-13.png" alt="" class="img-mp" />
            <img src="/partner-14.png" alt="" class="img-mp" />
            <img src="/partner-15.png" alt="" class="img-mp" />
            <img src="/partner-16.png" alt="" class="img-mp" />
            <img src="/partner-17.png" alt="" class="img-mp" />
          </b-col>
          <b-col lg="12" class="d-none">
            <h4>Social Media Pages</h4>
            <div class="instagram-feed">
              <div class="powr-instagram-feed" id="49559172_1601879308"></div>
              <script src="https://www.powr.io/powr.js?platform=vuejs"></script>
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
      slide: 0
    };
  },
  head() {
    return {
      title: "Deta Decon",
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: "description",
          name: "description",
          content:
            `PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the ${new Date().getFullYear() - 1994 }-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. `
        },
        { hid: "og:title", name: "og:title", content: "Deta Decon" },
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
