# Photontorch

Photontorch is a photonic simulator for highly parallel simulation and
optimization of photonic circuits in time and frequency domain.
Photontorch features CUDA enabled simulation and optimization of
photonic circuits. It leverages the deep learning framework PyTorch to
view the photonic circuit as essentially a recurrent neural network.
This enables the use of native PyTorch optimizers to optimize the
(physical) parameters of the circuit.

- Floris Laporte [[floris.laporte@ugent.be](mailto:floris.laporte@gmail.com)]
- Website: [photontorch.com](http://photontorch.com)

## Installation

### Stable version

Photontorch can be installed with pip:

```
pip install photontorch
```

### Development version

During development or to use the most recent Photontorch version,
clone the repository and link with pip:

```
git clone https://git.photontorch.com/photontorch.git
./install-git-hooks.sh # Unix [Linux/Mac/BSD/...]
install-git-hooks.bat  # Windows
pip install -e "photontorch[test]"
```

During development, use pytest to run the tests from within the root
of the git-repository:

```
pytest tests
```

## Documentation

Read the full documentation here: [https://docs.photontorch.com](https://docs.photontorch.com)

## Dependencies

Python 3.9 or newer. The test suite has been run through Python 3.12.

`pip install photontorch` installs torch, numpy, and scipy. Those three are imported whenever the package is imported. Torch must be at least 2.2 and older than 2.13. See [pytorch.org](https://pytorch.org) for a CUDA build.

Install an extra when you need that capability.

- `pip install photontorch[plot]` installs matplotlib. `Network.plot` and `BERLoss.plot` import it. A simulation does not.
- `pip install photontorch[graph]` installs matplotlib and networkx. `Network.graph` imports both. A simulation does not.
- `pip install photontorch[lfilter]` installs torch-lfilter. Detectors use it when it is present, and fall back to a pure Python filter when it is not.
- `pip install photontorch[examples]` installs matplotlib and tqdm. The notebooks use both. The library does not import tqdm.
- `pip install photontorch[test]` installs pytest, coverage, and pytest-cov.
- `pip install photontorch[docs]` installs sphinx and nbsphinx. Building the docs also needs [pandoc](https://pandoc.org), which is not a Python package.

## Reference

If you're using Photontorch in your work or feel in any way inspired by it,
we ask you to cite us in your work:

Floris Laporte, Joni Dambre, and Peter Bienstman. _"Highly parallel simulation
and optimization of photonic circuits in time and frequency domain based on the
deep-learning framework PyTorch."_ Scientific reports 9.1 (2019): 5918.

## Known issues

- Complex tensor support. Complex tensors are not supported in
  PyTorch/Photontorch. Wherever complex tensors would be applicable,
  Photontorch expects a real-valued tensor with the real and imag part
  stacked in the first dimension. The Photontorch issue can be
  followed [here](https://github.com/flaport/photontorch/issues/4) and
  the PyTorch issue [here](https://github.com/pytorch/pytorch/issues/755).
- Sparse tensor support. A lot of memory usage can probably be avoided
  when transitioning to a sparse tensor representation for the connection matrices and
  scatter matrices. The Photontorch issue can be followed [here](https://github.com/flaport/photontorch/issues/5)

## License

Photontorch used to be available under a custom Academic License, but Since October
2020, Photontorch is now fully open source and available under the [AGPLv3](LICENSE). 

Copyright © 2020, Floris Laporte - UGent - [AGPLv3](LICENSE)

