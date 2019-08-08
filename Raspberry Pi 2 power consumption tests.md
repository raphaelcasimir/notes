# Power consumption of the Pi In The Sky boards in typical use
*Effects of frequency and core count variation on power consumption.*

Test done by @raphaelcasimir

Using the Pi In The Sky complete system, an analog PSU @5.2V powering USB input, a Fluke multimeter for amps measurements.

Cores were disabled by editing "/boot/cmdline.txt" and adding "maxcpus=N"
Where N is in range 1 to 4.
Over (OC) and underclocking where done by editing "/boot/config.txt" and changing the "arm_freq" option.

2 images are captured with the camera every minute. The measurements are taken on one cycle at least, started and ended after the first image of the two captures is taken.

**Important note** : when shut down, the system is consuming approximatively 0.1 Amps. This may be because the Ethernet adapter was connected.

|  Nbr of cores |  Frequency (MHz)|  Avg. current draw (A)| Peak current (A)  |  Time between captures |
|:-:|---|---|---|---|
|  4 |  900 "OC: High" | 0,34  | 0,51  |  1m |
|  2 |  " |  0,39 |  0,54 | " |
|  4 | 700  |  0,34 |  0,51 |  " |
|  3 |  " | 0,37  |  0,53 |  " |
|  2 |  " |  0,38 |  0,54 |  " |
|  1 |  " | 0,39  |  0,54 |  " |
|  4 | 300  |  0,34 | 0,51 | "  |
|  " | 100  |  0,33 | " | "  |
|  2 |  " |  0,36 | "  |  " |
|  4 |  50 |  0,33 |  0,49 |  3m20s |

It seems that **underclocking** the CPU has **little to no effects** on power consumption. However, the system responsiveness is affected, even extremely under 100 MHz so the 1 minute time between captures is not respected. **Disabling cores** actually **increases power consumption**, which was unexpected.

## Conclusion
From those results, it can be concluded that **it is not worth it to change the core number or frequency** of the CPU to save power. On the contrary, disabling cores have the opposite effect.
