# Combine Stack Overflow Mining
Stack Overflow mining results used for the following paper during the 37th Brazilian Symposium on Software Engineering (SBES) for the Track Insightful Ideas and Emerging Results (IIER).:
> Reactive Programming with Swift Combine: An Analysis of Problems Faced by Developers on Stack Overflow.

## Data
Under the folders in `/data-explorer`, data either genereated by or collected for the mining and LDA execution can be found. The table gives a brief description of each folder:

| Folder   | Description         |
| :------------- |:-------------|
| consolidated-source | Contains posts collected from Stack Exchange Data Explorer |
| lda-results | Contains the results of the last LDA execution |
| result-processing | Contains data presented in the Result section |

The file `stopwords.txt` contains a list of stop words used during preprocessing.

### LDA results
The results for the last LDA (Latent Dirichlet Allocation) are available under `/data-explorer/lda-results/2023-01-03 21-25-53/`. As detailed in the paper, the execution with the following settings generated the most coherent results:
| Parameter     | Value         |
| :------------- |:-------------:|
| Topics         | 14 |
| HyperParameters | &alpha;=&beta;=0.01 |
| Iterations | 1,000 |

Each result is comprised of three CSV files following the bellow file name pattern:
* **all_withAnswers\_doctopicdist\__[#topics]_\_Body.csv** - contains the posts' ids and their distribution of topics+proportion, including the dominant topic and its proportion in a separate column for easy retrieval;
* **all_withAnswers\_topicdist\__[#topics]_\_Body.csv** - the topic distribution along with their words+proportion descendingly sorted by word proportion;
* **all_withAnswers\_topicdist\__[#topics]_\_Body - topwords.csv** - (extra) the same as the above one but presenting the topics only with their top words to facilitate the open card sorting technique.

Where:
* _[#topics]_: number of topics for that specific execution;

## Other Useful Information
### Stack Overflow Removed Terms
As defined in the preprocessing phase in the paper, some terms commonly found in the Stack Overflow posts were removed from the corpus. Those include:
> `differ`, `specif`, `deal`, `prefer`, `easili`, `easier`, `mind`, `current`, `solv`, `proper`, `modifi`, `explain`, `hope`, `help`, `wonder`, `altern`, `sens`, `entir`, `ps`, `solut`, `achiev`, `approach`, `answer`, `requir`, `lot`, `feel`, `pretti`, `easi`, `goal`, `think`, `complex`, `eleg`, `improv`, `look`, `complic`, `day`, `chang`, `issu`, `add`, `edit`, `remov`, `custom`, `suggest`, `comment`, `ad`, `refer`, `stackblitz`, `link`, `mention`, `detect`, `face`, `fix`, `attach`, `perfect`, `mark`, `reason`, `suppos`, `notic`, `snippet`, `demo`, `line`, `piec`, `appear`

### Topic-Label Mapping
| Topic #      | Label/Name    |
| ------------ |:-------------|
| 0 | Displaying Data From Collections |
| 1 | Operators for Stream Manipulation |
| 2 | ViewModel in SwiftUI |
| 3 | REST API Calls |
| 4 | Data Binding and View Updating |
| 5 | Introductory Combine |
| 6 | Stream Composition |
| 7 | Concurrency |
| 8 | UI and User Interaction |
| 9 | Software Development |
| 10 | Publishing Data |
| 11 | Stream Lifecycle |
| 12 | Data Typing |
| 13 | Bugs and Error Handling |
