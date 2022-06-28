# Learning Frequency-Specific Quantization Scaling in VVC for Standard-Compliant Task-driven Image Coding
This repo publishes the generated scaling lists in order to improve the coding perfromance of standard-compliant VVC test mdodel (VTM-10.0), when coding for Mask R-CNN as information sink. This work has been accepted for ICIP 2022. In total, 12 scaling lists are published derived from 4 different lambda values and 3 different noise strengths (iNF). If you are using our scaling lists, please cite our work [Fischer2022].

## Required Third-Party Software
Scaling lists are designed for compressing VTM-10.0 reference software published by JVET.
https://vcgit.hhi.fraunhofer.de/jvet/VVCSoftware_VTM

## Usage
VTM parameter `--ScalingList` has to be set to 2.

VTM parameter `--ScalingListFile` has to be set to desired scaling list file.

Exemplary call for Cityscapes dataset:

    PATH_TO_VTM/VVCSoftware_VTM-VTM-10.0/bin/EncoderAppStatic -i INPUT_FILE.yuv -c PATH_TO_VTM/VVCSoftware_VTM-VTM-10.0/cfg/encoder_intra_vtm.cfg  -wdt 2048 -hgt 1024 -f 1 -fr 30 --OutputBitDepth=8 --InputBitDepth=8 --InternalBitDepth=10 -q QP --ScalingList=2 --ScalingListFile=SCALING_LIST_FILE.txt -b BITSTREAM_FILE.bin --ReconFile=OUTPUT_FILE.yuv 


## Literature
[Fischer2022] K. Fischer, F. Brand, C. Herglotz, A. Kaup, "Learning Frequency-Specific Quantization Scaling in VVC for Standard-Compliant Task-driven Image Coding," accepted for IEEE International Conference on Image Processing (ICIP), Oct. 2022
