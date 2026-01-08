## Run demo

* run `ui.py` and input the handwritten picture directory and run inference 

### Prepare dataset
Follow these instructions to get the IAM dataset:

* Download https://drive.google.com/drive/folders/1H0fG5LsvmXSZeYq-rA6TuMsYKdB3St9E?usp=sharing
* Create a directory for the dataset (a folder name `dataset`), and create two subdirectories: `img` and `gt`
* Put .txt file from ascii zip folder into the `gt` directory
* Put the content (directories `a01`, `a02`, ...) of `words.tgz` into the `img` directory

### Run training

* Delete files from `model` directory if you want to train from scratch
* Go to the `src` (`cd src`) directory and run `python main.py --mode train --data_dir ../dataset` in terminal (run `python main.py --mode train --data_dir ../dataset --fast` if fast image loading enabled)

### Fast image loading
* Go to the `src` directory and run `create_lmdb.py --data_dir ../dataset` with the IAM data directory specified
* A subfolder `lmdb` is created in the IAM data directory containing the LMDB files
* When training the model, add the command line option `--fast`