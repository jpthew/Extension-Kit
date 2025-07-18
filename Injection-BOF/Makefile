all: bof

bof:
	@(mkdir _bin 2>/dev/null) && echo 'creating _bin directory' || echo '_bin directory exists'
	@(x86_64-w64-mingw32-gcc -I _include -masm=intel -Wall -Os -c inject_cfg/inject_cfg.c -o _bin/inject_cfg.x64.o && x86_64-w64-mingw32-strip --strip-unneeded _bin/inject_cfg.x64.o) && echo '[*] inject_cfg' || echo '[X] inject_cfg'
	@(x86_64-w64-mingw32-gcc -w -Wno-int-conversion -Wno-incompatible-pointer-types -I _include -Os -c inject_sec/inject_sec.c -o _bin/inject_sec.x64.o -DBOF && x86_64-w64-mingw32-strip --strip-unneeded _bin/inject_sec.x64.o) && echo '[*] inject_sec' || echo '[X] inject_sec'
	@(x86_64-w64-mingw32-gcc -w -Wno-int-conversion -Wno-incompatible-pointer-types -I _include -Os -c inject_pp/Varient_4.c -o _bin/inject_pp_4.x64.o -DBOF && x86_64-w64-mingw32-strip --strip-unneeded _bin/inject_pp_4.x64.o) && echo '[*] inject_pp_4' || echo '[*] inject_pp_4'
	@(x86_64-w64-mingw32-gcc -w -Wno-int-conversion -Wno-incompatible-pointer-types -I _include -Os -c inject_pp/Varient_5.c -o _bin/inject_pp_5.x64.o -DBOF && x86_64-w64-mingw32-strip --strip-unneeded _bin/inject_pp_5.x64.o) && echo '[*] inject_pp_5' || echo '[*] inject_pp_5'
	@(x86_64-w64-mingw32-gcc -w -Wno-int-conversion -Wno-incompatible-pointer-types -I _include -Os -c inject_pp/Varient_6.c -o _bin/inject_pp_6.x64.o -DBOF && x86_64-w64-mingw32-strip --strip-unneeded _bin/inject_pp_6.x64.o) && echo '[*] inject_pp_6' || echo '[*] inject_pp_6'
	@(x86_64-w64-mingw32-gcc -w -Wno-int-conversion -Wno-incompatible-pointer-types -I _include -Os -c inject_pp/Varient_7.c -o _bin/inject_pp_7.x64.o -DBOF && x86_64-w64-mingw32-strip --strip-unneeded _bin/inject_pp_7.x64.o) && echo '[*] inject_pp_7' || echo '[*] inject_pp_7'
	@(x86_64-w64-mingw32-gcc -w -Wno-int-conversion -Wno-incompatible-pointer-types -I _include -Os -c inject_pp/Varient_8.c -o _bin/inject_pp_8.x64.o -DBOF && x86_64-w64-mingw32-strip --strip-unneeded _bin/inject_pp_8.x64.o) && echo '[*] inject_pp_8' || echo '[*] inject_pp_8'

clean:
	rm _bin/*