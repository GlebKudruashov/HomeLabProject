FROM public.ecr.aws/docker/library/python:3.12-slim

RUN apt-get update && apt-get install -y --no-install-recommends \
    ffmpeg \
    libchromaprint-tools \
    libjpeg62-turbo-dev \
    zlib1g-dev \
    && rm -rf /var/lib/apt/lists/*

RUN pip install --no-cache-dir \
    beets==2.14.1 \
    flask \
    flask-cors \
    Pillow \
    pylast \
    pyacoustid \
    requests

ENV BEETSDIR=/config \
    HOME=/config \
    PYTHONUNBUFFERED=1

EXPOSE 8337

CMD ["beet", "web"]
