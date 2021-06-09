package(default_visibility = ["//visibility:public"])

filegroup(
    name = "models",
    srcs = glob(["*.tflite"]),
)

filegroup(
    name = "images",
    srcs = glob(["*.bmp"]),
)

filegroup(
    name = "reference_results",
    srcs = glob(["*.csv"]),
)

coral_test_data_posenet_images = declare_dependency(
  sources : run_command('../images.sh').stdout().strip().split('\n'),
)

coral_test_data_posenet_models = declare_dependency(
  sources : run_command('../models.sh').stdout().strip().split('\n'),
)

coral_test_data_posenet_reference_results = declare_dependency(
  sources : run_command('find', '-name', '*.csv').stdout().strip().split('\n'),
)
