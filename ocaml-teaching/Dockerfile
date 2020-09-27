FROM ocurrent/opam:ubuntu-20.04-ocaml-4.11

RUN sudo apt-get update && sudo apt-get install -y python3-pip libgmp-dev perl pkg-config libcairo2-dev libzmq3-dev m4
RUN pip3 install jupyter

ENV PATH $PATH:/home/opam/.local/bin
RUN opam user-setup install
RUN opam install -y jupyter
RUN opam exec -- ocaml-jupyter-opam-genspec
RUN jupyter kernelspec install --name ocaml-jupyter "$(opam config var share)/jupyter" --user

