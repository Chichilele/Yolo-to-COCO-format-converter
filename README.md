# Yolo-to-COCO-format-converter

When you use **Yolo-model**, you might create annotation labels with [Yolo-mark](https://github.com/AlexeyAB/Yolo_mark).  
For example,  
- `obj.names` - example of list with object names  
- `train.txt` - example with list of image filenames for training Yolo model  
- `train/` - example of folder that contain images and labels
> - *.jpg : example of list of image  
> - *.txt : example of list of label  

**But, when you want to use another model(ex. efficientdet), you need another annotation format! :disappointed_relieved:**  
### This code will help you make a COCO format annotations with Yolo format!  

## How to use
### Requirements
- numpy
- OpenCV  

You can make same environment with anaconda environment.  
- `conda create -n Yolo-to-COCO python=3.8`  
- `conda activate Yolo-to-COCO`  
- `pip install numpy`  
- `pip install PILLOW`  

Just clone this repository.  
- `git clone https://github.com/Chichilele/Yolo-to-COCO-format-converter.git`  
- `cd Yolo-to-COCO-format-converter`  

### It will be easy to understand if you refer to the tutorial folder.  

When you have your own Yolo annotation format, just change a little bit!  
#### 1. Change `classes` with your own dataset.  
Write `obj.names`  file as a list of existing objects in the dataset.

#### 2. Check the absolute path in `train.txt`.  
Make sure that it points to the absolute path to the folder where the image and text files are located.  
The file must contain a list of all image files.  

#### 3. Just run the code.  
You need to provide 2 argments(essential) & 1 argments(optional).  
- path : Absolute path of train.txt  
- output : Path to the output json file  
- objects : path to obj.names

When you want to make json file,  
- `python main.py --path [path of train.txt] --output [path of the json file] --objects [path of obj.names]`  
- (For example)`python main.py --path ./tutorial/train.txt --output ./train.json --objects ./obj.names`

#### Tips  
If you want to read json files more clearly, you should use `JQ`!  
- [JQ Manual](https://stedolan.github.io/jq/manual/)
- (For example) `cd output`
- `jq . train.json > train_jq.json`

## Contributors
- I created a repository by referring to [chrise96/image-to-coco-json-converter](https://github.com/chrise96/image-to-coco-json-converter).  
- **GeeJae Lee** helped to make it.

  
