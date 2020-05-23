//Reversing the direction

var timer = 16;  //game length
var Timer; //to start the timer
var virusXPos = 0; 
var virusYPos = 320; 
var virusXPos2 = -160; 
var virusYPos2 = 280; 
var virusXPos3 = -300; 
var virusYPos3 = 280; 
var bulletXPos = 0;
var gunYPos = 50; 
var bulletYPos = gunYPos; 
var bulletVirusDist = 1000; //any large number
var virusXSize = 50; 
var virusYSize = 50;
var coronaKilled = false; 
var counter = 0; 
var dif = 4; //difficulty level
var dif2 = 5; //difficulty level
var dif3 = 5; //difficulty level
var bulletsFiredX = []; 
var bulletsFiredY = [];
var bulletsCollisionDist = []; 
var score = 0; 
var isHit = []; 
var coronavirusImg;
var sanitizerImg;
var virusVisibility = true; 
var sanitizerLevel = 15; 
// var bestScore = []; //create YourOwnBestScore the games reloads everytime I run the program again and empties the array. There should be a 'replay' option in the game. 


function preload(){
  coronavirusImg = loadImage('coronavirus.png');
  coronavirusImg2 = loadImage('c2.jpeg');
  coronavirusImg3 = loadImage('c3.jpeg');
  sanitizerImg = loadImage('sanitizer.jpg');
  waterImg = loadImage('water.jpeg');
  LogoImg = loadImage('Logo.jpeg');
  gunSound = loadSound("gun1.mp3");
  killSound = loadSound("germKill.mp3");
  backgroundSound = loadSound("goCorona.mp3");
}
  
function setup() 
{
  createCanvas(640, 400);
  // frameRate(100);
  // playSound
  // backgroundSound.play();
  
  
  
}

function draw() 

  {
  background(255);
  // text(counter,300,50);
  textAlign(CENTER, CENTER);
  textSize(50);
  text(timer-1, width/2, height/2);
    
  //Drawing Sanitizer Level 
  noStroke();
 
    stroke("black");
    noFill();
 rect(80,10,15*15,35);   
 
    fill("blue");  
 rect(80,10,15*sanitizerLevel,35);   
    
 
 //-----------------//-----------------//----------------- 
    // console.log(frameCount); 
  //Putting the 15s timer in   
  if (frameCount % 60 == 0 && timer > 0 && Timer == true && sanitizerLevel > 0) { // if the frameCount is divisible by 60, then a second has passed. it will stop at 0
  
    timer --;
    
    console.log("check1");
  }
  if (sanitizerLevel == 0 || timer == 0) {
      textSize(25);

    text("Game Over! You killed "+score+" coronavirus. :D", width/2, height*0.6);
    // bestScore = score; 
    noLoop();
  
  }
    
 //-----------------//-----------------//-----------------     
    
    
  
  image(LogoImg,0,0,55,55);
    
//Creating a Gun Object below which can be moved by mouse
  image(sanitizerImg,mouseX,gunYPos,70,70);
  
    
//trying to shoot a bullet from this on mouseClicked  
//working fine for one bullet, when the array becomes empty. 

  //setting virus visibility to true after 2 secs   
  
  
    
    // rect(virusXPos,virusYPos,50,50); 
    image(coronavirusImg,virusXPos,virusYPos,65,65);
      virusXPos = virusXPos + dif; 
    
        if (virusXPos+dif == width )
      {
        virusXPos = 0; 
        rect(virusXPos,virusYPos,50,50); 
      }
    
    //2nd virus
      image(coronavirusImg2,virusXPos2,virusYPos2,40,40);
      virusXPos2 = virusXPos2 + dif2; 
    
        if (virusXPos2+dif2 == width )
      {
        virusXPos2 = 0; 
        rect(virusXPos2,virusYPos2,40,40); 
      }
    
       //3rd virus
      image(coronavirusImg3,virusXPos3,virusYPos3,50,50);
      virusXPos3 = virusXPos3 + dif3; 
    
        if (virusXPos3+dif3 == width )
      {
        virusXPos3 = 0; 
        rect(virusXPos3,virusYPos3,25,25); 
      }
    
    
    
   //Displaying the score
    

  // console.log(score); 
  textSize(20);  
  textAlign(CENTER, CENTER);
  text("Total Virus Killed",width-100,25);  
  text(score,width-100,50);  
  // console.log(bulletsFiredX.length);
    
  for (var i = 0; i< bulletsFiredX.length; i ++)
    {
      // console.log("check"); 
      noStroke();
      fill("black");
      image(waterImg,bulletsFiredX[i],bulletsFiredY[i],20,20); 
      
  
      bulletsFiredY[i]=bulletsFiredY[i]+5;
      
      //1st Virus

      //adding the collision conditions here 
     bulletsCollisionDist[i] = int(dist(bulletsFiredX[i],bulletsFiredY[i],virusXPos,virusYPos)); 
      
      // console.log(bulletsCollisionDist[i]); 
      
         //adding the collision condition 
      if (bulletsCollisionDist[i] < 60 && isHit[i] == false)
      {
        killSound.play(); 
        // console.log("hit"); 
        isHit[i] = true; 
        
        score++; 
        virusXPos = -200; 
        // virusVisibility = false; 
      } 
      
      if (bulletsFiredY[i] == 0)
        {
          bulletsFiredX.splice(i,1);
          bulletsFiredY.splice(i,1);
          isHit.splice(i,1); 
        }
     
      //2nd virus 
      
         bulletsCollisionDist[i] = int(dist(bulletsFiredX[i],bulletsFiredY[i],virusXPos2,virusYPos2)); 
      
      // console.log(bulletsCollisionDist[i]); 
      
     
         //adding the collision condition 
      if (bulletsCollisionDist[i] < 60 && isHit[i] == false)
      {
        killSound.play(); 
        // console.log("hit"); 
        isHit[i] = true; 
        
        score++; 
        virusXPos2 = -200; 
        // virusVisibility = false; 
      } 
      
      if (bulletsFiredY[i] == 0)
        {
          bulletsFiredX.splice(i,1);
          bulletsFiredY.splice(i,1);
          isHit.splice(i,1); 
        }
      
    //2nd virus 
      
         bulletsCollisionDist[i] = int(dist(bulletsFiredX[i],bulletsFiredY[i],virusXPos3,virusYPos3)); 
      
      // console.log(bulletsCollisionDist[i]); 
      
     
         //adding the collision condition 
      if (bulletsCollisionDist[i] < 60 && isHit[i] == false)
      {
        killSound.play(); 
        // console.log("hit"); 
        isHit[i] = true; 
        
        score++; 
        virusXPos3 = -200; 
        // virusVisibility = false; 
      } 
      
      if (bulletsFiredY[i] == 0)
        {
          bulletsFiredX.splice(i,1);
          bulletsFiredY.splice(i,1);
          isHit.splice(i,1); 
        }
      
      
      
    } 
    

  }            

    
//trying to make the virus disappear when the bullet hits. 
  

   // console.log(bulletVirusDist);  //the distance function works fine 
    
//making the virus disappear when the bullet hits 

    
  function mouseClicked() 
  {
  sanitizerLevel--; 
  // console.log(sanitizerLevel);    
  gunSound.play();
  Timer = true;   
  bulletXPos = mouseX;
  bulletsFiredX.push(bulletXPos+3); 
  bulletsFiredY.push(gunYPos+7);   
  isHit.push(false); //every bullet starts with no hit. 

  // console.log("new bullet is Fired");   
  // console.log(bulletsFiredX);    
  // console.log(isHit);
    
  } 

