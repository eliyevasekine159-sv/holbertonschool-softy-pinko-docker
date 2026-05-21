FROM ubuntu:latest

# APT yeniləmələri və paketlərin quraşdırılması
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y python3 python3-pip

# Flask quraşdırması üçün "Externally Managed" xətasını aradan qaldırırıq
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED

# Flask-ı pip ilə quraşdırırıq
RUN pip3 install flask

# İşçi qovluğunu təyin edirik və faylı köçürürük
WORKDIR /app
COPY api.py /app/api.py

# Konteyner işə düşəndə Flask serverini başladırıq
CMD ["python3", "api.py"]
