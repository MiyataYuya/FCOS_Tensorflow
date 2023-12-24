# FROM nvcr.io/nvidia/pytorch:23.09-py3
# FROM tensorflow/tensorflow:latest-gpu
FROM nvcr.io/nvidia/tensorflow:23.11-tf2-py3
# FROM ubuntu:20.04

RUN apt update && apt upgrade -y
RUN apt-get update && apt-get install -y sudo

RUN pip install numpy==1.23
RUN pip install -U tf-models-official

# user setting
# ARG UID=1000
# ARG GID=1000
# RUN groupadd -g $GID -o miyata && \
#     useradd -m -u $UID -g $GID miyata
# USER miyata
ARG UID=20000
ARG GID=20000
RUN groupadd -g $GID miyata && \
    useradd -m -u $UID -g $GID miyata
RUN echo 'miyata ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers

USER miyata

# RUN echo 'miyata ALL=(ALL) NOPASSWD: ALL' >> /etc/sudoers
