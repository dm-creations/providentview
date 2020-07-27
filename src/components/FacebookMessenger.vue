<template>
    <div class="fb-customerchat" page_id="110130504123888">
</div>
</template>

<script>
export default {
  name: 'FacebookMessenger',
  mounted(){
    this.init()    
  },
  methods: {
    init () {
        if (window.FB) {
            window.FB.init({
                appId      : '2659694474318162',
                status     : true,
                xfbml      : false,
                version    : 'v7.0'
            })
        }
    }
  }
}
</script>