<template>
  <section>
    <div class="bg"></div>
      <div class="container">
        <div class="row">
          <div class="row-text">
            <img src="../store/zsv.png" alt="" class="logo">
            <h2> Želiš da ove slike <span></span>postanu stvarnost?</h2> <span></span>
              <a href="https://zasvavrimena.nashajduk.hr/" target="_blank">
                <button class="btn">Upiši ime</button></a>
          </div>
            <!-- <div class="row-img row-img2">
              <img src="../store/park2.jpg" alt="" @contextmenu="handler($event)" class="row-img-position">
              <div class="row-img-name row-img-name2"> {{full_name}}<div class="row-img-right row-img-right2">{{num}}</div></div>
            </div> -->
        </div>



        <div class="row">
          <div class=" row-img row-img1">
              <img src="../store/park.jpg" alt="" @contextmenu="handler($event)" class="row-img-position">
              <div class="row-img-name row-img-name1"> {{full_name}}<div class="row-img-right row-img-right1">{{num}}</div></div>
          </div>
          <div class="row-img row-img3">
            <img src="../store/park3.jpg" alt="" @contextmenu="handler($event)" class="row-img-position">
            <div class="row-img-name row-img-name3"> {{full_name}}<div class="row-img-right row-img-right3">{{num}}</div></div>
          </div>
        </div>
      </div>
  </section>
</template>

<script>
export default {
 data(){
   return{
     full_name:this.$route.query.name,
     num:this.$route.query.clanska,
   }
 },
 methods : {
    handler: function(e) {
        e.preventDefault();
     }
}
}
</script>

<style lang="scss">
html{
  margin:0;
  background-color: #002C4C;
  height: 100%;
  width: 100%;
}
.bg{
    height: 100vh;
    background-image: linear-gradient(
        to right bottom,
        rgba(0, 44, 76, 0.93),
        rgba(0, 44, 76, 0.93)), 
        url(../store/slova.jpg);
    background-size: cover;
    background-position: top;
    position:relative;
}

.container{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  position: absolute;
  padding: 5rem;
  width: 100%;
  top: 0;
}

.logo{
  height: 4rem;
  margin-bottom: .5rem;
}

.row{
  display: flex;
  flex-direction: column;
  align-items: center;

  &-text{
    padding-top: 2rem;
    color: #fff;
    font-size: 2.2rem;
    text-align: center;
    font-family: 'Josefin Sans', sans-serif;
    font-style: italic;
    margin-bottom: 5rem;

    & span{
      display: block;
    }
  }

  &-img{
    -moz-user-select: none;
    -khtml-user-select: none;
    -webkit-user-select: none;
    height: 30rem;
    width: 40rem;
    transform: translate(0%,0%);
    display: grid;
    grid-template-rows:13rem 5.5rem 11.5rem;
    grid-template-columns:3.5rem 13.5rem 23rem;
    grid-column: 2/3;
    grid-row: 1/-1;
    

    &1{
      grid-template-rows:13rem 5.5rem 11.5rem;
      grid-template-columns:3.5rem 13.5rem 23rem;
          margin-bottom: 5rem;

    }
    &2{
      grid-template-rows:13rem 2rem 15rem;
      grid-template-columns:6.7rem 5.7rem 20rem;
      margin-bottom: 5rem;
    }
    &3{
      grid-template-rows:17.5rem 2rem 10.5rem;
      grid-template-columns:25.9rem 5.7rem 20rem;
    }

    &-position{
      height: 100%;
      grid-row: 1/-1;
      grid-column: 1/-1;
      outline-color:#fff;
      outline-width: .5rem;
      outline-style: solid;
    }


    &-name{
        position: absolute;
        left: 1%;
        font-family: 'Raleway', sans-serif;
        width: 100%;
        height: 2rem;
        transform-origin: left;
        font-weight: 600;
        grid-column: 2/3;
        grid-row: 2/3;
        text-transform:capitalize;
        z-index: 3;
        white-space: nowrap !important;
        color: white;
        display: flex;
        flex-wrap: nowrap !important;

        &1{
          transform: perspective(10rem) rotateY(20deg) rotate(-1deg);
          font-size: 1.6rem;
          top: 35%;
        }
        &2{
          transform: perspective(10rem) rotateY(20deg) rotate(-2deg);
          font-size: .5rem;
          top: 38%;
        }
        &3{
          transform: perspective(10rem) rotateY(-5deg) rotate(2deg);
          font-size: .5rem;
          top: 33%;
        }
    }

    &-right{
      position: absolute !important;

      &1{
        top: 0 !important;
        left: 155%;
      }
      &2{
        top: 0 !important;
        left: 96%;
      }
      &3{
        top: 0 !important;
        left: 100%;
      }
    }
  }




}

.btn{
  margin-top:2rem ;
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

  &:hover{
    background: linear-gradient(145deg, #fb374e, #d42e42);
  }
  &:active{
    box-shadow: inset 5px 5px 10px #ae2636, 
    inset -5px -5px 10px #ff405c;
  }
}

@media only screen and (max-width: 1466px){
  .container{
    padding: 2rem;
  }
}

@media only screen and (max-width: 1369px){
  .container{
    flex-direction: column;
  }

}

@media only screen and (max-width: 670px){
  .row-img{
    margin-bottom: 2rem;
    margin-left: -2.2rem;
    &-position{
      outline-width: 0;
      outline-color:transparent;
    }
  &1{
    height:17rem;
    width: 15rem;
    grid-template-rows:7.5rem 3rem 6.5rem;
    grid-template-columns:2rem 7.5rem 10.6rem;
    justify-content: center;
  }
  &-name1{
    top: 34%;
    font-size: .7rem;
    transform: perspective(10rem) rotateY(20deg) rotate(-2deg);
  }

  &2{
    height:17rem;
    width: 15rem;
    grid-template-rows:7.4rem 1.1rem 8.5rem;
    grid-template-columns: 3.82rem 3.3rem 13rem;
    justify-content: center;
  }

  &-name2{
    top: 37%;
    font-size: .28rem;
    transform: perspective(10rem) rotateY(20deg) rotate(-2deg);
  }

  &3{
    height:17rem;
    width: 15rem;
    grid-template-rows:10rem 1rem 6rem;
    grid-template-columns: 14.7rem 4.3rem 1rem;
    justify-content: center;
  }

  &-name3{
    top: 33%;
    font-size: .28rem;
    transform: perspective(10rem) rotateY(20deg) rotate(0deg);
  }

  &-right1{
    left:  110%;
  }
  &-right2{
    left: 86%;
  }
  &-right3{
    left: 100%;
  }
  }


  .container{
    align-items: center;
    justify-content: center;
    padding: 0;

  }
  .row-text{
    font-size: 1.2rem;
    margin-bottom: 2rem;
  }
  .row{
    margin-bottom: 0rem;
  }

  .btn{
  margin-top:1rem ;
  font-size: 1rem;
  height: 2.3rem;
  width: 7rem;
}
.logo{
  height: 2.5rem;
}
}




</style>