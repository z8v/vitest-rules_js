load("@npm//:defs.bzl", "npm_link_all_packages")
load("@npm//:vite/package_json.bzl", vite_bin = "bin")
load("@npm//:vue-tsc/package_json.bzl", vue_tsc_bin = "bin")

# This macro expands to a link_npm_package for each third-party package in package.json
npm_link_all_packages(name = "node_modules")
