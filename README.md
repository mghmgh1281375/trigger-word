# trigger-word
ضبط‌کن

# Instruction for old dataset
1. Cloning repository
  ```bash
  user@PC:~$ git clone https://github.com/mghmgh1281375/trigger-word.git
  ```
2. Concatenating zip chunks
  ```bash
  user@PC:~$ cat trigger-word/ZIPCHUNKS* > raw_data.zip
  ```
3. Extracting files
  ```bash
  user@PC:~$ unzip raw_data.zip
  ```
-----

# Instruction for new dataset
1. Cloning repository
  ```bash
  user@PC:~$ git clone https://github.com/mghmgh1281375/trigger-word.git
  ```
2. Concatenating tar chunks
  ```bash
  user@PC:~$ cat trigger-word/TARCHUNKS* > raw_data.tar.xz
  ```
3. Extracting files
  ```bash
  user@PC:~$ tar -xf raw_data.tar.xz
  ```
4. Converting M4A files to WAV
  ```bash
  user@PC:~$ for file in $(ls raw_data/Background/*.m4a);do ffmpeg -i raw_data/$file $file.wav; done
  ```
5. Removing broken files
  ```python
  >>> import os
  >>> black_list=("65-002.wav", "65-004.wav", "65-007.wav",  "66-011.wav", "67-006.wav")
  >>> for file in black_list:
  >>>   os.remove(os.path.join('raw_data', 'Background', file))
  ```
