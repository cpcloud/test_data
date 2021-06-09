test_data_models_targets = []

foreach source : run_command(fd, '\.tflite$', '--max-depth', '1').stdout().strip().split('\n')
  test_data_models_targets += custom_target(
    source.underscorify(),
    input : source,
    output : source.split('/')[-1],
    command : [cp, '@INPUT@', '@OUTPUT@'],
  )
endforeach

coral_test_data_tools_models = declare_dependency(
  sources : test_data_models_targets,
)
