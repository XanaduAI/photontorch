Photontorch
===========

:ref:`examples` · :ref:`documentation` · :ref:`genindex` · :ref:`modindex`

Photontorch is a photonic simulator for highly parallel simulation and
optimization of photonic circuits in time and frequency domain.
Photontorch features CUDA enabled simulation and optimization of
photonic circuits. It leverages the deep learning framework PyTorch to
view the photonic circuit as essentially a recurrent neural network.
This enables the use of native PyTorch optimizers to optimize the
(physical) parameters of the circuit.


Installation
------------

Stable version
^^^^^^^^^^^^^^

Photontorch can be installed with pip::

    pip install photontorch

Development version
^^^^^^^^^^^^^^^^^^^
During development or to use the most recent Photontorch version,
clone the repository and link with pip::

    git clone https://git.photontorch.com/photontorch.git
    ./install-git-hooks.sh # Unix [Linux/Mac/BSD/...]
    install-git-hooks.bat  # Windows
    pip install -e photontorch

During development, use pytest to run the tests from within the root
of the git-repository::

    pytest tests


Dependencies
------------

Python 3.9 or newer. The test suite has been run through Python 3.12.

``pip install photontorch`` installs torch, numpy, and scipy. Those three are imported whenever the package is imported. Torch must be at least 2.2 and older than 2.13. See `pytorch.org <https://pytorch.org>`_ for a CUDA build.

Install an extra when you need that capability.

- ``pip install photontorch[plot]`` installs matplotlib. ``Network.plot`` and ``BERLoss.plot`` import it. A simulation does not.
- ``pip install photontorch[graph]`` installs matplotlib and networkx. ``Network.graph`` imports both. A simulation does not.
- ``pip install photontorch[lfilter]`` installs torch-lfilter. Detectors use it when it is present, and fall back to a pure Python filter when it is not.
- ``pip install photontorch[examples]`` installs matplotlib and tqdm. The notebooks use both. The library does not import tqdm.
- ``pip install photontorch[test]`` installs pytest, coverage, and pytest-cov.
- ``pip install photontorch[docs]`` installs sphinx and nbsphinx. Building the docs also needs `pandoc <https://pandoc.org>`_, which is not a Python package.


Table of contents
-----------------

.. toctree::
   :maxdepth: 2

   examples
   photontorch


Reference
---------
If you're using Photontorch in your work or feel in any way inspired by it,
please be so kind to cite us in your work.

Floris Laporte, Joni Dambre, and Peter Bienstman. *"Highly parallel simulation
and optimization of photonic circuits in time and frequency domain based on the
deep-learning framework PyTorch."* Scientific reports 9.1 (2019): 5918.


Where to go from here?
----------------------
Check out the first example: `A brief introduction to Photontorch <examples/00_introduction_to_photontorch.html>`_.


License
-------

Photontorch is available under an
`Academic License <https://github.com/flaport/photontorch/blob/master/LICENSE>`_.
This means that there are no restrictions on the usage in a purely
non-commercial or academic context. For commercial applications you can
always contact the authors.

Copyright © 2020, Floris Laporte - Universiteit Gent - Ghent University -
`Academic License <https://github.com/flaport/photontorch/blob/master/LICENSE>`_.
