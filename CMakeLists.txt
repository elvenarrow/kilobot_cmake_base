CMAKE_MINIMUM_REQUIRED(VERSION 3.2)
SET(CMAKE_SYSTEM_NAME Generic)

#============================================================================================
PROJECT(kilobot_cmake_base) # Replace kilobot_cmake_base with your project's name

SET(DEVICE "atmega328p")
SET(FREQ "8000000")

#============================================================================================

SET(CMAKE_C_COMPILER /usr/local/bin/avr-gcc)    # Replace /usr/local/bin/avr-gcc with
                                                # the path to you avr-gcc compiler

SET(CMAKE_C_FLAGS  "-Os -mmcu=${DEVICE} -DF_CPU=${FREQ}UL -std=gnu99 -Wl,--gc-sections")

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/bin")

#============================================================================================

SET(SOURCE_FILES
        main.c
   )

INCLUDE_DIRECTORIES(include)
LINK_DIRECTORIES(lib)

#============================================================================================

ADD_EXECUTABLE(${PROJECT_NAME} ${SOURCE_FILES} main.c)

TARGET_LINK_LIBRARIES(${PROJECT_NAME} kilolib)

ADD_CUSTOM_COMMAND(TARGET ${PROJECT_NAME} POST_BUILD COMMAND avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/${PROJECT_NAME} ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/${PROJECT_NAME}.hex)