﻿# HALCON samples

This repository contains code samples for the usage of a **Zivid** 3D camera in **HALCON**.

## Samples list

There are two main categories of samples: **Camera** and **Applications**. The samples in the **Camera** category focus only on how to use the camera. The samples in the **Applications** category use the output generated by the camera, such as the 3D point cloud, a 2D image or other data from the camera. These samples shows how the data from the camera can be used.

Samples indicated by **(cpp)** are written in C++, samples indiced by **(csharp)** are written in C#, while samples written in HDevelop is indicated by **(hdev)**.  

- **Camera**
  - **Basic**
    - **Capture** ([**hdev**][hdev-capture-url]) - Capture point clouds, with color, from the Zivid camera and use it to generate a HALCON ObjectModel3D which is then visualized.
    - **CaptureHDR** ([**hdev**][hdev-captureHDR-url]) - Capture HDR point clouds, with color, from the Zivid camera and use it to generate a HALCON ObjectModel3D which is then visualized.
    - **CaptureHDRCompleteSettings** ([**hdev**][hdev-captureHDRCompleteSettings-url]) - Capture point clouds, with color, from the Zivid camera with fully configured settings and use it to generate a HALCON ObjectModel3D which is then visualized.
    - **CaptureHDRLoop** ([**hdev**][hdev-captureHDRLoop-url]) - Capture HDR point clouds, with color,  from the zivid camera in a loop (while actively changing some acquisition settings). Each point cloud is used to generate a HALCON ObjectModel3D which is then visualized. Settings are read from .json files from [**Zivid sample data**][zivid-sample-data-url]. However, you may also get settings from Zivid Studio. When you save settings they will be stored in .yaml format. Halcon only support reading JSON files, so in order to convert them to JSON use [**YAMLSettingsToJSON**][YAMLSettingsToJSON-url].
    - **ConnectToSerialNumberCamera** ([**hdev**][hdev-connectToSerialNumberCamera-url]) - Connect to a specific Zivid 3D camera based on its serial number. You should modify the sample to include your cameras serial number before running the sample.
    - **CaptureSavePLY** ([**hdev**][hdev-captureSavePLY-url]) - Capture a point cloud, with colors, from the camera and save it to a .ply file format. The .ply file is saved in the same folder as the sample.
    - **CaptureViaGenICam** ([**cpp**][cpp-captureViaGenICam-url], [**csharp**](csharp-captureViaGenICam-url)) - Capture and save a point cloud, with colors, using GenICam interface and Halcon C++/C# SDK.
    - **CaptureViaZivid** ([**cpp**][cpp-captureViaZivid-url], [**csharp**](csharp-captureViaZivid-url)) - Capture a point cloud, with colors, using Zivid SDK, transform it to a Halcon point cloud and save it using Halcon C++/C# SDK.
  - **InfoUtilOther**
    - **QuerySettingsAndParameters** ([**hdev**][hdev-querySettingsAndParameters-url]) - Query information about the image acquisition interface and selected specific parameters of Zivid camera.

- **Applications**
  - **Basic**
    - **FileFormats**
      - **ReadPLY** ([**hdev**][hdev-readPLY-url]) - Read point cloud from PLY file and visualize it.
  - **Advanced**
    - **ObjectMatching** ([**hdev**][hdev-objectMatching-url])
      - **SurfaceMatchingCreateModelFromFile** ([**hdev**][hdev-surfaceMatchingCreateModelFromFile-url]) - Load a model from file for surface-based matching algorithm integrated into HALCON. This example comes with three models created by this program: a Pringles can (190 g), a plastic Coca-Cola bottle (0.5 l) and a Twinings tea box (~15cm x 7cm x 8cm).
      - **SurfaceMatchingCreateModel** ([**hdev**][hdev-surfaceMatchingCreateModel-url]) - Create your own model for surface-based matching algorithm integrated into HALCON. This example comes with three models created by this program: a Pringles can (190 g), a plastic Coca-Cola bottle (0.5 l) and a Twinings tea box (~15cm x 7cm x 8cm).
      - **SurfaceMatchingFindModelFromFile** ([**hdev**][hdev-surfaceMatchingFindModelFromFile-url]) - Run surface-based 3D matching algorithm using a model from file. The model used for matching is created from a reference view of the object. That model is then searched for in a newly captured 3D point cloud. This example comes with three existing object models: a Pringles can (190 g), a plastic Coca-Cola bottle (0.5 l) and a Twinings tea box (~15cm x 7cm x 8cm).
      - **SurfaceMatchingFindModel** ([**hdev**][hdev-surfaceMatchingFindModel-url]) - Run surface-based 3D matching algorithm on data taken with the Zivid camera. The model used for matching is created from a reference view of the object. That model is then searched for in a newly captured 3D point cloud. This example comes with two existing object models: a Pringles can (190 g), a plastic Coca-Cola bottle (0.5 l) and a Twinings tea box (~15cm x 7cm x 8cm).

- **Procedures**
  - **get_first_available_zivid_device** ([**hdev**][hdev-get_first_available_zivid_device-url]) - This procedure returns the first Zivid device from the input tuple of devices. The input tuple 'Devices' is typically returned by info_framegrabber function as follows: 'info_framegrabber ('GenICamTL','device', Information, Devices)'
  - **get_zivid_sample_data_dir** ([**hdev**][hdev-get_zivid_sample_data_dir-url]) - This procedure returns the path to [**Zivid sample data**][zivid-sample-data-url]. This should be used if you want to use some of the sample data, e.g. settings in .json files. 

## Instructions

1. [**Install Zivid Software**](https://www.zivid.com/downloads).
Note: The samples require Zivid SDK v2 (minor version 2.1 or newer).

2. [**Download Zivid Sample Data**](https://zivid.atlassian.net/wiki/spaces/ZividKB/pages/450363393/Sample+Data).

3. [**Install HALCON Software**](https://www.mvtec.com/products/halcon/).
Note: The version tested with Zivid cameras is 20.05 Progress for Windows.

4. Launch HALCON.

5. Open and run one of the samples. Check out [how to run a HALCON sample](https://zivid.atlassian.net/wiki/spaces/ZividKB/pages/427841/How+to+run+a+HALCON+sample).

## Support
If you need assistance with using Zivid cameras, visit our Knowledge Base at [https://help.zivid.com/](https://help.zivid.com/) or contact us at [customersuccess@zivid.com](mailto:customersuccess@zivid.com).

## Licence
Zivid Samples are distributed under the [BSD license](https://github.com/zivid/halcon-samples/blob/master/LICENSE).

[hdev-capture-url]: source/hdev/Camera/Basic/Capture.hdev
[hdev-captureHDR-url]: source/hdev/Camera/Basic/CaptureHDR.hdev
[hdev-captureSavePLY-url]: source/hdev/Camera/Basic/CaptureSavePLY.hdev
[hdev-captureHDRCompleteSettings-url]: source/hdev/Camera/Basic/CaptureHDRCompleteSettings.hdev
[hdev-captureHDRLoop-url]: source/hdev/Camera/Basic/CaptureHDRLoop.hdev
[zivid-sample-data-url]: https://zivid.atlassian.net/wiki/spaces/ZividKB/pages/450363393/Sample+Data
[hdev-get_zivid_sample_data_dir-url]: source/hdev/Procedures/get_zivid_sample_data_dir.hdvp
[YAMLSettingsToJSON-url]: source/hdev/Camera/Basic/YAMLSettingsToJSON.py
[hdev-connectToSerialNumberCamera-url]: source/hdev/Camera/Basic/ConnectToSerialNumberCamera.hdev
[hdev-querySettingsAndParameters-url]: source/hdev/Camera/InfoUtilOther/QuerySettingsAndParameters.hdev
[hdev-readPLY-url]: source/hdev/Applications/Basic/FileFormats/ReadPLY.hdev
[hdev-objectMatching-url]: source/hdev/Applications/Advanced/ObjectMatching
[hdev-surfaceMatchingCreateModelFromFile-url]: source/hdev/Applications/Advanced/ObjectMatching/SurfaceMatchingCreateModelFromFile.hdev
[hdev-surfaceMatchingCreateModel-url]: source/hdev/Applications/Advanced/ObjectMatching/SurfaceMatchingCreateModel.hdev
[hdev-surfaceMatchingFindModelFromFile-url]: source/hdev/Applications/Advanced/ObjectMatching/SurfaceMatchingFindModelFromFile.hdev
[hdev-surfaceMatchingFindModel-url]: source/hdev/Applications/Advanced/ObjectMatching/SurfaceMatchingFindModel.hdev
[hdev-get_first_available_zivid_device-url]: source/hdev/Procedures/get_first_available_zivid_device.hdvp
[cpp-captureViaGenICam-url]: source/cpp/Camera/Basic/CaptureViaGenICam/CaptureViaGenICam.cpp
[cpp-captureViaZivid-url]: source/cpp/Camera/Basic/CaptureViaZivid/CaptureViaZivid.cpp
[csharp-captureViaGenICam-url]: source/csharp/Camera/Basic/CaptureViaGenICam
[csharp-captureViaZivid-url]: source/csharp/Camera/Basic/CaptureViaZivid