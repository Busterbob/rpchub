genrule(
    name = "headers",
    srcs = [
        "ddl2cpp",
        "schema.sql",
    ],
    outs = ["schema.h"],
    cmd = """
      $(location ddl2cpp) $(location schema.sql) schema hub::db::sql
      cp schema.h $@
        """,
)

cc_library(
    name = "schema",
    hdrs = [":headers"],
    data = [
        "schema.sql",
        "triggers.mariadb.sql",
        "triggers.sqlite3.sql",
    ],
    visibility = ["//visibility:public"],
)
