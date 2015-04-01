Anaconda Python 2.7.8 and Tornado.
This cartdrige provides Python 2.7.8 + Tornado 4.1.0 + Extraport + Websocket .
It is built using continuum.io MiniConda Python, providing very powerful conda package manager and conda virtualenv.


It is minimal , only 100mb all libs installed.

To login to virtualenv enter : ```$NADO_VENV```

Python Bin Dir  :  ```cd $NADO_CONDA```

***Installation*** :
```

rhc app create AppName http://cartreflect-claytondev.rhcloud.com/github/v3ss0n/openshift-python-tornado-extraport

```

How this cartdrige installed behind the scenes?

```
MINICONDA_VERSION=3.5.5
pushd $OPENSHIFT_TMP_DIR
wget http://repo.continuum.io/miniconda/Miniconda-${MINICONDA_VERSION}-Linux-x86_64.sh
/bin/bash ./Miniconda-${MINICONDA_VERSION}-Linux-x86_64.sh -b -p ${OPENSHIFT_PYNADO_DIR}pynado
rm Miniconda-${MINICONDA_VERSION}-Linux-x86_64.sh
popd
${OPENSHIFT_PYNADO_DIR}pynado/bin/conda create --yes -n pynadoenv python 
echo "Before activing VirtualEnv :  pynadoenv"
source ${OPENSHIFT_PYNADO_DIR}pynado/bin/activate pynadoenv
echo "inside VirtualEnv :  pynadoenv"
conda install --yes pip  pycurl
pip install pymongo toro httpie "Tornado==4.1"
```

