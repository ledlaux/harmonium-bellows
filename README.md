# Harmonium bellows 

This Pure Data patch simulates bellows dynamics for a harmonium-like instrument. 

Based on the research of N.Puranik and G.Scavone
**https://www.dafx.de/paper-archive/2023/DAFx23_paper_47.pdf**

Patch loads harmonium soundfont from the 2mbgmgs sound bank.

 It features:
 
 	•	MIDI Control:
[ctlin 1 1] receives MIDI CC#1 (mod wheel), and maps it to bellows pressure with a 1-second fade time via [line].
	
 •	Bellows Ramp Control:
A [line] object receives messages like [1 4000] to simulate smooth audio amplitude pressure changes (e.g., swell to full in 4 seconds).
	
 •	Start Delay:
A [delay 1000] introduces a 1-second wait before the bellows ramp begins, mimicking the physical delay when pumping air.
	
 •	Manual Input:
Vertical slider and number box allow direct control of bellows pressure; values are scaled and sent as [value 1000] to [line].

	•	Audio Modulation:
Audio inputs (filt_out, filt_outR) are multiplied by the smoothed bellows signal via [line~], then clipped with clip~ -0.5 0.5 before stereo output.

 
Ideal for use with harmonium, shruti box, or other drone instrument emulations.


