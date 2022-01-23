if (NOT TARGET pico_sdio)
    add_library(pico_sdio INTERFACE)
    
    pico_generate_pio_header(pico_sdio ${CMAKE_CURRENT_LIST_DIR}/sdio.pio)
    
    target_sources(pico_sdio INTERFACE
            ${CMAKE_CURRENT_LIST_DIR}/sdio.c
    )
    
    target_include_directories(pico_sdio INTERFACE ${CMAKE_CURRENT_LIST_DIR}/include)
    target_link_libraries(pico_sdio INTERFACE hardware_dma hardware_pio)
endif()
