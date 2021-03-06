# CPIH
A large-scale database for CTU partition of intra-mode HEVC (CPIH).

For reducing HEVC encoding complexity through deep learning based approach, a large-scale database is established [1]. 

It is served for CTU Partition of Intra-mode HEVC, namely CPIH database. To the authors' best knowledge, this is the first database on CTU partition patterns. First, 2000 images at resolution 4928\*3264 are selected from Raw Images Dataset (RAISE, http://mmlab.science.unitn.it/RAISE/). These 2000 images are randomly divided into training (1700 images), validation (100 images) and test (200 images) sets. Furthermore, each set is equally divided into four subsets: one subset is with original resolution and the other three subsets are down-sampled to be 2880\*1920, 1536\*1024 and 768\*512. As such, this CPIH database contains images at different resolutions. This ensures sufficient and diverse training data for learning to predict CTU partition. 

Next, all images are encoded by the HEVC reference software HM 16.0. Specifically, four QPs {22,27,32,37} are applied for encoding with the configuration file encoder intra main.cfg in the common test conditions. After encoding, the binary labels indicating splitting (=1) and non-splitting (=0) are obtained for all CUs, and each CU with its corresponding binary label is seen as a sample. 

In total, the CPIH database contains 12 sub-databases according to QP and CU size, on account that 4QPs are applied and CUs with 3 different sizes (64\*64, 32\*32 and 16\*16) are allowed to be split.

To download original images and labels (compressed in 8 files), visit:

https://drive.google.com/open?id=0B-x4IFNM0upjWmllNDdnc182dlU

https://drive.google.com/open?id=0B-x4IFNM0upjVTZHMmpveElGOGM

https://drive.google.com/open?id=0B-x4IFNM0upjLXByNkpIM3lTMTA

https://drive.google.com/open?id=0B-x4IFNM0upjbUxsQW5oeDdZb3M

https://drive.google.com/open?id=0B-x4IFNM0upjYzFQaEhPNEZRaWM

https://drive.google.com/open?id=0B-x4IFNM0upjNzl5SGtqOTB3WG8

https://drive.google.com/open?id=0B-x4IFNM0upjSVh0NEgtRXV0ajQ

https://drive.google.com/open?id=0B-x4IFNM0upjY2JDclFsZEtjdU0

Extract all data above to get 12 YUV files and 8 DAT files. Then execute "extractCUDepthGrndTruthCPIH.m" and generate all the training, validation and test samples.

If the CPIH database is helpful to your research, please cite this paper:

[1] Tianyi Li, Mai Xu and Xin Deng. A Deep Convolutional Neural Network Approach for Complexity Reduction on Intra-mode HEVC. IEEE International Conference on Multimedia and Expo (ICME), 2017.
