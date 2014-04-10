CC=avr-gcc
CXX=avr-g++
MCU=-mmcu=atmega328p
CPU_SPEED=-DF_CPU=16000000UL
CFLAGS=-c -g -Os -Wall -ffunction-sections -fdata-sections -mmcu=atmega328p -DF_CPU=16000000L -MMD -DUSB_VID=null -DUSB_PID=null -DARDUINO=101
CXXFLAGS= -c -g -Os -Wall -fno-exceptions -ffunction-sections -fdata-sections -mmcu=atmega328p -DF_CPU=16000000L -MMD -DUSB_VID=null -DUSB_PID=null -DARDUINO=101 
BOARD=arduinoUno
LIBNAME=libArduinoModif.a 
INCDIR=../include 
LDFLAGS=
LIBDIR=../lib
OBJECTS=wiring.o wiring_analog.o wiring_digital.o \
        wiring_pulse.o wiring_shift.o Print.o   \
        Tone.o WMath.o WString.o WInterrupts.o \
	CDC.o USBCore.o HID.o IPAddress.o Stream.o \
	main.o HardwareSerial.o new.o malloc.o realloc.o

default: $(OBJECTS)
	 avr-ar rcs $(LIBNAME) $^ $(LDFLAGS)
	mkdir -p $(INCDIR)
	mkdir -p $(LIBDIR)
	 cp *.h $(INCDIR)
	 mv $(LIBNAME) $(LIBDIR)
	 cp -R $(INCDIR) ~/programmation/arduinoProgrammation/
	cp -R $(LIBDIR) ~/programmation/arduinoProgrammation/
	 rm *.o

%.o : %.c
	  $(CC) -I$(INCDIR) $< $(CFLAGS) -o $@

%.o : %.cpp
	  $(CXX) -I$(INCDIR) $< $(CXXFLAGS) -o $@