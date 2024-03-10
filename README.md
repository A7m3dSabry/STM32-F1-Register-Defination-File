# STM32 F1 Register Defination File

## The register defination file to support two different ways to access registers

- Register access way
  - in this way we access the full register with its address
  - The Register is represneted using MACROs in C
  - Normally used with masks to acceess specific bits
  - this can lead to errors if not accessing the right bit or accessing wrong bit location

- Struct Access Way
  - The Register is defined as a Struct which has elements (bit fields)
  - Using this approach you ensure you only accessing specific bits
  - the flaw can happen if you casted the struct on a wrong address but can be fixed easily and this prevents human error in deciding which bit to access and where is its location


## Sneaky way in accessing Peripherals
a lot of manufacture (ex: ST) makes similar peripherals locations in memory in adjecent way, so , i coded that you can access the similar adjecent peripherals like an array
- this optimize the code on the flash as you don't need to switch over the user input to check which peripheral it choosed (EX: USART1 or USART2) you can make an enum and make the user choice is actually the index of the peripheral
- benifits: optimize flash code and makes performance faster
