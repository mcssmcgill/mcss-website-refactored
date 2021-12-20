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
          src="https://res.cloudinary.com/die52atcc/image/upload/v1640042145/MCSS/Members22/mcssfam_lxfjlj.jpg"
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
                  <p><strong>Hometown:</strong> Ottawa, ON</p>
                  <p><strong>Major:</strong> U3 Neuroscience</p>
                </div>
              </div>
              <b-img-lazy
                src="https://res.cloudinary.com/die52atcc/image/upload/v1640031672/MCSS/Members22/DSC_0274-Edit_alyz6v.jpg"
                blank-src="https://res.cloudinary.com/die52atcc/image/upload/v1603139815/MCSS/About/placeholder_wox9nt.png"
                alt="Co-President"
              />
            </transition>
            <p class="name">Amy Li</p>
            <p class="role">Co-President</p>
            <br /><br />
          </b-col>
          <b-col sm="12" md="6" class="avatar" v-on:click="togglePres2()">
            <transition name="flip">
              <div class="card-container-pres" v-if="pres2flipped">
                <div class="member-desc">
                  <p><strong>Hometown:</strong> Bangkok, Thailand</p>
                  <p><strong>Major:</strong> U3 Materials Engineering</p>
                </div>
              </div>
              <b-img-lazy
                src="https://res.cloudinary.com/die52atcc/image/upload/v1640031746/MCSS/Members22/DSC_0284-Edit_hmwd9i.jpg"
                blank-src="https://res.cloudinary.com/die52atcc/image/upload/q_auto,f_auto/v1603139815/MCSS/About/placeholder_wox9nt.png"
                alt="Co-President"
              />
            </transition>
            <p class="name">Karist Ng</p>
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
          name: 'Melody Zhou',
          id: 'melody',
          role: 'VP Internal',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640032157/MCSS/Members22/Copy_of_DSC_0356-Edit_jkbgo3.jpg',
          hometown: 'Boston, MA',
          major: 'U4 Cognitive Science',
          flipped: false,
        },
        {
          name: 'Yuecheng Huang',
          id: 'yuecheng',
          role: 'VP External',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640032363/MCSS/Members22/DSCF2855-Edit_c9xjma.jpg',
          hometown: 'Ottawa, ON',
          major: 'U3 Philosophy/International Development',
          flipped: false,
        },
        {
          name: 'Jeremy Leung',
          id: 'jeremy',
          role: 'VP Internal',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640032271/MCSS/Members22/DSC_0420-Edit_a51wdo.jpg',
          hometown: 'Toronto, ON',
          major: 'U3 Microbiology & Immunology',
          flipped: false,
        },
        {
          name: 'Jian Qiao He',
          id: 'mike',
          role: 'Senior Advisor',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640034481/MCSS/Members22/DSCF3185-Edit_wph3os.jpg',
          hometown: 'Jilin City, China',
          major: 'U3 Marketing',
          flipped: false,
        },
        {
          name: 'Xi Ran Chen',
          id: 'xiran',
          role: 'VP Finance',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640034596/MCSS/Members22/DSCF3039-Edit_awz5lw.jpg',
          hometown: 'Shandong, China',
          major: 'U3 Joint Economics & Accounting',
          flipped: false,
        },
        {
          name: 'Jennifer Chen',
          id: 'jennifer',
          role: 'Junior VP Finance',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640034707/MCSS/Members22/DSCF3020_1_-Edit_pjjn5p.jpg',
          hometown: 'Toronto, ON',
          major: 'U2 Computer Science',
          flipped: false,
        },
        {
          name: 'Julian Qu',
          id: 'julian',
          role: 'Sponsorship Director',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640034817/MCSS/Members22/DSCF2873-Edit_xdzmt5.jpg',
          hometown: 'Richmond, BC',
          major: 'U3 Civil Engineering',
          flipped: false,
        },
        {
          name: 'Kimberly Yang',
          id: 'kimberley',
          role: 'Sponsorship Director',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640036376/MCSS/Members22/DSCF2880-Edit_vnrcfz.jpg',
          hometown: 'Thornhill, ON',
          major: 'U0 Undeclared',
          flipped: false,
        },
        {
          name: 'Chris Gao',
          id: 'chris',
          role: 'Sponsorship Director',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640036063/MCSS/Members22/DSCF2842-Edit_ujx89r.jpg',
          hometown: 'Markham, ON',
          major: 'U3 Psychology',
          flipped: false,
        },
        {
          name: 'Hoang Kevin Say',
          id: 'kevin',
          role: 'Project Manager',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640036477/MCSS/Members22/Copy_of_DSC_0565-Edit_o50gfu.jpg',
          hometown: 'Montréal, QC',
          major: 'U2 Accounting',
          flipped: false,
        },
        {
          name: 'Jessica Yip',
          id: 'jessica',
          role: 'Project Manager',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640036557/MCSS/Members22/DSC_0669-Edit_hw6lwx.jpg',
          hometown: 'Montréal, QC',
          major: 'U4 Accounting',
          flipped: false,
        },
        {
          name: 'Michelle Lee',
          id: 'michelle',
          role: 'Project Manager',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640036652/MCSS/Members22/DSC_0551-Edit_hns0w4.jpg',
          hometown: 'Montréal, QC',
          major: 'U2 Computer Engineering',
          flipped: false,
        },
        {
          name: 'Melina Chen',
          id: 'melina',
          role: 'Project Manager',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640036710/MCSS/Members22/DSC_0633-Edit_zntp3i.jpg',
          hometown: 'Boston, MA',
          major: 'U2 Biochemistry',
          flipped: false,
        },
        {
          name: 'Charlene Yin',
          id: 'charlene',
          role: 'Junior Project Manager',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640036816/MCSS/Members22/DSC_0601-Edit_huidcq.jpg',
          hometown: 'Vancouver, BC',
          major: 'U1 Cognitive Science',
          flipped: false,
        },
        {
          name: 'Nancy Xiang',
          id: 'nancy',
          role: 'VP Academics',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640041067/MCSS/Members22/DSCF2755-Edit_jn2foy.jpg',
          hometown: 'Oakville, ON',
          major: 'U3 Psychology',
          flipped: false,
        },
        {
          name: 'Anita Zheng',
          id: 'anita',
          role: 'Social Director',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640036988/MCSS/Members22/DSCF2917-Edit_ciri9f.jpg',
          hometown: 'Whitby, ON',
          major: 'U1 Computer Science',
          flipped: false,
        },
        {
          name: 'Jia Liu',
          id: 'jia',
          role: 'Social Director',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640037083/MCSS/Members22/DSCF2927-Edit_wgmi9b.jpg',
          hometown: 'Montréal, QC',
          major: 'U3 Microbiology & Immunology',
          flipped: false,
        },
        {
          name: 'Yuheng Liu',
          id: 'yuheng',
          role: 'VP Communications & Marketing',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640037384/MCSS/Members22/DSCF3142-Edit_z9fkbq.jpg',
          hometown: 'Windsor, ON',
          major: 'U1 Bioengineering',
          flipped: false,
        },
        {
          name: 'Young Rock Han',
          id: 'youngrock',
          role: 'VP Marketing',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640037448/MCSS/Members22/DSCF3069-Edit_pcww66.jpg',
          hometown: 'Winnipeg, MB & Seoul, Korea',
          major: 'U3 Nursing',
          flipped: false,
        },
        {
          name: 'Ivy Chen',
          id: 'ivy',
          role: 'VP Media',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640040876/MCSS/Members22/DSCF2697-Edit_c9mziq.jpg',
          hometown: 'Newmarket, ON',
          major: 'U2 Nursing',
          flipped: false,
        },
        {
          name: 'Dorothy Ma',
          id: 'dorothy',
          role: 'Junior VP Media',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640040923/MCSS/Members22/DSCF2683-Edit_mhovlo.jpg',
          hometown: 'Vancouver Mountains',
          major: 'U1 Bioengineering',
          flipped: false,
        },
        {
          name: 'Dian Dian Dai',
          id: 'dian',
          role: 'Photographer',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640040458/MCSS/Members22/DSC03859-Edit_dzovcg.jpg',
          hometown: 'Toronto, ON',
          major: 'U3 Computer Science',
          flipped: false,
        },
        {
          name: 'Dimitri Yang',
          id: 'dimitri',
          role: 'Photographer',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640040525/MCSS/Members22/DSCF2963-Edit_fd1q1t.jpg',
          hometown: 'Vancouver, BC',
          major: 'U3 Neuroscience',
          flipped: false,
        },
        {
          name: 'Owen Bai',
          id: 'owen',
          role: 'Photographer',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640040647/MCSS/Members22/DSCF3094-Edit-2_kxiq73.jpg',
          hometown: 'Beijing, China',
          major: 'U4 Computer Science & East Asian Studies',
          flipped: false,
        },
        {
          name: 'Andy Wang',
          id: 'andy',
          role: 'Videographer',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640040749/MCSS/Members22/DSCF3207-Edit_isezev.jpg',
          hometown: 'ShenZhen, China',
          major: 'U3 Bioengineering',
          flipped: false,
        },
        {
          name: 'Xin Rui Li',
          id: 'xinrui',
          role: 'Webmaster',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640041361/MCSS/Members22/DSCF2676_l2nih3.jpg',
          hometown: 'Montreal, QC',
          major: 'U4 Computer Science',
          flipped: false,
        },
        {
          name: 'Emily Xin Yuan Zhang',
          id: 'emily',
          role: 'First Year Rep',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640041489/MCSS/Members22/emily_mgdzud.jpg',
          hometown: 'NanNing, China',
          major: 'U1 Sociology',
          flipped: false,
        },
        {
          name: 'Shirley Wen',
          id: 'shirley',
          role: 'First Year Rep',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640041577/MCSS/Members22/DSC_0009-Edit_lwagxv.jpg',
          hometown: 'Montréal, QC ',
          major: 'U1 Physical Education',
          flipped: false,
        },
        {
          name: 'Emma Liu',
          id: 'emma',
          role: 'First Year Rep',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640041675/MCSS/Members22/DSC_0148-Edit_nnc0ch.jpg',
          hometown: 'Markham, ON',
          major: 'U0 Undeclared Faculty of Management',
          flipped: false,
        },
        {
          name: 'Amy Zhu',
          id: 'amy_z',
          role: 'First Year Rep',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640041824/MCSS/Members22/DSC_0027-Edit_kysycs.jpg',
          hometown: 'Windsor, ON',
          major: 'U0 Kinesiology',
          flipped: false,
        },
        {
          name: 'Amy Huang',
          id: 'amy_h',
          role: 'First Year Rep',
          image: 'https://res.cloudinary.com/die52atcc/image/upload/v1640041914/MCSS/Members22/DSC_0214-Edit_zhfis6.jpg',
          hometown: 'Around Boston',
          major: 'U1 CS & Stats',
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
    padding-top: 120%; /* Aspect Ratio */
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
      padding-top: 120%; /* Aspect Ratio */
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
