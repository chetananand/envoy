package(default_visibility = ["//visibility:public"])

load("//bazel:envoy_build_system.bzl", "envoy_cc_library")

envoy_cc_library(
    name = "dispatcher_lib",
    srcs = [
        "dispatcher_impl.cc",
        "event_impl_base.cc",
        "file_event_impl.cc",
        "signal_impl.cc",
        "timer_impl.cc",
    ],
    hdrs = [
        "signal_impl.h",
        "timer_impl.h",
    ],
    deps = [
        ":dispatcher_includes",
        "//include/envoy/event:signal_interface",
        "//include/envoy/event:timer_interface",
        "//include/envoy/network:listen_socket_interface",
        "//include/envoy/network:listener_interface",
        "//source/common/common:assert_lib",
        "//source/common/filesystem:watcher_lib",
        "//source/common/network:connection_lib",
        "//source/common/network:dns_lib",
        "//source/common/network:listener_lib",
        "//source/common/ssl:connection_lib",
    ],
)

envoy_cc_library(
    name = "dispatcher_includes",
    hdrs = [
        "dispatcher_impl.h",
        "event_impl_base.h",
        "file_event_impl.h",
    ],
    deps = [
        ":libevent_lib",
        "//include/envoy/event:deferred_deletable",
        "//include/envoy/event:dispatcher_interface",
        "//include/envoy/event:file_event_interface",
        "//include/envoy/network:connection_handler_interface",
        "//source/common/common:logger_lib",
    ],
)

envoy_cc_library(
    name = "libevent_lib",
    srcs = ["libevent.cc"],
    hdrs = ["libevent.h"],
    external_deps = [
        "event",
        "event_pthreads",
    ],
    deps = [
        "//source/common/common:assert_lib",
        "//source/common/common:c_smart_ptr_lib",
    ],
)
