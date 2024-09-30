## Tutorials

### How to install Logic Analyzer drivers

- The LA uses userspace WinUSB drivers. Install drivers with zadig
- Install zadig from http://zadig.akeo.ie/
- Tested with zadig 2.8
- Use zadig to “install driver” for “unknown device” to WinUSB

![[Pasted image 20240929221616.png]]

### How to install Logic Analyzer Software (Pulseview)

- Last full release (0.4.2) does not have the very useful ‘tabular decoder output view’; we want nightly build
- The PulseView automated builds system is broken right now (and has been for a year or so)
- Grab the last available 64bit nightly build from the internet archive: [Here](https://web.archive.org/web/20220510071316/https:/sigrok.org/download/binary/pulseview/pulseview-NIGHTLY-64bit-static-release-installer.exe)
- Install with all defaults
![[Pasted image 20240929221830.png]]

### How to Install: Find Performance Limit

- Close Pulseview; Connect Logic Analyzer (LA); Start Pulseview
- Start by setting highest sample rate (i.e. 48MHz)
- Repeat the following to find the highest reliable sample rate
	- Set a >60s capture window by choosing 5G sample or similar
	- Start capture 
	- If ‘Run’ button becomes enabled and resulting capture length is short then this sample rate is unstable. In that case: reduce sample rate and repeat
	- BUT if the ‘Run’ button stays disabled for a while and you got a long signal capture then this is a reliable sample rate
- If you find your PC doesn’t support > 2MHz reliably try:
	- NO USB Hub 
	- Add a USB Hub
	- Different USB Cables
	- Different USB port on the PC 
	- Connect laptop to OEM charger
- Maybe repeat the above to convince yourself of what a safe sample rate is for your laptop
- e.g. on some of my laptops the highest reliable sample rate is 24MHz; on others it is 4MHz.

### How to Install: Add CAN2 Decoder

The default sigrok CAN decoder is not great. Install the can2 decoder from Dr. Ken Tindell: clone or download zip from https://github.com/kentindell/canhack

- Close Pulseview
- Copy the `can2\ dir` from  `canhack\src\`  into `C:\Program Files\sigrok\PulseView\share\libsigrokdecode\decoders\`
	- i.e. the result should be a `libsigrokdecode\decoders\can2` dir
- This will probably require clicking ‘yes’ on an administrator privilege button
- Start Pulseview; there will be a new decoder available
![[Pasted image 20240929222720.png]]

### How to connect Logic Analyzer to pins

- Always connect LA Ground (GND) to target ground
- Connect CH1, CH2, etc. to target pins

*Note: On some units the GND connection that's adjacent to input six isn't actually a ground, it appears to be some sort of clock signal. We recommend not using that pin for anything just to be safe*
### How to do a capture of pin voltages

- Configure sample rate
- Try the fastest your PC supports; 
- Configure your number of samples 
	- If you have no trigger set then use really really large (gigasample) 
- Hit ‘Run’ or press spacebar. Ditto to stop early.
- When you understand the target signal you can set the SR to 4x the highest frequency in the signal 
![[Pasted image 20240929222929.png]]

### How to attempt a decode of the captured traces (e.g. changing baud rate)

- Optional: disable traces you are not interested in
- Click ‘add protocol decoder’
- Browse / filter for a decoder to try
- Double-click the desired decoder
- Default decoder has no channel assigned
- Click on decoder ‘row label’ to configure  
- Assign target channel(s) to decoder

![[Pasted image 20240929223100.png]]

#### What am I looking at
![[Pasted image 20240929223137.png]]

#### CTF Mode 
![[Pasted image 20240929223205.png]]


#### More Analysis

![[Pasted image 20240929223238.png]]
