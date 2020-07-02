# Compare Keras SavedModel memory usage between TF 1.x and TF 2.x

`tf1` contains the notebook for TF 1.15
`tf2` contains the notebook for TF 2.2


## Summary

[View notebook](Memory%20usage%20analysis%20TF%20Keras%201.15%20v%202.2.ipynb)

- In-process SavedModel memory usage for TF2 vs TF1: **14.3x**
- On-disk space used for SavedModel TF2 vs TF1: **16.7x**

### Compare with TF Serving

Loaded the SavedModel output of the notebooks (in `tf1` and `tf2`) in out-the-box TF Serving docker container `tensorflow/serving`. 

Output of `docker container stats`:

Overall, TF 2 vs TF 1 memory usage: **17.6x**

| NAME      | CPU %     | **MEM USAGE** / LIMIT     | MEM % |
| -         | -         | -                         | -     |
| serving_base | 0.09%  | **13.73MiB** / 7.78GiB    | 0.17% |
| test-tf2  | 0.04%     | **191.4MiB** / 7.78GiB    | 2.40% |
| test-tf1  | 0.13%     | **23.77MiB** / 7.78GiB    | 0.30% |