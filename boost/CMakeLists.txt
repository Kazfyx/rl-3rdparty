ExternalProject_Add(
	boost
	URL https://boostorg.jfrog.io/artifactory/main/release/1.83.0/source/boost_1_83_0.7z
	#URL ${CMAKE_CURRENT_SOURCE_DIR}/boost_1_83_0.7z
	URL_MD5 3200e75aaad7167d549433d7985d1c00
	CONFIGURE_COMMAND ""
	BUILD_COMMAND ""
	BUILD_IN_SOURCE 1
	INSTALL_COMMAND ${CMAKE_COMMAND} -E copy_directory <SOURCE_DIR>/boost ${CMAKE_INSTALL_FULL_INCLUDEDIR}/boost
)

ExternalProject_Add_Step(
	boost install-licenses
	DEPENDEES install
	COMMAND ${CMAKE_COMMAND} -E copy <SOURCE_DIR>/LICENSE_1_0.txt ${CMAKE_INSTALL_FULL_DATADIR}/licenses/boost/LICENSE_1_0.txt
)
