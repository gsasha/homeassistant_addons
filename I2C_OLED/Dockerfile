ARG BUILD_FROM
FROM $BUILD_FROM

# Install requirements for add-on
RUN \
  apk add --no-cache \
    git \
    python3 \
    py3-pip \
    py3-pillow \
    py3-smbus \
    py3-requests

RUN git clone --single-branch --depth 1 https://github.com/gsasha/rpi_i2c_oled.git /I2C_OLED; cd ./I2C_OLED;\
 git checkout b7932d4
#RUN git clone -b v1.0.55 --single-branch --depth 1 https://github.com/gsasha/rpi_i2c_oled.git /I2C_OLED
#COPY requirements.txt /
#RUN pip3 install --no-cache-dir --break-system-packages -r /requirements.txt

COPY run.sh /
WORKDIR /data
RUN chmod a+x /run.sh
CMD [ "/run.sh" ]
