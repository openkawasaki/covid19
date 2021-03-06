<template>
  <v-card class="DataView pa-1">
    <v-toolbar flat class="DataView-content">
      <div class="DataView-TitleContainer">
        <v-toolbar-title>
          {{ title }}
        </v-toolbar-title>
        <slot name="button" />
      </div>
      <v-spacer />
      <slot name="infoPanel" />
    </v-toolbar>
    <v-card-text :class="$vuetify.breakpoint.xs ? 'DataView-CardTextForXS' : 'DataView-CardText'">
      <slot />
    </v-card-text>
    <v-footer class="DataView-Footer">
      <time :datetime="date">{{ date }} 更新</time>
      <a v-if="url" class="OpenDataLink" :href="url" target="_blank" rel="noopener">オープンデータへのリンク
        <v-icon class="ExternalLinkIcon" size="15">
          mdi-open-in-new
        </v-icon>
      </a>
      <a class="DataView-Link" target="_blank" :href="sourceLink">出典: {{ sourceFrom }} <v-icon size="15">mdi-open-in-new</v-icon></a>
    </v-footer>
  </v-card>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class DataView extends Vue {
  @Prop() private title!: string
  @Prop() private date!: string
  @Prop() private url!: string
  @Prop() private info!: any
  @Prop() private sourceFrom!: string
  @Prop() private sourceLink!: string // FIXME expect info as {lText:string, sText:string unit:string}
}
</script>

<style lang="scss">
.DataView {
  &-DataInfo {
    &-summary {
      color: $gray-2;
      font-family: Hiragino Sans;
      font-style: normal;
      font-size: 30px;
      line-height: 30px;
      white-space: nowrap;
      &-unit {
        font-size: 0.6em;
        width: 100%;
      }
    }
    &-date {
      font-size: 12px;
      line-height: 12px;
      color: $gray-3;
      width: 100%;
      display: inline-block;
    }
  }
}
.DataView {
  @include card-container();
  height: 100%;
  &-content {
    height: auto !important;
    .v-toolbar__content {
      align-items: start;
    }
  }
  &-Header {
    background-color: transparent !important;
    height: auto !important;
  }
  &-TitleContainer {
    padding: 14px 0 8px;
    color: $gray-2;
  }
  &-Title {
    @include card-h2();
  }
  &-CardText {
    margin-bottom: 46px;
    margin-top: 35px;
  }
  &-CardTextForXS {
    margin-bottom: 46px;
    margin-top: 70px;
  }
  &-Footer {
    background-color: $white !important;
    margin: 2px 4px 12px;
    @include font-size(12);
    color: $gray-3 !important;
    justify-content: space-between;
    flex-direction: row-reverse;
    .OpenDataLink {
      text-decoration: none;
      .ExternalLinkIcon {
        vertical-align: text-bottom;
      }
    }
  }
}
.v-toolbar__content {
  height: auto !important;
}
.v-toolbar__title {
  white-space: inherit !important;
}
</style>
