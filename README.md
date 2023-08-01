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

### Technologies 




