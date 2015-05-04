# pps-gpio-amlogic
GPIO PPS for Amlogic devices (ODROID C1)

The PPS driver available in the kernel sources published by HardKernel for ODROID C1 
(https://github.com/hardkernel/linux/tree/odroidc-3.10.y) lacks device tree support.
In addition, using GPIO devices on this tree requires one to call Amlogic-specific
GPIO calls, instead of the default kernel GPIO lib.

## To compile
Replace the upstream pps-gpio.c with this version and recompile your kernel.

## To use
Add a similar snippet to your DTS file, and recreate a DTB for your board.
This example uses header pin 12 for PPS. Refer to http://www.hardkernel.com/main/products/prdt_info.php?g_code=G141578608433&tab_idx=2
to find the correct gpios for your setup.

pps {
	compatible = "pps-gpio";
	gpios = "GPIOY_7";
};
