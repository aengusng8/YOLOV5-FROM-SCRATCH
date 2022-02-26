First, run del_py_files.py to delete all .py file in the repository.
```bash
python del_py_files.py --folder ./
```

Second, reimplement every single line.

```python
# del_py_files.py
# change directory to yolov5 folder
# python del_py_files.py --folder ./

import os
import argparse

def parse_opt():
    parser = argparse.ArgumentParser()
    parser.add_argument('--folder', type=str)
    args = parser.parse_args()
    
    return args

def del_py_files(FOLDER_PATH):
    lst = os.listdir(f"{FOLDER_PATH}/")
    print(FOLDER_PATH)

    for obj in lst:
        print(obj)
        if os.path.isfile(f"{FOLDER_PATH}/{obj}"):
            if obj[-3:] == ".py" and obj != "del_py_files.py":
                os.remove(f"{FOLDER_PATH}/{obj}")
        else:
            del_py_files(f"{FOLDER_PATH}/{obj}")

def main(opt):
    del_py_files(opt.folder)

if __name__ == "__main__":
    opt = parse_opt()
    main(opt)
```
