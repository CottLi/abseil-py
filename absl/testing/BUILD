licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

py_library(
    name = "absltest",
    testonly = 1,
    srcs = ["absltest.py"],
    srcs_version = "PY2AND3",
    visibility = ["//visibility:public"],
    deps = [
        ":xml_reporter",
        "//absl:app",
        "//absl/flags",
        "//absl/logging",
        "@six_archive//:six",
    ],
)

py_library(
    name = "flagsaver",
    testonly = 1,
    srcs = ["flagsaver.py"],
    srcs_version = "PY2AND3",
    visibility = ["//visibility:public"],
    deps = [
        "//absl/flags",
        "@six_archive//:six",
    ],
)

py_library(
    name = "parameterized",
    testonly = 1,
    srcs = ["parameterized.py"],
    srcs_version = "PY2AND3",
    visibility = ["//visibility:public"],
    deps = [
        ":absltest",
        "@six_archive//:six",
    ],
)

py_library(
    name = "xml_reporter",
    testonly = 1,
    srcs = ["xml_reporter.py"],
    srcs_version = "PY2AND3",
    visibility = ["//visibility:public"],
    deps = ["@six_archive//:six"],
)

py_library(
    name = "_bazelize_command",
    testonly = 1,
    srcs = ["_bazelize_command.py"],
    srcs_version = "PY2AND3",
    visibility = ["//:__subpackages__"],
    deps = ["//absl/flags"],
)

py_test(
    name = "tests/absltest_filtering_test",
    size = "small",
    srcs = ["tests/absltest_filtering_test.py"],
    data = [":tests/absltest_filtering_test_helper"],
    srcs_version = "PY2AND3",
    deps = [
        ":_bazelize_command",
        ":absltest",
        "//absl/logging",
    ],
)

py_binary(
    name = "tests/absltest_filtering_test_helper",
    testonly = 1,
    srcs = ["tests/absltest_filtering_test_helper.py"],
    srcs_version = "PY2AND3",
    deps = [":absltest"],
)

py_test(
    name = "tests/absltest_randomization_test",
    size = "medium",
    srcs = ["tests/absltest_randomization_test.py"],
    data = [":tests/absltest_randomization_testcase"],
    srcs_version = "PY2AND3",
    deps = [
        ":_bazelize_command",
        ":absltest",
        ":parameterized",
        "//absl/flags",
    ],
)

py_binary(
    name = "tests/absltest_randomization_testcase",
    testonly = 1,
    srcs = ["tests/absltest_randomization_testcase.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":absltest",
    ],
)

py_test(
    name = "tests/absltest_sharding_test",
    size = "small",
    srcs = ["tests/absltest_sharding_test.py"],
    data = [":tests/absltest_sharding_test_helper"],
    srcs_version = "PY2AND3",
    deps = [
        ":_bazelize_command",
        ":absltest",
        "//absl/flags",
    ],
)

py_binary(
    name = "tests/absltest_sharding_test_helper",
    testonly = 1,
    srcs = ["tests/absltest_sharding_test_helper.py"],
    srcs_version = "PY2AND3",
    deps = [":absltest"],
)

py_test(
    name = "tests/absltest_test",
    size = "small",
    srcs = ["tests/absltest_test.py"],
    data = [":tests/absltest_test_helper"],
    srcs_version = "PY2AND3",
    deps = [
        ":_bazelize_command",
        ":absltest",
        ":parameterized",
        "//absl/flags",
        "@six_archive//:six",
    ],
)

py_binary(
    name = "tests/absltest_test_helper",
    testonly = 1,
    srcs = ["tests/absltest_test_helper.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":absltest",
        "//absl/flags",
    ],
)

py_test(
    name = "tests/flagsaver_test",
    srcs = ["tests/flagsaver_test.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":absltest",
        ":flagsaver",
        "//absl/flags",
    ],
)

py_test(
    name = "tests/parameterized_test",
    srcs = ["tests/parameterized_test.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":absltest",
        ":parameterized",
        "@six_archive//:six",
    ],
)

py_test(
    name = "tests/xml_reporter_test",
    srcs = ["tests/xml_reporter_test.py"],
    data = [":tests/xml_reporter_helper_test"],
    srcs_version = "PY2AND3",
    deps = [
        ":_bazelize_command",
        ":absltest",
        ":parameterized",
        ":xml_reporter",
        "//absl/logging",
        "@mock_archive//:mock",
        "@six_archive//:six",
    ],
)

py_binary(
    name = "tests/xml_reporter_helper_test",
    testonly = 1,
    srcs = ["tests/xml_reporter_helper_test.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":absltest",
        "//absl/flags",
    ],
)
