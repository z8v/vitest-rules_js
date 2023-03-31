load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "aspect_rules_js",
    sha256 = "7c50475662810ce9635fa45d718220285a8adef32b2febd8631aae62e5816353",
    strip_prefix = "rules_js-1.23.2",
    url = "https://github.com/aspect-build/rules_js/releases/download/v1.23.2/rules_js-v1.23.2.tar.gz",
)

load("@aspect_rules_js//js:repositories.bzl", "rules_js_dependencies")

rules_js_dependencies()

load("@rules_nodejs//nodejs:repositories.bzl", "DEFAULT_NODE_VERSION", "nodejs_register_toolchains")

nodejs_register_toolchains(
    name = "nodejs",
    node_version = "16.16.0",
)

load("@aspect_rules_js//npm:npm_import.bzl", "npm_translate_lock")

npm_translate_lock(
    name = "npm",
    data = ["//:package.json"],
    pnpm_lock = "//:pnpm-lock.yaml",
    verify_node_modules_ignored = "//:.bazelignore",
    npmrc = "//:.npmrc",
    update_pnpm_lock = True,
)

load("@npm//:repositories.bzl", "npm_repositories")

npm_repositories()
