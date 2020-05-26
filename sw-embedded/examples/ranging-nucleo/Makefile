CONTIKI_PROJECT = rng
all: $(CONTIKI_PROJECT)

ca: clean all

CFLAGS += -u _printf_float

# Add stm32nucleo platform folder
#TARGETDIRS += ../../platform/stm32nucleo-dw1000

DEFINES+=PROJECT_CONF_H=\"project-conf.h\"

# No network stack for the moment
CONTIKI_WITH_IPV4 = 0
CONTIKI_WITH_IPV6 = 1
CONTIKI_WITH_RIME = 1

CONTIKI = ../..
include $(CONTIKI)/Makefile.include

#include $(CONTIKI)/NodeSerialNumbers.include

NODEA=303637304646333333303336343334423433303335393332
NODEB=303636384646353434383534363737353637313734363436

upInitiator: rng.bin
	st-flash --serial $(NODEA) write $(CONTIKI_PROJECT).bin 0x08000000

upResponder: rng.bin
	st-flash --serial $(NODEB) write $(CONTIKI_PROJECT).bin 0x08000000

upboth: upResponder upInitiator
