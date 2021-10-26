<template>
  <div class="container justify-center h100">
    <div class="row button-group">
      <Flicking :options="{horizontal: true}">
        <label class="button-group__btn col" @click="load('animals')"
          ><input type="radio" name="check" />
          <span class="button-group__label design">Animals</span></label
        >
        <label class="button-group__btn col" @click="load('doors')"
          ><input type="radio" name="check" />
          <span class="button-group__label design">Doors</span></label
        >
        <label class="button-group__btn col" @click="load('design')"
          ><input type="radio" name="check" />
          <span class="button-group__label design">Design</span></label
        >
        <label class="button-group__btn col" @click="load('cities')"
          ><input type="radio" name="check" />
          <span class="button-group__label cities">Cities</span></label
        >
        <label class="button-group__btn col" @click="load('night')"
          ><input type="radio" name="check" />
          <span class="button-group__label night">Night</span></label
        >
        <label class="button-group__btn col" @click="load('landscapes')"
          ><input type="radio" name="check" />
          <span class="button-group__label landscape">Landscapes</span></label
        >
        <label class="button-group__btn col" @click="load('peoples')"
          ><input type="radio" name="check" />
          <span class="button-group__label people">People</span></label
        >
      </Flicking>
    </div>
  </div>
</template>

<script>
import { Parallax } from "@egjs/flicking-plugins";

export default {
  layout: "default",
  data: () => ({
    repository: "animals",
    inc: 10,
    options: {
      horizontal: true,
    },
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
</style>
