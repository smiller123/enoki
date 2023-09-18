# Enoki
Enoki is a framework for rapid development of Linux kernel schedulers. It will be presented at Eurosys '24.

The main directories are `bento`, `enoki-schedulers`, and `enoki-kernel`.

The `enoki-kernel` repository holds the custom modified kernel for enoki. The kernel must be compiled and installed before the schedulers will build. The module linked under this directory can be found at [https://gitlab.cs.washington.edu/sm237/ghost-kernel](https://gitlab.cs.washington.edu/sm237/ghost-kernel).

The `bento` directory contains the framework for supporting safe access to kernel data structures. It builds upon the library used in the Bento work.

The `enoki-schedulers` directory contains the code for the schedulers. The module linked under this directory can be found at [https://gitlab.cs.washington.edu/sm237/bento-ghost](https://gitlab.cs.washington.edu/sm237/bento-ghost).

Currently, documented benchmarks are included in the `enoki-schedulers` directory.

### Supported Environments
Enoki uses a custom Linux kernel based on version 5.11. To install and run Enoki, this custom kernel must be installed on your device or in a QEMU based virtual machine.

### Installation instructions
To load the submodules, run: `git submodule update --init --recursive` in the root directory.
To update, run `git submodule update --recursive --remote`.

Then, build the code in the submodules following the instructions there.
Start with `enoki-kernel`. Build and install the kernel following the instructions in this repository.

Then, move to the `bento` repository. Run `git submodule update --init --recursive` to ensure that the submodules are loaded. Run `git checkout ghost-support` to switch to the correct branch. This directory does not need to be compiled because it is used as a library in the next step.

Move to the `enoki-schedulers` directory. Compile and test the scheduler according to the instructions in that directory.

