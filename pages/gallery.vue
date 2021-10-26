<template>
  <div class="containera justify-center h100">
    <Flicking :options="options" :plugins="plugins" :hideBeforeInit="true" :firstPanelSize="'200px'">
      <div class="itema" v-for="repo in repositories" :key="repo.id">
        <div class="image-area">
          <div class="image-inner-area">
            <img
              :src="repo.default_img"
            />
          </div>
        </div>
        <div class="info">
          <p class="title"> {{repo.title}}</p>
          <br />
          <p class="subtitle">{{repo.subtitle}}</p>
        </div>
      </div>
      <span slot="viewport" class="flicking-arrow-prev"></span>
      <span slot="viewport" class="flicking-arrow-next"></span>
    </Flicking>
  </div>
</template>

<script>
import { Parallax, Arrow } from "@egjs/flicking-plugins";

export default {
  layout: "default",
  data: () => ({
    repositories: [
      {
        id: 0,
        repo: "darkness",
        title: "Darkness",
        subtitle: "Carelessness in the darkness",
        default_img: require('~/assets/img/darkness/3.JPG')
      },
      {
        id: 1,
        repo: "animals",
        title: "Animals",
        subtitle: "Animal on my holidays",
        default_img: require('~/assets/img/animals/3.JPG')
      },
      {
        id: 3,
        repo: "night",
        title: "Night",
        subtitle: "Photos during the night",
        default_img: require('~/assets/img/night/6.JPG')
      },
      {
        id: 2,
        repo: "Doors",
        title: "Doors",
        subtitle: "Multiples doors in the world",
        default_img: require('~/assets/img/doors/3.JPG')
      },
      {
        id: 4,
        repo: "warm",
        title: "Warm Evening",
        subtitle: "Photos during the sunset",
        default_img: require('~/assets/img/warm/5.JPG')
      },
      {
        id: 5,
        repo: "up",
        title: "Look up",
        subtitle: "Symetric properties",
        default_img: require('~/assets/img/up/5.JPG')
      },
      {
        id: 6,
        repo: "flowers",
        title: "Flowers",
        subtitle: "Power of flowers",
        default_img: require('~/assets/img/flowers/9.JPG')
      },
      {
        id: 7,
        repo: "bw",
        title: "Black and White",
        subtitle: "Classic B&W",
        default_img: require('~/assets/img/bw/2.JPG')
      }
    ],
    inc: 10,
    options: {
      horizontal: true,
      circular: true,
      duration: 500
    },
    plugins: [new Parallax("img", 0.8), new Arrow()]
  }),
  methods: {
    load(name) {
      this.repository = name;
    },
  },
};
</script>
<style lang="scss" scoped>
$button-group-height: 30px !default;
$button-group-line-height: $button-group-height !default;
$button-group-padding: 20px !default;
$button-group-border-radius: 5px !default;
$button-group-font-color: #000 !default;
$button-group-background-color: #777 !default;
$button-group-border-color: #444 !default;
$button-group-selected-background-color: #999 !default;
$button-group-selected-font-color: #fff !default;
$button-group-selected-border-color: #666 !default;


.containera {
  position: relative;
  width: 100%;
  height: 100%;
} 
.button-group {
  &__btn {
    cursor: pointer;

    input[type="radio"],
    input[type="radio"] {
      opacity: 0;
      position: absolute;
    }
  }

  &__label {
    color: $button-group-font-color;
    display: block;
    font-family: "Urbanist";
    font-size: 16px;
    font-weight: 400;
    height: $button-group-height;
    line-height: $button-group-height;
    padding: 0 $button-group-padding;
    text-align: center;
    transition: color opacity 0.6s ease-out;
    opacity: 0.5;
    border: 2px solid black;
  }

  // Border radius on first element
  &__btn &__label {
    border-radius: $button-group-border-radius $button-group-border-radius
      $button-group-border-radius $button-group-border-radius;
  }

  // Styles when selected
  input:checked + &__label {
    border-bottom-color: $button-group-selected-border-color;
    border-top-color: $button-group-selected-border-color;
    color: $button-group-selected-font-color;
    opacity: 1;
    border: 2px solid white;
  }
}

.design {
  transition: all 0.6s ease-out;
}
.design:hover {
  opacity: 1;
}

.cities {
  transition: all 0.6s ease-out;
}
.cities:hover {
  opacity: 1;
}

.night {
  transition: all 0.6s ease-out;
}
.night:hover {
  opacity: 1;
}

.landscape {
  transition: all 0.6s ease-out;
}
.landscape:hover {
  opacity: 1;
}

.people {
  transition: all 0.6s ease-out;
}
.people:hover {
  opacity: 1;
}

.itema {
  cursor: pointer;
  position: relative;
  height: 100%;
  width: 400px;
}
.itema:hover {
  z-index: 2;
}
.itema:hover .image-area {
  width: 120%;
}
.itema .image-area {
  position: absolute;
  width: 100%;
  height: 100%;
  left: 50%;
  transform: translate(-50%) skew(-10deg);
  overflow: hidden;
  transition: width ease 0.5s;
}
.itema .image-area .image-inner-area {
  position: relative;
  width: 100%;
  height: 100%;
  transform: skew(10deg);
}
.itema .image-area .image-inner-area:after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}
.itema img {
  min-width: 100%;
  min-height: 100%;
  position: absolute;
  left: 50%;
  top: -100%;
  bottom: -100%;
  margin: auto 0px;
  transform: translate(-50%);
}
.itema .info {
  position: absolute;
  top: 50%;
  left: 40px;
  transform: translateY(-50%);
}
.itema .info p {
  display: inline-block;
  padding: 10px 15px;
  background: rgba(0, 0, 0, 0.8);
  color: white;
  margin: 5px 0px;
}
.itema .info .subtitle {
}
</style>
