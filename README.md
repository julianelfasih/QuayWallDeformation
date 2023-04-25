# Amsterdam Internships - Predicting the Deformation of Quay Walls in Amsterdam

This repository containts code for my master's thesis project. The project aims to predict the deformation of quay walls in Amsterdam using soil and satellite data. The soil data contains information on the subsurface of the quay wall, whereas the satellite data provides the subsidence of the ground. The target variable is the tacheometry data of the quay walls, measuring deformation in x, y, and z direction. The predictions will be done with different configurations of BiLSTM models, conforming to early, incremental, and late model fusion.

---


## Project Structure

- EploratoryDataAnalysis.ipynb contains the EDA on all data except for the satellite data.
- Load_satellite.ipynb contains the loading functions, EDA, and preprocessing for the satellite data. It stores three preprocessed csv for horizontal, vertical and hinterland settlemen in the end.
- LoadMeetbouten.ipynb contains the loading functions and some preprocessing for the building tacheometry data. It yields a preprocessed csv.
- LoadSoil.ipynb contains the loading functions for the soil data, the data is stored in one csv for CPT data and one for Bore data.
- LoadTacheometry.ipynb contains the loading functions for the quay wall tacheometry data. The data is stored in different formats in different csv's, because of changing my mind on the format. - TO DO: make sure only one format remains and is adjusted everywhere appropriately.
- prepare_cpt.ipynb contains functions to preprocess the CPT data. It outputs a preprocessed csv, ready for the training notebook. - TO DO: combine with loadSoil.ipynb for better overview.
- prepare_tcmt.ipynb contains functions to preprocess the tacheometry data. It outputs a preprocessed csv, ready for the training notebook. - TO DO: combine with LoadTacheometry.ipynb for better overview.
- Train.ipynb contains functions to train and evaluate the data. It also contains the experiments and their results.

<!-- Explain briefly what's where so people can find their way around. For example:

There are the following folders in the structure: -->

<!-- 1) [`resources`](./resources): Random nice resources, e.g. [`useful links`](./resources/README.md) - Does not contain anything now.
1) [`src`](./src): Folder for all source files specific to this project - Does not contain anything now.
1) [`scripts`](./scripts): Folder with example scripts for performing different tasks (could serve as usage documentation) - Does not contain anything now.
1) [`tests`](./tests) Test example - Does not contain anything now.
1) [`media`](./media): Folder containing media files (icons, video) - Does not contain anything now.
1) ...

OR

Or use something like `tree` to include the overall structure with preferred level of detail (`-L 2` or `-d` or `-a`...)
```buildoutcfg
├── media --> you can still add comments and descriptions in this tree
│   └── examples
├── resources --> a lot of useful links here
├── scripts
├── src --
└── tests
```



If you are lacking ideas on how to structure your code at the first place, take a look at [`CookieCutter`](https://drivendata.github.io/cookiecutter-data-science/)

--- -->


## Installation

Explain how to set up everything. 
Let people know if there are weird dependencies - if so feel free to add links to guides and tutorials.

A person should be able to clone this repo, follow your instructions blindly, and still end up with something *fully working*!

1) Clone this repository:
    ```bash
    git clone https://github.com/Amsterdam-Internships/QuayWallDeformation/
    ```

1) If you are using submodules don't forget to include `--recurse-submodules` to the step above or mention that people can still do it afterwards:
   ```bash
   git submodule update --init --recursive
   ```

1) Install all dependencies:
    ```bash
    pip install -r requirements.txt
    ```
---


## Usage

Explain example usage, possible arguments, etc. E.g.:

To train... 


```
$ python train.py --some-importang-argument
```

If there are too many command line arguments, you can add a nice table with explanation (thanks, [Diana Epureano](https://www.linkedin.com/in/diana-epureanu-235104153/)!)

|Argument | Type or Action | Description | Default |
|---|:---:|:---:|:---:|
|`--batch_size`| int| `Batch size.`|  32|
|`--device`| str| `Training device, cpu or cuda:0.`| `cpu`|
|`--early-stopping`|  `store_true`| `Early stopping for training of sparse transformer.`| True|
|`--epochs`| int| `Number of epochs.`| 21|
|`--input_size`|  int| `Input size for model, i.e. the concatenation length of te, se and target.`| 99|
|`--loss`|  str|  `Type of loss to be used during training. Options: RMSE, MAE.`|`RMSE`|
|`--lr`|  float| `Learning rate.`| 1e-3|
|`--train_ratio`|  float| `Percentage of the training set.`| 0.7|
|...|...|...|...|


Alternatively, as a way of documenting the intended usage, you could add a `scripts` folder with a number of scripts for setting up the environment, performing training in different modes or different tasks, evaluation, etc (thanks, [Tom Lotze](https://www.linkedin.com/in/tom-lotze/)!)

---


## How it works

You can explain roughly how the code works, what the main components are, how certain crucial steps are performed...

---
## Acknowledgements


Don't forget to acknowledge any work by others that you have used for your project. Add links and check whether the authors have explicitly stated citation preference for using the DOI or citing a paper or so. 
For example:

Our code uses [YOLOv5](https://github.com/ultralytics/yolov5) [![DOI](https://zenodo.org/badge/264818686.svg)](https://zenodo.org/badge/latestdoi/264818686)

