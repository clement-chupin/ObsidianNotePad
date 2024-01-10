


### docker commands


```bash
docker run hello-world
docker run -ir ubuntu bash
docker ps

docker rm $id
/exit

docker build -t image_name .
docker run -p 80:80 image_name

`docker pull pytorch/pytorch`

```


### docker image

```bash
gedit Dockerfile
{
FROM python:3.9
WORKDIR . /app
COPY ./app
RUN conda env create --file environment.yml  
EXPOSE 80
}
```



```
FROM continuumio/anaconda3:2020.11

COPY . .
RUN conda env create
RUN conda run -n nyc-taxi-fare-prediction-deployment-example \
  python -m pip install --no-deps -e .
CMD [ \
  "conda", "run", "-n", "nyc-taxi-fare-prediction-deployment-example", \
  "gunicorn", "-k", "uvicorn.workers.UvicornWorker", "nyc_taxi_fare.serve:app" \
]
```


```
COPY predict-linux-64.lock .
RUN mamba create --name nyc-taxi-fare-prediction-deployment-example --file predict-linux-64.lock && \ 
    conda clean -afy
```


```
# Container for building the environment
FROM condaforge/mambaforge:4.9.2-5 as conda

COPY predict-linux-64.lock .
RUN mamba create --copy -p /env --file predict-linux-64.lock && conda clean -afy
COPY . /pkg
RUN conda run -p /env python -m pip install --no-deps /pkg

# Distroless for execution
FROM gcr.io/distroless/base-debian10

COPY --from=conda /env /env
COPY model.pkl .
CMD [ \
  "/env/bin/gunicorn", "-b", "0.0.0.0:8000", "-k", "uvicorn.workers.UvicornWorker", "nyc_taxi_fare.serve:app" \
]
```




```
# Container for building the environment
FROM condaforge/mambaforge:4.9.2-5 as conda

COPY predict-linux-64.lock .
RUN --mount=type=cache,target=/opt/conda/pkgs mamba create --copy -p /env --file predict-linux-64.lock && echo 4
COPY . /pkg
RUN conda run -p /env python -m pip install --no-deps /pkg
# Clean in a separate layer as calling conda still generates some __pycache__ files
RUN find -name '*.a' -delete && \
  rm -rf /env/conda-meta && \
  rm -rf /env/include && \
  rm /env/lib/libpython3.9.so.1.0 && \
  find -name '__pycache__' -type d -exec rm -rf '{}' '+' && \
  rm -rf /env/lib/python3.9/site-packages/pip /env/lib/python3.9/idlelib /env/lib/python3.9/ensurepip \
    /env/lib/libasan.so.5.0.0 \
    /env/lib/libtsan.so.0.0.0 \
    /env/lib/liblsan.so.0.0.0 \
    /env/lib/libubsan.so.1.0.0 \
    /env/bin/x86_64-conda-linux-gnu-ld \
    /env/bin/sqlite3 \
    /env/bin/openssl \
    /env/share/terminfo && \
  find /env/lib/python3.9/site-packages/scipy -name 'tests' -type d -exec rm -rf '{}' '+' && \
  find /env/lib/python3.9/site-packages/numpy -name 'tests' -type d -exec rm -rf '{}' '+' && \
  find /env/lib/python3.9/site-packages/pandas -name 'tests' -type d -exec rm -rf '{}' '+' && \
  find /env/lib/python3.9/site-packages -name '*.pyx' -delete && \
  rm -rf /env/lib/python3.9/site-packages/uvloop/loop.c

# Distroless for execution
FROM gcr.io/distroless/base-debian10

COPY --from=conda /env /env
COPY model.pkl .
CMD [ \
  "/env/bin/gunicorn", "-b", "0.0.0.0:8000", "-k", "uvicorn.workers.UvicornWorker", "nyc_taxi_fare.serve:app" \
]

```

```
docker buildx build -t nyc-taxi-distroless-buildkit-expert --load -f docker/Dockerfile.distroless-buildkit-expert .
docker run -ti -p 8000:8000 nyc-taxi-distroless-buildkit-expert
```



```
docker build --rm --build-arg DISTRO_NAME=centos --build-arg DISTRO_VER=6 -f linux-anvil-comp7/Dockerfile .
docker build --rm --build-arg DISTRO_NAME=centos --build-arg DISTRO_VER=6 --build-arg CUDA_VER=10.2 -f linux-anvil-cuda/Dockerfile .
```


### From conda/pip to docker

```bash
djdjjd
```
