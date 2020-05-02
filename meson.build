project('chrono-tsc', ['c', 'cpp'], default_options : ['cpp_std=c++17'])

openmp_dep = dependency('openmp')

inc = include_directories('.')
inc_interface = include_directories('interface')
inc_interface_native = include_directories('interface/native')

src= [
  'src/mach_absolute_time.cc',
  'src/mach_clock_get_time.cc',
  'src/posix_clock_gettime.cc',
  'src/syscall_clock_gettime.cc',
  'src/tbb_tick_count.cc',
  'src/x86_tsc.cc',
  'src/x86_tsc_clock.cc',
  'src/x86_tsc_tick.cc',
  'src/native/x86_tsc_clock.cc'
]

chrono_static = static_library('chrono-tsc', [src],
                               dependencies: openmp_dep,
                               include_directories: [inc, inc_interface, inc_interface_native],
                               install: true)

libchrono_dep = declare_dependency(include_directories: [inc, inc_interface, inc_interface_native],
                                link_with: chrono_static)
