# Datasets

## Elon Musk's tweets

A set of tweets from Elon Musk.

Download from: https://query.data.world/s/i63ntyye4lzdjb3sfeor4ex7labc5j

Source: https://data.world/adamhelsinger/elon-musk-tweets-until-4-6-17

```
import pandas as pd
df = pd.read_csv('https://query.data.world/s/i63ntyye4lzdjb3sfeor4ex7labc5j')
```

Also see (for more Twitter datasets): https://github.com/shaypal5/awesome-twitter-data

## British Library 19th century books

A set of 452 books (their first volume) from the British Library, (mostly from the) 19th century.

Source: https://data.bl.uk/digbks

The extra metadata with book type and genre information was kindly made available by Christin Hoene <C.Hoene@kent.ac.uk>.

### Contents

* [Sample dataset folder](bl_books/sample) with:
    - [Catalog metadata](bl_books/sample/book_data_sample.json)
    - [Enriched metadata](bl_books/sample/data/bl_books/sample/extra_metadatasample.csv)
    - [Fulltext files](bl_books/sample/full_texts)
* [Sample tidy dataset folder](bl_books/sample_tidy) this is the tidy version of the sample dataset. We create it as part of class 2.1. It includes:
    - [book dataframe](bl_books/sample_tidy/df_book.csv)
    - [book_text dataframe](bl_books/sample_tidy/df_book_text.csv)
    - [author dataframe](bl_books/sample_tidy/df_author.csv)
    - [author-book dataframe](bl_books/sample_tidy/df_author_book.csv)
* [Original metadata (compressed)](bl_books/book_metadata.zip) contains catalog metadata for every book in the full dataset.
* [Original enriched metadata (csv)](bl_books/data/bl_books/sample/extra_metadata_sample.csv) contains the enriched metadata for every book in the full dataset (amnd more).
* [Original enriched metadata (xls)](bl_books/data/bl_books/sample/extra_metadata_sample.xls) contains the enriched metadata for every book in the full dataset (amnd more).

### How we created the sample

We used the extra metadata file to pick books in English, and sample 120 books for each of the four categories provided there: prose, poetry, music and drama. We only picked the first volumes for books with more than one volume. Some of the books in the sample did not have an associated fulltext, hence we dropped them, resulting in 452 books/volumes.

More details are given in the [BL_sample notebook](bl_books/BL_sample.ipynb).

## Contracts of apprenticeship in early modern Venice

A set of contracts of apprenticeship from the records of the Archives of Venice. The contracts have been transcribed and then processed into a machine readable spreadsheet.

Download from: [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.2652855.svg)](https://doi.org/10.5281/zenodo.2652855)

Reference paper: https://www.researchgate.net/publication/318284139_Apprenticeship_in_Early_Modern_Venice.

To read more about these data, see the [project website](https://garzoni.hypotheses.org).

## Early African-American Film Database, 1909–1930

This project was created by UCLA students and faculty members to reconstruct and revive the history of early African-American silent race films.

This dataset contains information on films, actors, production companies, and other aspects of early silent-era African American race films. It is intended to allow the public to learn about this period in film history that is too rarely discussed.

Downloaded from: [![DOI](https://zenodo.org/badge/62099402.svg)](https://zenodo.org/badge/latestdoi/62099402)

Reference paper: https://openhumanitiesdata.metajnl.com/articles/10.5334/johd.7

To read more about these data, see the [project website](http://dhbasecamp.humanities.ucla.edu/afamfilm/).

## Crypto art transactions

A set of transactions of crypto artworks from the [SuperRare gallery](https://superrare.co), roughly from April 2018 to April 2019.

This dataset contains four networks in [GraphML format](http://graphml.graphdrawing.org):
* [Undirected sale network](crypto_art/undirSaleNet.graphml): An undirected network with information about how much total Ether (ETH) was exchanged between two users via sales.
* [Directed sale network](crypto_art/saleNet.graphml): Same as above but directed and with an edge (+ timestamp) for every indivual sale transaction. The graph is thus a multigraph.
* [Directed bid network](crypto_art/bidNet.graphml): Same as above but directed and with an edge (+ timestamp) for every indivual bid transaction. The graph is thus a multigraph. A bid may or may not be accepted and result in a sale.

*Hint: you might want to try Gephi, networkx or igraph to explore this dataset.*

### A guide to attributes

Node attributes (for users):
* *v_id*: unique id.
* *v_address*: blockchain id.
* *v_artist*: artist rating (see paper below).
* *v_authority*: HITS authority rating (see paper below).
* *v_sell*: value of sold items in ETH.
* *v_n_sell*: number of sold items.
* *v_collector*: collector rating (see paper below).
* *v_hub*: HITS hub rating (see paper below).
* *v_buy*: value of bought items in ETH.
* *v_n_buy*: number of bought items.

Edge attributes:
* *e_price*: price of the transaction in ETH. Note that in the undirected network, this is the sum of the prices of all transactions which occurred between two users.
* *e_timestamp*: time elapsed from the beginning of the year 1970 (Unix standard time) in hundredths of seconds. Thus, if you divide by 100 (recover seconds) times 3600 (seconds in an hour) times 24 (hours in a day) times 365 (days in a year), the integer part of the result will be the number of years to add to 1970 to know the year when the transaction took place.
* *e_artwork*: id of the exchanged artwork. An artwork can be exchanged multiple times.

Reference paper: https://arxiv.org/abs/1907.07758.

Also see the paper's data and code release: [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3344713.svg)](https://doi.org/10.5281/zenodo.3344713).

## Alto XML

The four alto XML files contained in `data/altoxml/` are part of the [ALTO XML reference samples collection](https://github.com/altoxml/reference_samples).
