# TRMNL Firmware - Seeed XIAO ESP32c3  +  Waveshare e-paper display 7.5" 

created for the [TRMNL](https://usetrmnl.com) e-ink display.

## Thanks to...
* [@datacompboy / Make yourself your own TRMNL][make-yourself-your-own-TRMNL]


## Hardware
+ [Waveshare E-Paper Display 7.5" v2](https://www.waveshare.com/wiki/7.5inch_e-Paper_HAT_Manual#Working_With_Arduino)
+ [Seeed XIAO ESP32c3]()

## Notes
- [TRMNL Firmware repo](https://github.com/usetrmnl/trmnl-firmware?tab=readme-ov-file#uploading-guide-platformio) instructions are convoluted and delicate.  if you're using `pio` on linux, you dont' need to do nearly any steps described.  don't even look at it.

- follow instructions for wiring as mentioned in [@datacompboy's article][2]
- the TRMNL firmware binaries are included in upstream repo.  when building image with `pio` you can define which version to use in [./include/config.h](./include/config.h)
  ```cpp
  #define FW_MAJOR_VERSION 1
  #define FW_MINOR_VERSION 5
  #define FW_PATCH_VERSION 11
  ```
- update value for `API_BASE_URL` in [include/config.h](./firmware/include/config.h) if you want to use a BYOS service instead of the official TRMNL

## Build Firmware
1. make changes or pull my branch of [usetrmnl/firmware][trmnl-firmware]
1. plugin esp32c3
1. `pio run -e seeed_xiao_esp32c3 --target upload`
1. solder wires
1. power-up
1. start local API service
1. enter WIFI details & custom API url



[make-yourself-your-own-TRMNL]: https://medium.com/@datacompboy/make-yourself-your-own-trmnl-146486fbf13e "@datacompboy's article"
[trmnl-firmware]: https://github.com/usetrmnl/firmware "TRMNL Firmware" 
[trmnl-byod]: https://docs.usetrmnl.com/go/diy/byod "TRMNL BYOD"
[trmnl-setup-new-device]: https://help.usetrmnl.com/en/articles/9416306-how-to-set-up-a-new-device "How to set up a new device"
[trmnl-byod-license]: https://shop.usetrmnl.com/products/byod "Buy TRMNL BYOD License"
