+++
title = "Dice"
date = 2018-04-15T22:22:55-05:00
tags = [""]
categories = [""]
draft = false
+++

<script>
function roll() {
    var num = document.getElementById("dnum").value;
    var max = document.getElementById("dmax").value;
    var print = "";
    
    var sum = 0;
    var dice = 0;
    
    for(var i = 0; i < num; i++){
    	dice = Math.ceil(Math.random()*max);
		print += dice + "<br />";
		sum += dice;
    }
    print += "sum: " + sum;

    document.getElementById("print").innerHTML = print;
}
</script>

<center>
Number <input type="number" id="dnum" value="1" min="0" max="10"></input>
<br />
Dice Type <input type="number" id="dmax" value="6" min="1"></input>
<br />
<button type="button" onclick="roll()">Roll!</button>
<br />
<br />
<span id="print"></span>
</center>
