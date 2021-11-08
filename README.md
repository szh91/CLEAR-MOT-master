#CLEAR-MOT

A standard metric for evaluating the multiple target tracking algorithm is the CLEAR MOT.  This metric is described in the paper [1] .

![Clear MOT matlab script](http://www.micc.unifi.it/masi/wp-content/uploads/2012/05/Schermata-05-2456054-alle-17.53.02.png)

## Papers using our code

[1] D. Karatzas, F. Shafait, S. Uchida, M. Iwamura, L. Gomez i Bigorda, S. Robles Mestre, J. Mas, D. Fernandez Mota, J. Almazan Almazan; L.-P. de las Heras, "ICDAR 2013 Robust Reading Competition," Document Analysis and Recognition (ICDAR), 2013 12th International Conference on , vol., no., pp.1484,1493, 25-28 Aug. 2013 doi: 10.1109/ICDAR.2013.221

[2] A. Milan, K. Schindler, S. Roth, "Challenges of Ground Truth Evaluation of Multi-target Tracking," Computer Vision and Pattern Recognition Workshops (CVPRW), 2013 IEEE Conference on , vol., no., pp.735,742, 23-28 June 2013 doi: 10.1109/CVPRW.2013.111

## Details

We provide the code that implements the metric CLEAR-MOT has described by the authors in [1]. The function is implemented in MATLAB and has been tested
on real data generated by a multiple-target tracker.

The tarball contains these MATLAB/Octave files:

1. generateData.m create the basic structures for the algorithm. Ground-truth objects are specificated by bounding box as [tl.x tl.y width height] in the "gt" cell structure. The "result" structure contains the tracking hypothesis as taken from the ground truth files. 
1. evaluateMOT.m is the function that perform the evaluation.
1. demo.m is the main file that you can launch to test the CLEAR-MOT script.
1. GreedyAssociation.m is the file that performs the association give the distance matrix. You can replace with other solver like Hungarian algorithm. These files are an example: if you want to use the script to evaluate you multiple target tracking, you have to recreate the structures groundtruth.mat and result.mat with your own data.


## Demo Example
To run our code and have a brief results just copy-paste this code:
	
	%this gives the results and the groundtruth
	generateData
	%threshold used to associate a tracker to a ground-truth
	VOCscore = 0.5;
	%display the result at the end
	dispON  = true;
	% run evaluation and save the result in a structure 'ClearMOT'
	ClearMOT = evaluateMOT(gt,result,VOCscore,dispON);


## Citation

Please cite our paper with the following bibtex if you use our dataset:

``` latex
@article{ masi:multimedia12,
author = {Bagdanov, Andrew D. and Del Bimbo, Alberto and Dini, 
Fabrizio and Lisanti,  Giuseppe and Masi, Iacopo},
title = {Posterity Logging of Imagery for Video Surveillance},
booktitle = {IEEE Multimedia},
year = {2012}, }
```

## References

[1] Keni Bernardin and Rainer Stiefelhagen. “Evaluating multiple
objec tracking performance: the CLEAR MOT metrics” J. Image Video
Process. 2008, Article 1 (January 2008), 10 pages.” DOI=10.1155/2008/246309
http://dx.doi.org/10.1155/2008/246309

##License
CLEAR-MOT Matlab script is Copyright (c) 2013 of Iacopo Masi and Giuesppe Lisanti *\<iacopo.masi,giuseppe.lisanti\>@unifi.it*.
[Media Integration and Communication Center (MICC), University of Florence. ](http://www.micc.unifi.it/vim)
