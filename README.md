# TPM2-initcpio
TPM2 Settings for initcpio builds

install tpm2-tools
install tpm2-tss

Install tpm2-hook in /etc/initcpio/hooks/tpm2
Install tpm2-install in /etc/initcpio/install/tpm2

edit mkinitcopio.conf and add tpm2 before encryption

Could try to add 
export TPM2TOOLS_TCTI="device:/dev/tpm0"

/etc/udev/rules.d/tpm-udev.rules
# tpm devices can only be accessed by the tss user but the tss
# group members can access tpmrm devices
KERNEL=="tpm[0-9]*", MODE="0660", OWNER="tss"
KERNEL=="tpmrm[0-9]*", MODE="0660", OWNER="tss", GROUP="tss"


