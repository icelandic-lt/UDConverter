# UDConverter - Treebank format converter

![Version](https://img.shields.io/badge/Version-1.1|22.01-darkviolet)
![Python](https://img.shields.io/badge/python-3.9-blue?logo=python&logoColor=white)
![Python](https://img.shields.io/badge/python-3.10-blue?logo=python&logoColor=white)
![CI Status](https://img.shields.io/badge/CI-[unavailable]-red)
![Docker](https://img.shields.io/badge/Docker-[unavailable]-red)

UDConverter is a tool for converting constituency treebanks in the format of PPCHE (Penn Parsed Corpora of Historical English) to dependency treebanks following the Universal Dependencies framework. The tool is specifically configured to convert treebanks in the IcePaHC format.

## Overview
- **Language:** Python
- **Language Version/Dialect:**
  - Python: 3.9, 3.10
- **Category:** [Support Tools](https://github.com/icelandic-lt/icelandic-lt/blob/main/doc/st.md)]
- **Domain:** Generic
- **Status:** Stable
- **Origins:** [UDConverter 22.01](http://hdl.handle.net/20.500.12537/169) and [Github](https://github.com/thorunna/UDConverter).

## Description

A Python module for converting bracket-parsed [PPCHE-format](https://www.ling.upenn.edu/hist-corpora/) treebanks to the [Universal Dependencies](https://universaldependencies.org/) framework. It is heavily based on existing [NLTK](https://www.nltk.org/) packages.

The module is specifically configured to convert treebanks in the [IcePaHC](https://linguist.is/icelandic_treebank/Icelandic_Parsed_Historical_Corpus_(IcePaHC)) format, which is based on PPCME.

The converter has been used to create two Icelandic UD treebanks: [UD_Icelandic-IcePaHC](https://github.com/UniversalDependencies/UD_Icelandic-IcePaHC/tree/master) and [UD_Icelandic-Modern](https://github.com/UniversalDependencies/UD_Icelandic-Modern/tree/master), and one Faroese: [UD_Faroese-FarPaHC](https://github.com/UniversalDependencies/UD_Faroese-FarPaHC/tree/master).

Version 1.1 has an 82.87 LAS.

## Installation

Install all requirements by running: 

``` shell
python3 -m venv .venv && . .venv/bin/activate # optionally create and activate a virtual environment
pip install -r requirements.txt
```

## Usage

Scripts to run are in the `scripts` folder.

_In all examples below, the_ `--output` _flag is used to write to files in the_ `/CoNLLU/` _output folder. Otherwise prints to standard output._

*Convert single file or directory of files:*

> `convert.py -N -i path/to/corpus/file.psd --output --post_process`

> `convert.py -N -i path/to/corpus/* --output --post_process`

_For further usage, input files must be placed in a folder within the_ `corpora` _folde:r_

*Convert single tree in treebank using sentence ID (only prints to standard output):*

> `convert.py -C FOLDER_NAME -id SENTENCE_ID`

*Convert single file in treebank*

> `convert.py -C FOLDER_NAME -f FILE_NAME --output --post_process`

_Additionally included is a script to only convert the IcePaHC corpus (_ `icepahc-v0.9`_), with pre- and post-processing:_

> `convert_icepahc.py`

## License

Copyright 2022 The Árni Magnússon Institue for Icelandic Studies

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

## Acknowledgements
This converter is part of the UniTree project for IcePaHC, funded by The Strategic Research and Development Programme for Language Technology, grant no. 180020-5301. Thanks are due to Örvar Kárason, whose previous work was used as a basis for the conversion.

This converter was improved as part of the Language Technology Programme for Icelandic 2019-2023. The programme, which is managed and coordinated by Almannarómur (https://almannaromur.is/), is funded by the Icelandic Ministry of Education, Science and Culture.
