# File intended only to be ran with GNU make. Use any other make program at your own risk!
OUTPUT := lc3test
WXCPPFLAGS := $(shell wx-config --cppflags)
WXCPPLIBS := $(shell wx-config --libs)
CPPFLAGS := -Wall -O3 -s -I../liblc3 -I. $(WXCPPFLAGS)
LDFLAGS := -O3 -Wall -s -rdynamic -L../liblc3
LDLIBS := -llc3 $(WXCPPLIBS)
CC := g++ $(ARCH_FLAGS)
CXX := $(CC)
RM := rm
INSTALL := install
FILES := main.o XmlTestParser.o

$(OUTPUT) : $(FILES)
	$(CC) $(LDFLAGS) $^ -o $(OUTPUT) $(LDLIBS)

clean : 
	$(RM) -rf *.o $(OUTPUT)

install : $(OUTPUT)
	$(INSTALL) -m 0755 $(OUTPUT) $(PREFIX)/bin

uninstall :
	$(RM) -rf $(PREFIX)/bin/$(OUTPUT)
