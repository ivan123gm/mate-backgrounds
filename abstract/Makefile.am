backgrounddir = $(datadir)/backgrounds/mate/abstract

background_DATA = \
	Arc-Colors-Transparent-Wallpaper.png \
	Flow.png \
	Gulp.png \
	Silk.png \
	Spring.png \
	Waves.png \
	Elephants.jpg \
	Elephants_3840x2160.jpg \
	Elephants_5640x3172.jpg

metadata_in_files = mate-abstract.xml.in
metadatadir = $(datadir)/mate-background-properties
metadata_DATA = $(metadata_in_files:.xml.in=.xml)

$(metadata_DATA): $(metadata_in_files)
	$(AM_V_GEN) GETTEXTDATADIR=$(top_srcdir) $(MSGFMT) --xml --template $< -d $(top_srcdir)/po -o $@

noinst_DATA = mate-abstract.xml.in
CLEANFILES = mate-abstract.xml mate-abstract.xml.in

EXTRA_DIST = \
	$(background_DATA) \
	mate-abstract.xml.in.in \
	meson.build

mate-abstract.xml.in: mate-abstract.xml.in.in Makefile
	$(AM_V_GEN)sed -e 's^\@datadir\@^$(datadir)^g' < $(srcdir)/mate-abstract.xml.in.in > mate-abstract.xml.in.tmp \
	&& mv mate-abstract.xml.in.tmp mate-abstract.xml.in

MAINTAINERCLEANFILES = \
	Makefile.in

-include $(top_srcdir)/git.mk
