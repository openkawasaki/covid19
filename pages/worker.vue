<template>
  <div class="Worker">
    <h2 class="Worker-Heading">
      企業の皆様・はたらく皆様へ
    </h2>
    <div v-for="(item, i) in items" :key="i">
      <TextCard :title="item.title" :body="item.body" />
    </div>
  </div>
</template>
<script lang="ts">
import TextCard from '@/components/TextCard.vue'
export default {
  components: {
    TextCard
  },
  data() {
    return {
      items: [
        {
          title: '中小企業経営相談窓口',
          body:
            '<a href="https://www.pref.kanagawa.jp/docs/m6c/cnt/f5782/200205corona.html" target="_blank" rel="noopener">https://www.pref.kanagawa.jp/docs/m6c/cnt/f5782/200205corona.html</a> <br />新型コロナウイルスの流行により影響を受ける県内中小企業に対する「経営相談窓口」を設置します（神奈川県産業労働局）'
        },
        {
          title: '中小企業向け金融支援',
          body:
            '<a href="https://www.pref.kanagawa.jp/docs/m6c/cnt/f5782/200205corona.html" target="_blank" rel="noopener">https://www.pref.kanagawa.jp/docs/m6c/cnt/f5782/200205corona.html</a> <br />新型コロナウイルスの流行により事業活動に影響を受けている中小企業の皆さまに金融支援を実施します（神奈川県産業労働局）'
        },
        {
          title: '宿泊事業者向け支援',
          body:
            '<a href="https://www.pref.kanagawa.jp/docs/ya3/senryaku/korona-kankoujigyousha-sien.html" target="_blank" rel="noopener">https://www.pref.kanagawa.jp/docs/ya3/senryaku/korona-kankoujigyousha-sien.html</a><br />新型コロナウイルス感染症に関する支援等について（神奈川県国際文化観光局）'
        },
        {
          title: '旅館業営業者・住宅宿泊事業者・管理業者の皆様へ',
          body:
            '<a href="https://www.pref.kanagawa.jp/docs/ya3/senryaku/korona-kankoujigyousha-sien.html" target="_blank" rel="noopener">https://www.pref.kanagawa.jp/docs/ya3/senryaku/korona-kankoujigyousha-sien.html</a><br />新型コロナウイルスに関連した宿泊施設の対応について（神奈川県健康医療局）'
        }
      ]
    }
  },
  head() {
    return {
      title: '企業の皆様・はたらく皆様へ'
    }
  }
}
</script>
<style lang="scss">
.Worker {
  &-Heading {
    @include font-size(30);
    font-weight: normal;
    color: $gray-2;
    margin-bottom: 12px;
  }
}
a {
  @include text-link();
}
</style>
