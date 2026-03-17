# User guide
## Foreward
The new aktsomhetskart for flom is built in a modular manner, iterable through a jupyter notebook script that is provided in this github repository. New iterations are published when developed, and code modularity is emphasised, with different applicable modules being added in future iterations. These modules should be easily added and removed from the main script based on needs. The main script is based on the old aktsomhetskart for flom published by NVE (https://www.nve.no/media/10583/metodebeskrivelse-aktsomhetskart-for-flom.pdf). To use the new model, there are several basic requirements which are documented below as a series of instructions. A dev branch will be maintained for development editing between major commits.
## Setup instructions
1. Download the current newest version of the aktsomhetskart script from its github page. The newest version can typically be found under releases as the latest release, found here: https://github.com/ThobNVE/Nytt_aktsomhetskart/releases.
2. Ensure that your machine has upwards of 64gb of RAM, particularly if you aim to develop the code rather than simply iterate (it is recommended to run on a virtual server).
3. Set-up anaconda on your machine. If using firmaportalen as an NVE-internal user, download and install Anaconda Navigator, or if on a non-managed machine, download from https://www.anaconda.com and follow the setup instructions. An alternative is to use Command Prompt or PowerShell for setting up anaconda once the base package is installed. All setup modes are documented under "Installing Anaconda Distribution" on the Anaconda website.
4. Using your newly set up Anaconda distribution, install the environment that has come with the latest version of the Aktsomhetskart script. This should be in the folder "envs" under the current version on the main branch. This can be done either using import in Anaconda Navigator, or by opening Anaconda PowerShell and navigating to your saved environment directory by typing:

    <code>cd path/to/directory</code>

    Then typing:

    <code>conda env create -f PythonGIS.yml</code>
    
    Let this run, and your environment should be set up. To activate and use the environment afterwards via PowerShell or Command Line you can type:

    <code>conda activate PythonGIS</code>

5. Otherwise, it should now be possible to use the script via Microsoft VSCode, or other python clients directly, by selecting PythonGIS as your operating kernel.
6. Now, you must set up your file system. You are required to have the following layout:

        |/Main folder/  |
                        | /FLOWACC/ | For "flow accumulation" files
                        | /BURNED/  | For burned-in DTM files
                        | /ELV/     | For DTM-based river network data
                        | /FLD/     | For produced flood layers
                        | /RNET/    | For vectorised river networks
                        | /OUT/     | For scaled DTMs
                        | /RAW/     | For raw 1m DTM data
                        | /FDIR/    | For flow direction data
                        | /Scripts/ | For main scripts both .ipynb and .py
                        | /envs/    | For Python environment .yml files. 
7. From here, it is possible to run the script. Be aware that if you do not have the associated DTM in an already processed fashion, this can take an hour or longer for a medium sized catchment for the first iteration. Running the script without editing start-up parameters will produce outputs for the Gaula catchment area (designation 122.Z) in the Trondheim area of Norway. Be aware of your storage space for the 1m elevation data.
8. Within the script, the cell "DEFINE VARIABLES" allows for modification of the output. The primary variable for non-developers is "vassdrag_nr", which defines the catchment region to be mapped. A query can be made in "Søk her for vassdraget ditt", allowing for a specific region to be identified by a string of characters from its name, returning the metadata including vassdrag_nr.
9. Once parameters are set, clicking on "Run all >>" should set the PythonGIS kernel running, and will produce a series of outputs.
10. The key outputs that are relevant for the aktsomhetskart are as follows:

        |/FLD/  | {version}_AKT_TOT_VD_Gaula_STO6_RB5_R5m.tif
                | {version}_AKT_TOT_VD_Gaula_STO6_RB5_R5m.gpkg
                | {version}_AKT_DYBDE_VD_Gaula_STO6_RB5_R5m.tif
                | {version}_AKT_VSS_VD_Gaula_STO6_RB5_R5m.tif
                | {version}_HAND_VD_Gaula_RB5_R5m.tif
        |/ELV/  | {version}_SORD_VD_Gaula_RB5_R5m.tif

## Output name anatomy
Each output filename indicates the exact content of the output data. The figure below shows the general contents of an end-state flood output filename.

![Diagram of filename anatomy](/Images/Filename%20anatomy.png "Filename anatomy diagram")







                