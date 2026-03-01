# Advanced-Data-Challenge-template-code
This repository contains the template code for the TU/e course JBG040 Advanced Data Challenge.
Please read this document carefully as it has been filled out with important information.

## Code structure
The template code is structured into multiple files, based on their functionality. 
There are five `.py` files in total, each containing a different part of the code. 
Feel free to create new files to explore the data or experiment with other ideas.

- To download the data: 
  - Log in to Canvas, go to course JBG040 (2025-3) Advanced Data Challenge.
  - Go to the Files page. 
  - Download the four files `X_test.npy`, `X_train.npy`, `Y_test.npy` and `Y_train.npy`.
  - Create a folder called `data` in `dc1\`.
  - Move the files to the created folder `dc1\data\`.
  - You will only have to do this once usually, at the beginning of your project.

- To run the whole training/evaluation pipeline: run `main.py`. **As the interpreter, select Python 3.11, as some packages are incompatible with newer Python versions.**
This script does the following things:
    - It loads your train and test data. _Make sure it's downloaded beforehand!_
    - It initializes the neural network as defined in the `Net.py` file.
    - It initializes the loss functions and optimizers. If you want to change the loss function/optimizer, do it here.
    - It defines the number of training epochs and the batch size.
    - It checks and enables GPU acceleration for training (if you have a CUDA or Apple Silicon enabled device).
    - It trains the neural network and performs evaluation on the test set at the end of each epoch.
    - It provides plots about the training losses both during training in the command line and as a png, saved in the `\artifacts\` subdirectory.
    - Finally, it saves your trained model's weights in the `\model_weights\` subdirectory so that you can reload them later.

In your project, you are free to modify any parts of this code based on your needs. 
Note that the Neural Network structure is defined in the `Net.py` file, so if you want to modify the network itself, you can do so in that script.
The loss functions and optimizers are all defined in `main.py`.

## GitHub setup instructions
1. Click the green *<> Code* button at the upper right corner of the repositiory.
2. Make sure that the tab *Local* is selected and click *Download ZIP*.
3. Go to the GitHub homepage and create a new repository.
4. Make sure that the repository is set to **private** and give it the name **JBG040-GroupXX**, where XX is your group number.
5. Press *uploading an exisiting file* and upload the extracted files from Data-Challenge-1-template-main.zip to your repository. Note that for the initial commit you should commit directly to the main branch.
6. Invite your **group members, tutor, and the teachers "arthurvancamp" and "justyna2000"** by going to *Settings > Collaborators > Add people*.
7. Open PyCharm and make sure that your GitHub account is linked.*
8. In the welcome screen of PyCharm, click *Get from VCs > GitHub* and select your repository and click on clone.
9. After the repository is cloned, you can now create a virtual environment using the requirements.txt.

*For information on how to install PyCharm and link Github to your PyCharm, we refer to the additional resources page on Canvas.


## Environment setup instructions
We recommend to set up a virtual Python environment to install the package and its dependencies. To install the package, we recommend to execute `pip install -r requirements.txt` in the command line. This will install it in editable mode, meaning there is no need to reinstall after making changes. If you are using PyCharm, it should offer you the option to create a virtual environment from the requirements file on startup. Note that also in this case, it will still be necessary to run the pip command described above.

## Submission instructions
After each sprint, you are expected to submit your code. This will **not** be done in Canvas, instead you will be creating a release of your current repository. 
A release is essentially a snapshot of your repository taken at a specific time. 
Your future modifications are not going to affect this release.
**Note that you are not allowed to update your old releases after the deadline.**
For more information on releases, see the [GitHub releases](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases) page.

1. Make sure that your code is running without issues and that **everything is pushed to the main branch**.
2. Head over to your repository and click on *Releases* (located at the right-hand side).
3. Click on *Create a new release*.*
4. Click on *Choose a tag*.
5. Fill in the textbox with **SprintX** where X is the current sprint number and press *Create new tag: SprintX*.
6. Make sure that *Target: main* or *Target: master* (depending on your main/master branch) is selected, so that the code release will be based on your main branch.
7. Fill in the title of the release with **Group XX Sprint X** where XX is your group number and X is the current sprint number.
8. Click the *Publish release* button to create a release for your sprint.
9. **Verify** that your release has been successfully created by heading over to your repository and press the *Releases* button once again. There you should be able to see your newly created release.

*After the first release, you should click *Draft a new release* instead of *Create a new release*.

## Mypy
The template is created with support for full typehints. This enables the use of a powerful tool called `mypy`. Code with typehinting can be statically checked using this tool. It is recommended to use this tool as it can increase confidence in the correctness of the code before testing it. Note that usage of this tool and typehints in general is entirely up to the students and not enforced in any way. To execute the tool, simply run `mypy`. For more information see https://mypy.readthedocs.io/en/latest/faq.html

## Argparse
Argparse functionality is included in the main.py file. This means the file can be run from the command line while passing arguments to the main function. Right now, there are arguments included for the number of epochs (nb_epochs), batch size (batch_size), and whether to create balanced batches (balanced_batches). You are free to add or remove arguments as you see fit.

To make use of this functionality, first open the command prompt and change to the directory containing the main.py file.
For example, if you're main file is in C:\Data-Challenge-1-template-main\dc1\, 
type `cd C:\Data-Challenge-1-template-main\dc1\` into the command prompt and press enter.

Then, main.py can be run by, for example, typing `python main.py --nb_epochs 10 --batch_size 25`.
This would run the script with 10 epochs, a batch size of 25, and balanced batches, which is also the current default.
If you would want to run the script with 20 epochs, a batch size of 5, and batches that are not balanced, 
you would type `main.py --nb_epochs 20 --batch_size 5 --no-balanced_batches`.
