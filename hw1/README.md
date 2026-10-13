# Homework1
## task2
- mkdir hw1
- cd hw1
- nano complement.py
```
#!/usr/bin/env python3

import argparse

def reverse_complement(seq):
    comp = {'A': 'T', 'T': 'A', 'G': 'C', 'C': 'G',
            'a': 't', 't': 'a', 'g': 'c', 'c': 'g'}
    return ''.join(comp.get(base, base) for base in reversed(seq))

def gc_content(seq):
    seq = seq.upper()
    if not seq:
        return 0.0
    return (seq.count('G') + seq.count('C')) / len(seq)

def main():
    parser = argparse.ArgumentParser()
    parser.add_argument('--seq', required=True, help='DNA sequence')
    args = parser.parse_args()

    print(reverse_complement(args.seq))
    print(f"{gc_content(args.seq):.3f}")

if __name__ == "__main__":
    main() 
```
- делаем файл исполняемым ```chmod +x complement.py```
- делаем первый коммит ```git add ./complement.py``` ```
git commit -m "hw1: add complement.py with basic functionality"```
- делаем второй коммит ```git add ./README.md``` ```git commit -m "hw1: add README with description"```
- ``` git push  ```
## task3
- делаю скрипт _count_kmers.py_
- ``` git add ./count_kmers.py```
- ``` git commit -m "add count_kmers.py" ```
- ``` git push origin main ```
- сделал исправления на github
- переделал код локально и закоммитил ```add --k and --out parameters```
- столкнулся с конфликтом при ```git push```
- ```git pull --no-rebase origin main```
- исправил конфликт, выбрав нужный код, обернутый в `<<<<<<<`, `=======` и `>>>>>>>`
- `git add count_kmers.py`
- `git commit -m "resolve conflict"`
- `git push origin main`
