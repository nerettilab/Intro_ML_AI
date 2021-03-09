# Face recognition

## Setting up the conda environments

### Set up conda environment for Python
```zsh
conda create -n object_recognition python=3.7 matplotlib numpy pandas scipy scikit-learn tensorflow more-itertools seaborn pip jupyter

conda install -n object_recognition -c conda-forge plotnine shap jupyterlab opencv dlib face_recognition

```

#### Activate environment for Python
```zsh
conda activate object_recognition
```

#### Deactivate environment for Python
```zsh
conda deactivate
```

### Running the face recognitions program
Store training JPEG images in the data/faces folder. Sctivate the object_recognition environment as exllained above. To run the face recognition program use the following command in a terminal window:

```zsh
python run_face_recognition.py
```

Make sure you run the software from the folder where it is stored. ctrl + c to exit.
****