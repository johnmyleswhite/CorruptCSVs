Writing a CSV parser is really hard because the format is just utterly awful,
but people insist that you "successfully" parse ill-formatted files.

```bash
$ hexdump r_example_1.tsv
0000000 31 0a 32 0a 33 0a 34 0a 35 09 30 0a
000000c
$ hexdump r_example_2.tsv
0000000 31 0a 32 0a 33 0a 34 0a 35 0a 36 09 30 0a
000000e
```

```R
> read.csv("r_example_1.tsv", header = FALSE, sep = "\t")
  V1 V2
1  1 NA
2  2 NA
3  3 NA
4  4 NA
5  5  0
>
> read.csv("r_example_2.tsv", header = FALSE, sep = "\t")
  V1
1  1
2  2
3  3
4  4
5  5
6  6
7  0
```
