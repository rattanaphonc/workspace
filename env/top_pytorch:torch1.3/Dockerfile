FROM pytorch/pytorch:1.3-cuda10.1-cudnn7-runtime
RUN apt-get update && \
    apt-get install sshfs -y && \
    pip install --upgrade pip
WORKDIR /mount
VOLUME /mount
COPY ./requirements.txt /mount/requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# docker build . -t image:version