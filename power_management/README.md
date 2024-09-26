# 1. powertop - power analysis tool

`sudo apt install powertop && sudo powertop --calibrate`

# 2. auto-cpufreq - automatic cpu speed and power optimizer

```bash
git clone https://github.com/AdnanHodzic/auto-cpufreq.git
cd auto-cpufreq
sudo ./auto-cpufreq-installer
sudo auto-cpufreq --install 
```

# 4. s2idle -> s2deep
https://devnull.land/laptop-s2idle-to-deep

# 5. Battery level config

[Link to Source](https://askubuntu.com/a/800398)

- ## Set low battery level to 20%:

    ```sudo sed -i 's/^PercentageLow.*/PercentageLow=20/' /etc/UPower/UPower.conf```

- ## Set critical battery level to 10%:

    ```sudo sed -i 's/^PercentageCritical.*/PercentageCritical=10/' /etc/UPower/UPower.conf```

- ## Set critical battery action (HybridSleep) to execute when the battery reaches 10%:

    ```sudo sed -i 's/^PercentageAction.*/PercentageAction=10/' /etc/UPower/UPower.conf```