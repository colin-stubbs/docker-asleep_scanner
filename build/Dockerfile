FROM python:3

ENV LANG=C.UTF-8
ENV LC_ALL=C.UTF-8
ENV PIP_NO_CACHE_DIR=off

WORKDIR /usr/src

RUN apt update && \
  apt upgrade -y && \
  apt install -y libgl1 masscan git && \
  git clone https://github.com/S0Ulle33/asleep_scanner.git && \
  cd asleep_scanner && \
  pip3 install -r requirements.txt && \
  sed -i.original -e 's/^import imp$/#import imp - python3.3 legacy thing, replaced by importlib, and yet not required.../' export.py && \
  chmod 0755 /usr/src/asleep_scanner/asleep.py

WORKDIR /root

ENTRYPOINT [ "/usr/src/asleep_scanner/asleep.py" ]