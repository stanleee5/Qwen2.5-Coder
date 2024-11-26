FROM pytorch/pytorch:2.4.0-cuda12.4-cudnn9-devel

ARG DEBIAN_FRONTEND=noninteractive
ENV TZ=Asia/Seoul

# install git
RUN apt-get update && apt-get install -y git

# for evaluation
RUN apt-get install -yqq mono-devel libboost-dev libssl-dev php nodejs npm openjdk-11-jdk 
RUN npm install -g typescript

# upgrade to latest pip
RUN pip install -U pip
RUN pip install --no-cache-dir \
    jsonlines \
    transformers \
    vllm==0.6.2

COPY . /qwencoder-eval
WORKDIR /qwencoder-eval

CMD ["bash"]
