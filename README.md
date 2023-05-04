Download Link: https://assignmentchef.com/product/solved-csci544-homework-2-simple-lemmatizer
<br>
In this assignment you will write a very , which learns a lemmatization function from an annotated corpus. The function is so basic I wouldn’t even consider it machine learning: it’s basically just a big lookup table, which maps every word form attested in the training data to the most common lemma associated with that form. At test time, the program checks if a form is in the lookup table, and if so, it gives the associated lemma; if the form is not in the lookup table, it gives the form itself as the lemma (identity mapping).

The program performs training and testing in one run: it reads the training data, learns the lookup table and keeps it in memory, then reads the test data, runs the testing, and reports the results. The program output is in a fixed format, reporting 15 counters and 5 performance measures. The assignment will be graded based on the correctness of these measures.

<h1>Data</h1>

A set of training and test data is available as a compressed ZIP archive on <a href="http://blackboard.usc.edu/">Blackboard</a><a href="http://blackboard.usc.edu/">.</a> The uncompressed archive contains the following files:

Three corpus files in universal dependencies format, with the file names indicating whether the file is for development, training, or testing (only the training and testing files will be used in the exercise).

Additional readme and license files, which will not be used for the exercise.

The submission script will learn the model from the training data, test it on the test data, output the results, and compare them to the known solution. The grading script will do the same, but on training and test data from a different language.

<h1>Program</h1>

You will write a program called lookup-lemmatizer.py in Python 3 (Python 2 has been deprecated), which will take the paths to the training and test data files as command-line arguments. Your program will be invoked in the following way:

&gt; python lookup-lemmatizer.py /path/to/train/data /path/to/test/data

The program will read the training data, learn a lookup table, run the lemmatizer on the test data, and write its report to a file called lookup-output.txt. The report has a fixed format of 22 lines which looks as follows:

Training statistics

Wordform types: 16879

Wordform tokens: 281057

Unambiguous types: 16465

Unambiguous tokens: 196204

Ambiguous types: 414

Ambiguous tokens: 84853

Ambiguous most common tokens: 75667

Identity tokens: 201485

Expected lookup accuracy: 0.967316238343

Expected identity accuracy: 0.716883052192

Test results

Total test items: 35430

Found in lookup table: 33849

Lookup match: 32596

Lookup mismatch: 1253

Not found in lookup table: 1581

Identity match: 1227

Identity mismatch: 354

Lookup accuracy: 0.962982658276

Identity accuracy: 0.776091081594

Overall accuracy: 0.954642957945

The numbers above are a correct output when running the program on the supplied data (the submission script). There is some variability possible in the output; see <u>note</u> below. The numbers will be different when the program is run on the data used by the grading script.

Starter code is available on <a href="http://blackboard.usc.edu/">Blackboard</a><a href="http://blackboard.usc.edu/">,</a> which already reads the input and formats the output correctly. You are strongly encouraged to use this starter code; you will need to write the code that performs the counts and calculates the results correctly.