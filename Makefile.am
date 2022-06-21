AUTOMAKE_OPTIONS = foreign

lib_LTLIBRARIES = libiz.la

libiz_la_SOURCES = src/libiz.cpp src/table.cpp

libiz_la_LIBADD = @LTLIBOBJS@
libiz_la_LDFLAGS = -release @VERSION@

include_HEADERS = src/bitcoder.h src/encoder.h src/decoder.h src/file.h src/image.h src/intmacros.h src/iz_p.h src/libiz.h src/pixel.h src/portableimage.h src/predict.h
EXTRA_DIST = src/bitcoder.h src/encoder.h src/decoder.h src/file.h src/image.h src/intmacros.h src/iz_p.h src/libiz.h src/pixel.h src/portableimage.h src/predict.h
noinst_HEADERS = src/bitcoder.h src/encoder.h src/decoder.h src/file.h src/image.h src/intmacros.h src/iz_p.h src/libiz.h src/pixel.h src/portableimage.h src/predict.h

iz_SOURCES = src/file.cpp src/main.cpp src/portableimage.cpp
iz_LDADD = $(lib_LTLIBRARIES)
bin_PROGRAMS = iz
