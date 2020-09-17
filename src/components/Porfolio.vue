<template>
  <div class="container-fluid px-0">
    <article class="main-image">
      <section>
        <h1>Acessórios Rabicózinho</h1>
        <span>Lindo acessórios feitos a mão.</span>
        <button class="btn btn-xl btn-light" @click="scrollTo('find-more')" >Veja Mais</button>
      </section>
    </article>

    <article id="find-more" class="white-section">
      <section>
        <h3>Quem Somos:</h3>
        <span>Mãe e filhas, apaixonadas por design... Lorem ipsum dolor sit amet consectetur, adipisicing elit. 
          Facilis eius possimus accusantium similique nostrum animi recusandae doloribus incidunt iusto. 
          Praesentium exercitationem molestiae in veritatis quibusdam quos quia, laboriosam ex vero.</span>
        <button class="btn btn-xl btn-dark" @click="scrollTo('offers')" >Nossas idéias</button>
      </section>
    </article>

    <article id="offers" class="blue-section">
      <section class="container">
        <h2>O que oferecemos:</h2>
        <div class="row">
          <div
            class="col-lg-3 col-md-6 mb-5 mb-lg-0"
            v-for="(offer, index) in offers"
            :key="index"
          >
            <div class="icon mx-auto">
              <i class="fas" :class="offer.icon"></i>
            </div>
            <h4>{{ offer.title }}</h4>
            <span>{{ offer.description }}</span>
          </div>
        </div>
      </section>
    </article>

    <article class="second-image">
      <section>
        <h2>Conheça um  <i>pouco</i><br />dos nossos trabalhos!</h2>
        <button class="btn btn-xl btn-dark " @click="scrollTo('recent-projects')" >Projetos Recentes</button>
      </section>
    </article>

    <article id="recent-projects" class="white-section">
      <section class="container">
        <h3>Projetos Recentes</h3>
        <div class="row no-gutters">
          <div class="col-lg-6" v-for="(project, index) in recentProjects" :key="index">
            <a href="" class="portfolio-item">
              <span class="caption">
                <span class="caption-content">
                  <h2>{{ project.title }}</h2>
                  <p class="mb-0">{{ project.description }}</p>
                </span>
              </span>
              <img class="img-fluid" :src="require('../assets/' + project.img)" alt="" />
            </a>
          </div>
        </div>
      </section>
    </article>

    <article id="social" class="blue-section">
      <section class="container">
        <h2>Entre em contato</h2>
        <div class="row">
          <div
            class="col-lg-3 col-md-6 mb-5 mb-lg-0"
            v-for="(social, index) in socialContact"
            :key="index"
          >
            <div class="icon mx-auto">
              <a class="iconSocial"  target="_blank" rel="noopener noreferrer" :href="social.link">
              <i class="fab" :class="social.icon"></i>
              </a>
            </div>
          </div>
        </div>
      </section>
    </article>

  </div>
</template>

<script>
export default {
  data: () => {
    return {
      offers: [
        {
          icon: "fa-hand-holding-heart",
          title: "Feitos a mão",
          description: "Produtos feitos a mão com carinho e atenção.",
        },
        {
          icon: "fa-fist-raised",
          title: "Wakanda Forever",
          description: "Feitos por pessoas negras.",
        },
        {
          icon: "fa-users",
          title: "Família",
          description: "Um projeto familiar, de Porto Alegre.",
        },
        {
          icon: "fa-question-circle",
          title: "Dúvidas?",
          description: "Fale com a gente.",
        },
      ],
      recentProjects: [
        {
          img: "gallery01.jpg",
          title: "Stationary",
          description: "lorem001",
        },
        {
          img: "gallery01.jpg",
          title: "Ice Cream",
          description: "lorem002",
        },
        {
          img: "gallery03.jpg",
          title: "Strawberries",
          description: "lorem003",
        },
        {
          img: "gallery02.jpg",
          title: "Workspace",
          description: "lorem004",
        },
      ],
      socialContact: [
        {
          icon:"fa-instagram",
          link:"https://www.instagram.com/acessorios_rabicozinho/",
        },
        {
          icon:"fab fa-facebook",
          link:"/",
        },
        {
          icon:"fa-twitter",
          link:"/",
        },
        {
          icon:"fa-whatsapp",
          link:"/",
        }
      ]
    };
  },
  methods: {
      scrollTo(element) {
          const el = document.querySelector('#' +element);
          el.scrollIntoView({
              behavior:'smooth',
              block:'start'
          });
      }
  }
};
</script>

<style lang="scss">
@import url("https://use.fontawesome.com/releases/v5.8.1/css/all.css");
@import url("https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css");

article {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  padding: 0 10px;
}

.btn.xl {
  padding: 20px 35px;
  font-family: serif;
  font-size: 1.25rem;
}

.main-image,
.second-image {
  min-height: 100vh;
  background-size: cover;
  padding: 0 10px;
  text-align: center;

  h1 {
    font-size: 5rem;
    font-weight: bold;
  }

  h2 {
    font-size: 3rem;
    font-weight: bold;
    margin-bottom: 30px;
  }

  span {
    display: block;
    padding-bottom: 30px;
    font-size: 1.6rem;
    font-weight: bold;
  }
}

.main-image {
  background: url("../assets/img8.jpg") center center;
}

.second-image {
  background: url("../assets/img2.jpg") center center;
}

.white-section {
  padding: 120px 10px;
  background-color: #fff;
  text-align: center;

  h3 {
    font-size: 2rem;
    font-weight: bold;
  }

  span {
    display: block;
    padding-bottom: 30px;
    font-size: 1.25rem;
  }
  .row {
    padding-top: 50px;
  }

  .portfolio-item {
    display: block;
    position: relative;
    overflow: hidden;

    .caption {
      display: flex;
      height: 100%;
      width: 100%;
      position: absolute;
      top: 0;
      bottom: 0;
      z-index: 1;
      background-color: rgba($color: #000000, $alpha: .2);
      transition: transform .2s linear;

      .caption-content {
        text-align: left;
        color: #fff;
        margin: auto 2rem 2rem;
      }
    }

    img {
      transition: transform .2s linear;
    }
    &:hover {
      img {
        transform: scale(.9);
      }
      .caption {
        transform: scale(.9);
        background-color: rgba($color: #000000, $alpha: .5);
      }
    }
  }
}

.blue-section {
  padding: 120px 10px;
  background-color: #1d809f;
  color: #fff;
  text-align: center;

  h2 {
    font-size: 3rem;
    font-weight: bold;
    margin-bottom: 50px;
  }

  h4 {
    font-size: 1.6rem;
    padding-top: 20px;
  }

  .icon {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 120px;
    height: 120px;
    background-color: #fff;
    color: #1d809f;
    border-radius: 50%;
  .iconSocial {
    padding: 25px;
  }
    i {
      font-size: 2rem;
    }
  }
}
</style>
