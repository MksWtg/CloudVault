Prerequisites: [[Alternating Current]] 

How do we convert single phase AC waveform to three phase for three phase motor?

The most common and practical method is using a Variable Frequency Drive (VFD) or electronic inverter. The single-phase AC first goes through a rectifier (usually a diode bridge) which converts the AC into DC. This DC is filtered by capacitors to create a relatively smooth DC bus. Then an inverter stage made of switching devices such as IGBTs or MOSFETs rapidly switches the DC on and off using PWM control to synthesize three separate AC waveforms that are 120 degrees apart. These three outputs feed the three motor terminals, effectively creating a three-phase supply from a single-phase input.