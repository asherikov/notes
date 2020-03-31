Changing LCD brightness on HP 8470p
===================================

1) acpi (as well as sysctl) does not work

    a) install /usr/ports/sysutils/acpi_call
    b) kldload acpi_call
    c) Change brightness:
        acpidump -dt out.asl

        acpi_call -v -p '\_SB.PCI0.GFX0.DD02._BCM' -i '9'
        acpi_call -v -p '\_SB.PCI0.GFX0.DD02._BQC'

    This patch does not help
        https://bugs.freebsd.org/bugzilla/show_bug.cgi?id=190186

2) intel_backlight from intel-gpu-tools works
    a) git clone git://github.com/asherikov/intel-gpu-tools__backlight

    b) install python3, swig2
        ./autogen.sh --disable-tests

    c) gmake install

    d) Apparently needs to be run by root


Flash
=====
www/nspluginwrapper
www/linux-c6-flashplugin11

Before the plugin is first used, each user must run:
% nspluginwrapper -v -a -i

When the plugin port has been updated and reinstalled, each user must run:
% nspluginwrapper -v -a -u


Ports
=====
    - Create plist automatically: make makeplist
    - Configure ports recursively: make config-recursive


Delete old files after installworld
===================================
    make BATCH_DELETE_OLD_FILES=true delete-old delete-old-libs


/tmp noexec flag
================
    'noexec' flag for /tmp causes a failure during installworld:
    'Unable to determine compiler type for CC=cc'
    https://forums.freebsd.org/threads/42969/


Switch version
==============
`svn switch '^/stable/9'`


Bluetooth
=========
    hccontrol -n ubt0hci inquiry
    hccontrol -n ubt0hci create_connection <id>
    hccontrol -n ubt0hci write_authentication_enable 1
    hccontrol -n ubt0hci write_encryption_mode 1
    hccontrol -n ubt0hci read_connection_list
    virtual_oss -S -C 2 -c 2 -r 48000 -b 16 -s 768 -R /dev/null -P /dev/bluetooth/<id> -d dsp
