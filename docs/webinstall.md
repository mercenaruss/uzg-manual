---
title: UZG - Web Flasher
description: Firmware Web Installer for UZG Firmware
---

<style>
  .md-content__button {
    display: none;
  }
  .pick-variant select {
    background: transparent;
    width: 300px;
    padding: 1px;
    font-size: 16pt;
    border: 1px solid #ddd;
    height: 51px;
    border-radius: 15px;
  }
</style>

# UZG-01 - Web Flasher

Flash or Find your device using next options:

<ol>
  <li>Plug in your UZG-01 to a USB port.</li>
  <li id="coms">Hit "Install" and select the correct COM port. <a onclick="showSerialHelp()">No device found?</a></li>
  <li>Get UZG-01 firmware installed and connected in less than 3 minutes!</li>
</ol>

<esp-web-install-button manifest="https://raw.githubusercontent.com/mercenaruss/zigstar_gateways/main/files/ESP-HOME/zigstar-gw-lan/langw-zigbee.json" class="button-connect">
  <button slot="activate" class="md-button md-button--primary">INSTALL</button>
  <span slot="unsupported">Use Chrome Desktop</span>
  <span slot="not-allowed">Not allowed to use this on HTTP!</span>
</esp-web-install-button>
<a href="http://uzg-01.local/"><button class="md-button">OPEN DEVICE</button></a>

<br>Powered by <a href="https://esphome.github.io/esp-web-tools/" target="_blank">ESP Web Tools</a><br>

<script>	
	function showSerialHelp() {
	  document.getElementById('coms').innerHTML = `Hit "Install" and select the correct COM port.<br><br>
	  You might be missing the drivers for your board.<br>
	  Here are drivers for chip used in UZG-01 board:
	  <a href="https://sparks.gogo.co.nz/ch340.html" target="_blank">CH340C</a><br><br>
	  Make sure your USB cable supports data transfer.<br><br>
	  `;
	}
</script>