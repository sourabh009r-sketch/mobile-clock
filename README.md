# mobile-clock
<!DOCTYPE html>
<html>
<head>
<title>Mobile Clock</title>
<style>
body{
  margin:0;
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  background: linear-gradient(-45deg, #0f2027, #203a43, #2c5364, #1a1a1a);
  background-size: 400% 400%;
  animation: gradientBG 8s ease infinite;
  color:white;
  font-family: Arial, sans-serif;
}

@keyframes gradientBG {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

.time{
  font-size:70px;
  text-shadow:0 0 20px cyan;
}
.time{
  font-size:70px;
}
.sec{
  font-size:30px;
  color:cyan;
}
</style>
</head>
<body>

<div class="time">
<span id="h">00</span>:
<span id="m">00</span>
<span class="sec" id="s">00</span>
<span id="ap">AM</span>
</div>

<script>
setInterval(()=>{
let d=new Date();
let h=d.getHours(),m=d.getMinutes(),s=d.getSeconds(),ap="AM";
if(h>=12) ap="PM";
if(h>12) h-=12;
if(h==0) h=12;
h=h<10?"0"+h:h;
m=m<10?"0"+m:m;
s=s<10?"0"+s:s;
h=document.getElementById("h").innerHTML=h;
document.getElementById("m").innerHTML=m;
document.getElementById("s").innerHTML=s;
document.getElementById("ap").innerHTML=ap;
},1000);
</script>

</body>
</html>
