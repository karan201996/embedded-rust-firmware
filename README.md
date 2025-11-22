# Embedded Rust Firmware  

## Overview  
This project rewrites a simple embedded application (such as an LED blink and button debounce) using Rust. It leverages `embedded-hal` traits and board support crates to demonstrate memory‑safe, modern firmware development for microcontrollers.  

## Hardware Requirements  
- A Rust‑supported MCU board (e.g., STM32F3 Discovery, RP2040, or nRF52).  
- On‑board LED and push button.  
- Debug probe (ST‑Link, J‑Link, or PicoProbe).  

## Software Requirements  
- Rust toolchain with `rustup` (`rustup target add thumbv7em-none-eabihf` or appropriate target).  
- `cargo‑embed` or `probe‑run` for flashing and debugging.  
- Crates: `cortex-m`, `cortex-m-rt`, `embedded-hal`, and a board support crate.  

## Build & Flash Instructions  
1. Install Rust via `rustup` and add the required target triple.  
2. Clone this repository.  
3. Run `cargo build --release` to compile the firmware.  
4. Flash using `cargo embed --release` or `probe-run --release`.  
5. Observe the LED blinking and verify the button toggles the LED state.  

## Features  
- Fully memory‑safe firmware avoiding null pointers and data races.  
- Abstraction over hardware using `embedded-hal`.  
- Simple state machine for button debouncing.  
- Host‑side unit tests demonstrating logic verification.  

## Demo  
Press the button to toggle the LED; the LED blinks at a steady rate and switches states without bouncing. Run `cargo test` on your host to see logic tests pass.  

## Future Work  
- Add support for additional peripherals (I²C, SPI).  
- Integrate RTIC or Embassy for concurrency.  
- Experiment with `no_std` data structures using `heapless`. 
