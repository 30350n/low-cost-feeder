# Low Co$t Feeder

This is a cost optimized version of the original LumenPnP Feeders by
[Opulo](https://www.opulo.io/).

## Warning: This is still highly experimental, PCBs haven't been ordered/tested at all yet.

### Changes:

- **3.3V -> 5V mcu/logic supply**  
  The original RS485 transceiver costs 6-7€ in Qty 10, alternative parts that can be powered
  by 3.3V start at 3-4€. Similar 5V powered parts are already available for ~1€.
- **STM32F031 -> ATmega328P**  
  This is just the first MCU I could think of that's 5V compatible. It has just enough IO, is
  available in similar packages (TQFP and QFN), is similarly priced and should be able to run
  the photon firmware just fine.
- **470uF -> 100uF buck converter output capacitor**  
  There are very few 470uF 10V capable caps available in the specified package. The 470uF cap
  is also very overspecd, 100uF should be totally sufficient for the application. (The original
  value probably got copied straight from the datasheet example schematic.)
- **Countersinks -> [24882 solderable standoffs](https://www.digikey.com/en/products/detail/keystone-electronics/24882/9921841)**  
  Getting the countersinks done by the PCB manufacturer is probably way to expensive,
  especially for low qty orders. The standoffs would add a cost of ~2.5€ per board.
  Alternatively it might be possible to use a 3D print with standard M3 nuts/heat set inserts,
  glued to the PCB in their place.  
  Adding the countersinks to the holes yourself is still possible too.
- **Option to bypass the onboard SMPS** (thanks @FL140 for the idea!)  
  Added a 0R resistor to bypass the onboard SMPS for **users of +12V machines**. This should
  save 1-2€ in components and might also have some other benefits, like better EMC.  
  **If this option is being used, the DRV8837 motor drivers should be replaced with +12V
  tolerant ones, for example DRV8220.**

## LumenPnP Feeders
The LumenPnP Feeders are open source pick and place feeders to aid in [Mid-Scale Manufacturing](https://stephenhawes.com/level-2-manufacturing/).

![LumenPnP Feeders](img/hero-alpha.png)

LumenPnP Feeders are available for sale on the [Opulo Website](https://www.opulo.io/). If you build or buy one, please help the project by documenting bugs with a GitHub issue.

The LumenPnP Feeders run [Photon](https://github.com/photonfirmware/photon), an open source firmware project for pick and place feeders. The popular pick and place control software [OpenPnP](https://openpnp.org/) has Photon support built in, so it's easy to get going with the LumenPnP feeders using your existing OpenPnP setup. These feeders are designed to work with the [LumenPnP](https://opulo.io/products/lumenpnp).

The development process is being cataloged in a series of videos. A playlist of these can be found [here](https://www.youtube.com/playlist?list=PLIeJXmcg1baLBz3x0nCDqkYpKs2IWGHk4).

### Documentation
Feeder user documentation can be found on the [Opulo Docs Page](https://docs.opulo.io/). Open Hardware Assembly instructions can be found at [ohai.opulo.io](https://ohai.opulo.io/).

### Community
Discussion about the project happens on the [STR Discord server](https://discordapp.com/invite/TCwy6De)!