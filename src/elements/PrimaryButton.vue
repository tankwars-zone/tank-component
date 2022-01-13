<template>
  <component :is="type" :href="href" :type="submit" class="button">
    <span class="left">
      <span class="center">
        <slot />
      </span>
    </span>
  </component>
</template>

<script>
export default {
  name: "PrimaryButton",
  props: {
    type: {
      type: String,
      default: "button",
      validator: value => {
        return value.match(/(button|a)/)
      },
    },
    href: {
      type: String,
      default: "",
    },
    submit: {
      type: String,
      default: null,
      validator: value => {
        return value.match(/(null|submit)/)
      },
    },
  },
}
</script>

<style lang="scss" scoped>
$_mobile_size: 13px auto;

.left {
  background: url("/v3/buttons.png") no-repeat left top;
  padding-left: 17px;
  display: block;

  @include mobile {
    background-size: $_mobile_size;
    padding-left: 13px;
  }
}

.center {
  background: url("/v3/buttons.png") left -182px repeat-x;
  display: block;
  padding: 27px 20px;

  @include mobile {
    padding-top: 16px;
    padding-bottom: 17px;
    background-size: $_mobile_size;
    background-position: left -139px;
  }
}

.button {
  display: inline-flex;
  border: 0;
  text-decoration: none;
  cursor: pointer;
  font-size: 36px;
  line-height: 32px;
  text-shadow: 2px 2px 2px rgba(0, 0, 0, 0.25);
  text-align: center;
  background: url("/v3/buttons.png") no-repeat right -91px;
  padding: 0 17px 0 0;
  color: #fff;
  font-weight: bold;

  @include mobile {
    font-size: 24px;
    line-height: 32px;
    background-size: $_mobile_size;
    padding-right: 12px;
    background-position: right -70px;
  }

  &:hover,
  &:focus {
    color: #0d123a;
    text-shadow: none;
    background-position: right -364px;

    @include mobile {
      background-position: right -279px;
    }

    .left {
      background-position: left -273px;

      @include mobile {
        background-position: left -209px;
      }
    }

    .center {
      background-image: none;
      background-color: #f4bf01;
    }
  }

  &:disabled,
  &.disabled {
    color: #526bab;
    background-image: url("/v3/button-right-disabled.png");

    .left {
      background-image: url("/v3/button-left-disabled.png");
    }

    .center {
      background-image: none;
      background-color: #394079;
    }
  }
}
</style>
