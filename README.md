# Calculate system state dynamics of temporal networks

Usage:

1. Download all codes in the same folder.

2. Prepare a temporal network data as a CSV file. The format is described in the beginning of into-snapshots.py

3. Run

```
python3 into-snapshots.py infilename resolution ID_offset
```

- The infilename should not contain '.csv'.

- 'resolution' and 'ID_offset' are optional.

- See the beginning of into-snapshots.py for more details.

This will create snapshots adj1.csv, adj2.csv, ...

4. Set dir_data in preprocess_state_dyn.m to the folder you have all codes and data.

5. Download [dunns.m](https://uk.mathworks.com/matlabcentral/fileexchange/27859-dunn-s-index)
in the same folder.

6. Run in MATLAB

```
state_dyn_with_spectdist(if_normalize)
```

where if_normalize = 1, 2, 3, or 4 and corresponds to different Laplacian spectral distance measures.

The results are shown as a figure. The state dynamics are output on the command line (which you can save by slightly modifying code).

Alternatively, if DELTACON is used as the distance measure, download [MATLAB code for DELTACON](http://web.eecs.umich.edu/~dkoutra/)
in the same folder and run

```
state_dyn_deltacon()
```

Alternatively, if the Jensen-Shannon divergence is used as the distance measure, run

```
state_dyn_with_spectdivergence(beta)
```

where beta is a parameter. In our paper, beta = 0.1, 1, and 10 are used.

