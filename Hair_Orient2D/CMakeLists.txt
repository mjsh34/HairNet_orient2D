cmake_minimum_required(VERSION 3.8)
project(Orient2D)

set(CMAKE_CXX_STANDARD 11)


set(SOURCE_FILES main_nobodyrender.cpp Color.h Im.hpp lineqn.h MathUtils.hpp Orient2D.hpp OrientMap.hpp
        util.h Vec.hpp
        )

find_package(OpenCV REQUIRED)
#find_package(FFTW3 REQUIRED)
find_package(JPEG REQUIRED)
find_package(PNG  REQUIRED)

include_directories(
	${OpenCV_INCLUDE_DIR}
	#${FFTW3_INCLUDE_DIR}
	${JPEG_INCLUDE_DIR}
        ${PNG_INCLUDE_DIR}
)

add_executable(Orient2D ${SOURCE_FILES} )

target_link_libraries(Orient2D
        ${OpenCV_LIBS}
	#${FFTW3_LIBRARIES}
	/usr/lib/x86_64-linux-gnu/libfftw3.a
        ${JPEG_LIBRARIES}
        ${PNG_LIBRARIES}
        )
