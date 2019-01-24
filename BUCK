load('//:subdir_glob.bzl', 'subdir_glob')

genrule(
  name = 'config',
  out = 'config.h',
  cmd = 'touch $OUT'
) 

cxx_library(
  name = 'cityhash',
  header_namespace = '',
  srcs = glob(['src/city.cc']),
  exported_headers = subdir_glob([
    ('src', '*.h')
  ]),
  headers = [':config'],
  visibility = ["PUBLIC"]
)

cxx_binary(
  name = 'test',
  srcs = ['src/city-test.cc'],
  deps = [':cityhash']
)
