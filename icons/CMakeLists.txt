if(BINARY_ICONS_RESOURCE)
    generate_binary_resource(icons binary_resource)
endif()

########### install files ###############

set(pantherx_icon_dirs
    actions animations applets apps categories preferences devices emblems
    emotes mimetypes pantherx places status)

set(PANTHERX_INSTALL_DIR ${KDE_INSTALL_FULL_ICONDIR}/pantherx)

if (NOT SKIP_INSTALL_ICONS)
    install( DIRECTORY ${pantherx_icon_dirs} DESTINATION ${PANTHERX_INSTALL_DIR} )
    install( FILES index.theme DESTINATION ${PANTHERX_INSTALL_DIR})
endif()

gtk_update_icon_cache(${PANTHERX_INSTALL_DIR})

if(BINARY_ICONS_RESOURCE)
    install( FILES ${binary_resource} DESTINATION ${PANTHERX_INSTALL_DIR})
endif()
