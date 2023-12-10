<script>
	import Background from '../components/background.svelte';
	import Homebutton from '../components/homebutton.svelte';
	import Image from '../components/image.svelte';
	import Index from '../components/index.svelte';
  import Paragraph from '../components/paragraph.svelte';
	import Title from '../components/title.svelte';
</script>

<div class="global">
  <div class="background">
    <Background/>
    <div class="view">
      <div class="head">
        <Homebutton/>
        <Index/>
      </div>
      <div class="container">
        <Image/>
        <div class="content">
          <Title/>
          <Paragraph/>
        </div>
      </div>
    </div>
  </div>
</div>

<style lang=scss>
    .global {
        width: 100%;
        height: 100%;
        background-color: #322C46;
       
    }
    .background {
        width: 100%;
        height: 100%;
        position: relative;
        display: flex;
        justify-content: center;
       
    }
    .view {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      padding: 0 20px;
      @media (min-width: 768px) {
          padding: 0 80px;
      }
      @media (min-width: 1024px) {
          padding: 0 120px;
      }
    } 
    .head {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: start;
    }

    .container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      @media (min-width: 768px) {
        width: 80%;
         flex-direction: row-reverse;
         justify-content: space-between;
      }
    }

    .content {
        @media (min-width: 768px) {
            width: 70%;
            max-width: 800px;
        }
    }
</style>