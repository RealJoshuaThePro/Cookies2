<script>
let colour=null
let logsBefore=0
let logs=75
let planks=0
let lumberjacks=0
function getLogs() {
  logs += 1
}
function setwhite() {
  colour='white'
  window.setTimeout(setred,200);
}
function setred() {
  colour='red'
  window.setTimeout(finishwhite,100);
}
function finishwhite() {
  colour='white'
}
function lumberjack() {
  if(logs > 14) {
    lumberjacks += 1
    logs -= 15
  } else {
    colour='red'
        window.setTimeout(setwhite,100);
  }

  }
function calculateLogs() {
  logsBefore=logs
  logs = lumberjacks + logsBefore
}
var a = setInterval(calculateLogs,3000);
</script>

<main>
<p style="height: 60px">
</p>
<button style="color: {colour}"on:click={lumberjack}>
Lumberjack: 15 logs<br/>
1 log/3s
({lumberjacks} owned)
</button>
<br/>
<br/>
<button on:click={getLogs}>
Free Logs
</button>
<p style="height: 100px">
</p>
<p style="height: 20px">
Logs {logs} <br/>
Planks {planks}
</p>
</main>

<style>

</style>
