CONTIKI_PROJECT = rng
all: $(CONTIKI_PROJECT)

# Add EVB1000 platform folder
#TARGETDIRS += ../../platform/stm32nucleo-dw1000

DEFINES+=PROJECT_CONF_H=\"project-conf.h\"

# No network stack for the moment
CONTIKI_WITH_IPV4 = 0
CONTIKI_WITH_IPV6 = 0
CONTIKI_WITH_RIME = 1

CONTIKI = ../..
include $(CONTIKI)/Makefile.include

#include $(CONTIKI)/NodeSerialNumbers.include
NODEA=303637304646333333303336343334423433303335393332
NODEB=303636384646353434383534363737353637313734363436

upA: rpl-node.bin
	st-flash --serial $(NODEA) write rpl-node.bin 0x08000000

upB: rpl-node.bin
	st-flash --serial $(NODE5) write rpl-node.bin 0x08000000

upboth: upB upA
