load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")
load("@bazel_gazelle//:def.bzl", "gazelle")

# gazelle:prefix github.com/example/project
gazelle(name = "gazelle")

go_library(
    name = "go_default_library",
    srcs = [
        "file.go",
        "image.go",
        "metadata.go",
        "options.go",
        "resize.go",
        "resize_legacy.go",
        "resizer.go",
        "type.go",
        "version.go",
        "vips.go",
        "vips.h",
    ],
    cgo = True,
    copts = [
	    "-I/usr/include/glib-2.0",
	    ],
    clinkopts = [
	        "-L/usr/local/lib",
		"-lvips",
		"-lgobject-2.0",
	        "-lglib-2.0",
	        ],
    importpath = "github.com/example/project",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "file_test.go",
        "image_test.go",
        "metadata_test.go",
        "resizer_test.go",
        "type_test.go",
        "vips_test.go",
    ],
    data = glob(["testdata/**"]),
    embed = [":go_default_library"],
)
