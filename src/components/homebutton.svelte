<div class="button">E</div>

<style lang=scss>
    .button {
      width: 50px;
      height: 50px;
      margin-top: 30px;
      font-family: 'Porter';
      color: #DDEC5B;
      padding: 0;
        font-size: 40px;
        line-height: 40px;
      text-align: center;
      -webkit-animation: rotate 5s normal linear infinite;
      animation: rotate 5s normal linear infinite;
    }
    @keyframes rotate {
      0% {
        -webkit-transform: rotate3d(0, 0, 1, 0deg);
        transform: rotate3d(1, 1, 1, 0deg);
      }
      25% {
        -webkit-transform: rotate3d(0, 0, 1, 30deg);
        transform: rotate3d(0, 1, 1, 30deg);
      }
      50% {
        -webkit-transform: rotate3d(0, 0, 1, 0deg);
        transform: rotate3d(1, 1, 1, 0deg);
      }
      75% {
        -webkit-transform: rotate3d(0, 0, 1, -30deg);
        transform: rotate3d(0, 1, 1, -30deg);
      }
      100% {
        -webkit-transform: rotate3d(0, 0, 1, 0deg);
        transform: rotate3d(0, 0, 1, 0deg);
      }
    }
</style>