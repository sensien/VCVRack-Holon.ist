# Holonic Systems - VCV Rack Free Plugins

##### Table of Contents  
- [Holon.ist Receiver for VCV Rack](#holonist-receiver)
- [Pantry - Dual CV/Gate Recorder/looper](#pantry)
- [Swiss Cheese Knife - Quad Utility with a twist](#swiss-cheese-knife)
- [Gaps - Quad Utility with a twist](#gaps)
- [Junctions - dual switch](#junctions)


## Holon.ist Receiver

![Holon.ist Receiver](https://raw.githubusercontent.com/hdavid/VCVRack-Holon.ist/master/screencaps/Holon.ist-Receiver.png)

Holon.ist from http://holonic.systems can communicate with various virtual and physical studio gear using MIDI and OSC protocols.

Holon.ist Receiver VCV Rack Module integrates with the Holon.ist iOS app and outputs CV control signals to VCV Rack world.
- 8 channels of CV control from Holon.ist to your VCV rack.
- Per channel activity indicator, attenuverter and low pass filter.
- Multiple instances of the module can run at the same time. Each instance can be set to receive on its own bank, from A to H, allowing for a total of 64 channels of CV.

### Demos
We have put together some demos VCV patches that use the Holon.ist Receiver and some other of our plugins. Of course they use the Holon.ist app too!

Our demos are packaged in the plugin and are located in `c:\Users\<you>\Documents\Rack\Plugins\HolonicSystems-Free\demos` on Windows and `/Users/<you>/Documents/Rack/plugins/HolonicSystems-Free/demos`

Please make sure to check the installation steps below to avoid the common pitfalls like firewalls and the like and be sure autodetection will be working as it should.


### Installing
- Install latest version of Holon.ist on your iPhone or iPad: http://holonic.systems or https://testflight.apple.com/join/mBx4PTxL
- Install latest version of VCV rack installed : https://vcvrack.com/
- Install Holon.ist Receiver plugin from VCV Rack plugin manager and: https://vcvrack.com/plugins.html#holonic
- follow the instruction below how to get Holon.ist and the receiver to talk to each other.

### OSC Communication
mDNS/bonjour is used for autodiscovery.

- On MacOS Holon.ist will automatically detect VCV Rack if Holon.ist receiver plugin is loaded!
- On Windows you need to install Bonjour SDK from Apple: https://developer.apple.com/bonjour/ and check that the Bonjour Service is running. Then run the script `scripts\Holon.ist receiver bonjour.bat`. You will find this script in the plugin folder `c:\Users\<you>\Documents\Rack\Plugins\HolonicSystems-Free\` This will publish Holon.ist Receiver on the network and allow autodiscovery from Holon.ist App.
- On Linux you need to have Avahi running (it is usually the case), then run the script. `scripts\Holon.ist_receiver_avahi.sh`. This will publish Holon.ist Receiver on the network and allow autodiscovery.

Tips
- Make sure firewall, such as little snitch or others, are not blocking communication. For instance, on MacOS, with Little Snitch firewall, incoming communication must be specifically enabled for Rack.
- If you cannot get auto discovery to work for some reason, you can always manually create an OSC output in Holon.ist and input your computer IP and port 9000.
- Please read the Holon.ist manual http://holon.ist/manual/


### Receiving Bank
The Receiving bank pot selects from which bank the module receives signals from Holon.ist. This allows use of more than one instance of the module in the patch, providing up to 64 channels of voltage control in total!

### Activity LEDs
Activity LEDs for each channel indicate when Holon.ist Receiver receives OSC messages for the particular channel and receiving bank.

Note that output jacks will also show output values graphically, but for this to happen, a cable needs to be plugged in the jack.

### Attenuverters
Attenuverters on each channels lets one scale and invert CV values according to need.  

### Low Pass Filters
The slew is adjustable, in order to avoid stepped signals, and to make more organic CV changes.

### Outputs
VCV rack expects values between 0v and +10v for unipolar and between -5v and +5v for bipolar signals.

Holon.ist receivers clips signals to -10v, +10v.
  
Ensure that values are properly scaled in the Holon.ist scaling section.

## Pantry

![Pantry](https://raw.githubusercontent.com/hdavid/VCVRack-Holon.ist/master/screencaps/Pantry.png)

Pantry is a Dual CV/Gate Recorder/Looper.

Features :
- Dual Channel 
- CV and Gate
- Record: full loop length when CV rised or button is pressed
- Overdub: record or record while CV/button is held
- Length from 1 to 32 with CV
- Shifting with CV control


## Swiss Cheese Knife

![SwissCheeseKnife](https://raw.githubusercontent.com/hdavid/VCVRack-Holon.ist/master/screencaps/SwissCheeseKnife.png)

SwissCheeseKnife is a Quad utility module with a twist.

### Inverter
Inverts input signal.

### Attenuator 
Attenuator with range [0, 1] ratios.

### Sample and Hold
Classic Trigger and Hold.

### VCA
VCA with response shape ranging from linear to exponential.

### Low Pass Filter
Simple low pass filter.

### Slew Limiter
Slew limiter.

### DC Offset Remover
While in AC mode, any DC offset is removed. 

### Offset
Signal offset.

### Mixer
Last on the signal path, but not least. SwissCheeseKnife can also mix 4 signals, as its outputs are normalled.


## Gaps

![Gaps](https://raw.githubusercontent.com/hdavid/VCVRack-Holon.ist/master/screencaps/Gaps.png)

Gaps is a clock divider that supports multiple modes. 

- Integers: 2,3,4,5,6,7,8,9
- Even : 2,4,6,8,10,12,14,16
- Odd: 3,5,7,9,11,13,15,17
- Prime: 2,3,5,7,11,13,17,19
- Binary: 2,4,8,16,32,64,128,256
- Random: random probabilities 1/2, 1/3, 1/4, 1/5, 1/6, 1/7, 1/8, 1/9
- 8 step clock Sequencer


## Junctions

![Junctions](https://raw.githubusercontent.com/hdavid/VCVRack-Holon.ist/master/screencaps/Junctions.png)

A simple dual switch. Two inputs, one output.
