# amplify_arc105A

## 実行方法

1. プログラムと同じ階層にAmplifyのアクセストークンを記載した`tokenfile.txt`を作成する。

（もしくは直接`client.token`にアクセストークンを入力する）

2. テストケースをダウンロードする。
https://www.dropbox.com/sh/nx3tnilzqz7df8a/AADpZ-2W4pF1JT7prYveYlnVa/ARC105/A?dl=0&subfolder_nav_tracking=1

3. テストケースを置いたフォルダを指定する（inとoutのところをぞれぞれ）
```shell
files = os.listdir("ARC105A/in")
for file in files:
    with open("ARC105A/in/" + file, "r") as f:
        n = [int(i) for i in f.readline().split()]
    with open("ARC105A/out/" + file, "r") as f:
        ans = f.readline()
    result = q_annealing(n)
    print(file, "Amplify結果 =", result, "正解 =", ans)
```        
        
4. プログラムをを実行する

AC

```shell
random_01.txt Amplify結果 = Yes 正解 = Yes

random_02.txt Amplify結果 = Yes 正解 = Yes

random_03.txt Amplify結果 = Yes 正解 = Yes

random_04.txt Amplify結果 = Yes 正解 = Yes

random_05.txt Amplify結果 = No 正解 = No

random_06.txt Amplify結果 = No 正解 = No

random_07.txt Amplify結果 = No 正解 = No

random_08.txt Amplify結果 = Yes 正解 = Yes

random_09.txt Amplify結果 = Yes 正解 = Yes

random_10.txt Amplify結果 = No 正解 = No

random_11.txt Amplify結果 = No 正解 = No

random_12.txt Amplify結果 = No 正解 = No

sample_01.txt Amplify結果 = Yes 正解 = Yes

sample_02.txt Amplify結果 = No 正解 = No
```

## 原理

イジングモデルのハミルトニアンとしては、総和の二乗です。

上向きのスピンと下向きのスピンで打ち消しあって0になればyes、ならなければnoです。

https://quantum.fixstars.com/techresouces/research/ising-model-formulation/number-partitioning/


## 使用した量子アニーリングマシン

Fixstars Amplify AE

https://amplify.fixstars.com/
