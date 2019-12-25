# Description:
#   A Massively Spiffy Yet Delicately Unobtrusive Compression Library.

licenses(["notice"])  # BSD 3-Clause

load("@rules_pcl//bzl:pcl.bzl", "pcl_library")

exports_files(["pcl_config.h.in"])

pcl_library(
    name = "2d",
    exclude_srcs = ["2d/src/examples.cpp"],
    deps = [
        ":common",
        ":filters",
        "@boost//:smart_ptr",
    ],
)

pcl_library(
    name = "common",
    deps = [
        "@//:pcl_config",
        "@boost//:algorithm",
        "@boost//:date_time",
        "@boost//:filesystem",
        "@boost//:fusion",
        "@boost//:mpl",
        "@boost//:preprocessor",
        "@boost//:smart_ptr",
        "@boost//:signals2",
        "@eigen//:eigen",
    ],
)

pcl_library(
    name = "features",
    deps = [
        ":2d",
        ":common",
        ":filters",
        ":kdtree",
        ":octree",
        ":search",
        "@boost//:bind",
        "@boost//:function",
        "@boost//:graph",
        "@boost//:property_map",
        "@boost//:random",
        "@boost//:smart_ptr",
        "@boost//:unordered",
        "@eigen//:eigen",
    ],
)

pcl_library(
    name = "filters",
    deps = [
        ":common",
        ":sample_consensus",
        ":kdtree",
        ":octree",
        ":search",
        "@boost//:bind",
        "@boost//:dynamic_bitset",
        "@boost//:function",
        "@boost//:fusion",
        "@boost//:mpl",
        "@boost//:optional",
        "@boost//:random",
        "@boost//:smart_ptr",
        "@boost//:unordered",
        "@eigen//:eigen",
    ],
)

pcl_library(
    name = "geometry",
    deps = [
        ":common",
        "@boost//:concept_check",
        "@boost//:operators",
        "@boost//:smart_ptr",
        "@boost//:type_traits",
        "@boost//:version",
        "@eigen//:eigen",
    ],
)

pcl_library(
    name = "ml",
    deps = [
        ":common",
        "@eigen//:eigen",
    ],
)

# TODO(kgreenek): This one is going to be hard because it depends on a lot of the external
# dependencies above that aren't supported yet. For now, just exclude everything that has external
# dependencies. We'll probably need a macro to set the dependencies based on what external
# dependencies the user has enabled via the call to pcl_config. Alternatively, we may be able to
# break this out into a bunch of individual targets that can be selectively created / enabled in the
# pcl_config macro.

# Depends on David SDK and VTK.
IO_DAVIDSDK_SRCS = ["io/src/davidsdk_grabber.cpp"]
IO_DAVIDSDK_HDRS = ["io/include/pcl/io/davidsdk_grabber.h"]

IO_DEPTH_SENSE_SRCS = [
    "io/src/depth_sense/**",
    "io/src/depth_sense_grabber.cpp",
]
IO_DEPTH_SENSE_HDRS = [
    "io/include/pcl/io/depth_sense/**",
    "io/include/pcl/io/depth_sense_grabber.h",
]

# NOTE: These only depend on libusb-1.0.
IO_DINAST_SRCS = ["io/src/dinast_grabber.cpp"]
IO_DINAST_HDRS = ["io/include/pcl/io/dinast_grabber.h"]

IO_ENSENSO_SRCS = ["io/src/ensenso_grabber.cpp"]
IO_ENSENSO_HDRS = ["io/include/pcl/io/ensenso_grabber.h"]

IO_FZAPI_SRCS = ["io/src/fotonic_grabber.cpp"]
IO_FZAPI_HDRS = ["io/include/pcl/io/fotonic_grabber.h"]

IO_OPENNI_SRCS = [
    "io/src/oni_grabber.cpp",
    "io/src/openni_camera/**",
    "io/src/openni_grabber.cpp",
]
IO_OPENNI_HDRS = [
    "io/include/pcl/io/oni_grabber.h",
    "io/include/pcl/io/openni_camera/**",
    "io/include/pcl/io/openni_grabber.h",
]

IO_OPENNI2_SRCS = [
    "io/src/openni2/**",
    "io/src/openni2_grabber.cpp",
]
IO_OPENNI2_HDRS = [
    "io/include/pcl/io/openni2/**",
    "io/include/pcl/io/openni2_grabber.h",
]

IO_REAL_SENSE_SRCS = [
    "io/src/real_sense/**",
    "io/src/real_sense_grabber.cpp",
]
IO_REAL_SENSE_HDRS = [
    "io/include/pcl/io/depth_sense/**",
    "io/include/pcl/io/depth_sense_grabber.h",
]

IO_VTK_SRCS = [
    "io/src/png_io.cpp",
    "io/src/vtk_lib_io.cpp",
]
IO_VTK_HDRS = [
    "io/include/pcl/io/impl/vtk_lib_io.hpp",
    "io/include/pcl/io/png_io.h",
    "io/include/pcl/io/vtk_lib_io.h",
]

pcl_library(
    name = "io",
    exclude_srcs =
        IO_DAVIDSDK_SRCS +
        IO_DEPTH_SENSE_SRCS +
        IO_DINAST_SRCS +
        IO_ENSENSO_SRCS +
        IO_FZAPI_SRCS +
        IO_OPENNI_SRCS +
        IO_OPENNI2_SRCS +
        IO_REAL_SENSE_SRCS +
        IO_VTK_SRCS,
    exclude_hdrs =
        IO_DAVIDSDK_HDRS +
        IO_DEPTH_SENSE_HDRS +
        IO_DINAST_HDRS +
        IO_ENSENSO_HDRS +
        IO_FZAPI_HDRS +
        IO_OPENNI_HDRS +
        IO_OPENNI2_HDRS +
        IO_REAL_SENSE_HDRS +
        IO_VTK_HDRS,
    deps = [
        ":common",
        ":octree",
        "@boost//:algorithm",
        "@boost//:asio",
        "@boost//:bind",
        "@boost//:chrono",
        "@boost//:circular_buffer",
        "@boost//:cstdint",
        "@boost//:date_time",
        "@boost//:detail",
        "@boost//:filesystem",
        "@boost//:foreach",
        "@boost//:function",
        "@boost//:interprocess",
        "@boost//:lexical_cast",
        "@boost//:mpl",
        "@boost//:numeric_conversion",
        "@boost//:signals2",
        "@boost//:smart_ptr",
        "@boost//:thread",
        "@boost//:tokenizer",
        "@boost//:tuple",
        "@boost//:utility",
        "@boost//:version",
        "@org_libpng_libpng//:libpng",
    ],
)

pcl_library(
    name = "kdtree",
    deps = [
        ":common",
        # TODO flann. Seems to work anyway?
        "@boost//:smart_ptr",
    ],
)

pcl_library(
    name = "keypoints",
    deps = [
        ":common",
        ":features",
        ":octree",
        "@//:pcl_config",
        "@boost//:bind",
        "@boost//:function",
        "@boost//:smart_ptr",
        "@eigen//:eigen",
    ],
)

pcl_library(
    name = "octree",
    deps = [
        ":common",
        "@boost//:bind",
        "@boost//:smart_ptr",
        "@eigen//:eigen",
    ],
)

pcl_library(
    name = "recognition",
    deps = [
        ":common",
        ":features",
        ":io",
        ":ml",
        ":registration",
        ":search",
        "@boost//:algorithm",
        "@boost//:bind",
        "@boost//:filesystem",
        "@boost//:graph",
        "@boost//:random",
        "@boost//:smart_ptr",
        "@boost//:tuple",
        "@boost//:unordered",
        "@eigen//:eigen",
    ],
)

pcl_library(
    name = "registration",
    exclude_srcs = ["registration/src/pairwise_graph_registration.cpp"],
    deps = [
        ":common",
        ":features",
        ":filters",
        ":kdtree",
        ":octree",
        ":sample_consensus",
        ":search",
        "@boost//:accumulators",
        "@boost//:bind",
        "@boost//:core",
        "@boost//:function",
        "@boost//:graph",
        "@boost//:property_map",
        "@boost//:smart_ptr",
        "@boost//:tuple",
        "@boost//:unordered",
        "@eigen//:eigen",
    ],
)

pcl_library(
    name = "sample_consensus",
    deps = [
        ":common",
        ":search",
        "@//:pcl_config",
        "@boost//:math",
        "@boost//:random",
        "@boost//:smart_ptr",
        "@eigen//:eigen",
    ],
)

pcl_library(
    name = "search",
    deps = [
        ":common",
        ":kdtree",
        ":octree",
        # TODO flann. Seems to work anyway?
        "@boost//:smart_ptr",
    ],
)
