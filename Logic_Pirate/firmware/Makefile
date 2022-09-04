SRCS =	libUSB/usb_device.c \
	libUSB/CDC_Device_Driver/usb_function_cdc.c \
	general_exception_handler.c \
	main.c \
	usb_callback_functions.c \
	usb_descriptors.c

OBJS = $(patsubst %.c,build/%.o,$(SRCS))

CC = /opt/microchip/xc32/v1.40/bin/xc32-gcc
INCLUDE = -I/opt/microchip/xc32/v1.40/pic32mx/include/lega-c \
	-I/opt/microchip/mla2013/Microchip/Include \
        -I/home/tarn/projects/dangerous-prototypes-open-hardware/Logic_Pirate/firmware
LIBDIRS = -L/opt/microchip/xc32/v1.40/pic32mx/lib/
FLAGS = -mprocessor=32MX250F128B


firmware.elf: $(OBJS)
	$(CC) $(FLAGS) $(LIBDIRS) $(LIBS) $^ -o $@

build/%.o: %.c
	mkdir -p build
	$(CC) $(FLAGS) $(INCLUDE) -c $< -o $@

build/libUSB/%.o: libUSB/%.c
	mkdir -p build/libUSB
	$(CC) $(FLAGS) $(INCLUDE) -c $< -o $@
build/libUSB/CDC_Device_Driver/%.o: libUSB/CDC_Device_Driver/%.c
	mkdir -p build/libUSB/CDC_Device_Driver/
	$(CC) $(FLAGS) $(INCLUDE) -c $< -o $@

clean:
	rm -Rf build/

