# Lab 2: FRANTISEK BILEK

### 2-bit comparator

1. Karnaugh maps for other two functions:

   Greater than:

   ![K-maps](b_greater_a_sop.png)

   Less than:

   ![K-maps](b_less_a_pos.png)

2. Equations of simplified SoP (Sum of the Products) form of the "greater than" function and simplified PoS (Product of the Sums) form of the "less than" function.

   ![Logic functions](equations.jpg)

### 4-bit comparator

1. Listing of VHDL stimulus process from testbench file (`testbench.vhd`) with at least one assert (use BCD codes of your student ID digits as input combinations). Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   Last two digits of my student ID: **34**

```vhdl
    p_stimulus : process
    begin
        -- Report a note at the beginning of stimulus process
        report "Stimulus process started" severity note;

        -- First test case (OK)
        s_b <= "0011";		-- student ID = xxxx34
        s_a <= "0100";		-- student ID = xxxx34
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '1'))
        -- If false, then report an error
        report "Input combination 0011, 0100 FAILED" severity error;
        
        -- Second test case (intentional error)
        s_b <= "1000";		-- wrong
        s_a <= "0100";
        wait for 100 ns;
        -- Expected output
        assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '1'))
        -- If false, then report an error
        report "Input combination 0011, 0100 FAILED" severity error;

        -- Report a note at the end of stimulus process
        report "Stimulus process finished" severity note;
        wait;
    end process p_stimulus;
```

2. Text console screenshot during your simulation, including reports.

   ![Console](konzole.png)

3. Link to your public EDA Playground example:

   https://www.edaplayground.com/x/wQAw
