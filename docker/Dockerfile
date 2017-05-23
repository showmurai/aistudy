FROM centos:latest

# set env paths
ENV HOME /root
ENV PYENV_ROOT $HOME/.pyenv
ENV PATH $PYENV_ROOT/shims:$PYENV_ROOT/bin:$PATH
ENV ANACONDA_VERSION anaconda3-4.3.1

# prepare for install python
RUN yum update -y
RUN yum -y install gcc git curl make zlib-devel bzip2 bzip2-devel readline-devel sqlite sqlite-devel openssl openssl-devel

# install pyenv
RUN git clone https://github.com/yyuu/pyenv.git ~/.pyenv
RUN git clone https://github.com/yyuu/pyenv-virtualenv.git ~/.pyenv/plugins/pyenv-virtualenv
RUN echo 'export PYENV_ROOT=$HOME/.pyenv \
    export PATH=$PYENV_ROOT/bin:$PATH \
    eval "$(pyenv init -)" \
    eval "$(pyenv virtualenv-init -)"' >> ~/.bash_profile

# install anaconda
RUN pyenv install $ANACONDA_VERSION
RUN pyenv global $ANACONDA_VERSION
RUN pyenv rehash
ADD info.py /tmp/info.py

ENTRYPOINT ["python"]
CMD ["info.py"]
