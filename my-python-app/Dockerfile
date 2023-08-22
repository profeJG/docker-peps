FROM ubuntu:latest

RUN apt update && apt install -y \
python3 \
pip

WORKDIR /app
COPY . /app/
RUN pip install -r requierements.txt
ENTRYPOINT [ "pytest" ]