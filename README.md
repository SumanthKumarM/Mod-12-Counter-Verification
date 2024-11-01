# Mod-12-Counter-Verification
A verification environment based test bench has been implemented using System Verilog HVL to verify the behaviour of Mod-12 Counter.
The test bench environment consists of Transaction class, generator, driver, write monitor, read monitor, reference model and scoreboard.
The transaction class consists of properties declared as rand variables and a method to display the current values of those properties.
Generator class randomizes the transaction class properties and sends those randomized values to driver through driver class.
Driver class receives those randomized variables thorugh mailbox from generator class and assign those values to DUV(Mod-12 counter) through interface.
Write monitor retrieves those values sent by driver to DUV through the same interface and send those values to reference model through a mailbox.
Read monitor captures the output response of the DUV for provided inputs by driver and read monitor sends it to scoreboard.
Reference model consists of error free behavioural code for DUV. Reference model receives data from write monitor and sends the response to scoreboard.
The scoreboard receives data from both reference model and read monitor and performs a comparision between data received from reference model and read monitor. So the scoreboard compares the actual output of DUV and the error free output and gives the result.
