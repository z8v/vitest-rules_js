load("@aspect_rules_js//js:defs.bzl", "js_test")
load("@npm//:defs.bzl", "npm_link_all_packages")
load("@npm//:vite/package_json.bzl", vite_bin = "bin")
load("@npm//:vitest/package_json.bzl", vitest_bin = "bin")
load("@npm//:vue-tsc/package_json.bzl", vue_tsc_bin = "bin")

# This macro expands to a link_npm_package for each third-party package in package.json
npm_link_all_packages(name = "node_modules")

vitest_bin.vitest(name="vitest")

SRCS = glob(
    include = [
      "*",
      "src/**",
      "public/**",
    ],
    exclude = [
      "node_modules",
    ],
)

vite_bin.vite(
    name = "build",
    args = ["build"],
    out_dirs = ["dist"],
    srcs = SRCS + [":node_modules"],
)

js_test(
    name = "test",
    args = ["run"],
    chdir = package_name(),
    entry_point = "vitest__entry_point",
    data = SRCS + [":node_modules"],
)
