# This is used in MATECC_CAPPLETS_CFLAGS
cappletname = default-applications

bin_PROGRAMS = mate-default-applications-properties

bin_SCRIPTS = mate-at-visual mate-at-mobility

mate_default_applications_properties_LDADD = $(MATECC_CAPPLETS_LIBS)
mate_default_applications_properties_SOURCES = \
	mate-da-capplet.c mate-da-capplet.h

@INTLTOOL_DESKTOP_RULE@

uidir = $(pkgdatadir)/ui
dist_ui_DATA = mate-default-applications-properties.ui

mate-at-visual: mate-at-commandline.in
	cp $< $@

mate-at-mobility: mate-at-commandline.in
	cp $< $@

desktopdir = $(datadir)/applications
Desktop_in_files = default-applications.desktop.in
desktop_DATA = $(Desktop_in_files:.desktop.in=.desktop)

pkgconfigdir = $(datadir)/pkgconfig
pkgconfig_DATA = mate-default-applications.pc

autostartdir = $(sysconfdir)/xdg/autostart
autostart_in_files = mate-at-session.desktop.in
autostart_DATA = $(autostart_in_files:.desktop.in=.desktop)

INCLUDES = \
	$(MATECC_CAPPLETS_CFLAGS) \
	$(DEFAULT_APPLICATIONS_CAPPLET_CFLAGS) \
	-DMATELOCALEDIR=\""$(datadir)/locale"\"\
	-DMATECC_UI_DIR=\""$(uidir)"\"

CLEANFILES = $(MATECC_CAPPLETS_CLEANFILES) $(Desktop_in_files) $(desktop_DATA) $(autostart_DATA) $(bin_SCRIPTS)
EXTRA_DIST = mate-default-applications.pc.in

-include $(top_srcdir)/git.mk
