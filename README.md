# Overview

This `README.md` describes how to create a HTML or a PDF version of the *Climate Modelling Handbook* using [jupyter {book}](https://jupyterbook.org/en/stable/intro.html).

## Clone the repository with the climate modelling handbook notebooks

```
git clone --recurse-submodules https://github.com/mkrapp/climate-modelling-handbook_jb.git
```


## Create a `conda` environment

First,

```
conda conda env create --file climate-modelling-handbook_jb/climate-modelling-handbook/environment.yml
```

Then,

```
conda activate asp_winterschool
```

Finally,

```
conda install jupyter-book
```

## Install the Jupyter kernel

```
python -m ipykernel install --name asp_winterschool
```

## Add (soft) links to the input files

You need two sub-folders in your `climate-modelling-handbook_jb` folder, `data` (702MB) and `WRF_exercises` (45GB):

```
data
├── era5.nc
├── gabrielle_track.csv
└── satellite
    ├── BQ31.jgw
    ├── BQ31.jpg
    ├── himawari-8_snapshot-2023-08-03T01_40_00Z.tif
    ├── snapshot-2023-02-02T00_00_00Z.tiff
    ├── snapshot-2023-02-03T00_00_00Z.tiff
    ├── snapshot-2023-02-04T00_00_00Z.tiff
    ├── snapshot-2023-02-05T00_00_00Z.tiff
    ├── snapshot-2023-02-06T00_00_00Z.tiff
    ├── snapshot-2023-02-07T00_00_00Z.tiff
    ├── snapshot-2023-02-08T00_00_00Z.tiff
    ├── snapshot-2023-02-09T00_00_00Z.tiff
    ├── snapshot-2023-02-10T00_00_00Z.tiff
    ├── snapshot-2023-02-11T00_00_00Z.tiff
    ├── snapshot-2023-02-12T00_00_00Z.tiff
    ├── snapshot-2023-02-13T00_00_00Z.tiff
    ├── snapshot-2023-02-14T00_00_00Z.tiff
    ├── snapshot-2023-02-14T00_00_00Z_1km.tiff
    ├── snapshot-2023-02-15T00_00_00Z.tiff
    ├── snapshot-2023-02-16T00_00_00Z.tiff
    ├── snapshot-2023-02-17T00_00_00Z.tiff
    └── snapshot-2023-02-18T00_00_00Z.tiff
```

and 

```
WRF_exercises
└── outputs
    └── control
        ├── wrfout_d01_2023-02-01_00:00:00
        ├── wrfout_d01_2023-02-02_00:00:00
        ├── wrfout_d01_2023-02-03_00:00:00
        ├── wrfout_d01_2023-02-04_00:00:00
        ├── wrfout_d01_2023-02-05_00:00:00
        ├── wrfout_d01_2023-02-06_00:00:00
        ├── wrfout_d01_2023-02-07_00:00:00
        ├── wrfout_d01_2023-02-08_00:00:00
        ├── wrfout_d01_2023-02-09_00:00:00
        ├── wrfout_d01_2023-02-10_00:00:00
        ├── wrfout_d01_2023-02-11_00:00:00
        ├── wrfout_d01_2023-02-12_00:00:00
        ├── wrfout_d01_2023-02-13_00:00:00
        ├── wrfout_d01_2023-02-14_00:00:00
        ├── wrfout_d01_2023-02-15_00:00:00
        ├── wrfout_d01_2023-02-16_00:00:00
        ├── wrfout_d01_2023-02-17_00:00:00
        ├── wrfout_d01_2023-02-18_00:00:00
        ├── wrfout_d01_2023-02-19_00:00:00
        └── wrfout_d01_2023-02-20_00:00:00
```

## Build a jupyter book (HTML)

```
jupyter-book build climate-modelling-handbook_jb/
```


## Build a jupyter book (PDF)

```
jupyter-book build climate-modelling-handbook_jb/ --builder pdflatex
```

(this requires `texlive`, see [here](https://jupyterbook.org/en/stable/advanced/pdf.html#build-a-pdf-using-latex))


