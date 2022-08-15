Contents
====
- [Downloads the git from theAIGuysCode/yolov4-deepsorts](#downloads-the-git-from-theAIGuysCode/yolov4-deepsorts)
- [Change the folder](#change-the-folder)
- [Create a new environmet](#create-a-new-environmet(recommand))
- [Install requirements](#install-requirements)
- [Transfer darknet weights to tensorflow](#transfer-darknet-weights-to-tensorflow)
- [Amend the classes](#amend-the-classes)
- [Run it on video](#run-it-on-video)

🔱Downloads the git from theAIGuysCode/yolov4-deepsorts
====
https://github.com/theAIGuysCode/yolov4-deepsort

🔱Change the folder
====
    cd yolov4-deepsort

🔱Create a new environmet(Recommand)
====
## For CPU
    conda env create -f conda-cpu.yml
    conda activate yolov4-cpu

## For GPU
    conda env create -f conda-gpu.yml
    conda activate yolov4-gpu
    
🔱Install requirements
====
## For CPU
    pip install -r requirements.txt
    
## For GPU
    pip install -r requirements-gpu.txt
    
🔱Transfer darknet weights to tensorflow
====
    python save_model.py --model yolov4 

🔱Amend the classes
====
Change it to your classes of your trained model in file object_tracker.py line 162.

![image](https://user-images.githubusercontent.com/46515944/183457191-d5135ed6-bf24-413f-a21c-04138275e4c5.png)

Then, copy the file named coco.names to folder "data/classes".


🔱Run it on video
====
    python object_tracker.py --video ./data/video/test.mp4 --output ./outputs/demo.avi --model yolov4

If you wanna use the web camara, you only add the parameter "0" before --video

    python object_tracker.py --video 0 --output ./outputs/webcam.avi --model yolov4
