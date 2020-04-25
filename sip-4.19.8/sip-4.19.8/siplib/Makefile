TARGET = sip.pyd
OFILES = siplib.obj apiversions.obj descriptors.obj qtlib.obj threads.obj objmap.obj voidptr.obj array.obj int_convertors.obj bool.obj
HFILES = sip.h sipint.h array.h 

CC = cl
CXX = cl
LINK = link
CPPFLAGS = -DNDEBUG -DUNICODE -DWIN32 -I. -IC:\Users\Daniil\AppData\Local\Programs\Python\Python35\include
CFLAGS = -nologo -Zm200 -Zc:wchar_t- -FS -Zc:strictStrings -O2 -MD -W3 -w44456 -w44457 -w44458
CXXFLAGS = -nologo -Zm200 -Zc:wchar_t- -FS -Zc:strictStrings -D_HAS_EXCEPTIONS=0 -O2 -MD -W3 -w34100 -w34189 -w44996 -w44456 -w44457 -w44458 -wd4577
LFLAGS = /NOLOGO /DYNAMICBASE /NXCOMPAT /DLL /MANIFEST /MANIFESTFILE:$(TARGET).manifest /SUBSYSTEM:CONSOLE /INCREMENTAL:NO
LIBS = /LIBPATH:C:\Users\Daniil\AppData\Local\Programs\Python\Python35\libs python35.lib
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
	mt -nologo -manifest $(TARGET).manifest -outputresource:$(TARGET);2

install: $(TARGET)
	@if not exist C:\Users\Daniil\AppData\Local\Programs\Python\Python35\Lib\site-packages mkdir C:\Users\Daniil\AppData\Local\Programs\Python\Python35\Lib\site-packages
	copy /y $(TARGET) C:\Users\Daniil\AppData\Local\Programs\Python\Python35\Lib\site-packages\$(TARGET)
	@if not exist C:\Users\Daniil\AppData\Local\Programs\Python\Python35\include mkdir C:\Users\Daniil\AppData\Local\Programs\Python\Python35\include
	copy /y C:\Users\Daniil\Desktop\sip-4.19.8\sip-4.19.8\siplib\sip.h C:\Users\Daniil\AppData\Local\Programs\Python\Python35\include\sip.h
	@if not exist C:\Users\Daniil\AppData\Local\Programs\Python\Python35\Lib\site-packages mkdir C:\Users\Daniil\AppData\Local\Programs\Python\Python35\Lib\site-packages
	copy /y C:\Users\Daniil\Desktop\sip-4.19.8\sip-4.19.8\sip.pyi C:\Users\Daniil\AppData\Local\Programs\Python\Python35\Lib\site-packages\sip.pyi

clean:
	-del $(TARGET)
	-del siplib.obj
	-del apiversions.obj
	-del descriptors.obj
	-del qtlib.obj
	-del threads.obj
	-del objmap.obj
	-del voidptr.obj
	-del array.obj
	-del int_convertors.obj
	-del bool.obj
	-del $(TARGET).manifest
