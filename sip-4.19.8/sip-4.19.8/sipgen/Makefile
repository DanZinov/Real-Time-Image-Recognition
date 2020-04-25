TARGET = sip.exe
OFILES = main.obj transform.obj gencode.obj extracts.obj export.obj type_hints.obj heap.obj parser.obj lexer.obj
HFILES = sip.h parser.h

CC = cl
CXX = cl
LINK = link
CPPFLAGS = -DNDEBUG -DUNICODE -DWIN32 -I.
CFLAGS = -nologo -Zm200 -Zc:wchar_t- -FS -Zc:strictStrings -O2 -MD -W3 -w44456 -w44457 -w44458
CXXFLAGS = -nologo -Zm200 -Zc:wchar_t- -FS -Zc:strictStrings -D_HAS_EXCEPTIONS=0 -O2 -MD -W3 -w34100 -w34189 -w44996 -w44456 -w44457 -w44458 -wd4577
LFLAGS = /NOLOGO /DYNAMICBASE /NXCOMPAT /INCREMENTAL:NO /MANIFEST /MANIFESTFILE:$(TARGET).manifest /SUBSYSTEM:CONSOLE
LIBS = 
.SUFFIXES: .c .cpp .cc .cxx .C


{.}.cpp{}.obj::
	$(CXX) -c $(CXXFLAGS) $(CPPFLAGS) -Fo @<<
	$<
<<

{.}.cc{}.obj::
	$(CXX) -c $(CXXFLAGS) $(CPPFLAGS) -Fo @<<
	$<
<<

{.}.cxx{}.obj::
	$(CXX) -c $(CXXFLAGS) $(CPPFLAGS) -Fo @<<
	$<
<<

{.}.C{}.obj::
	$(CXX) -c $(CXXFLAGS) $(CPPFLAGS) -Fo @<<
	$<
<<

{.}.c{}.obj::
	$(CC) -c $(CFLAGS) $(CPPFLAGS) -Fo @<<
	$<
<<

all: $(TARGET)

$(OFILES): $(HFILES)

$(TARGET): $(OFILES)
	$(LINK) $(LFLAGS) /OUT:$(TARGET) @<<
	  $(OFILES) $(LIBS)
<<
	mt -nologo -manifest $(TARGET).manifest -outputresource:$(TARGET);1

install: $(TARGET)
	@if not exist C:\Users\Daniil\AppData\Local\Programs\Python\Python35 mkdir C:\Users\Daniil\AppData\Local\Programs\Python\Python35
	copy /y $(TARGET) C:\Users\Daniil\AppData\Local\Programs\Python\Python35\$(TARGET)

clean:
	-del $(TARGET)
	-del main.obj
	-del transform.obj
	-del gencode.obj
	-del extracts.obj
	-del export.obj
	-del type_hints.obj
	-del heap.obj
	-del parser.obj
	-del lexer.obj
	-del $(TARGET).manifest
