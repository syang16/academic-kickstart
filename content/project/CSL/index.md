+++
# widget = "Portfolio"  # Do not modify this line!
# active = true  # Activate this widget? true/false
# weight = 15  # Order that this section will appear.

# Note: a full width section format can be enabled by commenting out the `title` and `subtitle` with a `#`.
# title = "Cost Sensitive Statistical Relational Learning"
# subtitle = ""
  
# Project title.
title = "Cost Sensitive Statistical Relational Learning"

# Date this page was created.
date = 2019-03-13T00:00:00

# Project summary to display on homepage.
summary = "In this project, we consider the problem of incorporating the domain knowledge on different weights of positive samples and negative samples. One of the motivations is the class-imbalance situation in many relational domains where the classifier boundary could be easily dominated by the majority class and overfitting on its outliers. Hence, it is essential to steer the training process toward focusing more on the minority class by assigning different costs on false positive and false negative samples. Besides the requirement enforced by such data properties, there are also practical demands in certain domains, such as the diagnosis problem in medical domains, the quality checking in manufacturing data, the recommendation prediction in recommender systems, etc."

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["machine-learning","statistical-relational-learning", "cost-sensitive-learning", "class-imbalance"]

# Optional external URL for project (replaces project detail page).
#external_link = ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
#slides = "example-slides"

# Links (optional).
url_pdf = "https://shuoyang.netlify.com/publication/yang-14/yang-14.pdf"
#url_slides = ""
#url_video = ""
url_code = "https://shuoyang.netlify.app/project/csl/"

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
# url_custom = [{icon_pack = "fab", icon="twitter", name="Follow", url = "https://twitter.com/georgecushen"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
 [image]
 preview_only = true
  # Caption (optional)
  #caption = ""
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Right"
+++
In this project, we consider the problem of incorporating the domain knowledge on different weights of positive samples and negative samples. One of the motivations is the class-imbalance situation in many relational domains where the classifier boundary could be easily dominated by the majority class and overfitting on its outliers. Hence, it is essential to steer the training process toward focusing more on the minority class by assigning different costs on false positive and false negative samples. Besides the requirement enforced by such data properties, there are also practical demands in certain domains, such as the diagnosis problem in medical domains, the quality checking in manufacturing data, the recommendation prediction in recommender systems, etc.

The common approach for dealing with this problem is sampling approach, either sub-sampling of the majority class or over-sampling on the minority class. We proposed a soft margin learning approach on the basis of <a href="http://ftp.cs.wisc.edu/machine-learning/shavlik-group/natarajan.mlj12.pdf">relational functional gradient boosting</a>. Our approach allows explicit tunning the trade-off between false positive rate and false negative rate during the learning process by including two paramters into the objective function, which control the weights of false positives and false negatives respectively.

<div class="row-fluid spacing-top-bottom">
		<h1>What domains are applicable?</h1>  
			<div class="span4">
				<h2><font color="black">Class-Imbalanced Domains</font></h2> <a href="https://shuoyang.netlify.com/publication/yang-14/"> <u>[Yang et al. 2014]</u></a>
        <img src="cid.PNG" width="330" height="300">
				<p align="justify"><font color="black"> Class-Imbalance is a phenomenal problem in a lot of domains, especially for statistical relational learning problems where the number of the ground substitutions for a logical predicate is exponential in the number of the instances for the logical variables and among them only a few substitutions are true. </font></p>
			</div>
			<div class="span4">
				<h2><font color="black">False Negatives Cost More</font></h2> <a href="https://shuoyang.netlify.com/publication/chas-ehaley/"> <u>[MacLeod et al. 2016]</u></a>
				<img src="md.PNG" width="330" height="300">
				<p class="p-pad", align="justify"><font color="black"> Domains where the cost for false negative prediction is much more than that of the false positive prediction. For example, in medical diagnosis, the false positive prediction may just lead to few more clinical tests while the false negative prediction could cost the patient’s life. </font></p>
			</div>
			<div class="span4">
				<h2><font color="black">False Positives Cost More</font></h2> <a href="https://starling.utdallas.edu/assets/pdfs/HRSPreprint.pdf"> <u>[Yang et al. 2017]</u></a> 
				<img src="rs.PNG" width="330" height="300">
				<p class="p-pad", align="justify"> <font color="black"> Domains where the false positive prediction is more unfavorable. For example, in recommendation systems, one would rather overlook some of the candidate items that could match the users (false negatives) than send out numerous spam emails to the users with inappropriate recommendations (false positives).</font></p>
			</div>
</div>
    
<h1>How to use this package?</h1>

<h2> <font color="black"> The whole package can be downloaded <a href="CostSensitiveLearningPackage.zip"> <u>here.</u></a> </font> </h2>
		<p class="p-pad", align="justify"> <font color="black">The package includes the pre-processing code for standard machine learning input data, the Soft-Margin RFGB code and the code for calculating the measurements of evaluating the performance of learning algorithms for class-imbalance problems. </font></p>
		
<h2> <font color="black"> Data Pre-Processing </font> </h2> 
<p class="p-pad", align="justify"> <font color="black"> For standard machine learning problems, just run the python script <u> ConvertStandardData</u> in the package to convert the flat table into the input data format that Soft-Margin RFGB can take. <a href="PreProcess.zip"><u> ConvertData_standard</u></a> also contains a sample data set--heart disease data from <a href="https://archive.ics.uci.edu/ml/index.php"><u> UCI Machine Learning Repository.</u></a> Users can use this script to convert any data set from <a href="https://archive.ics.uci.edu/ml/index.php"><u> UCI Machine Learning Repository</u></a> by simply adding the variable names in the first row. </p> 

A sample usage is as below:

<pre><code>$ python ConvertStandardData.py filename=PATH/TO/YOUR/DATA/DATA.csv \
&gt; target=TargetVariable \ 
&gt; Discretize='feature1':[threshold list],'feature2':['value', Nclass],'feature3' ['quantile',Nclass] \ 
&gt; TestRatio=0.1 </code></pre>

<p class="p-pad", align="justify"> The optional arguments are <font color="blue"><b> Discretize </b></font> and <font color="blue"><b> TestRatio </b></font>.</p> 
<p class="p-pad", align="justify"> Use <font color="blue"><b> Discretize </b></font> if one wants to discretize the continuous-valued variables. There are three options: <b>i.</b> assign categorical values based on the thresholds given as a list; <b>ii. </b> categorize into N classes based on values by specifying ['value', Nclass] ;  <b> iii. </b> discretize into N bins based on sample quantiles by specifying ['quantile', Nclass]. If not given, numerical variables will be written out in their original value types. </p>
<p class="p-pad", align="justify"> Use <font color="blue"><b> TestRatio </b></font> to specify how you want to split the data into training and test sets. If not assigned, 80% of the samples will be assigned to the training and 20% to test. </p>

<p class="p-pad", align="justify"> For relational data sets, please refer to <a href="http://pages.cs.wisc.edu/~tushar/rdnboost/doc.html"><u>Mode Guide</u></a> for more sophisticated designs of logic predicates. </font></p> 
		
<h2> <font color="black"> Run Soft-Margin RFGB </font> </h2>
<p class="p-pad", align="justify"> <font color="black"> Here is a simple example on how to use the  <a href="SoftBoosting.jar"><u>Soft-Margin RFGB code</u></a>.</font></p>
<pre><code>$ java -cp SoftBoosting.jar edu.wisc.cs.Boosting.RDN.RunBoostedRDN \ 
&gt; -target num \ 
&gt; -l -train SampleData/OutputDataForSoft-RFGB/HD/train/ \ 
&gt; -i -test SampleData/OutputDataForSoft-RFGB/HD/test/ \ 
&gt; -alpha 2 \ 
&gt; -beta -1 </code></pre>
		
The parameter <font color="blue"> <b> alpha </b> </font> controls the cost of false negative samples while <font color="blue"><b> beta </b> </font> controls the cost of false positive samples. When the parameter (alpha or beta) is set positive, it assigns more weights on the miss-classified positive or negative samples, whearas when it is negative, it allows the model to put more tolerance on the the miss-classified positive or negative samples. When they are both zero, it is equivalent to the standard RFGB, i.e. false positive and false negative have uniform cost.
		
<h2> <font color="black"> Evaluation Metrics For Class-Imbalanced Data </font> </h2>
<p class="p-pad", align="justify"> <font color="black"> Standard evaluation metrics for the prediction performance include the use of accuracy, Area Under ROC or PR curves (AUC-ROC or AUC-PR), F1 score, etc., which measure accuracy with balanced weight between positive and negative examples. However, in the cost-sensitive learning, the model should identify as many important cases as possible as long as the accuracy on predicting the less importance class stays within a reasonable range. To better evaluate the performance of different algorithms for learning with class-imbalanced data, we employed F-beta measure and weighted AUC-ROC. For F-beta measure, beta controls the importance of Precision and Recall. When beta > 1, F-beta measure is recall dominated, while as 0< beta < 1 F-beta measure is precision dominated. </font></p>

More details about the algorithm and parameter settings can be found in <a href="https://shuoyang.netlify.com/publication/yang-14/"> <u>[Yang et al. 2014].</u></a> Please use the following citation to acknowledge the contribution made by this package to your research. [^1]

[^1]: Shuo Yang, Tushar Khot, Kristian Kersting, Gautam Kunapuli, Kris Hauser and Sriraam Natarajan, Learning from Imbalanced Data in Relational Domains: A Soft Margin Approach, International Conference on Data Mining (ICDM), 2014.
