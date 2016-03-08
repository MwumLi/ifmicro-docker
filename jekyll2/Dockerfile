FROM ubuntu:14.04
MAINTAINER Mwumli "mwumli@hotmail.com"

# define jekyll project path
ENV JEKYLL_MD /opt/jekyll/md
ENV JEKYLL_HTML /opt/jekyll/html

VOLUME $JEKYLL_MD
VOLUME $JEKYLL_HTML

COPY sources.ali.list /root/
RUN cp /root/sources.ali.list /etc/apt/sources.list 
RUN apt-get -yqq update

RUN apt-get -yqq install ruby ruby-dev make nodejs python python-pygments
# https://jekyllrb.com/docs/history/#v2-5-3
# 2.5.3 is latest versio 2
RUN gem install --no-rdoc --no-ri jekyll -v "2.5.3"

WORKDIR $JEKYLL_MD
CMD jekyll serve --watch -H 0.0.0.0 --destination=${JEKYLL_HTML}

EXPOSE 4000 80

