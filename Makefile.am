# 
#  Copyright 2005  Red Hat, Inc.
# 
#  Permission to use, copy, modify, distribute, and sell this software and its
#  documentation for any purpose is hereby granted without fee, provided that
#  the above copyright notice appear in all copies and that both that
#  copyright notice and this permission notice appear in supporting
#  documentation, and that the name of Red Hat not be used in
#  advertising or publicity pertaining to distribution of the software without
#  specific, written prior permission.  Red Hat makes no
#  representations about the suitability of this software for any purpose.  It
#  is provided "as is" without express or implied warranty.
# 
#  RED HAT DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE,
#  INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS, IN NO
#  EVENT SHALL RED HAT BE LIABLE FOR ANY SPECIAL, INDIRECT OR
#  CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE,
#  DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER
#  TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR
#  PERFORMANCE OF THIS SOFTWARE.

bin_PROGRAMS = x11perf

bin_SCRIPTS = x11perfcomp

LIBPATH = $(libdir)/X11/x11perfcomp

x11perfcompdir = $(LIBPATH)
dist_x11perfcomp_SCRIPTS = fillblnk.sh  perfboth.sh  perfratio.sh  Xmark.sh

x11perf_CFLAGS = $(X11PERF_CFLAGS)
x11perf_LDADD = $(X11PERF_LIBS) -lm

x11perf_SOURCES =	\
        bitmaps.c \
        bitmaps.h \
        do_arcs.c \
        do_blt.c \
        do_complex.c \
        do_dots.c \
        do_lines.c \
        do_movewin.c \
        do_rects.c \
        do_segs.c \
        do_simple.c \
        do_tests.c \
        do_text.c \
        do_traps.c \
        do_tris.c \
        do_valgc.c \
        do_windows.c \
        x11perf.c \
        x11perf.h

dist_man1_MANS = \
        x11perfcomp.man \
        x11perf.man \
        Xmark.man

x11perfcomp: x11pcomp.cpp
	$(SED) s/LIBPATH/`echo $(LIBPATH) | sed -e s/\\\\//\\\\\\\\\\\\\//g`/ < $(srcdir)/x11pcomp.cpp | \
		$(SED) s/XCOMM/\#/ > $@


CLEANFILES = $(bin_SCRIPTS) x11perfcomp

EXTRA_DIST = x11pcomp.cpp
