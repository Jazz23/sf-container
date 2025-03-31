ARG COQ_IMAGE=coqorg/coq:8.19.2-ocaml-4.14.2-flambda
FROM ${COQ_IMAGE}

ARG OPAM_PACKAGES="coq-equations.1.3+8.19 coq-quickchick coq-simple-io vscoq-language-server"

# Install opam packages
RUN opam install -y -j ${NJOBS} ${OPAM_PACKAGES} && \
    opam clean -y -a -c -s --logs && \
    opam update -y && \
    opam upgrade -y && \
    eval $(opam env)
