<template>
  <div class="members">
    <div class="intro-container-1">
      <div class="intro-img">
        <b-img-lazy
          src="https://res.cloudinary.com/die52atcc/image/upload/q_auto,f_auto/v1603139816/MCSS/About/recruiting_zt7mob.png"
          alt="recruitment"
          width=300
          height=300
          style="border-radius: 7px; margin-top: 5%;"
        />
      </div>
      <div class="centered">
        <h1 class="about-us">
          ABOUT <span>MCSS</span>
        </h1>
        <hr class="hr1">
        <p>MCSS, McGill Chinese Students' Society is the largest and most influential cultural
          student organization in Eastern Canada.
          With over <strong>15 events per year and 40 years of history</strong>, we provide
          a variety of events to our <strong>over 1,500 active members</strong> and help
          our members succeed in school and life.
          Our short-term goal is to provide our students with valuable events to make their
          student life more meaningful, while our long-term goal is to motivate and encourage
          our students to give back to their community and excel academically by providing
          them with helpful services including seminars, lessons, and talks.
          <br /><br />
          MCSS is a non-profit organization registered under the Students' Society of
          McGill University.
          All our proceeds either go to charity or are used to provide our students with
          more valuable services.
          <strong>Our events range from largescale shows to career planning
          and information seminars. In addition, we organize dinner outings,
          networking opportunities and parties for our members.</strong>
          </p>
      </div>
    </div>
    <hr class="hr2">

    <div class="intro-container-2">
      <div class="centered">
        <h1>WHY <span>MCSS</span></h1>
        <hr class="hr1">
        <p>MCSS has had a long and storied history of amazing
          events, from <strong>our annual Ski and New York Trips, to Be There or Be Square and
          hosting Wong Fu Productions.</strong>
          <br /><br />
          With MCSS, you’ll create unforgettable memories, have a blast, and learn a thing or
          two about event planning in the process. MCSS is a fun, loving, and close-knit
          family away from home!
          <br /><br />
          We accept executives from all around the world;
          <strong>you don’t have to be Chinese or even Asian!</strong>
          <br /><br />
          </p>
      </div>
      <div class="intro-img">
        <b-img-lazy
          src="https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800252/MCSS/DSCF5557_m5gye3.jpg"
          alt="Group Picture!"
          width=466
          height=300
          style="border-radius: 7px;" class="group-pic"
        />
      </div>
    </div>
    <hr class="hr2">

    <h1>OUR <span>TEAM</span></h1>
    <hr class="hr3">
    <br />

    <div class="board" >

      <div class="president">
        <b-row>
          <b-col sm="12" md="6" class="avatar" v-on:click="togglePres1()">
            <transition name="flip">
              <div class="card-container-pres" v-if="pres1flipped">
                <div class="member-desc">
                  <p><strong>Hometown:</strong> Montreal, QC</p>
                  <p><strong>Major:</strong> U3 Computer Engineering</p>
                </div>
              </div>
              <b-img-lazy
                src="https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800260/MCSS/Michelle.jpg"
                blank-src="https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800260/MCSS/Michelle.jpg"
                alt="Co-President"
              />
            </transition>
            <p class="name">Michelle Lee</p>
            <p class="role">Co-President</p>
            <br /><br />
          </b-col>
          <b-col sm="12" md="6" class="avatar" v-on:click="togglePres2()">
            <transition name="flip">
              <div class="card-container-pres" v-if="pres2flipped">
                <div class="member-desc">
                  <p><strong>Hometown:</strong> Montreal, QC</p>
                  <p><strong>Major:</strong> U3 Accounting</p>
                </div>
              </div>
              <b-img-lazy
                src="https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800258/MCSS/DSC_4278_kuyv90.jpg"
                blank-src="https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800258/MCSS/DSC_4278_kuyv90.jpg"
                alt="Co-President"
              />
            </transition>
            <p class="name">Hoang Kevin Say</p>
            <p class="role">Co-President</p>
          </b-col>
        </b-row>
      </div>
      <br /><br />
      <div class="restOfBoard">
        <b-row>
          <b-col sm="12" md="4" class="avatar"
            v-on:click="toggleCard(member)"
            v-for="member in boardMembers"
            :key="member.name"
          >
            <transition name="flip">
              <div class="card-container" v-if="member.flipped">
                <div class="member-desc">
                  <p><strong>Hometown:</strong> {{ member.hometown }}</p>
                  <p><strong>Major:</strong> {{ member.major }}</p>
                </div>
              </div>
              <b-img-lazy
                :src="member.image"
                blank-src="https://res.cloudinary.com/die52atcc/image/upload/q_auto,f_auto/v1603139815/MCSS/About/placeholder_wox9nt.png"
                offset="700"
                v-else
                v-bind:alt="member.name"
              />
            </transition>
            <p class="name">{{member.name}}</p>
            <p class="role">{{member.role}}</p>
            <br /><br />
          </b-col>
        </b-row>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'about',
  methods: {
    toggleCard(member) {
      // eslint-disable-next-line no-param-reassign
      member.flipped = !member.flipped;
    },
    togglePres1() {
      this.pres1flipped = !this.pres1flipped;
    },
    togglePres2() {
      this.pres2flipped = !this.pres2flipped;
    },
  },
  data() {
    return {
      pres1flipped: false,
      pres2flipped: false,
      boardMembers: [
        {
          name: 'Amy Huang',
          id: 'amy',
          role: 'VP Internal',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800257/MCSS/amy.jpg',
          hometown: 'Boston, MA',
          major: 'U2 Computer Science & Stats',
          flipped: false,
        },
        {
          name: 'Anita Zheng',
          id: 'anita',
          role: 'VP Internal',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800256/MCSS/Anita.jpg',
          hometown: 'Whitby, ON',
          major: 'U2 Computer Science',
          flipped: false,
        },
        {
          name: 'Charlene Yin',
          id: 'Charlene',
          role: 'VP Internal',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800259/MCSS/DSC_4257_tzfbgc.jpg',
          hometown: 'Vancouver, BC',
          major: 'U2 Cognitive Science',
          flipped: false,
        },
        {
          name: 'Emma Liu',
          id: 'emma',
          role: 'Project Manager',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800250/MCSS/DSC_3947_ibi2tj.jpg',
          hometown: 'Markham, ON',
          major: 'U1 BCOMM',
          flipped: false,
        },
        {
          name: 'Jun Na',
          id: 'Jun',
          role: 'Project Manager',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800253/MCSS/Na_Jun_crop_if_needed_kuwjut.jpg',
          hometown: 'Seoul, Korea',
          major: 'U3 Marketing',
          flipped: false,
        },
        {
          name: 'Shirley Wen',
          id: 'shirley',
          role: 'Project Manager',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800252/MCSS/IMG_0518_ob4cnd.jpg',
          hometown: 'Toronto, ON',
          major: 'U2 Software Engineering',
          flipped: false,
        },
        {
          name: 'Maggie Zhang',
          id: 'magie',
          role: 'Project Manager',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800250/MCSS/DSC_3972_nxgfqr.jpg',
          hometown: 'Montreal, QC',
          major: 'U3 Pharmacology',
          flipped: false,
        },
        {
          name: 'Sophia Li',
          id: 'sophia',
          role: 'Project Manager',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800250/MCSS/DSC_3959_eaxg0c.jpg',
          hometown: 'Markham, ON',
          major: 'U1 ',
          flipped: false,
        },
        {
          name: 'Karist NG',
          id: 'karist',
          role: 'Senior Advisor',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800251/MCSS/Copy_of_DSCF5522_dc7kd5.jpg',
          hometown: 'Bangkok, Thailand',
          major: 'U4 Materials',
          flipped: false,
        },
        {
          name: 'Ivy Chen',
          id: 'ivy',
          role: 'Senior Advisor',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800251/MCSS/DSCF5452_fcd175.jpg',
          hometown: 'Newmarket, ON',
          major: 'U3 Nursing',
          flipped: false,
        },
        {
          name: 'Xi Ran Chen',
          id: 'xi ran',
          role: 'Senior Advisor',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800251/MCSS/DSCF5474_xplluu.jpg',
          hometown: 'Shandong, China',
          major: 'Joint Honours Economics and Accounting',
          flipped: false,
        },
        {
          name: 'Jessica Yip',
          id: 'jessica',
          role: 'Senior Advisor',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800250/MCSS/Copy_of_DSCF5549_edx36o.jpg',
          hometown: 'Montréal, QC',
          major: 'GCPA / Accounting',
          flipped: false,
        },
        {
          name: 'Dimitri Yang',
          id: 'dimitri',
          role: 'Photographer',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800260/MCSS/DSCF5357_k9s2b0.jpg',
          hometown: 'Surrey, BC',
          major: 'M1 Medicine',
          flipped: false,
        },
        {
          name: 'Melina Chen',
          id: 'melina',
          role: 'Sponsorship Director',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800252/MCSS/DSC_4002_jzocq0.jpg',
          hometown: 'Boston, MA',
          major: 'U2 Biochemistry',
          flipped: false,
        },
        {
          name: 'Julian Qu',
          id: 'julian',
          role: 'Sponsorship Director',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800250/MCSS/DSCF5441_h1wpox.jpg',
          hometown: 'Vancouver, BC',
          major: 'U4 Civil Engineering',
          flipped: false,
        },
        {
          name: 'George Yin',
          id: 'george',
          role: 'Sponsorship Director',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800255/MCSS/Yin_George_f7ja2y.jpg',
          hometown: 'Ottawa, ON',
          major: 'U2 Pharmacology',
          flipped: false,
        },
        {
          name: 'Kimberly Yang',
          id: 'kimberly',
          role: 'VP external',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800259/MCSS/DSC_4430_hk5ucq.jpg',
          hometown: 'Thornhill, ON',
          major: 'U1 Joint Honours Philosophy & East Asian Studies',
          flipped: false,
        },
        {
          name: 'Cindy Liu',
          id: 'cindy',
          role: 'Social Director',
          // will replace
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670812180/MCSS/319302891_3046500542320857_3766511308049425752_n_siwnbl.jpg',
          hometown: 'Montreal, QC',
          major: 'U2 Marketing & Info Sys',
          flipped: false,
        },
        {
          name: 'Emily Xin Yuan Zhang',
          id: 'emily',
          role: 'Social Director',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800253/MCSS/DSC_4117_y9csz4.jpg',
          hometown: 'Nanning, GuangXi',
          major: 'U2 Sociology',
          flipped: false,
        },
        {
          name: 'Helene Lu',
          id: 'helene',
          role: 'VP Media Junior',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800260/MCSS/DSCF5431_mn37j2.jpg',
          hometown: 'Shanghai, China',
          major: 'U3 Marketing',
          flipped: false,
        },
        {
          name: 'Dorothy Ma',
          id: 'dorothy',
          role: 'VP Media',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800252/MCSS/DSC_4040_rlpmti.jpg',
          hometown: 'Vancouver, BC',
          major: 'U2 Bioengineering',
          flipped: false,
        },
        {
          name: 'Yi Fang Yuan',
          id: 'yifang',
          role: 'Webmaster',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800256/MCSS/DSC_4183_pw9yb7.jpg',
          hometown: 'Montreal, QC',
          major: 'U3 Computer Science',
          flipped: false,
        },
        {
          name: 'Xianos Fei',
          id: 'xianos',
          role: 'VP Finance',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800256/MCSS/Fei_Xianos_t9nmjc.jpg',
          hometown: 'Montreal, QC',
          major: 'U3 Accounting',
          flipped: false,
        },
        {
          name: 'Waner Jin',
          id: 'waner',
          role: 'VP Academic',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800255/MCSS/Copy_of_DSCF5389_xvaudj.jpg',
          hometown: 'Montreal, QC',
          major: 'U3 Microbiology & Immunology',
          flipped: false,
        },
        {
          name: 'Rico Li',
          id: 'rico',
          role: 'First Year Rep',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800258/MCSS/DSC_4347_srn3op.jpg',
          hometown: 'Montreal, QC',
          major: 'U1 Electrical Engineering',
          flipped: false,
        },
        {
          name: 'Nina Zhuang',
          id: 'nina',
          role: 'First year Rep',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800260/MCSS/DSC_4384_pyt2cz.jpg',
          hometown: 'Vaughan, ON',
          major: 'U0 Management',
          flipped: false,
        },
        {
          name: 'Bill Lin',
          id: 'bill',
          role: 'First Year Rep',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800260/MCSS/DSC_4390_r9pd85.jpg',
          hometown: 'Oakville, Ontario',
          major: 'U1 Marketing',
          flipped: false,
        },
        {
          name: 'Alina Lu',
          id: 'alina',
          role: 'First Year Rep',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800258/MCSS/DSC_4359_fvjzng.jpg',
          hometown: 'Chengdu, China',
          major: 'U1 Management',
          flipped: false,
        },
        {
          name: 'William Wang',
          id: 'william',
          role: 'First Year Rep',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800258/MCSS/DSC_4362_cgy2pt.jpg',
          hometown: 'Montreal, QC',
          major: 'U1 Software Engineering',
          flipped: false,
        },
        {
          name: 'Yuheng Liu',
          id: 'yuheng',
          role: 'VP Comms',
          image: 'https://res.cloudinary.com/dyi0a7i0a/image/upload/v1670800255/MCSS/DSC_4176_agun75.jpg',
          hometown: 'Windsor, ON',
          major: 'U2 Bioengineering',
          flipped: false,
        },
      ],
    };
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

  h1 {
    text-align: center;
    font-size: 30px;
    font-family: IKEABold;
  }

  h1 span {
    font-size: 30px;
    font-family: IKEABold;
    color: #be0819;
  }

  .intro-img {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .card-container {
    display: block;
    margin-right: auto;
    margin-left: auto;
    background-color: #be0819;
    border-radius: 7px;
    width: 80%;
    padding-top: 100%; /* Aspect Ratio */
    position: relative; /* If you want text inside of it */
    cursor: pointer;
    text-align: center;
    margin-bottom: 20px;
    -webkit-box-shadow: 9px 10px 22px -8px rgba(209,193,209,.5);
    -moz-box-shadow: 9px 10px 22px -8px rgba(209,193,209,.5);
    box-shadow: 9px 10px 22px -8px rgba(209,193,209,.5);
    will-change: transform;
  }
  .card-container-pres {
    display: block;
    margin-right: auto;
    margin-left: auto;
    background-color: #be0819;
    border-radius: 7px;
    width: 60%;
    padding-top: 90%; /* Aspect Ratio */
    position: relative; /* If you want text inside of it */
    cursor: pointer;
    text-align: center;
    margin-bottom: 20px;
    -webkit-box-shadow: 9px 10px 22px -8px rgba(209,193,209,.5);
    -moz-box-shadow: 9px 10px 22px -8px rgba(209,193,209,.5);
    box-shadow: 9px 10px 22px -8px rgba(209,193,209,.5);
    will-change: transform;
  }

  .flip-enter-active {
    transition: all 1s ease;
    transform-style: preserve-3d;
  }

  .flip-leave-active {
    display: none;
  }

  .flip-enter, .flip-leave {
    transform: rotateY(90deg);
    opacity: 0;
  }

  .member-desc {
    color: #fff;
    position: absolute;
    top: 40%;
    left: 0;
    bottom: 0;
    right: 0;
    margin: auto;
    margin-left: 5px;
    margin-right: 5px;
  }

  .member-desc p, .member-desc p strong, p.name {
    font-size: 2rem;
    font-family: IKEABold;
  }

  p.role {
    font-size: 1.5rem;
    font-family: Proxima;
  }

  .members{
    width: 90%;
    margin: auto;
  }
  .hr3{
    background-color: #be0819;
    width: 15%;
    height: 1px;
  }
  .hr2 {
    margin-top: 3rem;
    margin-bottom: 3rem;
    width: 80%;
    border: 0;
    border-top: 1px solid rgba(0,0,0,.1);
  }
  .hr1{
    background-color: #be0819;
    width: 30%;
    height: 1px;
  }
  h2{
    background-color: #0c5fa8;
    color: white;
    padding: 10px;
    border-radius: 30px;
  }
  .president {
    margin-left: auto;
    margin-right: auto;
    display: block;
    text-align: center;
  }
  .internals, .restOfBoard {
    margin-left: auto;
    margin-right: auto;
    display: block;
    text-align: center;
  }
  .avatar img{
    border-radius: 7px;
    width: 80%;
    height: auto;
    margin-bottom: 20px;
    cursor: pointer;
  }
  .avatar .name{
    font-weight: bold;
    margin-bottom: 0;
  }

  .members li{
    display: inline-grid;
    padding: 10px 20px 10px 20px;
    font-weight: bold;
  }
  @media screen and (min-width: 840px) {
    .intro-container-1 p, .intro-container-2 p {
      margin-right: 10%;
      margin-left: 10%;
      margin-top: 2%;
      font-family: Proxima;
      font-size: 1.8rem;
      text-align: justify;
    }

    .intro-container-1 p strong, .intro-container-2 p strong {
      font-family: Proxima;
      font-size: 1.8rem;
    }

    .intro-container-1 {
      display: flex;
      flex-wrap: nowrap;
      margin-left: 7vw;
    }

    .intro-container-2 {
      display: flex;
      flex-wrap: nowrap;
      margin-right: 7vw;
    }
    .president img{
      width: 60% !important;
    }

    .card-container-pres {
      display: block;
      margin-right: auto;
      margin-left: auto;
      background-color: #be0819;
      border-radius: 7px;
      width: 60%;
      padding-top: 75%; /* Aspect Ratio */
      position: relative; /* If you want text inside of it */
      cursor: pointer;
      text-align: center;
      margin-bottom: 20px;
      -webkit-box-shadow: 9px 10px 22px -8px rgba(209,193,209,.5);
      -moz-box-shadow: 9px 10px 22px -8px rgba(209,193,209,.5);
      box-shadow: 9px 10px 22px -8px rgba(209,193,209,.5);
      will-change: transform;
    }
  }
  @media screen and (max-width: 840px) {
    .intro-container-1 p, .intro-container-2 p {
      margin-right: 5%;
      margin-left: 5%;
      margin-top: 2%;
      font-family: Proxima;
      font-size: 1.8rem;
      text-align: justify;
    }

    .intro-container-1 p strong, .intro-container-2 p strong {
      font-family: Proxima;
      font-size: 1.8rem;
    }

    .intro-container-1 {
      display: flex;
      flex-direction: column;
    }
    .intro-container-1 .intro-img {
      margin-left: auto;
      margin-right: auto;
      display: block;
      text-align: center;
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
    .group-pic {
      width: 80%;
      height: auto;
    }
    .about-us {
      margin-top: 5%;
    }
  }

  @media screen and (max-width: 992px) {
    h2 {
      font-size: 25px;
    }
    .members li{
      width: 95%;
    }
  }
  @media screen and (max-width: 767px) {
    h2 {
      font-size: 25px;
    }
    .members li{
      width: 95%;
    }
    .card-container-pres {
      display: block;
      margin-right: auto;
      margin-left: auto;
      background-color: #be0819;
      border-radius: 7px;
      width: 80%;
      padding-top: 100%; /* Aspect Ratio */
      position: relative; /* If you want text inside of it */
      cursor: pointer;
      text-align: center;
      margin-bottom: 20px;
      -webkit-box-shadow: 9px 10px 22px -8px rgba(209,193,209,.5);
      -moz-box-shadow: 9px 10px 22px -8px rgba(209,193,209,.5);
      box-shadow: 9px 10px 22px -8px rgba(209,193,209,.5);
      will-change: transform;
    }
  }
</style>
