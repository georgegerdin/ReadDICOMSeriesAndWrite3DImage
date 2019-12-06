A sample project to make the following example

https://itk.org/ITKExamples/src/IO/GDCM/ReadDICOMSeriesAndWrite3DImage/Documentation.html

work with vcpkg

Installation instructions:
1. Install vcpkg
2. Using vcpkg install itk, openjpeg and eigen3
3. git clone this repository
4. enter the project dir, create and enter a build directory
5. Generate project solution with cmake
6. Build with visual studio
7. Execute with path to dicom file as first parameter