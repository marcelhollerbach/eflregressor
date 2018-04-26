FROM bu5hm4n/efl-ready-docker-archlinux

RUN rm -rf efl

RUN git clone -b v1.19.14 https://git.enlightenment.org/core/efl.git
RUN git clone -b v1.2.0 https://git.enlightenment.org/apps/terminology.git
RUN git clone -b v0.22.3 https://git.enlightenment.org/core/enlightenment.git

# BUILD EFL

RUN cd efl && ./autogen.sh --prefix /usr/ && make -j10 all && make -j10 install

RUN ldconfig
RUN cd ..

# BUILD terminology

RUN cd terminology && mkdir build && cd build && meson --prefix /usr/ .. && ninja all && ninja install

RUN ldconfig
RUN cd ..

# BUILD enlightenment

RUN cd enlightenment && ./autogen.sh --prefix /usr/ && make -j10 all && make -j10 install
