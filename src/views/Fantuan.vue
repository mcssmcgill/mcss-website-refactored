<template>
  <div class="events">
    <h1>MCSS <span style="color: black">AND </span> <span>FANTUAN</span></h1>
    <hr class="hr1">
    <div class="intro-container-2">
      <div class="intro-img">
        <b-img-lazy
          src="https://res.cloudinary.com/die52atcc/image/upload/v1628796701/MCSS/fantuan_gpcfma.jpg"
          alt="Group Picture!"
          width=542
          height=330
          style="border-radius: 7px;"
          class="group-pic"
        />
      </div>
      <div class="centered">
        <p class="card-text">
          Fantuan Delivery is offering <b>7$ off your first order (Min. $10).</b>
          Fantuan is the largest Asian food delivery service in North America and offers a selection
          of big name restaurants and local specialties.
        </p>
        <p class="card-text-btm">
          <b>USE PROMO CODE: MCSSS</b>
          <br />
          <br />
          Download the app today!
        </p>
        <div class="buttons">
          <a
            href="https://download.fantuan.ca/?channelCode=yyhz_dlp_0116_MCSShyxsh"
            class="tutorial-btn"
            target="_blank"
          >
            <i class="fa fa-download" aria-hidden="true"></i>
            GET THE APP
          </a>
        </div>
      </div>
    </div>
    <hr class="hr2">
  </div>
</template>

<script>
export default {
  name: 'fantuan',
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

  .card-btn:hover {
    opacity: 0.8;
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
      color: #be0819;
    }

    .event2 {
      width: 90%;
      margin-left: auto;
      margin-right: auto;
    }

    .events span {
      font-size: 25px;
      color: rgb(111, 195, 191);
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

    .card-text-btm {
      margin-bottom: 2%;
      font-family: Proxima;
      font-size: 1.8rem;
      text-align: center;
    }

    .check-it-out {
      font-family: IKEABold;
      font-size: 1.5rem;
    }
    .tutorial-btn {
      width: 24px;
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
      color: #be0819;
    }
    .events span {
      font-size: 30px;
      color: rgb(111, 195, 191);
    }

    .event2 {
      width: 80%;
      margin-left: auto;
      margin-right: auto;
    }

    .card-text {
      margin-left: 10%;
      margin-top: 2%;
      font-family: Proxima;
      font-size: 2.2rem;
      text-align: justify;
    }

    .card-text-btm {
      margin-left: 10%;
      margin-top: 4%;
      margin-bottom: 2%;
      font-family: Proxima;
      font-size: 2.2rem;
      text-align: justify;
    }

    .card-text b, .card-text-btm b {
      font-family: Proxima;
      font-size: 2.2rem;
    }

    .check-it-out {
      font-family: IKEABold;
      font-size: 3rem;
    }

    .tutorial-btn {
      margin-left: 10%;
      margin-right: auto;
      width: 245px;
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
    background: rgb(111, 195, 191);
    color: white;
    border: 3px solid rgb(111, 195, 191);
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
    opacity: 0.8;
    text-decoration: none;
  }

</style>
