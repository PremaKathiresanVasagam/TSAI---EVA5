
## 1. Dataset creation: Download and label images using VGG Annotator
50 images each of people wearing hardhat, vest, mask and boots labelled using VGG annotator

## 2. Export Annotations as JSON/CSV
In VGG annotator, Annotate --> Export annotations(as json) to download the JSON file with filename and it's attributes (Same way .csv can be downloaded as well)

## 3. Generate image size
As image resolution details are not present in the above downloaded JSON/CSV, create a csv with imagename and it's width and height using image.shape

## 4. Create final dataframe for YOLO implementation
* Merge the above two files(CSV from VGG annotator & Image resolution CSV)
* Keep only relevant columns and remove the unwanted columns

## 5. Final frame attributes and explanation:
![Img](https://github.com/PremaKathiresanVasagam/TSAI---EVA5/blob/master/S12/Assign_B/Images_for_README/Primary_DF.PNG)

* Explanation of attributes: <br />
Class - Boots/HardHat/Mask/Vests <br />
Filename   - Image name <br />
Img_width  - Width of the image <br />
Img_height - Height of the image #Resolution of image = Img_width X Img_height <br />
X          - In X-axis, Start of bounding box from top left corner <br />
Y          - In Y-axis, Start of bounding box from top left corner <br />
BBox_Width - Width of the bounding box(x) <br />
BBox_height- Height of the bounding box(y) <br />

## 6. BBox width and Height - Normalized and log(Normalized) are calculated
![Img1](https://github.com/PremaKathiresanVasagam/TSAI---EVA5/blob/master/S12/Assign_B/Images_for_README/Final_DF.PNG)

* Explanation of attributes: <br />
Norm_bbox_Width - Normalized bbox width (0 - 1) <br />
Norm_bbox_Height - Normalized bbox height (0 - 1) <br />
log_Norm_bbox_Width - log(Normalized bbox width (0 - 1)) <br />
log_Norm_bbox_Height - log(Normalized bbox height (0 - 1)) <br />


## 7.Elbow method and k-means clustering
The number of clusters is found using elbow method. <br />

![Img2](https://github.com/PremaKathiresanVasagam/TSAI---EVA5/blob/master/S12/Assign_B/Images_for_README/Elbow_method.PNG)

Number of clusters = 5

* Normalised BBox width Vs Normalised BBox Height <br />

![Img3](https://github.com/PremaKathiresanVasagam/TSAI---EVA5/blob/master/S12/Assign_B/Images_for_README/Norm_Cluster.PNG)

* Log-Normalised BBox width Vs Log-Normalised BBox Height <br />

![Img4](https://github.com/PremaKathiresanVasagam/TSAI---EVA5/blob/master/S12/Assign_B/Images_for_README/Log_Norm_Cluster.PNG)
