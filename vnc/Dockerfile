FROM jlesage/baseimage-gui:ubuntu-20.04-v4 AS base

ARG LOCALE="en-US"

ARG DEBIAN_FRONTEND="noninteractive"
RUN apt-get update \
	&& apt-get install -y --no-install-recommends \
	ca-certificates \
	curl \
	gnupg \
	gpg \
	xz-utils \
	&& rm -rf /var/lib/apt/lists/*

ARG DEBIAN_FRONTEND="noninteractive"
RUN apt-get update \
	&& apt-get install -y --no-install-recommends \
	libu2f-udev \
	libvulkan1 \
	file \
	libdbus-glib-1-2 \
	libgtk-3-0 \
	libx11-xcb1 \
	libxt6 \
	libasound2 \
	fonts-liberation \
	libdrm2 \
	libgbm1 \
	libnspr4 \
	libnss3 \
	xdg-utils \
	wget \
	xvfb \
	&& rm -rf /var/lib/apt/lists/*

ARG DEBIAN_FRONTEND="noninteractive"
RUN apt-get update \ 
	&& apt-get install -y --no-install-recommends \
	qutebrowser \
	kitty \
	ffmpeg \
	&& rm -rf /var/lib/apt/lists/*

RUN touch /etc/services.d/default/twitch.dep

COPY twitch /etc/services.d/twitch/ 

RUN chmod +x /etc/services.d/twitch/run

COPY ./boot.sh /startapp.sh
