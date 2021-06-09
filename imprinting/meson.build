test_data_imprinting_images_targets = []

foreach source : run_command(fd, '\.(bmp|jpg)$', '--max-depth', '1').stdout().strip().split('\n')
  test_data_imprinting_images_targets += custom_target(
    source.underscorify(),
    input : source,
    output : source.split('/')[-1],
    command : [cp, '@INPUT@', '@OUTPUT@'],
  )
endforeach

coral_test_data_imprinting_images = declare_dependency(
  sources : test_data_imprinting_images_targets,
)
