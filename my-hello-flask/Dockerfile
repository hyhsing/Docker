FROM python:3.5.2-alpine
MAINTAINER 何易星 h.y.hsing@gmail.com
ADD . /code
WORKDIR /code
RUN pip -V
RUN python -V
RUN pip install -r requirements.txt
CMD python hello.py
