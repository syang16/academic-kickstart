+++
# widget = "blank"  # Do not modify this line!
# active = true  # Activate this widget? true/false
# weight = 15  # Order that this section will appear.

# [design]
  # Choose how many columns the section has. Valid values: 1 or 2.
  # columns = "1"
  
# Project title.
title = "Knowledge-intensive Learning"

# Date this page was created.
date = 2019-03-13T00:00:00

# Project summary to display on homepage.
summary = "In this project, we consider the problem of incorporating the domain knowledge on different weights of positive samples and negative samples. One of the motivations is the class-imbalance situation in many relational domains where the classifier boundary could be easily dominated by the majority class and overfitting on its outliers. Hence, it is essential to steer the training process toward focusing more on the minority class by assigning different costs on false positive and false negative samples. Besides the requirement enforced by such data properties, there are also practical demands in certain domains, such as the diagnosis problem in medical domains, the quality checking in manufacturing data, the recommendation prediction in recommender systems, etc."

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["machine-learning","Bayesian-network", "knowledge-based-learning", "qualitative-constraints", "causal-independence"]

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
url_pdf = "https://shuoyang.netlify.com/publication/yang-n-13/yang-n-13.pdf"
#url_slides = ""
#url_video = ""
#url_code = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
#url_custom = [{icon_pack = "fab", icon="twitter", name="Follow", url = "https://twitter.com/georgecushen"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  #caption = ""
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Right"
+++
In this project, we consider the problem of incorporating the domain knowledge on different weights of positive samples and negative samples. One of the motivations is the class-imbalance situation in many relational domains where the classifier boundary could be easily dominated by the majority class and overfitting on its outliers. Hence, it is essential to steer the training process toward focusing more on the minority class by assigning different costs on false positive and false negative samples. Besides the requirement enforced by such data properties, there are also practical demands in certain domains, such as the diagnosis problem in medical domains, the quality checking in manufacturing data, the recommendation prediction in recommender systems, etc.

The common approach for dealing with this problem is sampling approach, either sub-sampling of the majority class or over-sampling on the minority class. We proposed a soft margin learning approach on the basis of relational functional gradient boosting . Our approach allows explicit tunning the trade-off between false positive rate and false negative rate during the learning process by including two paramters into the objective function, which control the weights of false positives and false negatives respectively. Learn more about the algorithm.
