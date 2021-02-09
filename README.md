# Introduction to Machine Learning and Artificial Intelligence

## Setting up the conda environments

### Set up conda environment for Python
```zsh
conda create -n ml_training_py python=3.7 matplotlib numpy pandas scipy scikit-learn tensorflow more-itertools seaborn pip jupyter

conda install -n ml_training_py -c conda-forge plotnine shap jupyterlab
```

#### Activate environment for Python
```zsh
conda activate ml_training_py
```

#### Deactivate environment for Python
```zsh
conda deactivate
```

### Set up conda environment for R

Note: It includes RStudio, and the ISLR pachage with examples used in the book "An Introduction to Statistical Learning".

```zsh
#conda install r-caret
#conda update r-caret
conda create -n ml_training_r r-ISLR r-essentials r-base
conda install -n ml_training_r -c r rstudio
```

#### Activate environment for R
```zsh
conda activate ml_training_r
```

#### Start RStudio
```zsh
rstudio
```

#### Deactivate environment for R
```zsh
conda deactivate
```

## Textbooks

1. [The Elements of Statistical Learning](https://web.stanford.edu/~hastie/Papers/ESLII.pdf), [Website](https://web.stanford.edu/~hastie/ElemStatLearn/)
2. [An Introduction to Statistical Learning](https://faculty.marshall.usc.edu/gareth-james/ISL/ISLR%20Seventh%20Printing.pdf), [Website](http://faculty.marshall.usc.edu/gareth-james/ISL/), [Course](https://www.r-bloggers.com/2014/09/in-depth-introduction-to-machine-learning-in-15-hours-of-expert-videos/), [Course @ Data School](https://www.dataschool.io/15-hours-of-expert-machine-learning-videos/)
3. [Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow, 2nd Edition](https://www.oreilly.com/library/view/hands-on-machine-learning/9781492032632/), [PDF](https://www.knowledgeisle.com/wp-content/uploads/2019/12/2-Aur%C3%A9lien-G%C3%A9ron-Hands-On-Machine-Learning-with-Scikit-Learn-Keras-and-Tensorflow_-Concepts-Tools-and-Techniques-to-Build-Intelligent-Systems-O%E2%80%99Reilly-Media-2019.pdf), [Git](https://github.com/ageron/handson-ml2)
4. [Interpretable Machine Learning](https://christophm.github.io/interpretable-ml-book/)

## Courses
1. [Data School](https://www.dataschool.io/)
2. [Andrew Ng's "Machine Learning"](https://www.coursera.org/learn/machine-learning)