<p align="center">
    <img src="https://thumbs.gfycat.com/SlushyEarnestDragonfly-max-1mb.gif" width="200" alt="Logo">
  <h1 align="center">Color For All</h1>

  <p align="center">
    Simulate Colorblindness and Correct Colors for People with Colorblindness
  </p>
</p>

[![PR's Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat)](https://github.com/vidhi-mody/Color-For-All/pulls)
![PRs](https://img.shields.io/github/issues-pr-closed/vidhi-mody/Color-For-All?color=pink)
![Issues](https://img.shields.io/github/issues/vidhi-mody/Color-For-All?color=purple)
[![Contributors](https://img.shields.io/github/contributors/vidhi-mody/Color-For-All)]()
![Languages](https://img.shields.io/github/languages/count/vidhi-mody/Color-For-All?color=orange)


## Installation

### Downloading the script

Go to the directory of your choice in terminal, and run the command below.
```shell
git clone https://github.com/vidhi-mody/Color-For-All.git
```

### Installing dependencies

To run this script, you need to install three libraries for python. Use pip or conda (or any package manager of your choice) to download PIL, Numpy and OpenCV.
```shell
sudo pip install Pillow numpy opencv-python
```

## Running the script

*Control flags and description (For command line/terminal usage)*

| Flag &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;| Args type &nbsp; &nbsp; &nbsp; &nbsp;| Description | Default  | Needed? |
| --------|:---------:|:-------:|:---:|---:|
| -input       | *string* | Path to the input image to simulate/correct. | *None* | Yes |
| -output      | *string* | Directory where all simulated/corrected images will be stored.| *None* | Yes |
| -protanopia_degree | *float: [0,1]* | Degree of protanopia to simulate/correct. | *1.0* | No |
| -deutranopia_degree | *float: [0,1]* | Degree of deutranopia to simulate/correct. | *1.0* | No |
| -tritanopia_degree | *float: [0,1]* | Degree of tritanopia to simulate/correct. | *1.0* | No |
| -sim_protanopia |  *None*  |    Use this flag to simulate Protanopia. | *False* | No |
| -sim_deutranopia |  *None*  |    Use this flag to simulate deutranopia. | *False* | No |
| -sim_tritanopia |  *None*  |    Use this flag to simulate tritanopia. | *False* | No |
| -sim_hybrid |  *None*  |    Use this flag to simulate hybrid colorblindness. | *False* | No |
| -correct_colors |  *None*  |    Use this flag to correct colors for protanopia and deutranopia. | *False* | No |
| -run_all |  *None*  |    Use this flag to perform all operations (simulate + correct). | *False* | No |
  

### *How to run the script*

Go to the directory
```shell
cd ~/Color-For-All
```

Run the script with flags.
Let's say we want to simulate only tritanopia, and correct the image 
for protanopia and deutranopia. We run the below command.
```shell
python recolor.py
  -input /Users/example_user/pictures/sample.jpg
  -output /Users/example_user/pictures/sample_dir/
  -protanopia_degree 0.9
  -deutranopia_degree 0.6
  -tritanopia_degree 0.5 
  -sim_tritanopia
  -correct_colors
```
  
 If you want to run all the operations, you can also use the -all flag. 
 We will keep the degrees as default (1.0) this time to focus on -run_all flag.
 ```shell
 python recolor.py
  -input /Users/example_user/pictures/sample.jpg
  -output /Users/example_user/pictures/sample_dir/
  -run_all
```
  
If you want to run correction for only protanopia, 
you can set the deutranopia_degree value to 0. 
Essentially forcing the algorithm to not assume deutranopia.
```shell
 python recolor.py
   -input /Users/example_user/pictures/sample.jpg
   -output /Users/example_user/pictures/sample_dir/
   -deutranopia_degree 0
   -correct_colors
```
