Technical Writing Portfolio: Allan Kiplagat
Documentation samples for embedded systems and robotics: CLI help and error design, a hardware API reference, and structured evaluation of AI-generated technical writing.
Each project pairs writing with technical review. Every sample ends with a side-by-side evaluation of two AI-generated responses, scored against a specification or style guide, with each error explained and its severity rated.
#	Project	Domain	Shows
1	mcu-tool: Embedded CLI & Flashing Guide	ESP32 / STM32 firmware flashing	CLI help text, error-message design, protocol-level diff review
2	ArmLink Controller API Reference	6-DOF robotic arm, REST API	Endpoint reference, fault and state-machine spec, rubric-based scoring
3	AMR Diagnostic & Log Evaluation	ROS 2 mobile robot	Log analysis, style-guide enforcement, tagged preference judgements
> These are illustrative samples. The tools, API and robot are designed for the portfolio. The hardware and protocol behaviour they describe (STM32 bootloader per ST AN3155, ESP32 ROM loader, CANopen, ROS 2 Humble, tf2) reflects real systems.
---
1. mcu-tool: Embedded CLI & Flashing Guide
A command-line tool for flashing ESP32 and STM32 microcontrollers over serial.
Help text written to fixed rules: imperative first line, every default shown, warnings next to the flag that causes the risk.
Error message matrix: eight failure cases rewritten from vague ("Timeout") to actionable, using one format: code, what failed, where, evidence, next action. Includes distinct exit codes for scripts and CI.
Diff analysis: two AI-written flashing transcripts. One connects at 8N1 to a bootloader that requires 8E1. Its first lines would still work, because those bytes happen to have an odd number of 1-bits, but the write could not complete. The review works through the protocol byte by byte to show why.
2. ArmLink Controller API Reference
A REST API for a 6-axis robot arm controller.
Endpoint reference covering status, joints, drive enable/disable, motion and faults, with units, joint limits, request and response schemas, and a standard error format.
Failure and error-state spec: a six-state machine and a fault table covering thermal derating, encoder slip, two-layer current protection and e-stop. Faults latch, and drives are never re-enabled automatically.
Rubric evaluation: two AI-written fault docs scored on accuracy, schema conformance, safety, completeness and clarity (4.90 vs 1.15). The losing doc invents a robot state and claims a jammed joint restarts on its own.
3. AMR Diagnostic & Log Evaluation
Three pairs of AI troubleshooting answers for a ROS 2 mobile robot, judged against a written brief and a one-page style guide.
Case	Bug	What the losing answer got wrong
1	LiDAR scan corruption	Confident but technically wrong: blamed DDS QoS for bytes lost on the serial port
2	Wheel start offset	Technically right, but failed the brief: heavy hedging, no structure, a ROS 1 command
3	tf2 extrapolation	Unsafe: hid a clock-sync fault behind a 5-second transform tolerance
The point of the set: a reviewer who checks only formatting misses Cases 1 and 3, and one who checks only correctness misses Case 2.
---
Skills shown
Developer documentation: CLI help, API references, error messages, state machines
Embedded and robotics knowledge: STM32/ESP32 bootloaders, UART framing, CANopen (SDO, RPDO, SYNC), ROS 2 Humble, Nav2, tf2
AI output evaluation: preference judgements, rubric scoring, severity rating, tagging, catching plausible-but-wrong output
Writing standards: style guides, consistent structure, plain language
Contact
Allan Kiplagat: [geniusrotich10@gmail.com] · [https://linkedin.com/in/allan-kiplagat-8a0a30402]
Open to technical writing, documentation and AI evaluation roles, including remote and part-time work.
