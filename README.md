I checked your lab manual. For **Experiment No. 2 – Simulation and Implementation of Logic Gates and Boolean Functions**, the manual uses the format: **Aim → Software Required → Program → Output → Result** and provides a Verilog program. 

If you want a **GitHub README in the same style but using VHDL**, you can use:

# EXPERIMENT NO. 2

# SIMULATION AND IMPLEMENTATION OF LOGIC GATES AND BOOLEAN FUNCTIONS

## AIM

To write VHDL programs for Logic Gates and Boolean Functions and verify their operation through simulation. 

## SOFTWARE REQUIRED

1. Xilinx Vivado / Xilinx ISE
2. ModelSim Simulator
3. GHDL (Optional)

---

## THEORY

Logic gates are the basic building blocks of digital circuits. They perform logical operations on binary inputs and produce a binary output. Common logic gates include AND, OR, NOT, NAND, NOR, XOR, and XNOR.

---

## PROGRAM

### LOGIC GATES

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity logic_gates is
    Port (
        A, B     : in STD_LOGIC;
        AND_OUT  : out STD_LOGIC;
        OR_OUT   : out STD_LOGIC;
        NOT_OUT  : out STD_LOGIC;
        NAND_OUT : out STD_LOGIC;
        NOR_OUT  : out STD_LOGIC;
        XOR_OUT  : out STD_LOGIC;
        XNOR_OUT : out STD_LOGIC
    );
end logic_gates;

architecture Behavioral of logic_gates is
begin
    AND_OUT  <= A and B;
    OR_OUT   <= A or B;
    NOT_OUT  <= not A;
    NAND_OUT <= A nand B;
    NOR_OUT  <= A nor B;
    XOR_OUT  <= A xor B;
    XNOR_OUT <= A xnor B;
end Behavioral;
```

---

### BOOLEAN FUNCTION

Boolean Expression:

[
Y=(A \cdot B)+C
]

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity boolean_function is
    Port (
        A, B, C : in STD_LOGIC;
        Y       : out STD_LOGIC
    );
end boolean_function;

architecture Behavioral of boolean_function is
begin
    Y <= (A and B) or C;
end Behavioral;
```

---

## TEST BENCH

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity tb_logic_gates is
end tb_logic_gates;

architecture behavior of tb_logic_gates is

signal A,B : STD_LOGIC := '0';
signal AND_OUT,OR_OUT,NOT_OUT : STD_LOGIC;
signal NAND_OUT,NOR_OUT,XOR_OUT,XNOR_OUT : STD_LOGIC;

begin

UUT: entity work.logic_gates
port map(
    A => A,
    B => B,
    AND_OUT => AND_OUT,
    OR_OUT => OR_OUT,
    NOT_OUT => NOT_OUT,
    NAND_OUT => NAND_OUT,
    NOR_OUT => NOR_OUT,
    XOR_OUT => XOR_OUT,
    XNOR_OUT => XNOR_OUT
);

process
begin
    A <= '0'; B <= '0'; wait for 10 ns;
    A <= '0'; B <= '1'; wait for 10 ns;
    A <= '1'; B <= '0'; wait for 10 ns;
    A <= '1'; B <= '1'; wait for 10 ns;
    wait;
end process;

end behavior;
```

---

## TRUTH TABLE

| A | B | AND | OR | NAND | NOR | XOR | XNOR |
| - | - | --- | -- | ---- | --- | --- | ---- |
| 0 | 0 | 0   | 0  | 1    | 1   | 0   | 1    |
| 0 | 1 | 0   | 1  | 1    | 0   | 1   | 0    |
| 1 | 0 | 0   | 1  | 1    | 0   | 1   | 0    |
| 1 | 1 | 1   | 1  | 0    | 0   | 0   | 1    |

---

## OUTPUT

The simulation waveform verifies the outputs of AND, OR, NOT, NAND, NOR, XOR, XNOR gates and the Boolean Function.

*(Insert waveform screenshot here)*

---

## RESULT

Thus, the simulation and implementation of Logic Gates and Boolean Functions using VHDL were successfully verified through simulation. Based on the lab manual format for Experiment 2. 

If you are preparing all 8 experiments for GitHub, I can also convert the remaining experiments from your lab manual into the same README format.
