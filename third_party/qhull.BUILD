# Description:
#   Convex hull, Delaunay triangulation, Voronoi diagrams, Halfspace intersection.

licenses(["notice"])  # BSD/MIT-like license

package(
    default_visibility = ["//visibility:public"],
)

cc_library(
    name = "libqhull",
    srcs = [
        "src/libqhull/global.c",
        "src/libqhull/stat.c",
        "src/libqhull/geom2.c",
        "src/libqhull/poly2.c",
        "src/libqhull/merge.c",
        "src/libqhull/libqhull.c",
        "src/libqhull/geom.c",
        "src/libqhull/poly.c",
        "src/libqhull/qset.c",
        "src/libqhull/mem.c",
        "src/libqhull/random.c",
        "src/libqhull/usermem.c",
        "src/libqhull/userprintf.c",
        "src/libqhull/io.c",
        "src/libqhull/user.c",
        "src/libqhull/rboxlib.c",
        "src/libqhull/userprintf_rbox.c",
    ],
    hdrs = [
        "src/libqhull/libqhull.h",
        "src/libqhull/geom.h",
        "src/libqhull/io.h",
        "src/libqhull/mem.h",
        "src/libqhull/merge.h",
        "src/libqhull/poly.h",
        "src/libqhull/qhull_a.h",
        "src/libqhull/qset.h",
        "src/libqhull/random.h",
        "src/libqhull/stat.h",
        "src/libqhull/user.h",
    ],
    includes = ["src"],
    linkopts = ["-lm"],
)

cc_library(
    name = "libqhull_r",
    srcs = [
        "src/libqhull_r/global_r.c",
        "src/libqhull_r/stat_r.c",
        "src/libqhull_r/geom2_r.c",
        "src/libqhull_r/poly2_r.c",
        "src/libqhull_r/merge_r.c",
        "src/libqhull_r/libqhull_r.c",
        "src/libqhull_r/geom_r.c",
        "src/libqhull_r/poly_r.c",
        "src/libqhull_r/qset_r.c",
        "src/libqhull_r/mem_r.c",
        "src/libqhull_r/random_r.c",
        "src/libqhull_r/usermem_r.c",
        "src/libqhull_r/userprintf_r.c",
        "src/libqhull_r/io_r.c",
        "src/libqhull_r/user_r.c",
        "src/libqhull_r/rboxlib_r.c",
        "src/libqhull_r/userprintf_rbox_r.c",
    ],
    hdrs = [
        "src/libqhull_r/libqhull_r.h",
        "src/libqhull_r/geom_r.h",
        "src/libqhull_r/io_r.h",
        "src/libqhull_r/mem_r.h",
        "src/libqhull_r/merge_r.h",
        "src/libqhull_r/poly_r.h",
        "src/libqhull_r/qhull_ra.h",
        "src/libqhull_r/qset_r.h",
        "src/libqhull_r/random_r.h",
        "src/libqhull_r/stat_r.h",
        "src/libqhull_r/user_r.h",
    ],
    includes = ["src"],
    linkopts = ["-lm"],
)

cc_library(
    name = "qhull",
    srcs = [
        "src/libqhullcpp/Coordinates.cpp",
        "src/libqhullcpp/PointCoordinates.cpp",
        "src/libqhullcpp/Qhull.cpp",
        "src/libqhullcpp/QhullFacet.cpp",
        "src/libqhullcpp/QhullFacetList.cpp",
        "src/libqhullcpp/QhullFacetSet.cpp",
        "src/libqhullcpp/QhullHyperplane.cpp",
        "src/libqhullcpp/QhullPoint.cpp",
        "src/libqhullcpp/QhullPointSet.cpp",
        "src/libqhullcpp/QhullPoints.cpp",
        "src/libqhullcpp/QhullQh.cpp",
        "src/libqhullcpp/QhullRidge.cpp",
        "src/libqhullcpp/QhullSet.cpp",
        "src/libqhullcpp/QhullStat.cpp",
        "src/libqhullcpp/QhullVertex.cpp",
        "src/libqhullcpp/QhullVertexSet.cpp",
        "src/libqhullcpp/RboxPoints.cpp",
        "src/libqhullcpp/RoadError.cpp",
        "src/libqhullcpp/RoadLogEvent.cpp",
    ],
    hdrs = [
        "src/libqhullcpp/Coordinates.h",
        "src/libqhullcpp/functionObjects.h",
        "src/libqhullcpp/PointCoordinates.h",
        "src/libqhullcpp/Qhull.h",
        "src/libqhullcpp/QhullError.h",
        "src/libqhullcpp/QhullFacet.h",
        "src/libqhullcpp/QhullFacetList.h",
        "src/libqhullcpp/QhullFacetSet.h",
        "src/libqhullcpp/QhullHyperplane.h",
        "src/libqhullcpp/QhullIterator.h",
        "src/libqhullcpp/QhullLinkedList.h",
        "src/libqhullcpp/QhullPoint.h",
        "src/libqhullcpp/QhullPoints.h",
        "src/libqhullcpp/QhullPointSet.h",
        "src/libqhullcpp/QhullQh.h",
        "src/libqhullcpp/QhullRidge.h",
        "src/libqhullcpp/QhullSet.h",
        "src/libqhullcpp/QhullSets.h",
        "src/libqhullcpp/QhullStat.h",
        "src/libqhullcpp/QhullVertex.h",
        "src/libqhullcpp/QhullVertexSet.h",
        "src/libqhullcpp/RboxPoints.h",
        "src/libqhullcpp/RoadError.h",
        "src/libqhullcpp/RoadLogEvent.h",
        "src/qhulltest/RoadTest.h",
    ],
    includes = ["src"],
    deps = [":libqhull_r", ":libqhull"],
)
