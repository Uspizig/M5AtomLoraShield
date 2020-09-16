# M5AtomLoraShield
This is a Lora Shield for the M5 Atom.
With this shield you may enable Lora or TheThingsNetwork on a M5 Atom ESP32

In the Attached folder you may see
1. Schematic(PDF)
2. Gerber Files(Zip File)
3. Changes in the SW for https://github.com/mcci-catena/arduino-lmic


You may change the following lines in the SW of Arduino-LMIC:
To do this
Change in the folder Arduino\libraries\arduino-lmic-master\src\hal 
the File hal.cpp the function "static void hal_spi_init to": 
static void hal_spi_init () {
    //SPI.begin();//Comment Uspizig Original und WEMOS D1
    //SPI.begin(lmic_pins.sck, lmic_pins.miso, lmic_pins.mosi, lmic_pins_cs); //sck, miso, mosi, cs
    SPI.begin(23, 22, 19, 33);//Comment Uspizig M5Matrix Lora Modul
}




