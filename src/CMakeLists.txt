list(APPEND sparkey_headers
  "buf.h"
  "endiantools.h"
  "hashalgorithms.h"
  "hashheader.h"
  "hashiter.h"
  "logheader.h"
  "MurmurHash3.h"
  "sparkey-internal.h"
  "util.h"
)

list(APPEND sparkey_sources
  "buf.c"
  "compress.c"
  "endiantools.c"
  "hashalgorithms.c"
  "hashheader.c"
  "hashiter.c"
  "hashreader.c"
  "hashwriter.c"
  "logheader.c"
  "logreader.c"
  "logwriter.c"
  "MurmurHash3.c"
  "returncodes.c"
  "util.c"
)

add_library(libsparkey INTERFACE)
target_include_directories(libsparkey INTERFACE "${PROJECT_SOURCE_DIR}/src/include")
target_sources(libsparkey INTERFACE ${sparkey_sources})
target_link_libraries(libsparkey INTERFACE c rt snappy zstd)

add_executable(sparkey "main.c")
target_link_libraries(sparkey PRIVATE libsparkey)
