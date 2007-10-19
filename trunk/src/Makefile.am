CSFLAGS =               \
        -debug          \
        -define:DEBUG   \
        -target:library

ASSEMBLY = TracPlugin.dll
SOURCES = \
	$(srcdir)/TracPlugin.cs.in

ASSEMBLY_REFERENCES = \
	$(TOMBOY_LIBS) 	\
	-r:Mono.Posix 	\
	-r:/usr/lib/pkgconfig/../../lib/mono/gtk-sharp-2.0/gnome-sharp.dll

plugindir = $(PLUGINDIR)
plugin_SCRIPTS = $(ASSEMBLY) $(ASSEMBLY).mdb

ASSEMBLY_RESOURCES = stock_bug.png

all: $(ASSEMBLY)

$(ASSEMBLY): $(SOURCES)
	sed -e "s|\@VERSION\@|$(VERSION)|" TracPlugin.cs.in > TracPlugin.cs
	$(MCS) -out:$(ASSEMBLY) $(CSFLAGS) $(ASSEMBLY_REFERENCES) -resource:$(ASSEMBLY_RESOURCES) TracPlugin.cs

EXTRA_DIST = $(SOURCES) $(ASSEMBLY_RESOURCES)
CLEANFILES = $(ASSEMBLY) $(ASSEMBLY).mdb 
DISTCLEANFILES = Makefile.in 

