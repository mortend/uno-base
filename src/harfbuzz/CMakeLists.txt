if (LINUX)
    return()
endif()

set(DIR ${PROJECT_SOURCE_DIR}/3rdparty/harfbuzz/src)
include_directories(${DIR}/hb-ucdn)
include_directories(${PROJECT_SOURCE_DIR}/3rdparty/freetype2/include)
add_definitions(-DHAVE_OT -DHAVE_FALLBACK -DHAVE_ATEXIT -DHAVE_ISATTY -DHAVE_ROUND -DHAVE_STDBOOL_H -DHAVE_FREETYPE=1 -DHAVE_UCDN -DHAVE_INTEL_ATOMIC_PRIMITIVES)

file(COPY ${DIR}/hb-blob.h            DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-buffer.h          DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-common.h          DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-coretext.h        DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-deprecated.h      DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-directwrite.h     DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-face.h            DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-font.h            DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-ft.h              DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-glib.h            DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-gobject-structs.h DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-gobject.h         DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-graphite2.h       DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-icu.h             DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-map.h             DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-ot-font.h         DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-ot-layout.h       DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-ot-math.h         DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-ot-shape.h        DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-ot-tag.h          DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-ot-var.h          DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-ot.h              DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-set.h             DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-shape-plan.h      DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-shape.h           DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-subset.h          DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-unicode.h         DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-uniscribe.h       DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb-version.h         DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)
file(COPY ${DIR}/hb.h                 DESTINATION ${PROJECT_SOURCE_DIR}/include/harfbuzz)

add_library(harfbuzz STATIC
    ${DIR}/hb-atomic-private.hh
    ${DIR}/hb-blob-private.hh
    ${DIR}/hb-blob.cc
    ${DIR}/hb-buffer-private.hh
    ${DIR}/hb-buffer-serialize.cc
    ${DIR}/hb-buffer.cc
    ${DIR}/hb-common.cc
    ${DIR}/hb-debug.hh
    ${DIR}/hb-dsalgs.hh
    ${DIR}/hb-face-private.hh
    ${DIR}/hb-face.cc
    ${DIR}/hb-font-private.hh
    ${DIR}/hb-font.cc
    ${DIR}/hb-map-private.hh
    ${DIR}/hb-map.cc
    ${DIR}/hb-mutex-private.hh
    ${DIR}/hb-object-private.hh
    ${DIR}/hb-open-file-private.hh
    ${DIR}/hb-open-type-private.hh
    ${DIR}/hb-ot-color-cbdt-table.hh
    ${DIR}/hb-ot-cmap-table.hh
    ${DIR}/hb-ot-glyf-table.hh
    ${DIR}/hb-ot-hdmx-table.hh
    ${DIR}/hb-ot-head-table.hh
    ${DIR}/hb-ot-hhea-table.hh
    ${DIR}/hb-ot-hmtx-table.hh
    ${DIR}/hb-ot-kern-table.hh
    ${DIR}/hb-ot-maxp-table.hh
    ${DIR}/hb-ot-name-table.hh
    ${DIR}/hb-ot-os2-table.hh
    ${DIR}/hb-ot-os2-unicode-ranges.hh
    ${DIR}/hb-ot-post-macroman.hh
    ${DIR}/hb-ot-post-table.hh
    ${DIR}/hb-ot-tag.cc
    ${DIR}/hb-private.hh
    ${DIR}/hb-set-digest-private.hh
    ${DIR}/hb-set-private.hh
    ${DIR}/hb-set.cc
    ${DIR}/hb-shape.cc
    ${DIR}/hb-shape-plan-private.hh
    ${DIR}/hb-shape-plan.cc
    ${DIR}/hb-shaper-list.hh
    ${DIR}/hb-shaper-impl-private.hh
    ${DIR}/hb-shaper-private.hh
    ${DIR}/hb-shaper.cc
    ${DIR}/hb-static.cc
    ${DIR}/hb-string-array.hh
    ${DIR}/hb-unicode-private.hh
    ${DIR}/hb-unicode.cc
    ${DIR}/hb-utf-private.hh
    ${DIR}/hb-warning.cc
    ${DIR}/hb-buffer-deserialize-json.hh
    ${DIR}/hb-buffer-deserialize-text.hh
    ${DIR}/hb-fallback-shape.cc
    ${DIR}/hb-aat-layout.cc
    ${DIR}/hb-aat-layout-common-private.hh
    ${DIR}/hb-aat-layout-ankr-table.hh
    ${DIR}/hb-aat-layout-bsln-table.hh
    ${DIR}/hb-aat-layout-feat-table.hh
    ${DIR}/hb-aat-layout-kerx-table.hh
    ${DIR}/hb-aat-layout-morx-table.hh
    ${DIR}/hb-aat-layout-trak-table.hh
    ${DIR}/hb-aat-layout-private.hh
    ${DIR}/hb-aat-fmtx-table.hh
    ${DIR}/hb-aat-gcid-table.hh
    ${DIR}/hb-aat-ltag-table.hh
    ${DIR}/hb-ot-font.cc
    ${DIR}/hb-ot-layout.cc
    ${DIR}/hb-ot-layout-base-table.hh
    ${DIR}/hb-ot-layout-common-private.hh
    ${DIR}/hb-ot-layout-gdef-table.hh
    ${DIR}/hb-ot-layout-gpos-table.hh
    ${DIR}/hb-ot-layout-gsubgpos-private.hh
    ${DIR}/hb-ot-layout-gsub-table.hh
    ${DIR}/hb-ot-layout-jstf-table.hh
    ${DIR}/hb-ot-layout-private.hh
    ${DIR}/hb-ot-color.cc
    ${DIR}/hb-ot-color-colr-table.hh
    ${DIR}/hb-ot-color-cpal-table.hh
    ${DIR}/hb-ot-color-sbix-table.hh
    ${DIR}/hb-ot-color-svg-table.hh
    ${DIR}/hb-ot-map.cc
    ${DIR}/hb-ot-map-private.hh
    ${DIR}/hb-ot-math.cc
    ${DIR}/hb-ot-math-table.hh
    ${DIR}/hb-ot-shape.cc
    ${DIR}/hb-ot-shape-complex-arabic.cc
    ${DIR}/hb-ot-shape-complex-arabic-fallback.hh
    ${DIR}/hb-ot-shape-complex-arabic-private.hh
    ${DIR}/hb-ot-shape-complex-arabic-table.hh
    ${DIR}/hb-ot-shape-complex-arabic-win1256.hh
    ${DIR}/hb-ot-shape-complex-default.cc
    ${DIR}/hb-ot-shape-complex-hangul.cc
    ${DIR}/hb-ot-shape-complex-hebrew.cc
    ${DIR}/hb-ot-shape-complex-indic.cc
    ${DIR}/hb-ot-shape-complex-indic-private.hh
    ${DIR}/hb-ot-shape-complex-indic-table.cc
    ${DIR}/hb-ot-shape-complex-khmer-private.hh
    ${DIR}/hb-ot-shape-complex-khmer.cc
    ${DIR}/hb-ot-shape-complex-myanmar-private.hh
    ${DIR}/hb-ot-shape-complex-myanmar.cc
    ${DIR}/hb-ot-shape-complex-thai.cc
    ${DIR}/hb-ot-shape-complex-tibetan.cc
    ${DIR}/hb-ot-shape-complex-use.cc
    ${DIR}/hb-ot-shape-complex-use-private.hh
    ${DIR}/hb-ot-shape-complex-use-table.cc
    ${DIR}/hb-ot-shape-complex-private.hh
    ${DIR}/hb-ot-shape-normalize-private.hh
    ${DIR}/hb-ot-shape-normalize.cc
    ${DIR}/hb-ot-shape-fallback-private.hh
    ${DIR}/hb-ot-shape-fallback.cc
    ${DIR}/hb-ot-shape-private.hh
    ${DIR}/hb-ot-var.cc
    ${DIR}/hb-ot-var-avar-table.hh
    ${DIR}/hb-ot-var-fvar-table.hh
    ${DIR}/hb-ot-var-hvar-table.hh
    ${DIR}/hb-ot-var-mvar-table.hh
    ${DIR}/hb-ot-shape-complex-indic-machine.hh
    ${DIR}/hb-ot-shape-complex-khmer-machine.hh
    ${DIR}/hb-ot-shape-complex-myanmar-machine.hh
    ${DIR}/hb-ot-shape-complex-use-machine.hh
    ${DIR}/hb-ft.cc
    ${DIR}/hb-ucdn.cc
    ${DIR}/hb-ucdn/ucdn.h
    ${DIR}/hb-ucdn/ucdn.c
    ${DIR}/hb-ucdn/ucdn_db.h
    ${DIR}/hb.h
    ${DIR}/hb-blob.h
    ${DIR}/hb-buffer.h
    ${DIR}/hb-common.h
    ${DIR}/hb-deprecated.h
    ${DIR}/hb-face.h
    ${DIR}/hb-font.h
    ${DIR}/hb-map.h
    ${DIR}/hb-set.h
    ${DIR}/hb-shape.h
    ${DIR}/hb-shape-plan.h
    ${DIR}/hb-unicode.h
    ${DIR}/hb-version.h
    ${DIR}/hb-ot.h
    ${DIR}/hb-ot-font.h
    ${DIR}/hb-ot-layout.h
    ${DIR}/hb-ot-math.h
    ${DIR}/hb-ot-shape.h
    ${DIR}/hb-ot-tag.h
    ${DIR}/hb-ot-var.h
    ${DIR}/hb-ft.h)
