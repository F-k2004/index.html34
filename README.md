<!DOCTYPE html>
<html lang="fa">
<head>
<meta charset="UTF-8">
<title>⚡ Plasma Energy Field</title>
<style>
  tml, body {
    margin: 0;
    padding: 0;
    overflow: hidden;
    background: #03030f;
    font-family: sans-serif;
  }
  #info {
    position: absolute;
    left: 10px;
    top: 10px;
    padding: 8px 14px;
    border-radius: 10px;
    background: rgba(255,255,255,0.05);
    color: #9fe3ff;
    backdrop-filter: blur(8px);
  }
</style>
</head>
<body>
<canvas id="c"></canvas>
<div id="info">⚡ Plasma Energy — Move Mouse</div>

<script>
const canvas = document.getElementById("c");
const ctx = canvas.getContext("2d");

let w, h;
function resize() {
  w = canvas.width = window.innerWidth;
  h = canvas.height = window.innerHeight;
}
resize();
window.addEventListener("resize", resize);

// plasma particles
const particles = [];
const COUNT = 1200;

for (let i = 0; i < COUNT; i++) {
  let a = Math.random() * Math.PI * 2;
  let r = Math.random() * 2.5 + 0.5;
  let dist = Math.random() * 260 + 40*
