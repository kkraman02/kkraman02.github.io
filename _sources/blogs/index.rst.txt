.. _BMC:

ACPI
----

ACPI defines `hardware
abstraction <https://en.wikipedia.org/wiki/Hardware_abstraction>`__
interfaces between the device’s firmware
(e.g. `BIOS <https://en.wikipedia.org/wiki/BIOS>`__,
`UEFI <https://en.wikipedia.org/wiki/UEFI>`__), the `computer
hardware <https://en.wikipedia.org/wiki/Computer_hardware>`__
components, and the `operating
systems <https://en.wikipedia.org/wiki/Operating_system>`__.

Power states
~~~~~~~~~~~~

Global states
^^^^^^^^^^^^^

The ACPI Specification defines the following four global “Gx” states and
six sleep “Sx” states for an ACPI-compliant computer system:

The specification also defines a *Legacy* state: the state of an
operating system which does not support ACPI. In this state, the
hardware and power are not managed via ACPI, effectively disabling ACPI.