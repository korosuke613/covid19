<template>
  <data-view :title="title" :title-id="titleId" :date="date">
    <template v-slot:button>
      <ul :class="$style.notes">
        <li>
          <t-i18n>
            {{ $t('（注）医療機関が保険適用で行った検査は含まれていない') }}
          </t-i18n>
        </li>
        <li>
          <t-i18n>
            {{
              $t(
                '（注）検査実施人数には、チャーター機帰国者、クルーズ船乗客等は含まれていない'
              )
            }}
          </t-i18n>
        </li>
        <li>
          <t-i18n>
            {{
              $t(
                '（注）速報値として公開するものであり、後日確定データとして修正される場合あり'
              )
            }}
          </t-i18n>
        </li>
      </ul>
    </template>
    <slot />
  </data-view>
</template>

<style lang="scss" module>
ul.notes {
  margin-top: 10px;
  margin-bottom: 0;
  padding-left: 0 !important;
  font-size: 12px;
  color: $gray-3;

  > li {
    list-style-type: none;
  }
}
</style>

<script lang="ts">
import Vue from 'vue'
import DataView from '@/components/DataView.vue'
import TI18n from '@/components/TI18n.vue'

export default Vue.extend({
  components: { DataView, TI18n },
  props: {
    title: {
      type: String,
      default: ''
    },
    titleId: {
      type: String,
      default: ''
    },
    date: {
      type: String,
      default: ''
    }
  }
})
</script>
