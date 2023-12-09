<script>
  import P5 from 'p5-svelte';
  import Profile from '$lib/assets/profile.png';
  
  const projects = [
    {
      name: 'Project 1',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec euismod, nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl',
      link: 'https://www.google.com',
    },
    {
      name: 'Project 2',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec euismod, nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl',
      link: 'https://www.google.com',
    },
    {
      name: 'Project 3',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec euismod, nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl',
      link: 'https://www.google.com',
    },
    {
      name: 'Project 4',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec euismod, nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl',
      link: 'https://www.google.com',
    },
    {
      name: 'Project 5',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec euismod, nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl',
      link: 'https://www.google.com',
    }
  ];
  
  const sketch = (p5) => {

    class Particle {
        constructor(){
          this.x = p5.random(0,p5.width);
          this.y = p5.random(0,p5.height);
          this.r = p5.random(1,8);
          this.xSpeed = p5.random(-2,2);
          this.ySpeed = p5.random(-1,1.5);
        }

        createParticle() {
            p5.noStroke();
            p5.fill('rgba(200,169,169,0.5)');
            p5.circle(this.x,this.y,this.r);
        }
      
        moveParticle() {
          if(this.x < 0 || this.x > p5.width)
            this.xSpeed*=-1;
          if(this.y < 0 || this.y > p5.height)
            this.ySpeed*=-1;
          this.x+=this.xSpeed;
          this.y+=this.ySpeed;
        }

        joinParticles(particles) {
          particles.forEach(element =>{
            let dis = p5.dist(this.x,this.y,element.x,element.y);
            if(dis<85) {
              p5.stroke('rgba(255,255,255,0.04)');
              p5.line(this.x,this.y,element.x,element.y);
            }
          });
        }
    }

    let particles = [];

    p5.setup = () => {
      p5.createCanvas(p5.windowWidth - 100, 600);
      for(let i = 0;i<p5.width/10;i++){
        particles.push(new Particle());
      }
    }

    p5.draw = () => {
      p5.background('#322C46');
      for(let i = 0;i<particles.length;i++) {
        particles[i].createParticle();
        particles[i].moveParticle();
        particles[i].joinParticles(particles.slice(i));
      }
    }
  };
</script>

<div class="global">
  <div class="rotate">E</div>
  <div class="index">
    {#each projects as project}
    <p>{project.name}</p>
    {/each}
  </div>
  <div class="background">
    <P5 {sketch} />
    <div class="container">
      <div class="image">
        <img src={Profile} alt="logo" width="100%" height="100%" style=""/>
        <span class="eye"/>
        <span class="eye2"/>
      </div>
        <div class="title">
          <p class="part1">ED</p><p class="part2">in Tech</p>
        </div>
        <hr class="separator"/>
        <p class="paragraph">
          My name is Edith. Im a developper and enthusiast design.
          I have work experience in enterprises as well as on small projects own my own. 
          Im a tech passionate but also a persona with lot of hobbies and interest. Check this out!
        </p>  
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
        position: relative;
        display: flex;
        justify-content: center;
    }
    .container {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
    }
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
    .title {
      display: flex;
      height: 50px;
      flex-direction: row;
      justify-content: center;
      align-items: end;

      & .part1 {
		    font-family: 'Porter';
        color: #DDEC5B;
        padding: 0;
        font-size: 40px;
        line-height: 40px;
        margin-right: 8px;
	    } 
      & .part2 {
        font-family: 'Prompt-Regular';
        color: #DDEC5B;
        padding: 0;
        font-size: 40px;
        line-height: 40px;
      }
    }

    .rotate {
      width: 50px;
      height: 50px;
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
   
    .paragraph {
        font-family: 'Prompt-Regular';
        font-size: 20px;
        color: white;
        width: 50%;
        @media (min-width: 768px) {
            width: 80%;
        }
    }

    .separator {
        width: 50%;
        margin-left: 25%;
        margin-top: 5%;
        border: 1px solid #DDEC5B;
        color: #DDEC5B
    }

    .index {
      font-family: 'Prompt-Regular';
      z-index: 1;
      border-radius: 4px;
       position: absolute;
        top: 0;
        right: 50px;
      height: fit-content;
      width: 200px;
      display: flex;
      flex-direction: column;
      padding: 10px;
      background: #DDEC5B;
    }
</style>