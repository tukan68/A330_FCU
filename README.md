# A330 FCU
The goal of this project is a dashboard with the most important buttons, switches and displays of a A330 FCU for X-Plane.
The communication between the dashboard and X-Plane uses UDP.

## Prerequisites
 * [X-Plane](http://www.x-plane.com)
 * [A330 from JARDesign](http://jardesign.org/a330/)

## Simulated controls
 * Displays:
   * Speed (SPD) inclusive managed speed dot
   * Heading (HDG) inclusive managed lateral dot
   * Altitude (ALT) inclusive managed level change dot
   * Vertical Speed (V/S)
 * Selectors knobs:
   * Speed
   * Heading
   * Altitude
   * Vertical Speed
 * Switches:
   * ND mode selector
   * ND range selector
 * Buttons:
   * AP1/AP2 engagement
   * A/THR activation
   * LOC/ALT/APPR engagement
   * FD/LS selectors
   * CSTR/WPT/VOR.D/NDB/APT selectors

## Hardware
 * ESP8266 (Wemos D1 mini)
 * MAX7219 (7 segment display driver, SPI bus) or
   MAX6955 (7 segment display driver, I2C bus)
 * MCP23017 (GPIO extender, I2C bus)

## Software
 * IDE: PlatformIO

## Thoughts
 * If the position of a selector switch is changed in the simulation the dashboard do not correspond
   to the simulation. Therefore the position of the selector switches is periodically send to X-Plane.
 * Add a refresh (reset) button which will send all positions to X-Plane and update all controls
   according their state in X-Plane
 * Control the brightness of the displays and LEDs. Either from the settings in X-Plane or
   on-board controls to set this individually for the displays and the LEDs.

## ToDo
 * Check, that DataRefs are available to control all elements

