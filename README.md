# ems_render
This is the code to render ems motion

## Environment
Please use the environment.yaml file to install required packages.
```bash
    conda env create -f environment.yaml
```
The rendering code use blender, please install it from [here](https://www.blender.org/download/releases/2-93/). Currently I use blender 2.93, higher version may also work :>.

Due to the size limit of github, I uploaded the preprocessed dependencies (smplh) [here](https://drive.google.com/drive/folders/1fpmU28pFRo_QTPUeCvH8tnodfAVMoht8?usp=sharing). Just download it and place it under $ems_render.

## Render
I uploaded one example ($ems_render/test/ems.npy) under test folder to check if everything is correctly set up.

just run
```bash
    rm ./text/ems.webm
    blender --background --python render.py -- npy=./test/ems.npy mode=video
```
If the blender is not installed through apt-get, may need to change the blender to $path_to_blender (e.g. /private/home/xxx/blender-2.93.9-linux-x64/blender)

## Generated Motions
The generated motions can be downloaded from [here](https://drive.google.com/drive/folders/1DICLcoX7Qji-cm9SqbBsed4x_2X7j_hd?usp=sharing). Under each folder, xxx.npy is the generated motion matrix with size of num_frames*num_of_vertices and xxx.txt is the text descriptions.

## Other Options
The generated motion format is SMPL vertice output, so you can also use any 3rd party visualization code to visualize it. (e.g. [AMASS](https://github.com/nghorbani/amass/blob/master/notebooks/01-AMASS_Visualization.ipynb))