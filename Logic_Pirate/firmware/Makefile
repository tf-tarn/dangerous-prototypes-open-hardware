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
	-I/opt/microchip/mla2013/Microchip/Include/USB \
        -I/home/tarn/projects/dangerous-prototypes-open-hardware/Logic_Pirate/firmware
LIBDIRS = -L/opt/microchip/xc32/v1.40/pic32mx/lib/
FLAGS = -mprocessor=32MX250F128B


# firmware.elf: $(SRCS)
# 	$(CC) $(FLAGS) $(INCLUDE) $(LIBDIRS) $(LIBS) $^ -o $@

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


# ./libUSB/Android Host Driver/usb_host_android.c
# ./libUSB/Audio Device Driver/usb_function_audio.c
# ./libUSB/Audio v1 Host Driver/usb_host_audio_v1.c
# ./libUSB/CCID Device Driver/usb_function_ccid.c
# ./libUSB/CDC Device Driver/usb_function_cdc.c
# ./libUSB/CDC Host Driver/usb_host_cdc.c
# ./libUSB/CDC Host Driver/usb_host_cdc_interface.c
# ./libUSB/Charger Host Driver/usb_host_charger.c
# ./libUSB/Generic Device Driver/usb_function_generic.c
# ./libUSB/Generic Host Driver/usb_host_generic.c
# ./libUSB/HID Device Driver/usb_function_hid.c
# ./libUSB/HID Host Driver/usb_host_hid.c
# ./libUSB/HID Host Driver/usb_host_hid_parser.c
# ./libUSB/MIDI Host Driver/usb_host_midi.c
# ./libUSB/MSD Device Driver/usb_function_msd.c
# ./libUSB/MSD Device Driver/usb_function_msd_multi_sector.c
# ./libUSB/MSD Host Driver/usb_host_msd.c
# ./libUSB/MSD Host Driver/usb_host_msd_scsi.c
# ./libUSB/PHDC Device Driver/usb_function_phdc_com_model.c
# ./libUSB/PHDC Device Driver/usb_function_phdc.c
# ./libUSB/Printer Host Driver/usb_host_printer.c
# ./libUSB/Printer Host Driver/usb_host_printer_esc_pos.c
# ./libUSB/Printer Host Driver/usb_host_printer_pcl_5.c
# ./libUSB/Printer Host Driver/usb_host_printer_postscript.c
# ./libUSB/Printer Host Driver/usb_host_printer_primitives.c
