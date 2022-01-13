<template>
  <section class="section-news">
    <div class="container">
      <Responsive>
        <template slot="desktop">
          <div class="row">
            <div class="col-12 col-md-9">
              <div class="row">
                <div v-for="item in data" :key="item.title" class="col-12 col-md-6">
                  <div class="title">
                    {{ item.title }}
                  </div>
                  <div>
                    <span class="frc"> FRC20 </span>
                    <span>
                      <span class="item-address">
                        {{ item.address }}
                      </span>
                      <Icon
                        name="copy"
                        size="small"
                        style="cursor: pointer"
                        @click="copy(item.address)"
                      />
                    </span>
                  </div>
                </div>
              </div>
            </div>
            <div class="col-12 col-md-3">
              <div class="title">Audit Report <span class="msc-badge">Verified</span></div>
              <div>
                Our SMC Audited by Verichains
                <ExternalLink :href="report">Read</ExternalLink>
              </div>
            </div>
          </div>
        </template>
        <template slot="ipad">
          <div>
            <div v-show="isShow">
              <div v-for="item in data" :key="item.title" class="mb-4">
                <div class="title">
                  {{ item.title }}
                </div>
                <div class="item-body">
                  <span class="frc"> FRC20 </span>
                  <span class="item-address">
                    {{ item.address }}
                  </span>
                  <span>
                    <Icon
                      name="copy"
                      size="small"
                      style="cursor: pointer"
                      @click="copy(item.address)"
                    />
                  </span>
                </div>
              </div>
              <div>
                <div class="title">Audit Report <span class="msc-badge">Verified</span></div>
                <div>
                  Our SMC Audited by Verichains
                  <ExternalLink :href="report">Read</ExternalLink>
                </div>
              </div>
            </div>
            <div class="toggle-bar" @click="isShow = !isShow">
              <div v-show="!isShow" class="title">Contract Address</div>
              <b-icon :icon="isShow ? 'chevron-up' : 'chevron-down'" aria-hidden="true"></b-icon>
            </div>
          </div>
        </template>
      </Responsive>
    </div>
  </section>
</template>

<script>
import Icon from "../elements/Icon.vue"
import ExternalLink from "../elements/ExternalLink.vue"

export default {
  name: "TopNews",
  components: {
    Icon,
    ExternalLink,
  },
  props: {
    data: {
      type: Array,
      default: () => [
        {
          title: "WBOND Contract Address",
          address: "0x3c714aa0ee19aa7d7f30a63f712080b1393fdb00",
        },
        {
          title: "TGOLD Contract Address",
          address: "0x3c714aa0ee19aa7d7f30a63f712080b1393fdb00",
        },
      ],
    },
    report: {
      type: String,
      default: "",
    },
  },
  data: () => ({
    isShow: false,
  }),
  methods: {
    copy(value) {
      this.$emit("copy", value)
    },
  },
}
</script>

<style lang="scss" scoped>
.section-news {
  background: var(--dark-blue);
  padding-top: 20px;
  padding-bottom: 20px;

  @include mobile {
    padding-top: 12px;
    padding-bottom: 12px;
  }
}

.title {
  font-size: 16px;
  line-height: 16px;
  font-weight: bold;
  font-family: var(--heading-font);
  color: #fff;
  text-transform: uppercase;
  margin-bottom: 5px;

  @include mobile {
    margin: 0;
  }
}

.msc-badge {
  font-weight: 600;
  font-size: 14px;
  line-height: 17px;
  color: var(--dark-blue);
  text-transform: uppercase;
  background: var(--green);
  border-radius: 4px;
  padding: 2px 8px;
}

.frc {
  font-weight: bold;
  font-size: 16px;
  line-height: 17px;
  color: var(--primary);
}

.toggle-bar {
  display: flex;
  color: #fff;
  justify-content: center;

  .title {
    margin-right: 10px;
  }
}

.item-address {
  @include mobile {
    display: inline-block;
    overflow: hidden;
    text-overflow: ellipsis;
    width: 70vw;
    padding-left: 12px;
    padding-right: 12px;
  }
}

.item-body {
  @include mobile {
    display: flex;
    align-items: center;
  }
}
</style>
