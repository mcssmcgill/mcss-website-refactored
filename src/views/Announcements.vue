<template>
  <div class="events">
    <h1>MCGILL INFERNO: <span>LOST IN PARADISE</span></h1>
    <hr class="hr1">
    <div class="event-container event2 upcoming" v-on:click="toggle = !toggle">
      <b-img-lazy
        src="https://res.cloudinary.com/die52atcc/image/upload/q_auto,f_auto/v1644191070/MCSS/Events/inferno_dlqken.png"
        :class="{toggled: toggle}"
        alt="MCSS CASINO NIGHT"
        style="border-radius: 7px;"
      />
      <a class="event-redirect" v-if="toggle" href="https://fb.me/e/18rekgzyF" target="_blank">
        <div class="middle">
          <h2 style="font-family: IKEABold;" class="check-it-out">Check out our event page!</h2>
        </div>
      </a>
    </div>
    <hr class="hr2">
    <h1>FALL 2021 <br><span>NEW RECRUITS</span></h1>
    <hr class="hr1">
    <div class="event2">
      <b-img-lazy
        src="https://res.cloudinary.com/die52atcc/image/upload/q_auto,f_auto/v1637031371/MCSS/mcss_2021_fvv397.jpg"
        alt="New Recruit Fall 2021"
        style="border-radius: 7px;"
      />
    </div>
    <hr class="hr2">
    <h1>OUR MCSS <span>MERCH IS HERE!</span></h1>
    <hr class="hr1">
    <div class="event-container event2 upcoming" v-on:click="toggle = !toggle">
      <b-img-lazy
        src="https://res.cloudinary.com/die52atcc/image/upload/q_auto,f_auto/v1605722567/MCSS/Merch/first-drop/tshirt_banner_wkccbu.jpg"
        class="toggled"
        alt="MCSS Merch"
        style="border-radius: 7px; border: 1px solid black"
      />
      <a class="event-redirect" href="/shop">
        <div class="middle">
          <h2 style="font-family: IKEABold;" class="check-it-out" >SOLD OUT</h2>
        </div>
      </a>
    </div>
    <hr class="hr2">
    <!-- SLIDES
    <div id="sogaeting"><h1>SOGAETING <br><span> FEB 14 2020</span></h1></div>
    <hr class="hr1">
    <div class="slideshow-container">
      <vueper-slides lazy lazy-load-on-drag slide-image-inside
        :slide-ratio="485 / 728"
        :touchable="false"
      >
        <vueper-slide v-for="(slide, i) in slides" :key="i" :image="slide.image">
          <template v-slot:loader>
            <i class="icon icon-loader spinning"></i>
            <span>Loading...</span>
          </template>
        </vueper-slide>
      </vueper-slides>
    </div>
    <hr class="hr2">
    -->
  </div>
</template>

<script>
export default {
  name: 'announcements',
  data() {
    return {
      toggle: false,
      wp_toggle: false,
      slides: [
        {
          title: 'Sogaeting 1',
          content: 'First Picture',
          // You can also provide a URL for the image.
          image: 'https://res.cloudinary.com/die52atcc/image/upload/q_auto,f_auto/v1603140042/MCSS/Events/Sogaeting/pic1_f2atg4.jpg',
        },
        {
          title: 'Sogaeting 2',
          content: 'Second Picture',
          // You can also provide a URL for the image.
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1603140041/MCSS/Events/Sogaeting/pic3_srnpsm.jpg',
        },
        {
          title: 'Sogaeting 3',
          content: 'Third Picture',
          // You can also provide a URL for the image.
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1603140040/MCSS/Events/Sogaeting/pic2_kinssy.jpg',
        },
        {
          title: 'Sogaeting 4',
          content: 'Fourth Picture',
          // You can also provide a URL for the image.
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1603140041/MCSS/Events/Sogaeting/pic4_oyqkts.jpg',
        },
        {
          title: 'Sogaeting 5',
          content: 'Fifth Picture',
          // You can also provide a URL for the image.
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1603140040/MCSS/Events/Sogaeting/pic5_ujt3a2.jpg',
        },
      ],
    };
  },
  methods: {
    redirectToCard() {
      this.$router.push('/shop/membership-card');
    },
  },
};
</script>

<style scoped>
  .centered {
    margin-left: auto;
    margin-right: auto;
    display: block;
    text-align: center;
  }

  .intro-img {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  b {
  font-size: 1.8rem;
  }

  .buttons {
    display: flex;
    flex-wrap: wrap;
  }
  .card-btn {
    font-family: IKEABold;
    height: 4.5rem;
    background: #be0819;
    color: white;
    border: none;
    border-radius: 5px;
    outline: none;
    font-size: 1.5rem;
    letter-spacing: 0.1rem;
    transition: all 0.3s ease-out;
    margin-right: auto;
    display: block;
    min-width: 167px;
  }

  .check-it-out {
    font-size: 3rem;
    position: absolute;
    text-align: center;
    top: 50%;
    transform: translateY(-50%);
    width: 100%;
    background-color: white;
    border:0.1em solid #000000;
    border-radius:2rem;
    padding:0.46em 1.6em;
    transition: all 0.5s;
    color: #be0819;
  }

  .check-it-out:hover {
    font-weight: 600;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2),
      0 6px 20px 0 rgba(0, 0, 0, 0.19);
    cursor: pointer;
    background: #be0819;
    color: white;
  }

  .card-btn:hover {
    opacity: 0.8;
  }

  .toggled {
    opacity: 0.6;
    transition: all 0.15s;
  }

  .upcoming {
    cursor: pointer;
  }

  .event-container {
    position: relative;
  }

  .vueperslide, .vueperslide__image {
    border-radius: 7px;
  }

  @media screen and (max-width: 1000px) {
    .slideshow-container {
      width: 90%;
      margin-right: auto;
      margin-left: auto;
      display: block;
    }

    .intro-container-2 {
      display: flex;
      flex-direction: column;
    }
    .intro-container-2 .intro-img {
      margin-left: auto;
      margin-right: auto;
      display: block;
      text-align: center;
    }
    .intro-img img{
      width: 80%;
      height: auto;
    }
    .events h1 {
      text-align: center;
      font-size: 25px;
      font-family: IKEABold;
      margin-left: 5%;
      margin-right: 5%;
    }

    .event2 {
      width: 90%;
      margin-left: auto;
      margin-right: auto;
    }

    .events span {
      font-size: 25px;
      color: #be0819;
    }
    .card-text {
      margin-right: 10%;
      margin-left: 10%;
      margin-top: 5%;
      margin-bottom: 5%;
      font-family: Proxima;
      font-size: 1.8rem;
      text-align: justify;
    }

    .check-it-out {
      font-family: IKEABold;
      font-size: 1.5rem;
    }
    .tutorial-btn {
      width: 25rem;
      margin-left: auto;
      margin-right: auto;
    }

    .card-btn {
      width: 25rem;
      margin-left: auto;
      margin-right: auto;
      margin-bottom: 10px;
    }
  }
  @media screen and (min-width: 1000px) {
    .slideshow-container {
      width: 80%;
      margin-right: auto;
      margin-left: auto;
      display: block;
    }

    .intro-container-2 {
      display: flex;
      flex-wrap: nowrap;
      width: 80%;
      margin: auto;
      margin-top: 2%;
    }

    .events h1 {
      text-align: center;
      font-size: 30px;
      font-family: IKEABold;
    }
    .events span {
      font-size: 30px;
      color: #be0819;
    }

    .event2 {
      width: 80%;
      margin-left: auto;
      margin-right: auto;
    }

    .card-text {
      margin-left: 10%;
      margin-top: 2%;
      margin-bottom: 5%;
      font-family: Proxima;
      font-size: 1.8rem;
      text-align: justify;
    }

    .check-it-out {
      font-family: IKEABold;
      font-size: 3rem;
    }

    .tutorial-btn {
      margin-left: 10%;
      margin-right: auto;
      width: 40%;
    }

    .card-btn {
      margin-left: 10%;
      margin-right: auto;
      width: 40%;
      margin-bottom: 10px;
    }
  }

  .hr1{
      background-color: #be0819;
      width: 28%;
      height: 1px;
  }

  .event2 img{
    border-radius: 7px;
    margin-top: 20px;
    width: 100%;
  }

  .hr2 {
    margin-top: 3rem;
    margin-bottom: 3rem;
    width: 80%;
    border: 0;
    border-top: 1px solid rgba(0,0,0,.1);
  }

  .tutorial-btn {
    font-family: IKEABold;
    height: 4.5rem;
    padding: 10px 15px;
    background: white;
    color: black;
    border: 3px solid black;
    border-radius: 5px;
    outline: none;
    font-size: 1.5rem;
    transition: all 0.3s ease-out;
    align-items: center;
    min-width: 167px;
  }

  .tutorial-btn:hover {
    font-weight: 600;
    cursor: pointer;
    background: black;
    color: white;
    text-decoration: none;
  }

</style>
