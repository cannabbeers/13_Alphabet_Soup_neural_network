# Neural Networks and Venture Capital  
Module 13 Challenge

In your original `dev` environment set up for this class, we created it using $`conda create -n env python=3.7 anaconda` - this installs the Anaconda Metadata package which does include TensorFlow, however, we need an older version < 2.11 and there is no reverse or backwards compatability to allow us to use an older version in the same `env`. In your terminal window type $`conda list tensorflow` and if it is installed there already, you will most likely find it's version is 2.11 or higher.  TensorFlow 2.0 does now include `keras`, so no separate installation is required, but in order for `keras` to function, Python version 3.8 to 3.11 must be functional. 

### Create new environment `env` for neural networks and machine learning: `nn_ml`
We need to be careful at installation as to not install the latest version of tensor flow because as versions of the Libraries, Dependencies and Packages required to run `tensorflow` *(now including `keras`)* are not the most recent versions in all cases, so to make everything run smoothly without errors while maintaining a stable environment, I recommend setting up a new `conda` environment as described by the [latest official TensorFlow Install Guide](https://www.tensorflow.org/install/pip)
  NOTE: current recommendation (from TensorFlow) is to run code with python=3.9 and then `pip install "tensorflow<2.11"` - for CPU based developers.
  
+ [TensorFlow: Windows Native / CPU](https://www.tensorflow.org/install/pip#windows-native_1)
+ [TensorFlow for macOS](https://www.tensorflow.org/install/pip#macos)
  NOTE: *while TensorFlow TensorFlow does support Apple Silicon (M1); not all packages have been made with compatible M1 versions.
    My current understanding is that macOS users may be able to run `TensorFlow` with x86 emulation and Rosetta or `Google-Colab`*

For Windows, from your `(base)` env: copy and paste this code in your `gitbash` terminal 
              $ conda create -n nn_ml -y -v -c conda-forge --strict-channel-priorit python=3.9 pandas jupyterlab matplotlib numpy pip scikit-learn
              
Once the new environment is created, you need to activate and then `pip` install tensorflow version < 2.11 in order to ensure it will function properly and be compatible with `keras` which is included with `tensorflow` and should function correectly in a python environment (3.8 to 3.11) 

              $ pip install "tensorflow<2.11" 

Confirm versions of `tensorflow` and `keras` are compatible by making sure that Tensorflow 2.0 was properly updated with a version < 2.11

  $ python -c "import tensorflow as tf;print(tf.__version__)
  $ python -c "import tensorflow as tf;print(tf.keras.__version__)"

## Technologies 

+ Anaconda: It's a platform that simplifies package management and deployment. The original environment setup included TensorFlow 2.11 or higher, which needs to be replaced with an older version for compatibility reasons.


+ Python: The environment requires a compatible Python 3.8 to 3.11; recommend following TensorFlow Instal Guide which is currently (in Aug 2023), Python 3.9 to ensure that Keras functions properly.  Check the [TensorFlow Installation Page](https://www.tensorflow.org/install/pip) for any updates on best practices now. 

+ Conda Environment: Creating a new conda environment (nn_ml) to encapsulate the specific versions of the packages, avoiding conflicts with other projects or system-wide packages.

## Libraries: 

+ TensorFlow: open-source machine learning framework developed by Google. The instructions here specify that a version older than 2.11 is needed, and that this older version includes Keras, so no separate installation is required.

+ Keras: high-level neural networks API that runs on top of TensorFlow. Since TensorFlow 2.0, Keras has been included in TensorFlow.
+ JupyterLab
+ Matplotlib
+ NumPy
+ Scikit-learn



## Optimization

Adjust the input data by dropping different features columns to ensure that no variables or outliers confuse the model.

Add more neurons (nodes) to a hidden layer.

Add more hidden layers.

Use different activation functions for the hidden layers.

Add to or reduce the number of epochs in the training regimen.


## Check out the H5PY or load a specific model with 'Keras':

### 1) Print the names and objects of everything inside the HDF5 file
        import h5py

        def print_structure(file_path):
            with h5py.File(file_path, 'r') as file:
                file.visititems(lambda name, obj: print(name, obj))

        file_path = "Resources/AlphabetSoup.h5"
            print_structure(file_path)

### 2) Load a specific model `h5py` to run on the data:

        from tensorflow.keras.models import load_model
        
        chosen_model = load_model("Resources/AlphabetSoup.h5")
        chosen_model.summary()




   
## Usage: 

In GitHub, navigate to my repo called `https://github.com/cannabbeers/13_Alphabet_Soup_neural_network/`

Open your Terminal or GitBash window

Create a folder using `mkdir` and `clone` the repo in your new directory

Activate your 'dev' environment for python 3.8 or higher

Enter `git pull` to import and then launch `Jupyter Lab` from Terminal/Git Bash prompt

Open the jupyter lab notebook: `venture_funding_with_deep_learning.ipynb` & run code from the top

---

## Contributors:

Mark Beers: 
[Linked In](https://www.linkedin.com/in/markwbeers/)

---

## License:

MIT License: A short and simple permissive license with conditions only requiring preservation of copyright and license notices. Licensed works, modifications, and larger works may be distributed under different terms and without source code.