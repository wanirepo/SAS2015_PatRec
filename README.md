# SAS2015 Pattern Recognition

Wani will use this github repository to help people get hands-on experience using [CANLab fMRI analysis tools](https://github.com/canlab/CanlabCore) for multivariate anlayses.

## Installation
You can download the CANLab core tools (written in **MATLAB**) using the following command line. You can also **fork** the CanlabCore repository. 

	$ git clone https://github.com/canlab/CanlabCore.git
	

## Overview

The main MATLAB function we will use for our purpose is <code>fmri\_data.predict</code>, which is a method of the <code>fmri_data</code> object. You can read a brief overview of our object-oriented tools for fMRI analysis [here](http://wagerlab.colorado.edu/wiki/doku.php/help/core/object_oriented_fmri). (We're sorry that documentations in that page are incomplete, but you will be able to get all the information you need for our purpose). 

### fmri_data object
This object is a child of the <code>image\_vector</code> object. <code>fmri\_data</code> stores 4-D data from a series of one or more images. It has special data fields for predictors, outcome data, and other associated information. It inherits all the methods from <code>image\_vector</code> (e.g., <code>fmri\_data.orthviews</code>), but also has special methods for data analysis, including <code>fmri\_data.predict</code>, <code>fmri\_data.preprocess</code>, <code>fmri\_data.rescale</code>, and others. 

### fmri_data.predict
Using this function, you will be able to run many different machine learning algorithms on your data. The algorithms include multiple regression, LASSO regression, LASSO-PCR, SVMs, SVR, etc. To run all of these algorithms, you may need **basic MATLAB toolboxes** provided by MathWorks. In addition, you need a couple of external toolboxes (see **dependency** below). 

## Dependency

Our [core toolbox](https://github.com/canlab/CanlabCore) has these external toolboxes within a directory called "External", but I recommend downloading them from their website directly.

#### 1. Spider toolbox for SVMs
[http://people.kyb.tuebingen.mpg.de/spider/download_frames.html](http://people.kyb.tuebingen.mpg.de/spider/download_frames.html)

#### 2. Lasso toolbox by Rocha and Zhao

[http://www.stat.berkeley.edu/~yugroup/downloads/](http://www.stat.berkeley.edu/~yugroup/downloads/)

If you downloaded this, please change <code>lasso.m</code> into <code>lasso\_rocha.m</code>. to avoid a name conflict with the lasso function provided by MathWorks. 

For your note, our <code>fmri\_data.predict</code> has both options for Rocha and Zhao's lasso function ('cv\_lassopcr') and MATLAB lasso function ('cv\_lassopcrmatlab'). This is because we started to use lasso methods before MATLAB provided the lasso function. You can use one of them. 

## Getting started

predict\_example.m has all the codes you need for the hands-on experience. The output figures and some explanations of the code are saved [here]().  






