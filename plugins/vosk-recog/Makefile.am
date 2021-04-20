
# Redefine VOSK_HOME according to your setup
VOSK_HOME     = $(HOME)/travis/install
VOSK_INCLUDES = -I $(VOSK_HOME)/include
VOSK_LIBS     = -L$(VOSK_HOME)/lib -Wl,-rpath=$(VOSK_HOME)/lib -lvosk -latomic -lm -lpthread

plugin_LTLIBRARIES         = voskrecog.la

voskrecog_la_CPPFLAGS      = $(UNIMRCP_PLUGIN_INCLUDES) $(VOSK_INCLUDES)
voskrecog_la_SOURCES       = src/vosk_recog_engine.c
voskrecog_la_LDFLAGS       = $(UNIMRCP_PLUGIN_OPTS) -rdynamic $(VOSK_LIBS)

include $(top_srcdir)/build/rules/uniplugin.am
