## VHDL modules description and simulations

### `dig_clock.vhd`

 | **Port name** | **Direction** | **Type** | **Description** |
 | :-: | :-: | :-- | :-- |
 | `btn_set` | in | `std_logic` | ... |
 | `set_second` | in  | `std_logic_vector(5 downto 0)` | ... |
 | `set_minute` | in | `std_logic_vector(5 downto 0)` | ... |
 | `set_hour` | in | `std_logic_vector(4 downto 0)` | ... |
 | `sec_o` | out | `std_logic_vector(5 downto 0)` | ... |
 | `min_o` | out | `std_logic_vector(5 downto 0)` | ... |
 | `hr_o` | out | `std_logic_vector(4 downto 0)` | ... |
 
This module ensures the functionality of the clock as such. It takes clock signal which is slow down to 1 second using the clock_enable module. Every second the second value increases by one, but to 59 and then back to zero. In the same way, the minute value also increases after the second value reaches 59, but up to 59. The hourly value increases when the minute value reaches 59 and rises to 23 and resets again to zero.

### `time_comp_alarm.vhd`
This module works both to remember the set alarm time and to trigger the alarm at the correct time.

### `button_debouncer.vhd`
Mechanical pushbutton often generate fake transitions when pressed due to its mechanical nature. If we want to set the time using pushbuttons, these fake transitions would be very problematic and it is necessary to get rid of them. Module called `button_debouncer` is used to do the job. It consists of 3 D-latches connected in series. The first one takes the push button signal as its input. When the enable signal is on high level, the input gest shifted to the next latch. The outputs of all three latches are connected to an AND gate which output is output of the whole debouncer. Clearly, when all three AND inputs are on HIGH level (i.e. the button is pressed for sufficient amount of time). button is pressed,  clock_enable module where g_MAX value is set to 1 000 000 for 10 ms debounce delay.

### `clock_setter.vhd`
text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text

### `driver_7seg_4digits.vhd`
text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text

### `to_bcd_conv.vhd`
text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text

### `clock_enable.vhd`
text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text

### `cnt_up_down_2.vhd`
text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text

### `driver_dig_clock.vhd`
text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text

### `hex_7seg.vhd`
text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text text
