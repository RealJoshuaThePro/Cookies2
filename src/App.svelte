<script>
let flashclass=""
let colour=null
let logsBefore=0
let logs=75
let planks=0
let lumberjacks=0
document.onkeypress=function(e){
  if (e.keyCode === 108) {
    getLogs()
  }
}
function getLogs() {
  logs += 1
}
function lumberjack() {
  if(logs > 14) {
    lumberjacks += 1
    logs -= 15
  } else {
    flashtwice()
  }
  }
function calculateLogs() {
  logsBefore=logs
  logs = lumberjacks + logsBefore
}
function flashtwice() {
  flashclass="flash"
  setTimeout(() => {flashclass=""}, 750)
}
var a = setInterval(calculateLogs,3000);
</script>

<main>
<p style="height: 60px">
</p>
<button class="{flashclass}" style="color: {colour}"on:click={lumberjack}>
Lumberjack: 15 logs<br/>
1 log/3s
({lumberjacks} owned)
</button>
<br/>
<br/>
<button on:click={getLogs}>
Free Logs (L)
</button>
<p style="height: 100px">
</p>
<p style="height: 20px">
Logs {logs} <br/>
Planks {planks}
</p>
</main>

<style>
.flash{animation: blinker 0.25s ease infinite;}
@keyframes blinker{
  50%{
    color: red;
  }
}
</style>
