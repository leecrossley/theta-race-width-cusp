# Tuning a prime race to one prime power

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24412651.svg)](https://doi.org/10.5281/zenodo.24412651)

This result is now maintained in [theta-host-split-inert-race](https://github.com/leecrossley/theta-host-split-inert-race/tree/main/results/theta-race-width-cusp). This repository is archived and keeps its releases and DOI.

**Set the width of the 547/727 prime-ideal race to $`p^j`$. One limiting measurement then determines the local trace $`\sum_\chi\chi(p)^j`$, including at ramified primes.** With the conductor data, two measurements at widths $`p`$ and $`p^2`$ determine the entire Euler factor. The earlier six-value reconstruction holds the width fixed at two. [Exact formula and proof](PROOF.md) · [Fixed-width theorem](https://github.com/leecrossley/theta-race-curvature-euler-factors/blob/af7093b56a7f6b4155dba27e735b5b1d471ff707/PROOF.md)

At a general width $`b\gt 1`$, combine the score at a height $`y`$ with the scores at $`e^{-h}y`$ and $`e^hy`$. After a known correction, its largest limiting value gives a signed sum over exactly the prime powers in $`(be^{-h},be^h)`$. For example, widths 31 and 47 give first traces of $`-8`$ and $`8`$. At width 2 the first trace vanishes, and at width 4 the second trace is 2. [Twenty certified values](evidence/weighted-extrema.tsv)

The ordinary symmetric second difference also detects prime powers. As the displacement $`h`$ shrinks, every width has an explicit term of order $`h\log(1/h)`$. The next term contains $`(\log p)\sum_\chi\chi(p)^j`$ after normalization when $`b=p^j`$. Moving the width to $`p^j e^{\lambda h}`$ multiplies that signal by $`\max(1-|\lambda|,0)`$ in the limit. At widths with vanishing trace the signal is zero. [Two-term asymptotic](PROOF.md#the-cusp-at-every-width) · [Prior work](PRIOR-WORK.md)

## Replay

In a Python 3.10+ virtual environment run

```sh
python -m pip install -r requirements.txt
python aperture.py
python cusp_check.py
python independent.py
python check_source.py
```

On x86-64 Linux with Git, curl, tar and zstd, `bash verify-release.sh` also checks the manifest, pinned upstream records and five local Lean deductions. With Lean 4.33.1 on PATH and a built Mathlib at commit `0df444a360eaa60ab8c11dca51a86af692955474`, run `bash verify-release.sh /path/to/mathlib4`. An optional second argument supplies the five upstream files. The explicit formula, limit and asymptotic expansion have written proofs. [Verification transcript](evidence/check.txt) · [Lean deductions](WidthCusp.lean) · [File hashes](SHA256SUMS)
