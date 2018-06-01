FROM wqael/notebooks:cuda8dnn7-conda3-py3-pytorch

RUN apt-get -qq update \
    && apt-get -qq install -y --no-install-recommends \
      build-essential \
      git \
    && apt-get -qq clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Install COCO API - Dataset @ http://cocodataset.org/
RUN git clone https://github.com/cocodataset/cocoapi.git /cocoapi && \
    cd /cocoapi/PythonAPI && \
    make install

#RUN pip --no-cache-dir install -q -U \
#      pycocotools
# Fails:
# Command "/opt/conda/bin/python -u -c "import setuptools, tokenize;__file__='/tmp/pip-install-vlv8p9x3/pycocotools/setup.py';f=getattr(tokenize, 'open', open)(__file__);code=f.read().replace('\r\n', '\n');f.close();exec(compile(code, __file__, 'exec'))" install --record /tmp/pip-record-qmstiekf/install-record.txt --single-version-externally-managed --compile" failed with error code 1 in /tmp/pip-install-vlv8p9x3/pycocotools/
