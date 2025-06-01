# Dataset of RKTS texts in individual files

This is a dataset of all RKTS data, as pulled from their GitHub repo. However,
each Buddhist text has been split into its own file.

The file names are in the form "D103.txt", meaning that this file is from the
"D" corpus (Derge Kanjur) with standard reference ID "D103".

Each file has lines in the following format:

```txt
MW22084|dkon brtsegs, ca|266b6|chen gyi lo ts+tsha ba ban de ye shes sde la sogs pas bsgyur cing zhus te gtan la phab pa  //  //  'phags pa dkon mchog brtsegs pa chen po'i chos kyi rnam grangs le'u stong phrag brgya pa las le'u sum cu rtsa lnga pa ste  /   sangs rgyas kyi yul
MW22084|dkon brtsegs, ca|266b7|bsam gyis mi khyab pa lung bstan pa  /   bam po dang po  //  rgya gar skad du  /   Ar+ya a tsin t+ya bud d+ha bi Sha ya ni ra de sha nA ma ma hA yA na sU tra  /   bod skad du  /   'phags pa sangs rgyas kyi yul bsam gyis mi khyab pa bstan pa zhes bya ba theg
MW22084|dkon brtsegs, ca|267a1|pa chen po'i mdo  /   sangs rgyas dang byang chub sems dpa' thams cad la phyag 'tshal lo  //  'di skad bdag gis thos pa dus gcig na  /   bcom ldan 'das mnyan yod na rgyal bu rgyal byed kyi tshal mgon med zas sbyin gyi
```

Each line has 4 fields:

* The "set" identifier (representing a physical collection somewhere, like a library, e.g. "MW22084" above)
* The volume name within that set (e.g. "dkon brtsegs, ca" above)
* The folio page and line identifier for the line of text (e.g. 266b6 above)
* The actual text of the line (e.g. the data "chen gyi lo ts+tsha....")

Note that sequences of multiple whitespace characters are not important, they are
an artifact of my cleaning process (i.e. I just didn't clean them into single
spaces).

## File storage

The file has been tar'd and compressed with `zstd`. My exact command line was:

```sh
tar -cf - . | zstd -19 --ultra -o ../my_archive.tar.zst
```

The archive should have a much better name. Not sure what yet.
