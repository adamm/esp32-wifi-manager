if(IDF_VERSION_MAJOR GREATER_EQUAL 4)
    idf_component_register(SRC_DIRS src
        PRIV_REQUIRES esp_wifi
        REQUIRES log nvs_flash mdns wpa_supplicant lwip esp_http_server
        INCLUDE_DIRS src
        EMBED_FILES src/wifi.css src/wifi.js src/wifi.html)
else()
    set(COMPONENT_SRCDIRS src)
    set(COMPONENT_ADD_INCLUDEDIRS src)
    set(COMPONENT_REQUIRES log nvs_flash mdns wpa_supplicant lwip esp_http_server)
    set(COMPONENT_EMBED_FILES src/wifi.css src/wifi.js src/wifi.html)
    register_component()
endif()
