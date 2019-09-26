# TPM2-initcpio
TPM2 Settings for initcpio builds

install tpm2-tools
install tpm2-tss

Install tpm2-hook in /etc/initcpio/hooks/tpm2
Install tpm2-install in /etc/initcpio/install/tpm2

edit mkinitcopio.conf and add tpm2 before encryption

Could try to add 
export TPM2TOOLS_TCTI="device:/dev/tpm0"

For the new Kernel after 5.3 have to add variable 
rng_core.default_quality=1000


If the above failes, try to add udev rules
/etc/udev/rules.d/tpm-udev.rules


