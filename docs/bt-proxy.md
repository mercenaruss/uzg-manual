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

# ESPHOME POE Bluetooth Proxy/Zigbee

UZG-01 utilizes ESP32 chip so can be used as a [ESPHome Bluetooth Proxy adapter for Home Assistant](https://esphome.github.io/bluetooth-proxies/).

![UZG-01 - ESPHome Bluetooth proxy mode](assets/images/bt-proxy/UZG-01-btproxy-logo.png){ data-title="UZG-01 - ESPHome Bluetooth proxy mode" .off-glb }

So with UZG-01 you can have:

- ESPHome Bluetooth Proxy
- ESPHome BTProxy & Zigbee (Mixed)

!!! warning "ESPHome BTProxy & Zigbee - Not recommended"
    Use at your own risk,may occur interference between Zigbee & Bluetooth<br>
    Recommended to test very well before using in production environment 

???+ note
    All ESPHome based firmware's are working over Ethernet.<br>
    For Wifi please download .yaml file and edit accordingly.

**How to set-up your UZG-01 as ESPHome Bluetooth proxy**

You can install using two methods described below:

### Web Installation

<ol>
  <li>Plug in your UZG-01 to a USB port. Select firmware for your device</li>
  <li id="coms">Hit "Install" and select the correct COM port. <a onclick="showSerialHelp()">No device found?</a></li>
  <li>Get UZG-01 selected firmware installed and connected in less than 3 minutes!</li>
</ol>

<div class="pick-variant">
<select>
    <option value="https://raw.githubusercontent.com/mercenaruss/zigstar_gateways/main/files/ESP-HOME/zigstar-gw-lan/langw-btproxy.json" > ESPHome BTProxy</option>
    <option value="https://raw.githubusercontent.com/mercenaruss/zigstar_gateways/main/files/ESP-HOME/zigstar-gw-lan/langw-mixed.json" > ESPHome Mixed</option>
</select>
<esp-web-install-button class="button-connect">
  <button slot="activate" class="md-button md-button--primary">INSTALL</button>
  <span slot="unsupported">Use Chrome Desktop</span>
  <span slot="not-allowed">Not allowed to use this on HTTP!</span>
</esp-web-install-button><br>
<br>Powered by <a href="https://esphome.github.io/esp-web-tools/" target="_blank">ESP Web Tools</a><br>
</div>

### Manual Installation

1. Generate ESPHome firmware based on the following ESPHome BTProxy YAML configuration files:

<div class="pick-variant">
  <form id="downloadyaml" onsubmit="this.action = document.getElementById('yaml').value">
    <select id="yaml">
        <option value="https://raw.githubusercontent.com/mercenaruss/zigstar_gateways/main/files/ESP-HOME/zigstar-gw-lan/langw-btproxy.yaml" > ESPHome BTProxy</option>
        <option value="https://raw.githubusercontent.com/mercenaruss/zigstar_gateways/main/files/ESP-HOME/zigstar-gw-lan/langw-mixed.yaml" > ESPHome Mixed</option>
    </select>
    <input type="submit" value="Download" class="button" >
  </form>
</div>

2. Flash you generated firmware to your UZG-01's ESP32 chip following the [Official manual](flashing-and-updating.md/#update-esp32).
3. Follow official [ESPHome BTProxy component documentation](https://esphome.io/components/bluetooth_proxy.html) for proper end-devices set-up.

<script>
	const selectEl = document.querySelector(".pick-variant select");
	const installEl = document.querySelector("esp-web-install-button");
	installEl.manifest = selectEl.value;
	selectEl.addEventListener("change", () => {
	  installEl.manifest = selectEl.value;
	});
	
	function showSerialHelp() {
	  document.getElementById('coms').innerHTML = `Hit "Install" and select the correct COM port.<br><br>
	  You might be missing the drivers for your board.<br>
	  Here are drivers for chip used in UZG-01 board:
	  <a href="https://sparks.gogo.co.nz/ch340.html" target="_blank">CH340C</a><br><br>
	  Make sure your USB cable supports data transfer.<br><br>
	  `;
	}
</script>