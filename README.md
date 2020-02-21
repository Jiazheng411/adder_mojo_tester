# adder_mojo_tester
This FPGA project is used to test the 1-bit full adder created for 50.002 1D mini hardware project, it has two modes: automated testing mode and manual testing mode


# inputs and ouputs for adder
* The inputs a b ci to the adders are connected with IO pin p97(io_led[0][0]), p98(io_led[0][1]), p94(io_led[0][2])
* The output of the adder are connected with p111(io_dip[1][1], Co), p112(io_dip[1][0],sum)


# check result from adder
* If the answer from the adder is correct, the io_led[2][7:0] will be on, and nothing displays on 7-segment displays
* If the answer from the adder is wrong, the io_led[2][7:0] will be off, and '0000' is displayed on 7-segment displays


# testing modes
* When io_dip[2][3:0] are all on, Mojo is in manual testing mode. This allows user to manually set the input to the adder by changing io_dip[0][2:0]
* When one of more io_dip[2][3:0] is(are) off, Mojo is in automated testing mode. Mojo will send all possible inputs to the adder and check the outputs from adder, after checking all the possible inputs, it stops. Pressing the reset button will ask Mojo to test all 8 possible cases again.
