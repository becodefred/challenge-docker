FROM python:3.7
RUN mkdir /app
COPY ./pipeline/model/model.py /app/model.py
COPY ./pipeline/preprocessing/preprocessing.py /app/preprocessing.py
COPY ./pipeline/utils/utils.py /app/utils.py
WORKDIR /app
RUN pip3 install numpy
CMD ["python", "./model.py"]
