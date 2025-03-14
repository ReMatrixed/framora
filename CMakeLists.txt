idf_build_get_property(target IDF_TARGET)

project(framora)
if(${target} STREQUAL "linux")
    idf_component_register(INCLUDE_DIRS include)
else()
    set(srcs "src/framora.c")

    # NOTE: Для будущего использования
    # if(CONFIG_FEATURE_GRAPHIUM)
    #     list(APPEND srcs "src/graphium/graphium.c")
    # endif()

    idf_component_register(
        SRCS "${srcs}"
        INCLUDE_DIRS include
        PRIV_INCLUDE_DIRS private_include
    )
endif()