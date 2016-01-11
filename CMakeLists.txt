cmake_minimum_required (VERSION 3.0)

project(go_cc)

include_directories(include src/cmd/6c src/cmd/6l)
add_definitions(-DGOOS="darwin" -DGOARCH="amd64" -DGOROOT="." -DGOVERSION="1.4.2" -DGOARM="6" -DGO386="sse2" -DGO_EXTLINK_ENABLED="1")

set (LIB9_SRC
src/lib9/_exits.c
src/lib9/_p9dir.c
src/lib9/atoi.c
src/lib9/await.c
src/lib9/cleanname.c
src/lib9/create.c
src/lib9/ctime.c
src/lib9/dirfstat.c
src/lib9/dirfwstat.c
src/lib9/dirstat.c
src/lib9/dirwstat.c
src/lib9/dup.c
src/lib9/errstr.c
src/lib9/exec.c
src/lib9/execl.c
src/lib9/exitcode.c
src/lib9/exits.c
src/lib9/flag.c
src/lib9/fmtlock2.c
src/lib9/getenv.c
src/lib9/getfields.c
src/lib9/getwd.c
src/lib9/goos.c
src/lib9/jmp.c
src/lib9/main.c
src/lib9/nan.c
src/lib9/notify.c
src/lib9/nulldir.c
src/lib9/open.c
src/lib9/readn.c
src/lib9/rfork.c
src/lib9/run_unix.c
src/lib9/seek.c
src/lib9/strecpy.c
src/lib9/sysfatal.c
src/lib9/tempdir_unix.c
src/lib9/time.c
src/lib9/tokenize.c
src/lib9/fmt/charstod.c
src/lib9/fmt/dofmt.c
src/lib9/fmt/dorfmt.c
src/lib9/fmt/errfmt.c
src/lib9/fmt/fltfmt.c
src/lib9/fmt/fmt.c
src/lib9/fmt/fmtdef.h
src/lib9/fmt/fmtfd.c
src/lib9/fmt/fmtfdflush.c
src/lib9/fmt/fmtlocale.c
src/lib9/fmt/fmtlock.c
src/lib9/fmt/fmtnull.c
src/lib9/fmt/fmtprint.c
src/lib9/fmt/fmtquote.c
src/lib9/fmt/fmtrune.c
src/lib9/fmt/fmtstr.c
src/lib9/fmt/fmtvprint.c
src/lib9/fmt/fprint.c
src/lib9/fmt/nan64.c
src/lib9/fmt/pow10.c
src/lib9/fmt/print.c
src/lib9/fmt/seprint.c
src/lib9/fmt/smprint.c
src/lib9/fmt/snprint.c
src/lib9/fmt/sprint.c
src/lib9/fmt/strtod.c
src/lib9/fmt/test.c
src/lib9/fmt/vfprint.c
src/lib9/fmt/vseprint.c
src/lib9/fmt/vsmprint.c
src/lib9/fmt/vsnprint.c
src/lib9/utf/rune.c
src/lib9/utf/runetypebody-6.3.0.h
src/lib9/utf/utfdef.h
src/lib9/utf/utflen.c
src/lib9/utf/utfrrune.c
src/lib9/utf/utfutf.c
src/lib9/utf/mkrunetype.c
src/lib9/utf/runetype.c
src/lib9/utf/utf.h
src/lib9/utf/utfecpy.c
src/lib9/utf/utfnlen.c
src/lib9/utf/utfrune.c
)

set (LIBBIO_SRC
src/libbio/bfildes.c
src/libbio/bgetc.c
src/libbio/bgetrune.c
src/libbio/boffset.c
src/libbio/bputc.c
src/libbio/brdline.c
src/libbio/bread.c
src/libbio/bwrite.c
src/libbio/bbuffered.c
src/libbio/bflush.c
src/libbio/bgetd.c
src/libbio/binit.c
src/libbio/bprint.c
src/libbio/bputrune.c
src/libbio/brdstr.c
src/libbio/bseek.c
)

set (LIBLINK_SRC
src/liblink/anames6.c
src/liblink/asm6.c
src/liblink/list6.c
src/liblink/obj6.c
#src/liblink/anames5.c
#src/liblink/asm5.c
#src/liblink/list5.c
#src/liblink/obj5.c
#src/liblink/anames8.c
#src/liblink/asm8.c
#src/liblink/list8.c
#src/liblink/obj8.c
src/liblink/objfile.c
src/liblink/pass.c
src/liblink/pcln.c
src/liblink/sym.c
src/liblink/data.c
src/liblink/go.c
src/liblink/ld.c
src/liblink/obj.c
)

set (LIB6C_SRC
src/cmd/6c/cgen.c
src/cmd/6c/div.c
src/cmd/6c/gc.h
src/cmd/6c/list.c
src/cmd/6c/machcap.c
src/cmd/6c/mul.c
src/cmd/6c/peep.c
src/cmd/6c/reg.c
src/cmd/6c/sgen.c
src/cmd/6c/swt.c
src/cmd/6c/txt.c
src/cmd/cc/cc.h
src/cmd/cc/bits.c
src/cmd/cc/com64.c
src/cmd/cc/com.c
src/cmd/cc/funct.c
src/cmd/cc/lex.c
src/cmd/cc/mac.c
#src/cmd/cc/omachcap.c
src/cmd/cc/sub.c
src/cmd/cc/y.tab.h
src/cmd/cc/acid.c
src/cmd/cc/cc.h
src/cmd/cc/dcl.c
src/cmd/cc/dpchk.c
src/cmd/cc/godefs.c
src/cmd/cc/scon.c
src/cmd/cc/y.tab.c
src/cmd/cc/pgen.c
src/cmd/cc/pswt.c
)

set(LIB6L_SRC
src/cmd/6l/6.out.h
src/cmd/6l/asm.c
src/cmd/6l/l.h
src/cmd/6l/list.c
src/cmd/6l/obj.c
src/cmd/ld/data.c
src/cmd/ld/dwarf.h
src/cmd/ld/elf.c
src/cmd/ld/go.c
src/cmd/ld/ldmacho.c
src/cmd/ld/lib.c
src/cmd/ld/macho.c
src/cmd/ld/pcln.c
src/cmd/ld/pe.h
src/cmd/ld/symtab.c
src/cmd/ld/decodesym.c
src/cmd/ld/dwarf.c
src/cmd/ld/dwarf_defs.h
src/cmd/ld/elf.h
src/cmd/ld/ldelf.c
src/cmd/ld/ldpe.c
src/cmd/ld/lib.h
src/cmd/ld/macho.h
src/cmd/ld/pe.c
src/cmd/ld/pobj.c
src/cmd/ld/textflag.h
)

set(LIB6A_SRC
src/cmd/6a/a.h
src/cmd/6a/lex.c
src/cmd/6a/y.tab.h
src/cmd/6a/y.tab.c
)

add_library(lib9 ${LIB9_SRC})
add_library(libbio ${LIBBIO_SRC})
add_library(liblink ${LIBLINK_SRC})
add_executable(6c ${LIB6C_SRC})
target_link_libraries(6c lib9 libbio liblink)

add_executable(6l ${LIB6L_SRC})
target_link_libraries(6l lib9 libbio liblink)

add_executable(6a ${LIB6A_SRC})
target_link_libraries(6a lib9 libbio liblink)
