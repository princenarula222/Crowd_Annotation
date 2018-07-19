# CROWD ANNOTATION

 This repository provides a MATLAB script to annotate your own crowd dataset (.jpg files) in accordance with standard datasets (UCF and ShanghaiTech) and 
generate corresponding ground truth .mat files to make your dataset compatible for training as well as testing with crowd counting models. 


# Annotation Procedure

Let us pick up the idea of using ShanghaiTech part B dataset along with the data we collected. We desire that the dataset remains sequential. You may modify 
the steps according to your needs once you understand the procedure described below.

We wish to add our training dataset to the ShanghaiTech part B training dataset. The steps are as follows:

1. Go to 'data_annotation' folder.

2. Place your dataset images in the 'images'(data_annotation/images/) folder.

   a. Rename your images to 'IMG_num(t+i)' (for example, 'IMG_401') where:

              t - number of images already in the 'ShanghaiTech/part_B/train_data/images/' folder

              i - corresponds to the ith image in the dataset collected by us

3. Open 'gt_mat_gen.m'(data_annotation/gt_mat_gen.m), modify the value of t with respect to the purpose defined in step 2 and run this .m file 
using MATLAB.

4. Images will open sequentially as figures in MATLAB along with a marker(cursor). Use your mouse and click on the heads of the people to
annotate the heads. Once you're done annotating all the heads in an image, press enter and wait for the next image to load. Repeat this 
step until you're done annotating all of your images.

5. Ground truth .mat files are generated in 'ground-truth'(data_annotation/ground-truth/) folder. Transfer the contents of this folder to 
'ShanghaiTech/part_B/train_data/ground-truth/' folder. Also, images are resized to 1024*768 as this is the resolution of ShanghaiTech
part B images. You may change this resolution to a new value by changing appropriate parameters in 'gt_mat_gen.m' as per your needs. 
Transfer the contents of 'images'(data_annotation/images/) folder to 'ShanghaiTech/part_B/train_data/images/' folder.


Note - If you're trying to add your testing dataset to the ShanghaiTech part B testing dataset, follow the same steps keeping in mind 
'ShanghaiTech/part_B/test_data/images/' instead of 'ShanghaiTech/part_B/train_data/images/' and 'ShanghaiTech/part_B/test_data/ground-truth/'
instead of 'ShanghaiTech/part_B/train_data/ground-truth/'. Use t=0 if you wish to annotate your dataset independently. I have provided some
samples for reference.