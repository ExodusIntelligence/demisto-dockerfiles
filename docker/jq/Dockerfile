
FROM demisto/python3-deb:3.10.11.59575

RUN apt-get update && apt-get install build-essential flex bison libtool make automake autoconf -y

COPY requirements.txt .

RUN apt-get update && apt-get install -y --no-install-recommends \
  gcc \
  python3-dev \
&& pip install --no-cache-dir -r requirements.txt \
&& apt-get purge -y --auto-remove \
  gcc \
  python3-dev \
&& rm -rf /var/lib/apt/lists/*
