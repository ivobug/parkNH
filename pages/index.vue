<template>
  <section>
    <div class="bg"></div>
    <div class="container">
      <div class="row">
        <div class="row-text">
          <img src="../store/zsv.png" alt="" class="logo" />
          <h2>
            Pogledaj kako izgleda <span></span> tvoje ime u parku
            <span></span> Za sva vremena
          </h2>
          <span></span>
          <br />
        </div>

        <div class="row-img row-img3">
          <img
            src="../store/slika_2022_3.jpg"
            alt=""
            @contextmenu="handler($event)"
            class="row-img-position"
          />
          <div class="row-img-name row-img-name3">
            {{ full_name }}
            <div class="row-img-right row-img-right3">{{ num }}</div>
          </div>
        </div>
      </div>

      <div class="row">
        <div class="row-img row-img1">
          <img
            src="../store/slika_2022_1.jpg"
            alt=""
            @contextmenu="handler($event)"
            class="row-img-position"
          />
          <div class="row-img-name row-img-name1">
            {{ full_name }}
            <div class="row-img-right row-img-right1">{{ num }}</div>
          </div>
        </div>

        <div class="row-img row-img2">
          <img
            src="../store/slika_2022_2.jpg"
            alt=""
            @contextmenu="handler($event)"
            class="row-img-position"
          />
          <div class="row-img-name row-img-name2">
            {{ full_name }}
            <div class="row-img-right row-img-right2">{{ num }}</div>
          </div>
        </div>
      </div>

      <div class="row cta">
        <div class="row-text">
          <h2>Želiš da ove fotografije <span></span>postanu stvarnost?</h2>
          <span></span>
          <a href="https://zasvavrimena.nashajduk.hr/" target="_blank">
            <button class="btn">Upiši ime</button></a
          >
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      full_name: this.$route.query.name,
      num: this.$route.query.clanska
    };
  },
  methods: {
    handler: function(e) {
      e.preventDefault();
    }
  }
};
</script>

<style lang="scss">
html {
  margin: 0;
  background-color: #002c4c;
  height: 100%;
  width: 100%;
}
.bg {
  height: 140vh;
  background-image: linear-gradient(
      to right bottom,
      rgba(0, 44, 76, 0.93),
      rgba(0, 44, 76, 0.93)
    ),
    url(../store/slova2.jpg);
  background-size: cover;
  background-position: top;
  position: relative;
}

.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  position: absolute;
  padding: 5rem;
  width: 100%;
  top: 0;
}

.logo {
  height: 7rem;
  margin-bottom: 1.5rem;
}

.row {
  display: flex;
  flex-direction: column;
  align-items: center;

  &.cta {
    position: absolute;
    bottom: 4rem;
    left: 9rem;
  }

  &-text {
    padding-top: 2rem;
    color: #fff;
    font-size: 2.2rem;
    text-align: center;
    font-family: "Josefin Sans", sans-serif;
    font-style: italic;

    & span {
      display: block;
    }
  }

  &-img {
    -moz-user-select: none;
    -khtml-user-select: none;
    -webkit-user-select: none;
    height: 30rem;
    width: 45rem;
    transform: translate(0%, 0%);
    display: grid;
    grid-template-rows: 13rem 5.5rem 11.5rem;
    grid-template-columns: 3.5rem 13.5rem 23rem;
    grid-column: 2/3;
    grid-row: 1/-1;

    &1 {
      grid-template-rows: 11rem 5rem 14rem;
      grid-template-columns: 7.5rem 18.5rem 19rem;
      margin-bottom: 5rem;
    }
    &2 {
      grid-template-rows: 12.5rem 6rem 11.5rem;
      grid-template-columns: 19rem 21rem 5rem;
      margin-bottom: 5rem;
    }
    &3 {
      grid-template-rows: 13.2rem 6.8rem 10rem;
      grid-template-columns: 20.2rem 24.8rem;
    }

    &-position {
      height: 100%;
      grid-row: 1/-1;
      grid-column: 1/-1;
      outline-color: #fff;
      outline-width: 0.5rem;
      outline-style: solid;
    }

    &-name {
      position: absolute;
      left: 1%;
      font-family: "Raleway", sans-serif;
      width: 100%;
      height: 2rem;
      transform-origin: left;
      font-weight: 600;
      grid-column: 2/3;
      grid-row: 2/3;
      text-transform: capitalize;
      z-index: 3;
      white-space: nowrap !important;
      color: white;
      display: flex;
      flex-wrap: nowrap !important;

      &1 {
        transform: perspective(10rem) rotateY(9deg) rotate(3deg);
        font-size: 1.5rem;
        top: 35%;
      }
      &2 {
        transform: perspective(35rem) rotateY(311deg) rotate(0.5deg);
        font-size: 1.4rem;
        top: 34%;
      }
      &3 {
        transform: rotate(0.7deg);
        font-size: 1.6rem;
        top: 33%;
      }
    }

    &-right {
      position: absolute !important;

      &1 {
        top: 0 !important;
        left: 105%;
      }
      &2 {
        top: 0 !important;
        left: 65%;
      }
      &3 {
        top: 0 !important;
        left: 73%;
      }
    }
  }
}

.btn {
  margin-top: 2rem;
  font-family: inherit;
  color: #fff;
  font-size: 1.1rem;
  font-weight: 300;
  background-color: #ae2636;
  cursor: pointer;
  height: 2.5rem;
  width: 8rem;
  border-radius: 4px;
  border: none;

  &:hover {
    background: linear-gradient(145deg, #fb374e, #d42e42);
  }
  &:active {
    box-shadow: inset 5px 5px 10px #ae2636, inset -5px -5px 10px #ff405c;
  }
}

@media only screen and (max-width: 1635px) {
  .container {
    padding: 2rem;
  }

  .row.cta {
    left: 7rem;
  }
}

@media only screen and (max-width: 1538px) {
  .bg {
    height: 240vh;
  }

  .container {
    flex-direction: column;
  }

  .row.cta {
    position: relative;
    left: inherit;
    bottom: inherit;
  }

  .row-img {
    margin-bottom: 3rem;
  }
}

@media only screen and (max-width: 768px) {
  .bg {
    height: 160vh;
  }

  .row-img {
    height: 14rem;
    width: 17rem;
    margin-bottom: 2rem;
    margin-left: -3.9rem;
    &-position {
      outline-width: 0.2rem;
    }
    &1 {
      grid-template-rows: 5.3rem 2.2rem 6.5rem;
      grid-template-columns: 3rem 9rem 5rem;
      justify-content: center;
    }
    &-name1 {
      top: 30%;
      left: 6%;
      font-size: 0.8rem;
      transform: perspective(10rem) rotateY(17deg) rotate(1.8deg);
    }

    &2 {
      grid-template-rows: 5.8rem 2.8rem 5.4rem;
      grid-template-columns: 9rem 8rem;
      justify-content: center;
    }
    &-name2 {
      top: 37%;
      font-size: 0.8rem;
      transform: perspective(35rem) rotateY(311deg) rotate(1.4deg);
    }

    &3 {
      grid-template-rows: 6.2rem 3rem 4.8rem;
      grid-template-columns: 9rem 8rem;
      justify-content: center;
    }
    &-name3 {
      top: 38%;
      left: 7%;
      font-size: 0.8rem;
      transform: rotate(0.5deg);
    }

    &-right1 {
      left: 100%;
    }
    &-right2 {
      left: 105%;
    }
    &-right3 {
      left: 100%;
    }
  }

  .container {
    align-items: center;
    justify-content: center;
    padding: 0;
  }
  .row-text {
    font-size: 1.2rem;
    margin-bottom: 2rem;
  }
  .row {
    margin-bottom: 0rem;
  }

  .btn {
    margin-top: 1rem;
    font-size: 1rem;
    height: 2.3rem;
    width: 7rem;
  }
  .logo {
    height: 2.5rem;
  }
}
</style>
