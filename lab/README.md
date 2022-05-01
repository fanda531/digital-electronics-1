## VHDL modules description

### `dig_clock.vhd`
This module ensures the functionality of the clock as such. It takes clock signal which is slow down to 1 second using the clock_enable module. Every second the second value increases by one, but to 59 and then back to zero. In the same way, the minute value also increases after the second value reaches 59, but up to 59. The hourly value increases when the minute value reaches 59 and rises to 23 and resets again to zero.

By default, the time runs from 00:00:00. If we press the button, the module reads the hours and minutes values from the `clock_setter.vhd` module and counts the time from them.

### `time_comp_alarm.vhd`
This module works both to remember the set alarm time from `clock_setter.vhd` module and to trigger the alarm at the correct time. By activating `button_set` we save alarm-time values to memory. The alarm function is active only when `activate_sw_i` is in the active position. If the values of the set alarm time and the current time are equal, the alarm is triggered.

### `button_debouncer.vhd`
Mechanical pushbutton often generate fake transitions when pressed due to its mechanical nature. If we want to set the time using pushbuttons, these fake transitions would be very problematic and it is necessary to get rid of them. Module called `button_debouncer` is used to do the job. It consists of 3 D-latches connected in series. The first one takes the push button signal as its input. When the enable signal is on high level, the input gest shifted to the next latch. The outputs of all three latches are connected to an AND gate which output is output of the whole debouncer. Clearly, when all three AND inputs are on HIGH level (i.e. the button is pressed for sufficient amount of time). button is pressed,  clock_enable module where g_MAX value is set to 1 000 000 for 10 ms debounce delay.

### `clock_setter.vhd`
Using this module, we set the time and choose whether it is the current time that we want to set or the time in which the alarm should be triggered. Apart from standard clock signal and enable signal, there are 2 buttons as inputs (using which we set the hours and minutes) and one switch with which we activate the module. The outputs of this block are the values of the hours and minutes we set.

### `cnt_up_down_2.vhd`
Predesigned bidirectional counter from lab exercises.

### `hex_7seg.vhd`
Predesigned 7-segment display decoder from lab exercises.

### `driver_7seg_4digits.vhd`
This module is used to control multiple 7-segment displays (6 in our case). Using the multiplexer, we only select one display at a time.

### `to_bcd_conv.vhd`
The outputs of the `dig_clock.vhd` module are 6-bit vectors in case of minutes and seconds and a 5-bit vector in case of hours. This block is used to divide these vectors into 4-bit BCD value, which then can be feed into the 7-segment driver. Each 4-bit vector represents one decimal digit.

### `clock_enable.vhd`
text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text

### `driver_dig_clock.vhd`
This block is used to encapsulate the `dig_clock.vhd`, `clock_setter.vhd` and `time_comp_alarm.vhd` modules. In addition, it contains a multiplexer, which switches between the current time display and the time setting, depending on the selected mode.


## Testbenches and simulations
