# Thesis instruction on how to run the code

There are two files for execution.

## First is the main.py

Which is used to train the model.

## Second is the eval_openset.py

Which is used to evaluate the model after training.

## To load checkpoint

- Add the path which save the checkpoint of the model to this line in cmdparser.py file

`parser.add_argument('--resume', default='', type=str, help='path to model to load/resume from(default: none). '
                                                           'Also for stand-alone openset outlier evaluation script')`

## Label of dataset class

    0: 'eosinophil',
    1: 'basophil',
    2: 'lymphocyte',
    3: 'neutrophil',
    4: 'monocyte'

## Execution and result

### main.py

- This file is used to train the model and also saved the checkpoint in the file called `checkpoint.pth.tar`.
- When you run the main.py file. The result of the dataset is saved in this path `'drive/Shareddrives/VGU_Thesis/runs/'`
- In the folder, you can see the result that you run based on the time you execute the code. The format of the name looks
like this `2021-09-08_07-19-59_PBC_WRN_variational_samples_1_latent_dim_80` first is the time you run the code, the name of dataset `PBC`,
the architecture you used `WRN`, the number of sample `1` and the dimension of latent space `80`
- The images that are generated and reconstructed are also saved in the corresponding folder in each execution.

### eval_openset.py

- In order to run this file, you need to specify the path to load the checkpoint, which is the result of the main.py
- `parser.add_argument('--resume', default='', type=str, help='path to model to load/resume from(default: none). '
                                                           'Also for stand-alone openset outlier evaluation script')`
- In the default parameters, you add the link of the checkpoint which is saved in the folder you run when executed the main.py
- For example: When you run `main.py` a folder named `2021-09-08_07-19-59_PBC_WRN_variational_samples_1_latent_dim_80_resumed`
will be created, the name of the folder may changed based on the time, architecture, number of examples and dimension of latent space.
The name `resumed` indicated that this folder is loaded from the checkpoint of another folder.
- When you located the folder you need to run using `eval_openset.py` file. You add that link to the `default` parameters
and add `/checkpoint.pth.tar` to load the checkpoint of that result.
- After finished adding the link, you can run this file to evaluate the result of the trained model.