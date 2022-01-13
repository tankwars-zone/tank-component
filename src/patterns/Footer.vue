<template>
  <div :class="`main-footer--${variant}`">
    <section class="community">
      <div class="container">
        <div class="community-container">
          <div class="heading"><slot name="heading" /></div>

          <div class="social">
            <a
              v-if="facebook"
              class="social-link"
              target="_blank"
              rel="noopener noreferrer"
              :href="facebook"
            >
              <Icon name="facebook" />
            </a>
            <a
              v-if="twitter"
              class="social-link"
              target="_blank"
              rel="noopener noreferrer"
              :href="twitter"
            >
              <Icon name="twitter" />
            </a>
            <a
              v-if="discord"
              class="social-link"
              target="_blank"
              rel="noopener noreferrer"
              :href="discord"
            >
              <Icon name="discord" />
            </a>
            <a
              v-if="telegram"
              class="social-link"
              target="_blank"
              rel="noopener noreferrer"
              :href="telegram"
            >
              <Icon name="telegram" />
            </a>
            <a
              v-if="medium"
              class="social-link"
              target="_blank"
              rel="noopener noreferrer"
              :href="medium"
            >
              <Icon name="medium" />
            </a>
          </div>
        </div>
      </div>
    </section>
    <footer class="footer">
      <div class="footerTxt">
        <slot name="copyright" />
      </div>
    </footer>
  </div>
</template>

<script>
import Icon from "../elements/Icon.vue"

export default {
  name: "Footer",
  components: {
    Icon,
  },
  props: {
    facebook: {
      type: String,
      default: "",
    },
    discord: {
      type: String,
      default: "",
    },
    medium: {
      type: String,
      default: "",
    },
    telegram: {
      type: String,
      default: "",
    },
    twitter: {
      type: String,
      default: "",
    },
    variant: {
      type: String,
      default: "normal",
      validator: val => ["simple"].includes(val),
    },
  },
}
</script>

<style lang="scss" scoped>
.footer {
  position: relative;
  text-align: center;
  text-transform: uppercase;
  font-weight: 600;
  font-size: 14px;
  color: #75a0e1;
}

.footerTxt {
  background: var(--dark-blue) url("/v3/bg-footer.jpg") no-repeat center top;
  padding-bottom: 25px;
  padding-top: 76px;

  @include mobile {
    background-image: url("/v3/bg-footer-mobile.jpg");
  }
}

.rights {
  @include mobile {
    display: block;
  }
}

.heading {
  font-weight: bold;
  font-size: 36px;
  line-height: 32px;
  text-align: center;
  text-transform: uppercase;
  color: var(--dark-blue);
  margin-bottom: 40px;

  @include iPadPro {
    font-size: 26px;
    line-height: 28px;
  }

  @include mobile {
    margin-bottom: 16px;
  }
}

.community {
  background: #373d6e url("/v3/base-community.jpg") no-repeat center top;
  min-height: 743px;
  display: flex;
  align-items: center;
  position: relative;
  background-size: cover;

  @include iPadPro {
    min-height: 686px;
  }

  &::after {
    content: "";
    display: block;
    height: 40px;
    width: 50%;
    position: absolute;
    background: var(--dark-blue) url("/v3/top-contact.jpg") no-repeat;
    right: 0;
    top: 0;
  }
}

.community-container {
  background: url("/v3/base-contact.png") no-repeat center top;
  text-align: center;
  padding: 148px 344px 148px 413px;

  @include iPadPro {
    padding: 85px 178px 93px 257px;
    background-size: 100% auto;
  }

  @include mobile {
    background-image: url("/v3/base-contact-mobile.png");
    background-size: 100% auto;
    padding: 70px 20px 328px;
  }
}

.social {
  display: flex;
  justify-content: space-between;
  max-width: 320px;
  margin-left: auto;
  margin-right: auto;
}

.main-footer {
  &--simple {
    .community {
      background: #191f54;

      @include iPadPro {
        min-height: 475px;
      }

      &::after {
        display: none;
      }
    }

    .footerTxt {
      background: url("/v3/simple-footer.png") no-repeat center top;
    }
  }
}
</style>
