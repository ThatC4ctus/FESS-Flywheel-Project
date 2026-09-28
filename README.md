# FESS-Flywheel-Project
First personal EE project designed around capturing energy from back EMF, by a decelerating motor

First rough iteration of the Flywheel schematic diagram:
<img width="1116" height="870" alt="image" src="https://github.com/user-attachments/assets/2b87650d-8e48-441c-9ae6-e8dbe688b02f" />
Explaining diagram:
Battery goes into fuse -> switch -> ammeter (data sent to micro controller) -> positive terminal of ESC -> motor
                          switch -> voltage divider -> A0 analog terminal -> input protection circuit (zener+capacitor)
                          this is so A0 can detect if the switch it on/off and detect the voltage at the ESC input
Battery negative -> GND net -> negative terminal for ESC -> motor
^
Above circuit is just to power up motor and then measure the power used to drive motor, via ammeter and voltage data sent to the micro controller.

Then the motor when spun will be disconnected from driving circuit and connected to generator circuit, this will use the diodes to path the generated
back-emf through the ammeter, where current data will be sent to MC, voltage data collected via similar voltage divide and protection circuit to GND net
where final power out will be calculated.
^
motor -> three phase bridge inverter -> ammeter -> load -> voltage divider -> GND
                                        ammeter -> MC      voltage divider -> MC
