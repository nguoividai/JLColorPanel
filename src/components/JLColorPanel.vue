<template>
  <div class="jl-colorpanel jl-hsv">
    <div class="jl-colors" @mousedown="choose" ref="vcolors">
      <div class="jl-color-pointer" :style="pointerPosition"></div>
      <div class="jl-color-base" :style="{ background: hueString }"></div>
      <div class="jl-brightness-light"></div>
      <div class="jl-brightness-dark"></div>
    </div>
    <div class="jl-color-control">
      <div class="jl-color-present">
        <div :style="{ backgroundColor: rgbString }"></div>
      </div>
      <div class="jl-color-slider">
        <div class="one-hue">
          <slider
            :vertical="false"
            :value="hueSlideValue"
            @change="hueSlide"
          ></slider>
        </div>
        <div class="one-opacity">
          <slider
            :style="opacityStyle"
            :value="opacitySlideValue"
            @change="opacitySlide"
          ></slider>
        </div>
      </div>
    </div>
    <div class="jl-color-value">
      <template>
        <div class="jl-type-ul jl-type-hex" v-show="isHex">
          <ul>
            <li>
              <input v-model="origin.hex" @change="change" />
              <p>{{ colorType.toUpperCase() }}</p>
            </li>
          </ul>
        </div>
      </template>
      <template>
        <div class="jl-type-ul jl-type-rgb" v-show="isRgb">
          <ul>
            <li>
              <input
                v-model.number="origin.rgb.r"
                type="number"
                @change="change"
              />
              <p>R</p>
            </li>
            <li>
              <input
                v-model.number="origin.rgb.g"
                type="number"
                @change="change"
              />
              <p>G</p>
            </li>
            <li>
              <input
                v-model.number="origin.rgb.b"
                type="number"
                @change="change"
              />
              <p>B</p>
            </li>
            <li>
              <input
                v-model.number="origin.alpha"
                type="number"
                step="0.01"
                @change="change"
              />
              <p>A</p>
            </li>
          </ul>
        </div>
      </template>
      <a href="javascript:;" class="jl-color-toggle" @click="toggleMode"></a>
    </div>
    <div class="jl-color-action"></div>
  </div>
</template>

<script>
import jlColorPickerMixin from "../mixin/jlColorPanelMixin";
import "../css/jlColorPanel.css";

export default {
  mixins: [jlColorPickerMixin],
};
</script>

