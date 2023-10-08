# File Layout

Layout followed by all projects:

- LICENSE.md
- README.md
- code_standard/ (this file's directory)
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
    - main.cpp
    - *header_a.hpp*
    - *header_b.hpp*

- build/... (optional as this is not technically a part of the project)
