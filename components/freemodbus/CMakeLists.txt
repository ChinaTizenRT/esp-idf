# The following five lines of boilerplate have to be in your project's
# CMakeLists in this exact order for cmake to work correctly
set(COMPONENT_SRCS  "common/esp_modbus_master.c"
                    "common/esp_modbus_slave.c"
                    "modbus/mb.c"
                    "modbus/mb_m.c"
                    "modbus/ascii/mbascii.c"
                    "modbus/rtu/mbrtu_m.c"
                    "modbus/rtu/mbrtu.c"
                    "modbus/rtu/mbcrc.c"
                    "modbus/tcp/mbtcp.c"
                    "port/port.c"
                    "port/portevent.c"
                    "port/portevent_m.c"
                    "port/portother.c"
                    "port/portother_m.c"
                    "port/portserial.c"
                    "port/portserial_m.c"
                    "port/porttimer.c"
                    "port/porttimer_m.c"
                    "modbus/functions/mbfunccoils.c"
                    "modbus/functions/mbfunccoils_m.c"
                    "modbus/functions/mbfuncdiag.c"
                    "modbus/functions/mbfuncdisc.c"
                    "modbus/functions/mbfuncdisc_m.c"
                    "modbus/functions/mbfuncholding.c"
                    "modbus/functions/mbfuncholding_m.c"
                    "modbus/functions/mbfuncinput.c"
                    "modbus/functions/mbfuncinput_m.c"
                    "modbus/functions/mbfuncother.c"
                    "modbus/functions/mbutils.c"
                    "serial_slave/modbus_controller/mbc_serial_slave.c"
                    "serial_master/modbus_controller/mbc_serial_master.c")
set(COMPONENT_ADD_INCLUDEDIRS common/include)
set(COMPONENT_PRIV_INCLUDEDIRS  common port modbus modbus/ascii modbus/functions
                                modbus/rtu modbus/tcp modbus/include)
list(APPEND COMPONENT_PRIV_INCLUDEDIRS serial_slave/port serial_slave/modbus_controller
                                        serial_master/port serial_master/modbus_controller)
set(COMPONENT_REQUIRES "driver")

register_component()
