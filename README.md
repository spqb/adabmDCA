# adabmDCA
`adabmDCA 2.0` – a flexible but easy-to-use package for Direct Coupling Analysis.

## Installation

`adabmDCA` is available in three languages: C++ (single-core CPU), Julia (multi-core CPU) and Python (GPU-oriented). Follow the instructions for installing the desired implementation.

### Python implementation :snake:
Open a terminal, clone the GitHub repository locally, and install the dependencies and the package:

```{bash}
git clone git@github.com:spqb/adabmDCApy.git
cd adabmDCApy
pip install -r requirements.txt
pip install -e .
```

The main repository of the implementation can be found at [adabmDCApy](https://github.com/spqb/adabmDCApy.git).

### Julia implementation
After installing [Julia](https://julialang.org/downloads/) on your system, you can install the package in one of the following ways:

#### Option 1: Using bash command
Open a terminal in the desired folder, and run the following commands:

```{bash}
# Download scripts from Github
wget -O adabmDCA.sh https://raw.githubusercontent.com/spqb/adabmDCA.jl/refs/heads/main/adabmDCA.sh
wget -O execute.jl https://raw.githubusercontent.com/spqb/adabmDCA.jl/refs/heads/main/execute.jl
chmod +x adabmDCA.sh

# Install ArgParse and adabmDCA.jl from the GitHub repo
julia --eval 'using Pkg; Pkg.add("ArgParse"); Pkg.add(PackageSpec(url="https://github.com/spqb/adabmDCA.jl"))'
```
This will install all necessary dependencies and set up the package.

#### Option 2: Manual Installation via Julia

1.  Open Julia and install the package by running:
    ```{Julia}
    using Pkg
    Pkg.add(url="https://github.com/spqb/adabmDCA.jl")
    Pkg.add("ArgParse")
    ```
    
2.  Download the files `adabmDCA.sh` and `execute.jl` into the same folder
    ```{bash}
    wget https://github.com/spqb/adabmDCA.jl/blob/main/install.sh
    wget https://github.com/spqb/adabmDCA.jl/blob/main/execute.jl
    ```

3.  Make the script executable by opening a terminal in the folder and running:
    ```{bash}
    chmod +x adabmDCA.sh
    ```
This will set up the package for use.

The main repository of the implementation can be found at [adabmDCA.jl](https://github.com/spqb/adabmDCA.jl.git).

### C++ implementation
1.    Clone the repository
      ```{bash}
      git clone git@github.com:spqb/adabmDCAc.git
      ```
2.    In the __src__ folder run
      ```{bash}
      make
      ```
3.    It will generate the executable file __adabmDCA__. In the main folder run also `chmod +x adabmDCA.sh` to use the main script file. See
      ```{bash}
      ./adabmDCA --help
      ```
      for a complete list of features.

The main repository of the implementation can be found at [adabmDCAc](https://github.com/spqb/adabmDCAc.git).


## Introducton
This package presents a new version of `adabmDCA`. The package comes in three different languages: C++ (single-core CPU), Julia (multi-core CPU), and Python (GPU-oriented). They share the same front-end interface from the terminal allowing the user to install and use one of the three equivalent versions based on hardware or software constraints.

We provide three different training routines:
- **bmDCA**: Trains a fully-connected DCA model;
- **eaDCA**: Trains a DCA model on a sparse coupling network by progressively adding couplings during the training;
- **edDCA**: Starts from a trained bmDCA model and iteratively removes the less informative couplings until the target sparsity is reached.

Additionally, we provide several routines for sampling and analyzing the generated sequences once a DCA model is trained, for constructing and evaluating - according to a DCA model - a single mutant library from a given wild type, and finally, for computing the pairwise contact scores, in terms of average-product corrected Frobenius norms of the DCA couplings.

## Usage
Check out the online [Documentation](https://spqb.github.io/adabmDCApy) :wink:

## License

This package is open-sourced under the MIT License.

## Citation

If you use this package in your research, please cite:

> Rosset, L., Netti, R., Muntoni, A.P., Weigt, M., & Zamponi, F. (2024). adabmDCA 2.0: A flexible but easy-to-use package for Direct Coupling Analysis.

## Acknowledgments

This work was developed in collaboration with Sorbonne Université, Sapienza Università di Roma, and Politecnico di Torino.
