---
title: "Classification Metrics, Clearly Explained!!!"
categories: [Machine Learning, Image classification, Metrics]
description: Wondering about which classification metric to use?
toc: true
---
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>


### Classification
<p>
	Is it A or not A, is it spam or not spam, is the puppy cute or not cute?
For example, we might decide to mark something as spam if it exceeds a spam probability of 0.8. Then our classification threshold is 0.8.</p>
<p><b>Now once we’ve chosen a classification threshold, how are we going to evaluate the quality of that model?</b>

Below are the classification metrics that are majorly used in different scenarios or use cases.</p>

<ul>
    <li>One classic way of evaluating classification performance is Accuracy. And by accuracy we mean count of all things you got right and divide by count of all things that were there.</li>
    <li>Basically, what percentage of the things did you get correct. Interestingly enough, even though accuracy is a very intuitive and widely used metric , it has some flaws. </li>
    <li> In particular, accuracy breaks down when we have class imbalance in our problems.</li>
    <li>Imbalance means not having an equal ratio or at least nearly equal ratio of all the classes. </li>
    <li>For suppose, consider a binary classification use case where the dataset of class-1 holds the 70% of the whole dataset and class-2 holds the remaining 30%. In such cases, when we use accuracy as our metric, we might end up getting a good accuracy value, yet the model is considered to be a bad model. Since, the majority of the datasets contains class-1, the model tends to be biased towards class-1 leading to more false positives. Mathematical explanation is given <a href="#accuracy">here</a>. 
</li>
    <li>Since, we all are aware that there are pretty low chances that we end up getting a balanced dataset in the real-time scenarios.</li>
    <li>So to deal with class imbalance problems, we need a more fine grained way of looking at the way that our models predict onto positives and negatives or different classes.
</li>
</ul>

### Metrics
<ol>
    <li>Confusion Matrix</li>
    <li>FPR (Type-I Error)</li>
    <li>FNR (Type-II Error)</li>
    <li>RECALL (TPR, SENSITIVITY)</li>
    <li>PRECISION (+VE PREDICTION VALUE)</li>
    <li>ACCURACY</li>
    <li>F BETA</li>
    <li>ROC CURVE, AUC SCORE</li>
    <li>LOG LOSS</li>
</ol>

### Confusion Matrix
<ul>
    <li>
        <h4>Wikipedia Definition:</h4>
        In the field of machine learning and specifically the problem of statistical classification, a confusion matrix, also known as an error matrix,[7] is a specific table layout that allows visualization of the performance of an algorithm, typically a supervised learning one (in unsupervised learning it is usually called a matching matrix). Each row of the matrix represents the instances in a predicted class while each column represents the instances in an actual class (or vice versa)
    </li>
    <li>
        In short, confusion matrix is a which quantifies about all the possible outcomes of the model, in essence, the true positive, true negative, false postitive, and false negative. 
    </li>
</ul>
<div id="cm">
    <center><img src="/assets/images/classification-metrics/Confusion Matrix.png" alt="confusion matrix"></center>
</div>

### True Positive Rate (TPR)
<div id="tpr">
    <center>
        $$TPR = {TP \over TP + FN}$$
    </center>
</div>

### True Negative Rate (TNR)
<div id="tnr">
    <h3><b></b></h3>
    <center>
        $$TNR = {TN \over TN + FP}$$
    </center>
</div>

### False Positive Rate (FPR)
<div id="fpr">
    <h3><b></b></h3>
    <center>
        $$FPR = {FP \over FP + TN}$$
    </center>
</div>

### False Negative Rate (FNR)
<div id="fnr">
    <h3><b></b></h3>
    <center>
        $$FNR = {FN \over FN + TP}$$
    </center>
</div>


### RECALL (TPR, SENSITIVITY)
<div>
    <center>
        $$RECALL = {TP \over TP + FN}$$
    </center>
</div>

### PRECISION (+VE PREDICTION VALUES)
<div>
    <center>
        $$PRECISION = {TP \over TP + FP}$$
    </center>
</div>

### ACCURACY
<div>
    <center>
        $$ACCURACY = {TP + TN \over FN + TP + FP + TN}$$
    </center>
</div>

### F-BETA
<p>
    Unlike Precision and Recall, which is used for measuring the false positives and used for measuring the false negatives respectively, F-beta is used when we want to quantify both the false positives as well as false negatives. </p>
<p>
    The reason for naming it as F-beta is, the beta holds different values in 3 different scenarios.
    The general formuala for the F-beta is mentioned below. 
</p>  
<div>
    <center>
        $$F-\beta = {(1+\beta)^2 * PRECISION*RECALL \over \beta ^2 * PRECISION+RECALL}$$
    </center>
</div>
    <h4>Case - 1 :</h4>
    <p> When both the false positive and false negatives are important, substitute $$ \beta=1 $$
    This is commonly called as F-1 Score.</p>
<div>
    <center>
        $$F-1 Score = {2 * PRECISION*RECALL \over  PRECISION+RECALL}$$
    </center>
</div>
<div>
   <h4>Case - 2 :</h4>
    <p> When the false positive is important, substitute $$ \beta=0.5 $$ </p>
   <h4>Case - 3 :</h4>
    <p> When the false negative is important, substitute $$ \beta=2 $$  </p>
</div>


### ROC CURVE, AUC SCORE
<div>
</div>

### LOG LOSS
<div>
    <center>
        $$ Log Loss = { y * log(p) + (1-y) * log(1-p)}.$$
    </center>
</div>