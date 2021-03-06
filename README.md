#CalaTK Parameters Test

Date : 06/30/2014
Author : Alexis Girault
CalaTK version tested : https://github.com/agirault/CalaTK/tree/7e827855b718936617a10bc9cbf70fa8e94e9125

##Introduction
Those scripts were built to run a pipeline in multi-threads that would help analyzing the optimum parameters Alpha and Gamma to use for the LDDMM registration - a tool from CalaTK - for a specific data.
The processing is based on a voxel intensity comparison between the expected target, and an image computed by applying the computed map to the source using applyMap.
It then writes a table showing the best matching depending on the parameters value, in a .m file readable with Matlab

##Requirements
- LDDMM (CalaTK)
- applyMap (CalaTK)
- ImageMath
- ImageStat
- unu

##Usage of the scripts

**CalaTK_const.sh**
- Define the inputs for LDDMM (source image, target image, configuration file), and the range and increment values for Alpha & Gamma.
- To be initialized before lauching the tests

**CalaTK_test.sh**
- Creates different threads for each value of gamma to do the pipeline.
- Run in terminal to process the test

**CalaTK_process.sh**
- Processes the pipeline
- NO NEED TO BE MODIFIED

**CalaTK_write.sh**
- writes the results in a .m file to run with Matlab
- Run once CalaTK_test is finished

**CalaTK_clean.sh**
- removes everything but the scripts in the directory
- Run when you want to clean your directory before doing a new test
