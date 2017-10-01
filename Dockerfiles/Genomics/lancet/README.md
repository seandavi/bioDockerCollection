# lancet

- https://github.com/nygenome/lancet

# Usage

```
  |                           |
  |      _` | __ \   __|  _ \ __|
  |     (   | |   | (     __/ |
 _____|\__,_|_|  _|\___|\___|\__|

Program: lancet (micro-assembly somatic variant caller)
Version: 1.0.0 (beta), September 18 2016
Contact: Giuseppe Narzisi <gnarzisi@nygenome.org>

Usage: lancet [options] --tumor <BAM file> --normal <BAM file> --ref <FASTA file> --reg <chr:start-end>
 [-h for full list of commands]

Required
   --tumor, -t              <BAM file>    : BAM file of mapped reads for tumor
   --normal, -n             <BAM file>    : BAM file of mapped reads for normal
   --ref, -r                <FASTA file>  : FASTA file of reference genome
   --reg, -p                <string>      : genomic region (in chr:start-end format)
   --bed, -B                <string>      : genomic regions from file (BED format)

Optional
   --min-k, k                <int>         : min kmersize [default: 11]
   --max-k, -K               <int>         : max kmersize [default: 100]
   --trim-lowqual, -q        <int>         : trim bases below qv at 5' and 3' [default: 10]
   --min-base-qual, -C       <int>         : minimum base quality required to consider a base for SNV calling [default: 17]
   --quality-range, -Q       <char>        : quality value range [default: !]
   --min-map-qual, -b        <inr>         : minimum read mapping quality in Phred-scale [default: 15]
   --tip-len, -l             <int>         : max tip length [default: 11]
   --cov-thr, -c             <int>         : coverage threshold [default: 5]
   --cov-ratio, -x           <float>       : minimum coverage ratio [default: 0.01]
   --max-avg-cov, -u         <int>         : maximum average coverage allowed per region [default: 10000]
   --low-cov, -d             <int>         : low coverage threshold [default: 1]
   --window-size, -w         <int>         : window size of the region to assemble (in base-pairs) [default: 600]
   --dfs-limit, -F           <int>         : limit dfs/bfs graph traversal search space [default: 1000000]
   --max-indel-len, -T       <int>         : limit on size of detectable indel [default: 500]
   --max-mismatch, -M        <int>         : max number of mismatches for near-perfect repeats [default: 2]
   --num-threads, -X         <int>         : number of parallel threads [default: 1]
   --node-str-len, -L        <int>         : length of sequence to display at graph node (default: 100)

Filters
   --min-alt-count-tumor, -a  <int>        : minimum alternative count in the tumor [default: 3]
   --max-alt-count-normal, -m <int>        : maximum alternative count in the normal [default: 0]
   --min-vaf-tumor, -e        <float>      : minimum variant allele frequency (AlleleCov/TotCov) in the tumor [default: 0.04]
   --max-vaf-normal, -i       <float>      : maximum variant allele frequency (AlleleCov/TotCov) in the normal [default: 0]
   --min-coverage-tumor, -o   <int>        : minimum coverage in the tumor [default: 4]
   --max-coverage-tumor, -y   <int>        : maximum coverage in the tumor [default: 1000000]
   --min-coverage-normal, -z  <int>        : minimum coverage in the normal [default: 10]
   --max-coverage-normal, -j  <int>        : maximum coverage in the normal [default: 1000000]
   --min-phred-fisher, -s     <float>      : minimum fisher exact test score [default: 5]
   --min-phred-fisher-str, -E <float>      : minimum fisher exact test score for STR mutations [default: 25]
   --min-strand-bias, -f      <float>      : minimum strand bias threshold [default: 1]

Short Tandem Repeat parameters
   --max-unit-length, -U      <int>        : maximum unit length of the motif [default: 4]
   --min-report-unit, -N      <int>        : minimum number of units to report [default: 3]
   --min-report-len, -Y       <int>        : minimum length of tandem in base pairs [default: 7]
   --dist-from-str, -D        <int>        : distance (in bp) of variant from STR locus [default: 1]

Flags
   --active-region-off, -W    : turn off active region module
   --kmer-recovery, -R        : turn on k-mer recovery (experimental)
   --print-graph, -A          : print graph (in .dot format) after every stage
   --verbose, -v              : be verbose
   --more-verbose, -V         : be more verbose
```
