## Setup of Acroba Platform

```
git clone https://github.com/ACROBA-Project/setup.git
cd setup
./setup.sh
```

**Usage:**

```
./setup.sh [[--skip] [-p|--pat] [-g|--git] [-v|--dev] [-d|--download]  [-c|--clean] [-o|--clean-code] [-i|--clean-images] [-z|--cell <cell_config_repo>] ]
```


the setup script will perform the following action: 

1. set up access to the Acroba project (github and container registry) `[-p|--pat]`
2. checkout the acroba platform & cell config repos `[-g|--git]`
3. download the docker images of the platform and the cell config  `[-d|--download]`
4. install platform (devcontainer usage) requirements `[-v|--dev]`

**Options:** 

- `--skip`<br>
    It is possible to trigger only some specific steps by using the optional shortcut strings describe above (short, e.g. "-d", or long options, e.g --download, can be used indifferently), e.g.: 
    ```
    ./setup.sh --git -p  # does only the git checkout and git registry access setup. 
    ```
    the `--skip|-s` option allows to skip some steps, e.g.
    ```
    ./setup.sh --skip -d # skips downloading of docker images
    ```

- `--clean`<br>
    clean the code repositories and removes all the docker images 

- `--clean-images`<br>
    removes all the docker images 
    
- `--clean-code`<br>
    clean the code repositories before checking out

- `--cell <cell_config_repo>`<br>
    specifies the repo of the cell config to use. 

Checkout<br>
Acroba repositories will be checked out by default in the `code` subfolder. 


#### Running the platform: 

After the setup script is completed, you should be able to run the acroba platform easily by running from the ACROBA-Platform folder:<br>

``` 
make run CELL=<cell config name>
```
or if you don't have a gpu: 
```
make run GPU=NO CELL=cell-config-bfh
```
