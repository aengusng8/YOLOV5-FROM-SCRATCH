First, run del_py_files.py to delete all .py file in the repository.
Second, reimplement every single line.

```python
# del_py_files.py
import os
import argparse

parser = argparse.ArgumentParser()
parser.add_argument('--folder', type=str)

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

args = parser.parse_args()
del_py_files(args.folder)

```
