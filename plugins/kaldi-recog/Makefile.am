AM_CPPFLAGS                = $(UNIMRCP_PLUGIN_INCLUDES)

KALDI_ROOT ?= $(HOME)/kaldi

AM_CPPFLAGS += -std=c++11 -g -DPIC -fPIC -I$(KALDI_ROOT)/tools/openfst/include -I$(KALDI_ROOT)/src 

KALDI_LIBS = \
    $(KALDI_ROOT)/src/online2/kaldi-online2.a \
    $(KALDI_ROOT)/src/decoder/kaldi-decoder.a \
    $(KALDI_ROOT)/src/ivector/kaldi-ivector.a \
    $(KALDI_ROOT)/src/gmm/kaldi-gmm.a \
    $(KALDI_ROOT)/src/nnet3/kaldi-nnet3.a \
    $(KALDI_ROOT)/src/tree/kaldi-tree.a \
    $(KALDI_ROOT)/src/feat/kaldi-feat.a \
    $(KALDI_ROOT)/src/lm/kaldi-lm.a \
    $(KALDI_ROOT)/src/rnnlm/kaldi-rnnlm.a \
    $(KALDI_ROOT)/src/lat/kaldi-lat.a \
    $(KALDI_ROOT)/src/hmm/kaldi-hmm.a \
    $(KALDI_ROOT)/src/transform/kaldi-transform.a \
    $(KALDI_ROOT)/src/cudamatrix/kaldi-cudamatrix.a \
    $(KALDI_ROOT)/src/matrix/kaldi-matrix.a \
    $(KALDI_ROOT)/src/fstext/kaldi-fstext.a \
    $(KALDI_ROOT)/src/util/kaldi-util.a \
    $(KALDI_ROOT)/src/base/kaldi-base.a \
    $(KALDI_ROOT)/tools/openfst/lib/libfst.a \
    $(KALDI_ROOT)/tools/openfst/lib/libfstngram.a \
    $(KALDI_ROOT)/tools/OpenBLAS/libopenblas.a \
    -lgfortran

plugin_LTLIBRARIES         = kaldirecog.la

kaldirecog_la_SOURCES       = src/kaldi_recog_engine.cc src/model.cc src/kaldi_recognizer.cc src/spk_model.cc
kaldirecog_la_LDFLAGS       = $(UNIMRCP_PLUGIN_OPTS) $(KALDI_LIBS)

include $(top_srcdir)/build/rules/uniplugin.am
