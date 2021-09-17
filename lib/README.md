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