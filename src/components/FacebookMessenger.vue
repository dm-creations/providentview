<template>
  <div>
    <!-- Load Facebook SDK for JavaScript -->
    <!-- <div id="fb-root"></div> -->
    <!-- <div class="fb-customerchat" page_id="110130504123888"></div> -->
    <!-- Your Chat Plugin code -->
      <div class="fb-customerchat"
        attribution=setup_tool
        page_id="110130504123888">
      </div>
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
                xfbml      : true,
                version    : 'v7.0',
                CustomerChat: {
                  show: {shouldShowDialog: true}
                }
            });
            // window.FB.CustomerChat.show({shouldShowDialog: true});
        }
    }
      // init() {
      //   window.fbAsyncInit = function() {
      //     window.FB.init({
      //       xfbml            : true,
      //       version          : 'v7.0'
      //     });
      //   };

      //   (function(d, s, id) {
      //     var js, fjs = d.getElementsByTagName(s)[0];
      //     if (d.getElementById(id)) return;
      //     js = d.createElement(s); js.id = id;
      //     js.src = 'https://connect.facebook.net/en_US/sdk/xfbml.customerchat.js';
      //     fjs.parentNode.insertBefore(js, fjs);
      //   }(document, 'script', 'facebook-jssdk'));
      // }
  }
}
</script>