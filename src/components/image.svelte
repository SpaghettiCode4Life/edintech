<script>
      import Profile from '$lib/assets/profile.png';
</script>

<div class="image">
    <img src={Profile} alt="logo" width="100%" height="100%" style=""/>
    <span class="eye"/>
    <span class="eye2"/>
</div>
<style lang=scss>
    .image {
      width: 400px;
      height: 400px;
      position: relative;
      & .eye {
        position: absolute;
        top: 45%;
        left: 37%;
        width: 8px;
        height: 8px;
        background-color: red;
        border-radius: 50%;
        transform: translate(-50%, -50%);
      }
      & .eye2 {
        position: absolute;
        top: 46%;
        left: 62%;
        width: 8px;
        height: 8px;
        background-color: red;
        border-radius: 50%;
        transform: translate(-50%, -50%);
      }
    }
</style>