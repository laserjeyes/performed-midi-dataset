Performed MIDI Dataset



---
#### curation procedure

...



---
#### objectives

build a dataset containing
- score files 
- MIDI performances
- down-beat / beat annotation (dates in performance)


usage:
- usage:
  - evaluation of symbolic  beat tracking procedure
    ground truth = annotations of positions of bars (in MIDI perfo)
  
  - evaluation of transcription
    bar-by-bar transcription taking the bar positions in input
  
    ground truth = scores 
  
   

---
#### source Dataset
the dataset is build by curation of the following dataset by Jeong et al.
(manual cleaning of the beat mark annotations)

- this dataset is used for the evalution of `VirtuosoNet` 
  https://github.com/jdasam/virtuosoNet
- the dataset is not public
- solo piano music, polyphonic, symbolic (MIDI + annote)

refs:
> Graph Neural Network for Music Score Data and Modeling Expressive Piano Performance
> Dasaem Jeong, Taegyun Kwon, Yoojin Kim, Juhan Nam 
> Proceedings of the 36th International Conference on Machine Learning, PMLR 97:3060-3070, 2019.
> http://proceedings.mlr.press/v97/jeong19a.html

> VirtuosoNet: A Hierarchical Attention RNN for Generating Expressive Piano Performance from Music Score
> Dasaem Jeong, Taegyun Kwon, Juhan Nam
> NIPS 2018
> https://github.com/jdasam/virtuosoNet

> VirtuosoNet: A Hierarchical RNN-based System for Modeling Expressive Piano Performance  
> Dasaem Jeong; Taegyun Kwon; Yoojin Kim; Kyogu Lee; Juhan Nam
> ISMIR 2019
> http://archives.ismir.net/ismir2019/paper/000112.pdf

for each opus:
- MIDI performance
  from Yamaha competition
- musicXML score
  from musescore
- MIDI quantified (MIDI score)
  obtained from musicXML with Musescore
- alignement (txt file) 
  obtained from the 2 MIDI files with following Nakamura algo.
  = ground truth?
  
> Performance Error Detection and Post-Processing for Fast and Accurate Symbolic Music Alignment  
> Eita Nakamura, Kazuyoshi Yoshii, Haruhiro Katayose
> ISMIR 2017
> https://eita-nakamura.github.io/articles/EN_etal_ErrorDetectionAndRealignment_ISMIR2017.pdf

---
#### dataset content and procedure

available at:  
https://github.com/fosfrancesco/performed-midi-dataset

You can test with every piece of one of the following authors:
- Bach
- Balakirev
- Beethoven
- Chopin
- Brahms
- Chopin
- Debussy
- Glinka
- Haydn
- Liszt
- Mozart
- Prokofiev
- Rachmaninoff
- Ravel
- Schubert
- Schumann
- Scriabin

The procedure is:
- Choose a Folder from the dataset (from authors above)
- Open Audacity https://www.audacityteam.org/
- File -> Import ->MIDI file: `midi_cleaned.mid`
- File -> Import ->Labels: `ann_quant.txt`
- File -> Import ->Audio: `quant_click.wav`
- Labels are annotated as `b` beat or `db` downbeat
- Labels that were automatically detected to have some problems are annotated with `W` after the name.

To export labels: File -> Export -> Labels : `ann_quant_cleaned.txt`

Test it, but don't work on it yet, because I need to figure out why it doesn't work for some authors.
Test it, but don't work on it yet, because I need to figure out why it doesn't work for some authors.
