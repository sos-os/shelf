# SHELF: SOS Horrible ELF library

a library for parsing, navigating, and loading 32- and 64-bit
[Executable and Linkable File]s for the [Stupid Operating System].

[Executable and Linkable File]: http://wiki.osdev.org/ELF
[Stupid Operating System]: http://github.com/sos-os

## why are we writing our own ELF lib?

although there are a number of other nice ELF libraries in Rust, such as
[xmas-elf] and [goblin], I'm writing my own for the following handful of
reasons:

+ requirements specific to our use-case (no std, no allocation, &c)
+ up to date with recent Rust language features (not all ELF libs are
  actively maintained)
+ compatibility with SOS' types & representations without translation
  layers (e.g., uses our `PAddr` type.)
+ it's fun & I want to do it myself!

[xmas-elf]: https://github.com/nrc/xmas-elf
[goblin]: https://github.com/m4b/goblin
