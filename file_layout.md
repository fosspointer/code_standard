# File Layout

Layout followed by all projects:

- license.md
- readme.md
- code_standard/ (this file's directory as a Git submodule)
- **core/** (for library code)
    - **include/** (project's include directory - headers)
        - *project_name/*
            - *module_a/*...
            - *module_b/*...
            - *module_c/*...
        - *project_name*.hpp (precompiled header)
    - **src/** (code to be compiled - sources)
        - *module_a/*...
        - *module_b/*...
        - *module_c/*...
- **client/** *or demo/ or application_name/* (for executable code)
    - *binary_a_name.cpp*
    - *binary_b_name.cpp*
    - *header_a.hpp*
    - *header_b.hpp*
- build/... (optional as this is not technically a part of the project)
