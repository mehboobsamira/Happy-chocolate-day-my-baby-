// Love Counter
const start = new Date('2025-07-06');
const now = new Date();
const days = Math.floor((now - start)/(1000*60*60*24));
document.getElementById('counter').innerText =
'Since the day we met: ' + days + ' days ❤️';

// Gallery swipe
const photos=document.querySelectorAll('.photo');
let current=0;
function nextPhoto(){
photos[current].classList.remove('active');
current=(current+1)%photos.length;
photos[current].classList.add('active');
}
document.addEventListener('click',nextPhoto);

// Celebration
function celebrate(){
alert('Love accepted ❤️');
}
function bigCelebrate(){
alert('Forever chosen 😌❤️');
}

// Shake detection
let lastX=0,lastY=0;
window.addEventListener('devicemotion',e=>{
let a=e.accelerationIncludingGravity;
if(Math.abs(a.x-lastX)>15||Math.abs(a.y-lastY)>15){
document.body.innerHTML+='❤️';
}
lastX=a.x;lastY=a.y;
});
