## VHDL modules description and simulations

### `dig_clock`
This module ensures the functionality of the clock as such. It takes a clock signal and pin enable as its inputs.

### `time_comp_alarm`
This module works both to remember the set alarm time and to trigger the alarm at the correct time.

### `button_debouncer`
Mechanical pushbutton often generate fake transitions when pressed due to its mechanical nature. If we want to set the time using pushbuttons, these fake transitions would be very problematic and it is necessary to get rid of them. Module called `button_debouncer` is used to do the job. It consists of 3 D-latches connected in series. The first one takes the push button signal as its input. When the enable signal is on high level, the input gest shifted to the next latch. The outputs of all three latches are connected to an AND gate which output is output of the whole debouncer. Clearly, when all three AND inputs are on HIGH level (i.e. the button is pressed for sufficient amount of time). button is pressed,  clock_enable module where g_MAX value is set to 1 000 000 for 10 ms debounce delay. This particuar debouncer 
