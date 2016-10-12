# Linux tips

To get the first 10,000 sequences in a fastq file:

```bash
head -n 40000 [infile.fq] > [outfile.fq]
```

Skip the first 10,000 sequences, then get the next 10,000 reads:

```bash
tail -n+40000 [infile.fq] | head -n 40000 > [outfile.fq]
```

