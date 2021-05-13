Using `GenerateProductVersion.cmake`
------------------------------

Basic usage:

```cmake
include(GenerateProductVersion)

GenerateProductVersion(ProductVersionFiles
    NAME MyProduct
    VERSION_MAJOR 3
    VERSION_MINOR 2
    VERSION_PATCH 12
    VERSION_REVISION 30303
    COMPANY_NAME MyCompany)
```

Two files will be generated in CMAKE_CURRENT_BINARY_DIRECTORY.
ProductVersionFiles output variable will be filled with path names to generated files.

You can use generated resource for your executable targets:

```cmake
add_executable(target-name ${target-files} ${ProductVersionFiles})
```

You can specify the resource strings in arguments:

- NAME               - name of executable (no defaults, ex: Microsoft Word)
- BUNDLE             - bundle (${NAME} is default, ex: Microsoft Office)
- ICON               - path to application icon (${CMAKE_SOURCE_DIR}/product.ico is default)
- VERSION_MAJOR      - 1 is default
- VERSION_MINOR      - 0 is default
- VERSION_PATCH      - 0 is default
- VERSION_REVISION   - 0 is default
- COMPANY_NAME       - your company name (no defaults)
- COMPANY_COPYRIGHT  - ${COMPANY_NAME} (C) Copyright ${CURRENT_YEAR} is default
- COMMENTS           - ${NAME} v${VERSION_MAJOR}.${VERSION_MINOR} is default
- ORIGINAL_FILENAME  - ${NAME} is default
- INTERNAL_NAME      - ${NAME} is default
- FILE_DESCRIPTION   - ${NAME} is default
