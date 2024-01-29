This is the source code to Jon Barron's public academic website: https://jonbarron.info/. Feel free to clone this code for your own personal use.


```html
<table style="width:100%;border:0px;border-spacing:0px;border-collapse:separate;margin-right:auto;margin-left:auto;"><tbody>
<tr onmouseout="gun_stop()" onmouseover="gun_start()">
<td style="padding:20px;width:25%;vertical-align:middle">

    <div class="one">
    <div class="two" id='GunMayhem'>
    <img src='images/gunmayhem.png' width="160">
    </div>
    <img src='images/gunmayhem_logo.png' width="160">
    
    <script type="text/javascript">
        function gun_start() {
        document.getElementById('GunMayhem').style.opacity = "1";
        }

        function gun_stop() {
        document.getElementById('GunMayhem').style.opacity = "0";
        }
        gun_stop();
    </script>
    </div>
</td>
```