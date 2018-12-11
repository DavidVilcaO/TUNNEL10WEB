<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p style="max-width: 700px; margin-left: auto; margin-right: auto;">
      Download large files with the easy-to-use BitTorrent client. Enjoy fast speeds, a simple interface, powerful options and more. Get started now with free, unlimited downloading.
    </p>
    <a class="button" v-if="os == 'Mac OS'" @click="download()">
      <i class="fab fa-apple"></i>
      <span>
        Download for macOS
      </span>
    </a>
    <a class="button" v-if="os == 'Windows'" @click="download()">
        <i class="fab fa-windows"></i>
        <span>
          Download for Windows
        </span>
    </a>
    <a class="button" v-if="os == 'Linux'">
      <i class="fab fa-linux"></i>
        <span>
          Download for Linux
        </span>
    </a>
    <a class="button" v-if="os == 'iOS'">
      <i class="fab fa-apple"></i>
        <span>
          Download for iOS
        </span>
    </a>
    <a class="button" v-if="os == 'Android'">
      <i class="fab fa-android"></i>
        <span>
          Download for Android
        </span>
    </a>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  data: () => {
    return {
      os: ''
    }
  },
  created() {
    var userAgent = window.navigator.userAgent,
        platform = window.navigator.platform,
        macosPlatforms = ['Macintosh', 'MacIntel', 'MacPPC', 'Mac68K'],
        windowsPlatforms = ['Win32', 'Win64', 'Windows', 'WinCE'],
        iosPlatforms = ['iPhone', 'iPad', 'iPod'],
        os = null;

    if (macosPlatforms.indexOf(platform) !== -1) {
      os = 'Mac OS';
    } else if (iosPlatforms.indexOf(platform) !== -1) {
      os = 'iOS';
    } else if (windowsPlatforms.indexOf(platform) !== -1) {
      os = 'Windows';
    } else if (/Android/.test(userAgent)) {
      os = 'Android';
    } else if (!os && /Linux/.test(platform)) {
      os = 'Linux';
    }

    console.log('os: ', os)
    this.os = os
  },
  computed: {
  },
  methods: {
    download () {
      console.log('download!')
      if(this.os == 'Windows') {
        let uri = './windows/Tunnel10 Setup 0.2.0.exe'
        let thefilename = 'Tunnel10 Setup 0.2.0.exe'
        
        var link = document.createElement("a");
        link.download = thefilename;
        // Construct the uri
        link.href = uri;
        document.body.appendChild(link);
        link.click();
        // Cleanup the DOM
        document.body.removeChild(link);
      }
      if(this.os == 'Mac OS') {
        let uri = './mac/Tunnel10-0.1.0.dmg'
        let thefilename = 'Tunnel10-0.1.0.dmg'
        
        var link = document.createElement("a");
        link.download = thefilename;
        // Construct the uri
        link.href = uri;
        document.body.appendChild(link);
        link.click();
        // Cleanup the DOM
        document.body.removeChild(link);
      }
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="stylus">
 h1 
  font-size 60px
  font-weight: 800;
  text-align: center;
  color: white;
  margin-top: 80px;
  // font-family: Avenir;
  background: linear-gradient(#4CB0F4, #8526FF);
  -webkit-text-fill-color: transparent;
  -webkit-background-clip: text;

@media screen and (max-width: 600px) {
  h1 {
    font-size 40px
  }
}


p 
    text-align: center;
    font-size: 16px;
    font-weight: 300;
    margin-top: 60px;
    color: white;
    // font-family: Avenir;

.button 
    width: 300px;
    height: 45px;
    background: white;
    text-align: center;
    display: inline-block;
    margin: 30px;
    border-radius: 4px;
    cursor: pointer;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    span
      font-size: 16px;
      // font-family: avenir;
      line-height: 45px;
      font-weight: 500;
      background: linear-gradient(#4CB0F4, #8526FF);
      -webkit-text-fill-color: transparent;
      -webkit-background-clip: text;
    i
      margin-right: 10px;
      background: linear-gradient(#4CB0F4, #8526FF);
      -webkit-text-fill-color: transparent;
      -webkit-background-clip: text;
      
@media screen and (max-width: 600px) {
  .button {
    margin: 0px;
  }
}
</style>
