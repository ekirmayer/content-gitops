FROM python:3-alpine
LABEL 'maintainer=notMe'
COPY . /python
WORKDIR /python
RUN pip install -r requirements.txt
CMD python /python/app.py
