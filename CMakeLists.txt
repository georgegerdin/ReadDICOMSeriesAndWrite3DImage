cmake_minimum_required(VERSION 3.8)

if(DEFINED ENV{VCPKG_ROOT} AND NOT DEFINED CMAKE_TOOLCHAIN_FILE)
  set(CMAKE_TOOLCHAIN_FILE "$ENV{VCPKG_ROOT}/scripts/buildsystems/vcpkg.cmake"
      CACHE STRING "")
endif()

project(ReadDICOMSeriesAndWrite3DImage)

find_package(ITK CONFIG REQUIRED
  ITKCommon
  ITKIOImageBase
  ITKIOGDCM
  ITKEigen3
  ITKIONRRD
  )

find_package(Eigen3 REQUIRED CONFIG)
find_package(OpenJPEG CONFIG REQUIRED)

include( ${ITK_USE_FILE} )

add_executable(ReadDICOMSeriesAndWrite3DImage
	main.cc
)

target_link_libraries(ReadDICOMSeriesAndWrite3DImage PUBLIC 
	ITKCommon 
	ITKIOImageBase 
	ITKIOGDCM
	ITKIONRRD
	openjp2
	Eigen3::Eigen
)