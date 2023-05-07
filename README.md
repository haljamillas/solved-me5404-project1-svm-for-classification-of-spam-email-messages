Download Link: https://assignmentchef.com/product/solved-me5404-project1-svm-for-classification-of-spam-email-messages
<br>
This project is designed for the student to demonstrate (through independent learning):

<ol>

 <li>Competence in implementing SVMs, and</li>

 <li>Understanding of the principles and issues of SVM for classification.</li>

</ol>

<h1>II.    DATA</h1>

The data used in this project is the Spam Data Set<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>, which contains a total of 4,601 examples. Each example has a feature vector with 57 attributes that represent the selected key features of an email message, and a label indicating whether the associated email message is spam or not. (Detailed description of these attributes can be found on the source webpage of the dataset.) One feature vector is shown below for illustration:

0.00000 0.01043 0.00000 0.00000 0.00000 0.00000 0.00000 0.00000

0.00000 0.00000 0.01043 0.01043 0.02105 0.00000 0.00000 0.00000

0.00000 0.03166 0.06332 0.00000 0.02105 0.00000 0.00000 0.00000

0.00000 0.00000 0.00000 0.00000 0.00000 0.00000 0.00000 0.00000

0.00000 0.00000 0.00000 0.00000 0.00000 0.00000 0.00000 0.00000

0.00000 0.00000 0.00000 0.00000 0.00000 0.00000 0.00000 0.00000

0.00000 0.00000 0.00000 0.00196 0.00000 0.00000 0.02601 0.12811 0.98827

For this project, three sub-datasets, namely, the <em>training </em>set (with the filed name train.mat), the <em>test </em>set (test.mat), and the <em>evaluation </em>set (eval.mat), have been created from the Spam dataset. The training set and the test set contain 2,000 and 1,536 randomly selected examples, respectively. They are in the MATLAB MAT-file format and are included in the zipfile that also contains this document; the eval.mat file is not included, since this dataset will be used in the assessment as decribed in Section V below.

In these two MAT-files, the feature vectors are held in a variable with the name:

<em>&lt;</em>file_name_without_extension<em>&gt;</em>_data, while the labels (either “+1” for spam or “−1” for non-spam) associated with the individual feature vectors are held in a variable with the name: <em>&lt;</em>file_name_without_extension<em>&gt;</em>_label. Thus in train.mat, the two variables are <em>train_data </em>and <em>train_label</em>. Similarly, in test.mat the variables are <em>test_data </em>and <em>test_label</em>.

The third sub-dataset, namely, eval.mat, is formed using a subset of the remaining examples (after train.mat and test.mat have been chosen) in the Spam dataset. This third dataset will be used for the assessment of the program that you will submit, as described in Section

V.

<h1>III.    REQUIREMENT</h1>

<ol>

 <li><em> What to be done</em></li>

</ol>

The main tasks involved in this project are:

Task 1: Write a MATLAB (M-file) program to compute the discriminant function g(·), if one exists, for the following SVMs, using the training set provided: (i) A hard-margin<a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a> SVM with the linear kernel

K                             (1)

<ul>

 <li>A hard-margin SVM with a polynomial kernel</li>

</ul>

<em>p</em>

K(2) where the values of <em>p </em>are listed in Table 1.

<ul>

 <li>A soft-margin SVM with a polynomial kernel as given in Equation (2) above, and with the values for <em>p </em>and <em>C </em>as listed in Table 1.</li>

</ul>

Note that a MATLAB function quadprog (available in the Optimization Toolbox) can be used to solve constraint optimization problems.

Task 2: Write a MATLAB (M-file) program to implement the SVMs with the discriminant functions obtained in Task 1. Apply these SVMs to classify the given training set and test set, and report the classification results in Table 1 by filling the entries indicated by “?”. Discuss the results and their implications, including issues related to the admissibility of the kernels and the existence of optimal hyperplanes for the three types of SVMs listed in Task 1 above.

<table width="672">

 <tbody>

  <tr>

   <td width="672">PETER C. Y. CHEN, 2021                                                                                                                                                                                                                                                                                                         2

    <table width="585">

     <tbody>

      <tr>

       <td width="124">Type of SVM</td>

       <td width="58"> </td>

       <td colspan="2" width="115">Training accuracy</td>

       <td width="58"> </td>

       <td width="58"> </td>

       <td colspan="2" width="115">Test accuracy</td>

       <td width="58"> </td>

      </tr>

      <tr>

       <td width="124">Hard margin with Linear kernel</td>

       <td width="58"> </td>

       <td colspan="2" width="115">?</td>

       <td width="58"> </td>

       <td width="58"> </td>

       <td colspan="2" width="115">?</td>

       <td width="58"> </td>

      </tr>

      <tr>

       <td rowspan="2" width="124">Hard margin with polynomial kernel</td>

       <td width="58"><em>p</em>=2</td>

       <td width="58"><em>p</em>=3</td>

       <td width="58"><em>p</em>=4</td>

       <td width="58"><em>p</em>=5</td>

       <td width="58"><em>p</em>=2</td>

       <td width="58"><em>p</em>=3</td>

       <td width="58"><em>p</em>=4</td>

       <td width="58"><em>p</em>=5</td>

      </tr>

      <tr>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

      </tr>

      <tr>

       <td width="124">Soft margin with polynomial kernel</td>

       <td width="58"><em>C</em>=0<em>.</em>1</td>

       <td width="58"><em>C</em>=0<em>.</em>6</td>

       <td width="58"><em>C</em>=1<em>.</em>1</td>

       <td width="58"><em>C</em>=2<em>.</em>1</td>

       <td width="58"><em>C</em>=0<em>.</em>1</td>

       <td width="58"><em>C</em>=0<em>.</em>6</td>

       <td width="58"><em>C</em>=1<em>.</em>1</td>

       <td width="58"><em>C</em>=2<em>.</em>1</td>

      </tr>

      <tr>

       <td width="124"><em>p</em>=1</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

      </tr>

      <tr>

       <td width="124"><em>p</em>=2</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

      </tr>

      <tr>

       <td width="124"><em>p</em>=3</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

      </tr>

      <tr>

       <td width="124"><em>p</em>=4</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

      </tr>

      <tr>

       <td width="124"><em>p</em>=5</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

       <td width="58">?</td>

      </tr>

     </tbody>

    </table>TABLE I: Results of SVM classification.</td>

  </tr>

 </tbody>

</table>

Task 3: Design a SVM of your own. This SVM can be one of the three types specified in Task 1 above (i.e., hardmargin with linear kernel, hard-margin with polynomial kernel, and soft-margin with polynomial kernel), or one with your own choice of kernel. Using the given training set, compute the discriminant function g(·) of the SVM. Implement the resulting SVM in a MATLAB M-file program. This program will be used to classify the evaluation set as part of the assessment discussed in Section V.

<ol>

 <li><em> What to submit</em></li>

 <li>A report (in a PDF file) describing the implementation and the results. It must contain a cover page showing:

  <ul>

   <li><em>student’s name,</em></li>

   <li><em>student number,</em></li>

   <li><em>student’s email address, </em>(iv) <em>name of module, and</em></li>

  </ul></li>

</ol>

(v) <em>project title.</em>

The report should be in PDF format and <u>no more </u>than ten pages (excluding the cover page). The name of the PDF file must be in the format:

StudentNumber_SVM.pdf

<ol start="2">

 <li>The M-file programs as specified in the description of Task 1, Task 2, and Task 3 in Section III-A above.</li>

 <li><em> How to submit</em></li>

</ol>

Only softcopy of the report (in PDF) and the MATLAB M-file programs are to be submitted. Please put the report and the M-file programs in a folder. Use your student number as the folder name. Generate a nonpassword-protected zipfile of this folder and upload this zipfile to LumiNUS at:




Note: Make sure to upload your report into the correct folder as specified above.

<h1>IV.   DEMO SESSION</h1>

A demo session will be conducted by the teaching assistant on the use of MATLAB for implementing the required SVMs. Please check the lecture slides about this demo.

<h1>V.  ASSESSMENT</h1>

The project will be assessed based on the following criteria:

<ol>

 <li><em>Discussion </em>(with supporting argument) on the results of classifications reported in Table 1.</li>

 <li><em>Presentation</em>. This includes good report style, clarity, and conciseness.</li>

 <li><em>Performance of your SVM M-file program for </em>Task 3 <em>(as described in Section III-A) in classifying the evaluation set </em>mat<em>. </em>Your M-file program must be workable in MATLAB under the Windows environment. During the assessment, eval.mat is first loaded into MATLAB, and your M-file program will then be run in MATLAB. Thus, before your M-file is loaded into MATLAB, the MATLAB workspace will have the variable “eval_data” that holds a 57× 600 matrix, in which each column represents one feature vector. Your M-file program must be able to process these 600 features vectors and generate (as output) a vector with the name eval_predicted, whose <em>n</em><sup>th </sup>element is the computed label of the <em>n</em><sup>th </sup>feature vector (i.e., the <em>n</em><sup>th </sup>column) in eval_data. When writing your M-file program, you can test its execution on your own by making up an eval.mat file containing dummy sample values.</li>

</ol>

<a href="#_ftnref1" name="_ftn1">[1]</a> http://archive.ics.uci.edu/ml/datasets/spambase.

<a href="#_ftnref2" name="_ftn2">[2]</a> From an implementation perspective, a hard-margin SVM can be approximated by a soft-margin SVM with a very large C value.