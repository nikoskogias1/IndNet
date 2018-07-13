# IndNet
Defining subject-specific brain networks by individualizing templates

## Introduction
IndNet uses a dual-regression-like seed-based approach to individualize general binary templates to specific subjects.
Resting-state and anatomical images are preprocessed and transformed into MNI space. Timecourses are extracted from the resting state images for all templates (using the first eigenvariate) and fed into a GLM analysis. Specific contrats, representing networks of interest, are tested and results are thresholded using spatial mixture modeling and subsequently binarized. In addition to the resulting main network maps (which might be overlapping), IndNet also outputs exclusive maps of the networks of interest (i.e. non-overlapping maps).

## Prerequisites
1. Install [Nipype](https://nipype.readthedocs.io)
2. Install [FSL](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/)
3. Install [graphviz](https://www.graphviz.org/)
4. Install ICA-AROMA
   - [Download](https://github.com/fladd/ICA-AROMA/archive/master.zip)
   - Install dependencies (see `requirements.txt`)
   - Make `ICA_AROMA.py` executable
   - Add `ICA_AROMA.py` to path, so it can be called system wide
5. [Download IndNet](https://github.com/can-lab/IndNet/archive/master.zip)

### Donders cluster
If you are working on the compute cluster of the Donders Institute, please follow the following steps:
1. Load Python module by running command: `module load python`
2. Install virtualenv by running command: `python -m pip install virtualenv --user`
3. Create new environment in home directory by running command: `cd && python -m virtualenv IndNet`
4. Activate new environment by running command: `source ~/IndNet/bin/activate`
5. Update pip in environment by running command: `pip install -U pip`
6. Install Nipype into environment by running command: `pip install nipype`
7. Install ICA-AROMA
   - [Download](https://github.com/fladd/ICA-AROMA/archive/master.zip) and extract `ICA-Aroma-master` to somewhere
   - Within `ICA-Aroma-master`
      - Install dependencies by running command: `pip install -r requirements.txt`
      - Make `ICA_AROMA.py` executable by running command: `chmod a+x ICA_AROMA.py`
   - Add `ICA_AROMA.py` to path, so it can be called system wide
      - Open file `~/.bash_profile` in a text editor and add: `export PATH=/path/to/ICA-Aroma-master/:$PATH`
8. Deactivate environment by running command: `source ~/IndNet/bin/deactivate`
9. [Download IndNet](https://github.com/can-lab/IndNet/archive/master.zip) and extract `IndNet-master` to somewhere

## Usage
1. Write script with custom workflow (see `Indnet-master/example.py` for an example)
2. Run script

### Donders cluster
If you are working on the compute cluster of the Donders Institute, please follow the following steps:
1. Load Python module by running command: `module load python`
2. Load graphviz module by running command: `module load graphviz`
3. Activate environment by running command: `source ~/IndNet/bin/activate`
4. Write script with custom workflow (see `Indnet-master/example.py` for an example) and save it as `my_script.py`
5. Run script by running command: `python my_script.py`

When done, deactivate environment by running command: source ~/IndNet/bin/deactivate


