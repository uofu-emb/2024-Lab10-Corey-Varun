# Executable file for code using sleep_ms for blinking LED.
add_executable(Blink_Sleep_MS
    blink_sleep_ms.c
    )

pico_set_program_name(Blink_Sleep_MS "test")
pico_set_program_version(Blink_Sleep_MS "0.1")

pico_enable_stdio_uart(Blink_Sleep_MS 0)
pico_enable_stdio_usb(Blink_Sleep_MS 1)

target_link_libraries(Blink_Sleep_MS PRIVATE
  pico_stdlib
  pico_multicore
  pico_async_context_freertos
  FreeRTOS-Kernel-Heap4
)

if(PICO_CYW43_SUPPORTED)
    target_link_libraries(Blink_Sleep_MS PRIVATE
        pico_cyw43_arch_none
    )
endif()
pico_add_extra_outputs(Blink_Sleep_MS)
add_custom_target(flash_sleep_ms picotool load -f $<TARGET_FILE:Blink_Sleep_MS> DEPENDS Blink_Sleep_MS)


# Executable file for code using different thread for blinking LED.
add_executable(Blink_RTOS
    blink_rtos.c
    )

pico_set_program_name(Blink_RTOS "test")
pico_set_program_version(Blink_RTOS "0.1")

pico_enable_stdio_uart(Blink_RTOS 0)
pico_enable_stdio_usb(Blink_RTOS 1)

target_link_libraries(Blink_RTOS PRIVATE
  pico_stdlib
  pico_multicore
  pico_async_context_freertos
  FreeRTOS-Kernel-Heap4
)

if(PICO_CYW43_SUPPORTED)
    target_link_libraries(Blink_RTOS PRIVATE
        pico_cyw43_arch_none
    )
endif()
pico_add_extra_outputs(Blink_RTOS)
add_custom_target(flash_rtos picotool load -f $<TARGET_FILE:Blink_RTOS> DEPENDS Blink_RTOS)


# Executable file for code to get 100% CPU utilization
add_executable(Blink_Busy_Loop
    blink_busy_wait.c
    )

pico_set_program_name(Blink_Busy_Loop "test")
pico_set_program_version(Blink_Busy_Loop "0.1")

pico_enable_stdio_uart(Blink_Busy_Loop 0)
pico_enable_stdio_usb(Blink_Busy_Loop 1)

target_link_libraries(Blink_Busy_Loop PRIVATE
  pico_stdlib
  pico_multicore
  pico_async_context_freertos
  FreeRTOS-Kernel-Heap4
)

if(PICO_CYW43_SUPPORTED)
    target_link_libraries(Blink_Busy_Loop PRIVATE
        pico_cyw43_arch_none
    )
endif()
pico_add_extra_outputs(Blink_Busy_Loop)
add_custom_target(flash_busy_loop picotool load -f $<TARGET_FILE:Blink_Busy_Loop> DEPENDS Blink_Busy_Loop)


# Executable file for code to toggle a GPIO in response to an external signal
add_executable(External_Interrupt
    interrupt.c
    )

pico_set_program_name(External_Interrupt "test")
pico_set_program_version(External_Interrupt "0.1")

pico_enable_stdio_uart(External_Interrupt 0)
pico_enable_stdio_usb(External_Interrupt 1)

target_link_libraries(External_Interrupt PRIVATE
  pico_stdlib
  pico_multicore
  pico_async_context_freertos
  FreeRTOS-Kernel-Heap4
)

if(PICO_CYW43_SUPPORTED)
    target_link_libraries(External_Interrupt PRIVATE
        pico_cyw43_arch_none
    )
endif()
pico_add_extra_outputs(External_Interrupt)
add_custom_target(flash_interrupt picotool load -f $<TARGET_FILE:External_Interrupt> DEPENDS External_Interrupt)


# Executable file for example code for hello_sleep_alarm.
add_executable(Sleep_Alarm
    hello_sleep_alarm.c
    )

pico_set_program_name(Sleep_Alarm "test")
pico_set_program_version(Sleep_Alarm "0.1")

pico_enable_stdio_uart(Sleep_Alarm 0)
pico_enable_stdio_usb(Sleep_Alarm 1)

target_link_libraries(Sleep_Alarm PRIVATE
  pico_stdlib
  pico_multicore
  pico_async_context_freertos
  FreeRTOS-Kernel-Heap4
  hardware_sleep
)

if(PICO_CYW43_SUPPORTED)
    target_link_libraries(Sleep_Alarm PRIVATE
        pico_cyw43_arch_none
    )
endif()
pico_add_extra_outputs(Sleep_Alarm)
add_custom_target(flash_sleep_alarm picotool load -f $<TARGET_FILE:Sleep_Alarm> DEPENDS Sleep_Alarm)


# Executable file for example code for hello_dormant_gpio.
add_executable(Dormant_GPIO
    hello_dormant_gpio.c
    )

pico_set_program_name(Dormant_GPIO "test")
pico_set_program_version(Dormant_GPIO "0.1")

pico_enable_stdio_uart(Dormant_GPIO 0)
pico_enable_stdio_usb(Dormant_GPIO 1)

target_link_libraries(Dormant_GPIO PRIVATE
  pico_stdlib
  pico_multicore
  pico_async_context_freertos
  FreeRTOS-Kernel-Heap4
  hardware_sleep
)

if(PICO_CYW43_SUPPORTED)
    target_link_libraries(Dormant_GPIO PRIVATE
        pico_cyw43_arch_none
    )
endif()
pico_add_extra_outputs(Dormant_GPIO)
add_custom_target(flash_dormant_gpio picotool load -f $<TARGET_FILE:Dormant_GPIO> DEPENDS Dormant_GPIO)
