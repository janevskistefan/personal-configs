# 1. powertop - power analysis tool

`sudo apt install powertop && sudo powertop --calibrate`
- In order for powertop to calibrate itself it needs to turn off your display, radios, keyboard backlight etc. After executing these commands give your system a couple of minutes to finish the calibration process. Do not touch the machine during the calibration.

# 2. auto-cpufreq - automatic cpu speed and power optimizer

[Link to Config File Reference](https://github.com/AdnanHodzic/auto-cpufreq#3-auto-cpufreq-config-file)

```bash
git clone https://github.com/AdnanHodzic/auto-cpufreq.git

cd auto-cpufreq

# Press i when prompted:
sudo ./auto-cpufreq-installer

sudo auto-cpufreq --install 
```
- create a symbolic link: `auto-cpufreq.conf` -> `/etc/auto-cpufreq.conf`

# 3. tlp - feature rich battery life optimizer 
[Link to Documentation](https://linrunner.de/tlp/settings/index.html)

```bash
sudo add-apt-repository ppa:linrunner/tlp &&
sudo apt update &&
sudo apt install tlp
```
- create a symbolic link: `tlp.conf` -> `/etc/tlp.d/tlp.conf`

# 4. s2idle -> s2deep
https://devnull.land/laptop-s2idle-to-deep

# 5. Battery level config

[Link to Source](https://askubuntu.com/a/800398)

- ## Set low battery level to 20%:

    ```sudo sed -i 's/^PercentageLow.*/PercentageLow=20/' /etc/UPower/UPower.conf```

- ## Set critical battery level to 5%:

    ```sudo sed -i 's/^PercentageCritical.*/PercentageCritical=5/' /etc/UPower/UPower.conf```

- ## Set critical battery action to execute when the battery reaches 5%:

    ```sudo sed -i 's/^PercentageAction.*/PercentageAction=5/' /etc/UPower/UPower.conf```

- ## Set the critical battery level action to Shut Down:

    *For my use-case this configuration is necessary because at least a small amount of charge is needed for the system to start charging via USB-C PD.*
    
    *If you don't charge your machine via USB-C this change is **optional**. The default setting is HybridSleep*

    ```sudo sed -i 's/^CriticalPowerAction.*/CriticalPowerAction=PowerOff/' /etc/UPower/UPower.conf```