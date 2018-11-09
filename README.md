# Morpheme Concepts (MCs)
This is a dataset of **Chinese Morpheme Embeddings**. We first constructed the rational knowledge of Chinese morphemes at Peking University. Then we extract this knowledge to design a template to create instances and proliferate instances based on similarity, as a source to train data for morpheme embeddings.

The work is published in AAAI 2019, entitled with "Implantin Rational Knowledge into Distributed Representation at Morpheme Level". This project maintains the dataset. Hope the data can be helpful for your research in the field of Chinese Information Processing. If you use the dataset, please cite this paper:

Zi Lin and Yang Liu. **Impanting Rational Knowledge into Distributed Representation at Morpheme Level**. The Thirty-Third AAAI Conference on Artificial Intelligence (AAAI), 2019.

## 296 & 500

`296.txt` and `500.txt` are `wordsim-296` and `PKU-500` respectively.

We extract the disyllabic words in the datasets and get a total of 141 words pairs and 232 word pairs in `wordsim-296` and `PKU-500` respectively. These serve as the test set for word similarity measurement.

Each column respectively denotes:

1. the 1st-morpheme of the first word
2. the 2nd-morpheme of the first word
3. the 1st-morpheme of the second word
4. the 2nd-morpheme of the second word
5. the first word
6. the word-formation of the first word
7. the second word
8. the word-formation of the second word
9. the similarity score by human judgment

wordsim-296 is from **SemEval-2012 task 4: evaluating Chinese word similarity**. [(Abstract)](https://www.cs.york.ac.uk/semeval-2012/task4.html) [(pdf)](http://dl.acm.org/citation.cfm?id=2387695)

PKU-500 is from **NLPCC-ICCPOL 2016 shared task: Chinese word similarity measurement**. [(Abstract)](https://link.springer.com/chapter/10.1007/978-3-319-50496-4_75)

## morpheme embeddings

`morpheme_vec.txt` is the embeddings of morphemes occurring in the datasets. The dimension is set to 20 and the window size 3.

## word embeddings

`word_vec.txt` is the embeddings of words occuring in the datasets, trained through CBOW models (word2vec). The dimension is set to 50 and the window size 5.

## Result
### Overall result
|      Model     | Wordsim-297 |   PKU-500   |
|  :-----------: | :---------: | :---------: |
|      CBOW      |    57.43    |    34.82    |
|    Skip-gram   |    62.17    |    40.19    |
|       MC       |    46.28    |    30.57    |
|    CBOW + MC   |    64.35    |    42.74    |
| Skip-gram + MC |  **67.58**  |  **45.91**  |

### wordsim-296
|   MC:CBOW   |    ρ × 100	  | MC:Skip-gram|    ρ × 100 	|
| :---------: |	 :---------:  | :---------: |  :---------:  |
| 0.00 : 1.00 | 57.4269336318 | 0.00 : 1.00 | 62.1710163699 |
| 0.05 : 0.95 | 58.3360089736 | 0.05 : 0.95 | 63.560852139  |
| 0.10 : 0.90 | 59.4124723344 | 0.10 : 0.90 | 65.0577136103 |
| 0.15 : 0.85 | 61.0934162145 | 0.15 : 0.85 | 66.3105564805 |
| 0.20 : 0.80 | 62.1759395522 | 0.20 : 0.80 | 67.6169122018 |
| 0.25 : 0.75 | 63.1733514855 | 0.25 : 0.75 | 68.0525068099 |
| 0.30 : 0.70 | 63.6350598707 | 0.30 : 0.70 | 67.6856227026 |
| 0.35 : 0.65 | 64.3510610523 | 0.35 : 0.65 | 67.5841623369 |
| 0.40 : 0.60 | 64.5469178777 | 0.40 : 0.60 | 66.8045871219 |
| 0.45 : 0.55 | 64.6015700674 | 0.45 : 0.55 | 66.1609345488 |
| 0.50 : 0.50 | 63.9703324757 | 0.50 : 0.50 | 64.5105982205 |
| 0.55 : 0.45 | 62.6545584925 | 0.55 : 0.45 | 62.9899770433 |
| 0.60 : 0.40 | 61.433823333  | 0.60 : 0.40 | 61.4644326838 |
| 0.65 : 0.35 | 60.2302122858 | 0.65 : 0.35 | 59.2701917369 |
| 0.70 : 0.30 | 58.071503872  | 0.70 : 0.30 | 57.5203215055 |
| 0.75 : 0.25 | 56.5834185082 | 0.75 : 0.25 | 55.2854107917 |
| 0.80 : 0.20 | 54.2551813821 | 0.80 : 0.20 | 53.2386512624 |
| 0.85 : 0.15 | 52.1382129921 | 0.85 : 0.15 | 51.2449764814 |
| 0.90 : 0.10 | 49.9531762555 | 0.90 : 0.10 | 49.5368462739 |
| 0.95 : 0.05 | 48.2172193655 | 0.95 : 0.05 | 47.7381723223 |
| 1.00 : 0.00 | 46.2832667294 | 1.00 : 0.00 | 46.2832667294 |

### PKU-500
|   MC:CBOW   |    ρ × 100	  | MC:Skip-gram|    ρ × 100 	|
| :---------: |	 :---------:  | :---------: |  :---------:  |
| 0.00 : 1.00 | 34.8244805623 | 0.00 : 1.00 | 40.1914939109 |
| 0.05 : 0.95 | 36.0420390854 | 0.05 : 0.95 | 41.1652043209 |
| 0.10 : 0.90 | 37.322986584  | 0.10 : 0.90 | 42.3635875588 |
| 0.15 : 0.85 | 38.8019825796 | 0.15 : 0.85 | 43.6010903009 |
| 0.20 : 0.80 | 39.790206614  | 0.20 : 0.80 | 44.3963600242 |
| 0.25 : 0.75 | 40.8113025658 | 0.25 : 0.75 | 45.0269337515 |
| 0.30 : 0.70 | 41.9601376357 | 0.30 : 0.70 | 45.5636975622 |
| 0.35 : 0.65 | 42.7420471352 | 0.35 : 0.65 | 45.9064978364 |
| 0.40 : 0.60 | 43.0004088728 | 0.40 : 0.60 | 45.6799987908 |
| 0.45 : 0.55 | 43.3234571614 | 0.45 : 0.55 | 45.1527024768 |
| 0.50 : 0.50 | 43.5534644672 | 0.50 : 0.50 | 44.4864694471 |
| 0.55 : 0.45 | 43.335856218  | 0.55 : 0.45 | 43.6387199959 |
| 0.60 : 0.40 | 42.5178548909 | 0.60 : 0.40 | 42.2482955558 |
| 0.65 : 0.35 | 41.3711343888 | 0.65 : 0.35 | 41.3174051436 |
| 0.70 : 0.30 | 40.2892926713 | 0.70 : 0.30 | 39.8494625705 |
| 0.75 : 0.25 | 39.0238199643 | 0.75 : 0.25 | 38.2420065815 |
| 0.80 : 0.20 | 37.4496684181 | 0.80 : 0.20 | 36.9782639755 |
| 0.85 : 0.15 | 35.9330907858 | 0.85 : 0.15 | 35.3969036754 |
| 0.90 : 0.10 | 34.2586895028 | 0.90 : 0.10 | 33.7358145578 |
| 0.95 : 0.05 | 32.560739624  | 0.95 : 0.05 | 32.3684100716 |
| 1.00 : 0.00 | 30.5697519851 | 1.00 : 0.00 | 30.5697519851 |
