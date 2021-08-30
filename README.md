# tdmelodic_openjtalk
This repository provides an openjtalk-style format of [tdmelodic](https://github.com/PKSHATechnology-Research/tdmelodic), an accent dictionary of Japanese that is robust to many neologisms. 

## tdmelodic and openjtalk
- [tdmelodic](https://github.com/PKSHATechnology-Research/tdmelodic): an opensource accent dictionary Japanese that estimates the accent of the words listed in [NEologd](https://github.com/neologd/mecab-ipadic-neologd) dictionary by a machine learning-based technique.
- [openjtalk](http://open-jtalk.sp.nitech.ac.jp/): an opensource Japanese text-to-speech (TTS) engine that includes TTS front-end, e.g., full-context labels generation. Its Python wrapper [pyopenjtalk](https://github.com/r9y9/pyopenjtalk) is used in [ESPnet](https://github.com/espnet/espnet).

## Install
You can install this dictionary by adding it to the pre-stored dictionaries. 

### for openjtalk (C++)
1. Download `tdmelodic_openjtalk.csv`
2. Download openjtalk from http://open-jtalk.sp.nitech.ac.jp/.
3. Unzip the downloaded zip file and move to the directory.
3. concatenate `tdmelodic_openjtalk.csv` to `mecab-naist-jdic/*.csv`, e.g., 
 ```
 $ cp mecab-naist-jdic/unidic-csj.csv mecab-naist-jdic/unidic-csj_org.csv 
 $ cat tdmelodic_openjtalk.csv mecab-naist-jdic/unidic-csj_org.csv > mecab-naist-jdic/unidic-csj.csv
 ```
4. Compile the source code of openjtalk.

### for [pyopenjtalk](https://github.com/r9y9/pyopenjtalk) (Python)
 Someone, tell me the way.
 ```
 # clone pyopenjtalk to your pc
 $ git clone https://github.com/r9y9/pyopenjtalk.git
 $ cd pyopenjtalk
 # clone submodules
 $ git submodule init
 $ git submodule update
 # next append the dic file
 $ cp lib/open_jtalk/src/mecab-naist-jdic/naist-jdic.csv lib/open_jtalk/src/mecab-naist-jdic/naist-jdic_org.csv
 $ cat this-repo/tdmelodic_openjtalk.csv lib/open_jtalk/src/mecab-naist-jdic/naist-jdic_org.csv > lib/open_jtalk/src/mecab-naist-jdic/naist-jdic.csv
 # finally install modified pyopenjtalk
 $ python setup.py install
 ```

## Author
- [Shinnosuke Takamichi](https://sites.google.com/site/shinnosuketakamichi/home) (Univ. of Tokyo, Japan)
- [Junya Koguchi](http://www.isc.meiji.ac.jp/~mmorise/lab/) (Meiji Univ., Japan)

## License 
- Non-commercial purpose (research purpose) only




