metafast
========

***MetaFast*** (METAgenome FAST analysis toolkit) is a toolkit for calculating a number of statistics 
of metagenome sequences and building the distance matrix between them.

Authors:
* **Software:** *Sergey Kazakov* and *Vladimir Ulyantsev*, ITMO University, Saint-Petersburg.
* **Testing:** *Veronika Dubinkina* and *Alexandr Tyakht*, SRI of Physical-Chemical Medicine, Moscow.
* **Idea, supervisor:** *Dmitry Alexeev*, SRI of Physical-Chemical Medicine, Moscow.


### Installation

The last stable release can be downloaded from <http://github.com/ctlab/metafast/releases>.

To run ***metafast*** *JRE* 1.6 or higher is requered. Only one metafast script (`metafast.sh`, `metafast.bat` or `metafast.jar`) is requered to run ***metafast***.

* For *Linux* and *Mac OS*: download `metafast.sh`, run the command `chmod a+x metafast.sh`, then run `./metafast.sh` from the command line.<br/>
* For *Windows*: download `metafast.bat` and run it from the command line.
* For other OS: download `metafast.jar` and run it via command `java -jar metafast.jar`.

If you would like to build the last version of ***metafast*** from the repository (and check the version stamp):
~~~
git clone https://github.com/ctlab/metafast.git
cd metafast 
ant
./out/metafast.sh --version
~~~


### Example

Download [tinytest_A.fastq](http://github.com/ctlab/metafast/raw/master/test_data/tinytest_A.fastq) and [tinytest_B.fastq](https://github.com/ctlab/metafast/raw/master/test_data/tinytest_B.fastq) and run the command:
~~~
./metafast.sh -k 7 -b 0 -l 8 -b1 3 -i tinytest_A.fastq tinytest_B.fastq
~~~

After it has finished, a distance matrix can be found in `workDir/matrices/dist_matrix_<date>_<time>.txt`:
~~~
#	tinytest_A.vec	tinytest_B.vec
tinytest_A.vec	0.0	0.09090909090909091
tinytest_B.vec	0.09090909090909091	0.0
~~~

The element `matrix[i][j]` is a distance between *sample i* and *sample j*.

K-mers frequency statistics is saved in `workDir/kmer-counter-many/stats/<in-file>.stat.txt`.


### Full documentation

To see the full documentation visit <http://github.com/ctlab/metafast/wiki>.


### See also

* [khmer](https://github.com/ged-lab/khmer) - a toolkit to split reads.
* [crAss](http://edwards.sdsu.edu/crass/) - Cross-Assembly of Metagenomes.
* [MaryGold](http://sourceforge.net/projects/metavar/) - Variation analysis of metagenomic samples.

