#
#  Copyright (C) CFEngine AS
#
#  This file is part of CFEngine 3 - written and maintained by CFEngine AS.
#
#  This program is free software; you can redistribute it and/or modify it
#  under the terms of the GNU General Public License as published by the
#  Free Software Foundation; version 3.
#
#  This program is distributed in the hope that it will be useful,
#  but WITHOUT ANY WARRANTY; without even the implied warranty of
#  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#  GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA  02111-1307, USA
#
# To the extent this program is licensed as part of the Enterprise
# versions of CFEngine, the applicable Commercial Open Source License
# (COSL) may apply to this file if you as a licensee so wish it. See
# included file COSL.txt.
#
noinst_LTLIBRARIES = libcf-report.la

AM_CPPFLAGS = \
	$(OPENSSL_CPPFLAGS) \
	-I$(srcdir)/../libutils \
	-I$(srcdir)/../libcfnet \
	-I$(srcdir)/../libenv \
	-I$(srcdir)/../libpromises \
	-I$(srcdir)/../cf-monitord \
	$(PCRE_CPPFLAGS) \
	$(ENTERPRISE_CPPFLAGS)

AM_CFLAGS = @CFLAGS@ \
	$(OPENSSL_CFLAGS) \
	$(ENTERPRISE_CFLAGS)

libcf_report_la_LIBADD = ../libpromises/libpromises.la ../cf-monitord/libcf-monitord.la

libcf_report_la_SOURCES = \
        cf-report.c \
	../cf-monitord/monitoring.c

if !BUILTIN_EXTENSIONS
 sbin_PROGRAMS = cf-report
 # Workaround for automake madness (try removing it if you want to know why).
 cf_report_CFLAGS = $(AM_CFLAGS)
 cf_report_LDADD = libcf-report.la
endif

CLEANFILES = *.gcno *.gcda

#
# Some basic clean ups
#
MOSTLYCLEANFILES = *~ *.orig *.rej
