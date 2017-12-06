# ghdl_internal_error_issue

This repo contains code to replicate a bug experienced in ghdl 

I have noted the unconstrained array limitation of ghdl, but the code doesn't uses such array, but gives an error similar to the issue #473

## Code explanation

The code uses 3 generic package to represent pixels in vhdl (it may not be the cleanest way to do so).



## Command line used to generate the bug with the provided code

ghdl -a -lv -v --std=08 --warn-library  --warn-delayed-checks  --warn-specs  --warn-unused   --warn-nested-comment --warn-parenthesis  --warn-runtime-error pixel_pkg.vhd pixel_column_pkg.vhd pixel_matrix_pkg.vhd test_op.vhd

ghdl -e -v -v --std=08 --warn-library  --warn-delayed-checks  --warn-specs  --warn-unused   --warn-nested-comment --warn-parenthesis  --warn-runtime-error test_op &> error.txt

## Resulting error can be found under the file "error.txt"
