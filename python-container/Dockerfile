#
# python:3.7.9-alpine3.12 with pyyaml and kubernetes client 
#

FROM python:3.7.9-alpine3.12

RUN pip install pyyaml && pip install kubernetes && pip install flask && pip install rejson && pip install json2html && pip install pdfkit
RUN apk add --no-cache redis
#RUN apk add --no-cache wkhtmltopdf

COPY job-node_DaemonSet.yaml .
COPY bench_api.py .
COPY kube_flask.py .
COPY /templates /templates
COPY rejson.so rejson.so
COPY module.json module.json

CMD ["python","kube_flask.py"]
