Download Link: https://assignmentchef.com/product/solved-ai-homework2-random-forests
<br>
The objective of this assignment is for you to experiment with supervised learning using <strong>random forests</strong>. We will focus on the <strong>classification</strong> task. The following explains what you need to implement.

You need to first implement a decision tree. Your implementation will include the <strong>induction</strong> part (for building the tree from the training data) and the <strong>inference</strong> part (for classifying new samples). We will use only datasets with <strong>real-valued attributes</strong>. Use <strong>CART</strong> as the base tree, which is a binary tree. No pruning is required.

When attempting to split a node, you need to select an attribute as well as a <strong>threshold</strong>. The process:

<ul>

 <li>To select a threshold for a given attribute:

  <ul>

   <li>Let the values of the given attribute be <em>v</em><sub>1</sub>, <em>v</em><sub>2</sub>, …, <em>v</em><sub>n</sub>, where <em>n</em> is the number of samples associated with the node.</li>

   <li>For threshold selection, the easiest way is to have the values sorted such that <em>v</em><sub>1</sub> &lt; <em>v</em><sub>2</sub> &lt; … &lt; <em>v<sub>n</sub></em>. Now you only need to test the following threshold values (<em>v</em><sub>1</sub>+<em>v</em><sub>2</sub>)/2, (<em>v</em><sub>2</sub>+<em>v</em><sub>3</sub>)/2, …, (<em>v<sub>n</sub></em><sub>-1</sub>+<em>v<sub>n</sub></em>)/2.</li>

   <li>For each possible threshold, divide the <em>n</em> samples into two groups according to the threshold.</li>

   <li>For each group, compute its Gini’s impurity (here the summation is over the output classes):</li>

  </ul></li>

</ul>

<em>G</em>1<em>p<sub>k</sub></em><sup>2 </sup>         <em><sup>k </sup></em>

<ul>

 <li>For each threshold, compute the total remaining impurity as <em>n<sub>A</sub>G<sub>A</sub>+n<sub>B</sub>G<sub>B</sub></em>. Here <em>A</em> and <em>B</em> indicate the two group of samples. Select the one threshold with the lowest total impurity. This is the threshold for that attribute.</li>

</ul>

<ul>

 <li>Repeat the above for all the attributes (only those considered when splitting the current node; see <strong>attribute bagging</strong>), and select the one with the lowest total remaining impurity for splitting the node.</li>

</ul>

The next task is to build a forest. For this, you need to implement <strong>tree bagging</strong> (bagging of samples) and <strong>attribute bagging</strong>.

You need to do some experiments with your trees/forest. Three datasets are provided (as text files) for you to test with. In addition, you can check out the <strong>UCI Machine Learning Repository</strong> for other datasets. (There are numerous datasets there.)

You need to divide a dataset into a <strong>training subset</strong> (for tree induction) and a <strong>validation subset</strong> (for evaluation). Be sure to do the division randomly. You can also try cross-validation, but this is not required. Report the <strong>correct classification rates</strong> for both the training and validation subsets.

Go to the <u>UCI Machine Learning Repository</u> to get datasets for your experiments. To start, choose from the following datasets that have been used a lot in the literature: <u>Iris</u>, <u>Breast Cancer</u>, <u>Glass</u>, <u>Ionosphere</u>, <u>Optical</u> <u>Recognition of Handwritten Digits</u>, and <u>Wine</u>. You are not required to use all of them. You can go through the list of hundreds of datasets to find others to play with. In addition, I will also provide two two-attribute two-class datasets, <u>ellipse.txt</u> and <u>cross.txt</u>. These two are useful for visualizing the decision boundaries.

Regarding the experiments, below are a few things you can try. You are not required to try them all.

<ul>

 <li>Relative sizes of the training and validation subsets.</li>

 <li>Number of trees in the forest.</li>

 <li>Parameters used during tree induction, such as how many attributes to consider at each node splitting.</li>

 <li>Methods that limit a tree’s size. Examples include the minimum number of samples per node, or an upper bound on the tree’s depth.</li>

 <li>Comparisons of out-of-bag errors and validation-set errors.</li>

 <li><strong>Extremely random forest</strong>: At each node splitting, just randomly select an attribute.</li>

 <li></li>

</ul>