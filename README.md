adept_tcl
=========

TCL package written to handle the file export capabilities found in Jim Wu's ADEPT software (https://sites.google.com/site/adepthome/home).

This is a subset of functionality/capability of ADEPT, mainly because these functions are designed to do some of the nice features ADEPT has, but PlanAhead/Vivado has many of the features already (Export to XDC, Export HDL (Verilog/VHDL), Export CSV, etc).

TODO
----
1. Add MGT Exports (MGT Map, etc)
2. Add Utilization Export
3. Add Clock Region Export
4. Add Port Pinout Export
5. Add more comments

All the above exports will come in 2 flavors: CSV, and Excel. The Excel flavor is on WINDOWS ONLY. This means Linux users will only have access to the CSV version.

How It Works
------------
It works in two ways, in pure TCL mode, or in the PlanAhead/Vivado custom command mode.

### Pure TCL Mode ###
You source the `adept_tcl.tcl` file once PlanAhead/Vivado is launched.

Do note that the tcom package is for WINDOWS ONLY this means that it will not load on Linux, and you will be forced to use CSV.

Now you will have the list of commands.

### GUI Mode ###
There are a couple things you could do here:

1. Modify the PlanAhead/Vivado init.tcl script to source the `adept_tcl.tcl` file, or...
2. Create a Custom Command button, and reference the `adept_tcl.tcl` file in the command. (This means if the file is moved, the command will not work.)

As I get more time to work on this, it should get better, but due to lack of free time, this will not be actively worked on all that much.

Features of ADEPT TCL
---------------------
The biggest feature is, if you're an OrCAD user, it will export it into a CSV that can be used to generate a schematic object!

To use this, load up PlanAhead/Vivado and source the script. You will have `adept_tcl::write_pkgorcad`. The only switch working is the -file switch (where you want the location of the CSV to exist).

More features are to come!
