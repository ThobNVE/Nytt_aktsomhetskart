# Guide for installing the virtual environment for the aktsomhetskart scripts

The new aktsomhetskart python environment is built using uv, replacing the old anaconda environment.
This is generally functional, but requires a few extra steps to set up, particularly in relation to gdal as it is not a native pip package.
As such, if you have the access, use anaconda (despite it being slower), otherwise, uv is a fast and effective solution as documented here.

1) Ensure that you have:

    a) Python version 3.13.5 installed

    b) a compatible version of uv python package manager. It can also be useful to have miniforge for future work.

    c) VS code installed.

2) Create a folder in your C:/ directory (or elsewhere if required) named "uv_miljø".
3) Download the "requirements_uvPythonGIS.txt" file, along with the packaged version of gdal. These are both found in /venvs/.
4) Open Powershell, and use cd to navigate to your main directory in your C:/ drive.
5) In Powershell, type `uv venv uvPythonGIS`
6) Now activate your environment with `.\uvPythonGIS\Scripts\activate`
7) Install gdal with `uv pip install .\gdal_3.12.2-cp313-cp313-win-amd64.whl`
8) Install the virtual environment by using `uv pop install -r requirements_uvPythonGIS.txt`
9) Check the installation with `uv pip list`
10) Run `uv pip install ipykernel`
11) Open VS Code for the first time. Log in in the bottom-right using your github copilot if required (NVE employees should use their NVE account).
12) In VS code, choose "File - Open Folder" and find your folder in your C:/ directory, then open it. This should open an explorer panel.
13) From the panel, open a jupyter notebook script (e.g. "Nytt_Aktsomhetskart_0.9.26_dev.ipynb")
14) Press Ctrl + Shift + P and choose "Python Select Interpreter".

    a) Choose interpreter path

    b) Choose find

    c) Navigate to "uvPythonGIS/Scripts/python.exe"

15) Back in VS Code choose "Select Kernel" in the top-right.
16) Open:

  a) Python environments

  b) Select uvPythonGIS 3.13.5
