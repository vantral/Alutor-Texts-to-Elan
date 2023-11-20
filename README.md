# Alutor Texts

The repository is organized into the following sections:

- `eafs` directory contains Elan files that have been automatically converted.
  - `.eaf` files have the following tiers: `tx` (text), `tr` (translation), `comm` (comment),  `pr` (problems)
- `texts` directory holds the initial docx files.
- `converter.ipynb` file contains code for the conversion process.
- `eaf_template.eaf` is a Jinja template designed for the automatic generation of eaf files.


## Alignment Instructions

Automatic identification of borders may not be entirely accurate. The primary objective is to align all borders to correspond with the beginnings and endings of the respective utterances.

### Collaborative Work

To align borders, follow these steps:

1. Clone this repository using either pure `git clone LINK_TO_REPOSITORY` or third-party software.
2. Choose a text to align, download its audio from the Yandex Disk folder ALUTOR-SOUND or from [this](https://drive.google.com/drive/folders/1_VDNNI8Zg0p9qmHScX2GQKPo2f_Cx8DO?usp=sharing), and place it in the `eafs` directory alongside the corresponding `.eaf` file.
3. Open the `.eaf` file and make necessary edits.
4. Stage changes for commit using `git add .`. Perhaps, in a third-party app, there is no this step.
5. Commit the changes using `git commit -m "SOME COMMIT MESSAGE"` or `pull` function of a third-party app.
6. Pull any changes made by other collaborators since your last pull using `git pull` or the `pull` button if you are using a third-party app.
7. Push your changes to the remote repository using `git push` or the `push` button if you are using a third-party app.

### Automatic Annotation Process

Within the tier labeled `problems`, various issues have been identified and documented.

The annotator provided annotations for utterances, translations (if applicable), time of the end of the utterance, and comments on a speaker.

However, these four components—utterance, translation, time, and comment—differ in their consistency across the annotations.
While utterances are consistently present, translations may be absent (particularly for utterances in Russian). Timecodes for some utterances might also be missing, and comments are sporadically recorded.

### Identification of Language Parts

* The algorithm attempts to identify two language parts: Russian and Alutor.
* There are instances where only one part is identified, and conversely, there are cases where more than two parts are identified.
* These scenarios are appropriately tagged as `ONE PART` and `MORE THAN TWO PARTS`, respectively.
* Occasionally, there are titles present in the initial file that are not intended to be included in the `eaf` file.


### Timecode estimation

* Timecodes for utterance starting points are automatically estimated by the algorithm.
* It is crucial to correct these automatically estimated timecodes.
* Additionally, timecodes for utterance endings are sometimes missing. In such cases, the utterances are positioned between utterances with known timecodes.
* Instances of missing utterance endings are marked with the `TIME` tag within the `pr` tier.

**It is important to acknowledge that both the algorithm and the annotator are susceptible to making mistakes at any stage of the annotation process.**