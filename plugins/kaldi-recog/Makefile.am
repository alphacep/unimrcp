AM_CPPFLAGS                = $(UNIMRCP_PLUGIN_INCLUDES)

ATLASLIBS := -L/usr/lib/x86_64-linux-gnu -l:libatlas.so.3 -l:libf77blas.so.3 -l:libcblas.so.3 -l:liblapack_atlas.so.3 -Wl,-rpath=/usr/lib/x86_64-linux-gnu
KALDI_ROOT := /home/shmyrev/voicechat/kaldi
KALDI_FLAGS := -std=c++11 -g -Wall -DPIC -fPIC \
-DKALDI_DOUBLEPRECISION=0 -DHAVE_POSIX_MEMALIGN \
-Wno-sign-compare -Wno-unused-local-typedefs -Winit-self \
-DHAVE_EXECINFO_H=1 -rdynamic -DHAVE_CXXABI_H -DHAVE_ATLAS \
-I$(KALDI_ROOT)/tools/ATLAS/include \
-I$(KALDI_ROOT)/tools/openfst/include -I$(KALDI_ROOT)/src 

AM_CPPFLAGS += $(KALDI_FLAGS)

KALDI_LIBS = \
    -rdynamic -Wl,-rpath=$(KALDI_ROOT)/tools/openfst/lib \
    $(KALDI_ROOT)/src/online2/kaldi-online2.a \
    $(KALDI_ROOT)/src/decoder/kaldi-decoder.a \
    $(KALDI_ROOT)/src/ivector/kaldi-ivector.a \
    $(KALDI_ROOT)/src/gmm/kaldi-gmm.a \
    $(KALDI_ROOT)/src/nnet3/kaldi-nnet3.a \
    $(KALDI_ROOT)/src/tree/kaldi-tree.a \
    $(KALDI_ROOT)/src/feat/kaldi-feat.a \
    $(KALDI_ROOT)/src/lat/kaldi-lat.a \
    $(KALDI_ROOT)/src/hmm/kaldi-hmm.a \
    $(KALDI_ROOT)/src/transform/kaldi-transform.a \
    $(KALDI_ROOT)/src/cudamatrix/kaldi-cudamatrix.a \
    $(KALDI_ROOT)/src/matrix/kaldi-matrix.a \
    $(KALDI_ROOT)/src/fstext/kaldi-fstext.a \
    $(KALDI_ROOT)/src/util/kaldi-util.a \
    $(KALDI_ROOT)/src/base/kaldi-base.a \
    -L$(KALDI_ROOT)/tools/openfst/lib -lfst \
    $(ATLASLIBS) \
    -lm -lpthread

plugin_LTLIBRARIES         = kaldirecog.la

kaldirecog_la_SOURCES       = src/kaldi_recog_engine.cc src/model.cc src/kaldi_recognizer.cc
kaldirecog_la_LDFLAGS       = $(UNIMRCP_PLUGIN_OPTS) $(KALDI_LIBS)

include $(top_srcdir)/build/rules/uniplugin.am
