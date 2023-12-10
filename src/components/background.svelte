<script>
   import P5 from 'p5-svelte';
    const sketch = (p5) => {
  
      class Particle {
          constructor(){
            this.x = p5.random(0,p5.width);
            this.y = p5.random(0,p5.height);
            this.r = p5.random(1,4);
            this.xSpeed = p5.random(-2,1);
            this.ySpeed = p5.random(-1,1);
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

<P5 {sketch} />