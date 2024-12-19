# VHDL Counter Overflow Bug

This repository demonstrates a common error in VHDL code: a counter that overflows without proper handling. The original `counter.vhdl` code lacks a mechanism to prevent the `internal_count` signal from exceeding its defined range (0 to 15). This can lead to unexpected behavior and potentially incorrect simulation results.  The corrected version, `counter_fixed.vhdl`, addresses this issue. 

## Bug Description

The `counter.vhdl` file contains a simple counter entity and architecture.  When the counter reaches its maximum value (15), it continues to increment. This wraps around to 0 and potentially to negative values, depending on the simulator and integer representation. This incorrect behavior is the bug.

## Solution

The `counter_fixed.vhdl` file provides a solution.  The solution incorporates a check to reset the counter to 0 when it reaches its maximum value (15). This prevents the overflow and ensures the counter functions correctly.

## How to Reproduce

1.  Simulate `counter.vhdl` and observe the counter's behavior after it reaches 15. 
2. Simulate `counter_fixed.vhdl` and observe the expected behavior.  The counter should reset to 0 after reaching 15.
