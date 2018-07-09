FROM stefanschmidt1/ci-support-files:Archlinux

# Install dependencies from enlightenment


RUN rm -rf efl

RUN git clone --depth 1 -b v1.19.2 https://git.enlightenment.org/core/efl.git
RUN git clone --depth 1 -b v1.1.1 https://git.enlightenment.org/apps/terminology.git
RUN git clone --depth 1 -b v0.21.11 https://git.enlightenment.org/core/enlightenment.git

# BUILD EFL

RUN cd efl && ./autogen.sh --prefix /usr/ && make all && make install

RUN ldconfig
RUN cd ..

