# Description:
#   Skydoc is a documentation generator for skylark files.
#
#   It is currently experimental and in development.
#
# Usage:
# skydoc <target_file> <output_file>

package(
    default_visibility = ["//src:__subpackages__"],
)

licenses(["notice"])  # Apache 2.0

filegroup(
    name = "srcs",
    srcs = glob(["**"]) + [
        "//src/main/java/com/google/devtools/build/skydoc/fakebuildapi:srcs",
        "//src/main/java/com/google/devtools/build/skydoc/rendering:srcs",
    ],
)

java_binary(
    name = "skydoc",
    main_class = "com.google.devtools.build.skydoc.SkydocMain",
    runtime_deps = [
        ":skydoc_lib",
    ],
)

java_library(
    name = "skydoc_lib",
    srcs = glob(["*.java"]),
    deps = [
        "//src/main/java/com/google/devtools/build/lib:events",
        "//src/main/java/com/google/devtools/build/lib:syntax",
        "//src/main/java/com/google/devtools/build/lib/skylarkbuildapi",
        "//src/main/java/com/google/devtools/build/lib/vfs:pathfragment",
        "//src/main/java/com/google/devtools/build/skydoc/fakebuildapi",
        "//src/main/java/com/google/devtools/build/skydoc/rendering",
        "//third_party:guava",
        "//third_party:jsr305",
    ],
)
