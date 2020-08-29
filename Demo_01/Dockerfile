FROM ubuntu:16.04

RUN apt-get update && \
    apt-get install -y python3-pip python3-dev && \
    cd /usr/local/bin && \
    ln -s /usr/bin/python3 python && \
    pip3 install --upgrade pip


WORKDIR /app

COPY requirements.txt .
RUN pip3 install -r requirements.txt

COPY wine_quality.csv .

COPY train.py .

CMD [ "sh", "-c", "python3 train.py --key $WANDB_KEY" ]