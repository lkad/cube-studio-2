# docker build -t ccr.ccs.tencentyun.com/cube-studio/kubeflow-dashboard:2023.04.01 -f install/docker/Dockerfile .

FROM lkad/cube-studiobase:latest

COPY install/docker/docker-add-file/rest.py /usr/local/lib/python3.9/dist-packages/kubernetes/client/rest.py
COPY install/docker/docker-add-file/__init__.py /usr/local/lib/python3.9/dist-packages/marshmallow_enum/__init__.py

COPY myapp /home/myapp/myapp
COPY myapp/static/appbuilder/frontend /data/web/frontend
ENV PATH=/home/myapp/myapp/bin:$PATH
ENV PYTHONPATH=/home/myapp:$PYTHONPATH

COPY install/docker/entrypoint.sh /entrypoint.sh

# ENTRYPOINT ["/entrypoint.sh"]
# HEALTHCHECK CMD ["curl", "-f", "http://localhost:80/health"]





