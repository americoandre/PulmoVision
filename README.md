# PulmoVision
8-electrode Electrical Impedance Tomography (EIT) system designed for real-time
monitoring of pulmonary ventilation. The system estimates spatiotemporal impedance
variations across the thoracic region by injecting controlled electrical currents 
through configurable electrode pairs and measuring the resulting boundary voltage
distributions. These measurements are directly correlated with lung air volume changes,
enabling non-invasive tracking of regional ventilation dynamics.

The acquisition architecture is built for deterministic timing and low-noise operation.
A Teensy 4.1 is used as the real-time control core, responsible for precise electrode switching,
timing synchronization, and data acquisition orchestration. Signal generation is handled by an AD9850, 
providing stable excitation waveforms. Electrode multiplexing is implemented using the ADG1606, while 
low-level bio-potential amplification is performed by the AD8221 to ensure high common-mode rejection and signal integrity.

A Raspberry Pi runs a Linux-based service responsible for system orchestration, data logging, streaming,
and higher-level processing. The entire software stack is implemented in C++, prioritizing deterministic
performance, low latency, and efficient memory management.

The system supports sequential electrode scanning strategies for frame-based EIT reconstruction, with
emphasis on stability under low-amplitude physiological signals. Noise mitigation techniques, synchronized 
sampling, and calibrated current injection are used to improve measurement robustness. The platform is intended 
for biomedical engineering research, experimental respiratory monitoring, and development of real-time impedance-based 
imaging systems for thoracic ventilation analysis.
