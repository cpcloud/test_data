test_data_images_targets = []

foreach source : run_command(fd, '\.(bmp|jpg)$', '--max-depth', '1').stdout().strip().split('\n')
  test_data_images_targets += custom_target(
    source.underscorify(),
    input : source,
    output : source.split('/')[-1],
    command : [cp, '@INPUT@', '@OUTPUT@'],
  )
endforeach

coral_test_data_posenet_images = declare_dependency(
  sources : test_data_images_targets,
)

test_data_models_targets = []

foreach source : run_command(fd, '\.tflite$', '--max-depth', '1').stdout().strip().split('\n')
  test_data_models_targets += custom_target(
    source.underscorify(),
    input : source,
    output : source.split('/')[-1],
    command : [cp, '@INPUT@', '@OUTPUT@'],
  )
endforeach

coral_test_data_posenet_models = declare_dependency(
  sources : test_data_models_targets,
)

test_data_reference_results_targets = []

foreach source : run_command(fd, '\.csv$', '--max-depth', '1').stdout().strip().split('\n')
  test_data_reference_results_targets += custom_target(
    source.underscorify(),
    input : source,
    output : source.split('/')[-1],
    command : [cp, '@INPUT@', '@OUTPUT@'],
  )
endforeach

coral_test_data_posenet_reference_results = declare_dependency(
  sources : test_data_reference_results_targets,
)
