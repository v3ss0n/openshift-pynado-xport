Anaconda Python 2.7.8 and Tornado.
This cartdrige provides Python 2.7.8 + Tornado 3.2.2 + Extraport + Websocket .
It is built using continuum.io MiniConda Python, providing very powerful conda package manager and conda virtualenv.
This does the trick.

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
    conda install --yes pip "Tornado==3.2.2" pycurl
    pip install pymongo  httpie
```

It is minimal , only 100mb all libs installed.
to login to virtualenv : $NADO_VENV
Bin dir for anaconda pyton : $NADO_CONDA

installation :
    rhc app create AppName http://cartreflect-claytondev.rhcloud.com/github/v3ss0n/openshift-pynado-xport

