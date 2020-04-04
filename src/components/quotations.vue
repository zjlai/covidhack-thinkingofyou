<template>
  <div class="text-overline text-white">{{versetext}}-{{verseref}}</div>
</template>

<script>
export default {
  name: 'Quotations',
  data () {
    return {
      versetext: '',
      verseref: ''
    }
  },
  mounted () {
    this.getverse()
  },
  methods: {
    getverse () {
      const headers = {
        headers: {
          'x-youversion-developer-token': '0PLOGz6WJVh7UKUOcJxgsr_rgKs',
          accept: 'application/json'
        }
      }

      this.$axios.get('https://developers.youversionapi.com/1.0/verse_of_the_day/1?version_id=1', headers)
        .then((res) => {
          this.versetext = res.data.verse.text
          this.verseref = res.data.verse.human_reference
          console.log(this.versetext)
        })
    }
  }
}
</script>
