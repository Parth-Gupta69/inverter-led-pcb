# inverter-led-pcb #
(export (version D)
  (components
    (comp (ref BT1)
      (value Battery)
      (footprint Battery:Battery_Holder))
    (comp (ref U1)
      (value NOT_Gate)
      (footprint Package_DIP:DIP-14))
    (comp (ref R1)
      (value 220)
      (footprint Resistor_THT:R_Axial))
    (comp (ref SW1)
      (value Switch)
      (footprint Button_Switch_THT:SW_PUSH))
    (comp (ref LED1)
      (value LED)
      (footprint LED_THT:LED_D5.0mm))
  )

  (nets
    (net (code 1) (name VCC)
      (node (ref BT1) (pin +))
      (node (ref SW1) (pin 1))
    )

    (net (code 2) (name SIGNAL_IN)
      (node (ref SW1) (pin 2))
      (node (ref U1) (pin IN))
    )

    (net (code 3) (name SIGNAL_OUT)
      (node (ref U1) (pin OUT))
      (node (ref R1) (pin 1))
    )

    (net (code 4) (name LED_LINE)
      (node (ref R1) (pin 2))
      (node (ref LED1) (pin A))
    )

    (net (code 5) (name GND)
      (no
