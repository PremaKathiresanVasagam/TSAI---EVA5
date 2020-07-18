# 1. What are Channels and Kernels (according to EVA)?
 
 # Channels:
        Channel is a container of unique/specific information. We can keep on adding similar info into that container. 
 # Kernel: 
        A kernel is a filter that extracts features.
        Also called, 3 X 3 matrix or feature extractor.
 
 E.g. In EVA5 class, students who are above threshold 70 in their assignments are put under sincere channels and others under lazy channel. Here, above threshold 70 is a filter.
 
 # 2. Why should we (nearly) always use 3x3 kernels?
   
   1. Symmetric matrix helps in easy detection of edges and gradients (3X3, 5X5, ...)
   2. 1X1 (Moving 1 pixel at a time) doesn't help in detecting edges and gradients.
   3. 5X5, 7X7, ... have more number of parameters and are computationally heavy. Whereas, 3X3 kernel is with the least number of parameters.
      Kernels  No. of. Params
      3X3                  9
      5X5                 25
      7X7                 49
      ...
      
  # 3. How many times to we need to perform 3x3 convolutions operations to reach close to 1x1 from 199x199 (type each layer output like 199x199 > 197x197...)

100 layers, 99 convolutions

1.199X199


2.197X197


3.195X195


4.193X193


5.191X191


6.189X189


7.187X187


8.185X185


9.183X183


10.181X181


11.179X179


12.177X177


13.175X175


14.173X173


15.171X171


16.169X169


17.167X167


18.165X165


19.163X163


20.161X161


21.159X159


22.157X157


23.155X155


24.153X153


25.151X151


26.149X149


27.147X147


28.145X145


29.143X143


30.141X141


31.139X139


32.137X137


33.135X135


34.133X133


35.131X131


36.129X129


37.127X127


38.125X125


39.123X123


40.121X121


41.119X119


42.117X117


43.115X115


44.113X113


45.111X111


46.109X109


47.107X107


48.105X105


49.103X103


50.101X101


51.99X99


52.97X97


53.95X95


54.93X93


55.91X91


56.89X89


57.87X87


58.85X85


59.83X83


60.81X81


61.79X79


62.77X77


63.75X75


64.73X73


65.71X71


66.69X69


67.67X67


68.65X65


69.63X63


70.61X61


71.59X59


72.57X57


73.55X55


74.53X53


75.51X51


76.49X49


77.47X47


78.45X45


79.43X43


80.41X41


81.39X39


82.37X37


83.35X35


84.33X33


85.31X31


86.29X29


87.27X27


88.25X25


89.23X23


90.21X21


91.19X19


92.17X17


93.15X15


94.13X13


95.11X11


96.9X9


97.7X7


98.5X5


99.3X3


100.1X1

# Python snippet:

a = 0
for i in range(199, 0, -2):
    a = a+1
    print(str(a)+ '.' + str(i) + 'X' + str(i))
    print('\n')
    
# 4. How are kernels initialized? 
Kernels are initialised randomly between 0 and 1 following uniform distribution

np.random.rand(3, 3) #The values are always less than one.
 
# What happens during the training of a DNN?

 ----------------        --------------------      ---------------      -------   
|Edges & Gradients|  -> |Textures & Patterns | -> |Part of objects| -> |Objects|
 ----------------        --------------------      ---------------      -------
 
 Once the input image is given, 3X3 matrix are initialised at random and these matrices extracts features. These kernels convolve on input images detecting edges and gradients. 
 From that Textures and patterns are identified forming parts of an object. And finally, parts of a image construct an object.
        
