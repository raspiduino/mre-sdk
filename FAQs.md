# FAQs
Here are some FAQs related to MRE development and solutions/answers for them.

## Problem: I can't get a free version of the ADS1.2 compiler!
**Solution:** Download the GCC compiler by Sourcery instead: https://sourcery.mentor.com/sgpp/lite/arm/portal/package6496/public/arm-none-eabi/arm-2010q1-188-arm-none-eabi.exe

## Problem: I can't install my .vxp files in MODIS!
**Solution:** Some `.vxp` files will fail to install because they were compiled for `arm` architecture. To fix this, you need to compile it for `x86`.
Do the steps mentioned below to get your MRE app working in MODIS:

1. Load the project to VS2022 (open the .vcproj file in VS2022)
2. There should be an upgrade prompt, just accept it
3. After accepting, the project will open.
4. Right click on the project, then choose project properties.
5. Goto the Debugging tab
6. Insert the path to your MODIS executable in the Command box. The default path for MODIS with MRE 3.0 skin is `C:\Program Files (x86)\MRE SDK V3.0.00\models\Model03_HVGA_MRE3.0\MoDIS\Release\MoDIS.exe`. You can choose the model that fits your need.
7. Goto the VC Directories tab.
8. Add include and library path to the end of corresponding boxes. You must add ; between paths. Add the MRE include and lib directories to the box. i.e, add `C:\Program Files (x86)\MRE SDK V3.0.00\include` to Include paths and `C:\Program Files (x86)\MRE SDK V3.0.00\lib\MRE30\armgcc_t` to Library paths
9. If are having problems with building VC projects (for me, it was VS2022 not able to find Windows SDK's include and lib path, then add the path to WinSDK's include and lib path to the boxes in the VC Directories tab. For me, I added `D:\Windows Kits\10\Include\10.0.22000.0\ucrt\ to the include path and D:\Windows Kits\10\Lib\10.0.22000.0\ucrt\x86\` to the lib path.
