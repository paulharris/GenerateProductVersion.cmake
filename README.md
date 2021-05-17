Using `GenerateProductVersion.cmake`
------------------------------

Basic usage:

```cmake
include(GenerateProductVersion)

GenerateProductVersion(
    ProductVersionFiles
    NAME MyProduct
    COMPANY_NAME MyCompany
)
```

Two files will be generated in CMAKE_CURRENT_BINARY_DIRECTORY.
ProductVersionFiles output variable will be filled with path names to generated files.

You can use generated resource for your executable targets:

```cmake
add_executable(target-name ${target-files} ${ProductVersionFiles})
```

You can specify the resource strings in arguments:

- NAME               - Name of executable (no defaults, ex: Microsoft Word)
- BUNDLE             - Bundle (${NAME} is default, ex: Microsoft Office)
- ICON               - Path to application icon (${CMAKE_SOURCE_DIR}/product.ico is default)
- VERSION            - The version of the product; Defaults to `${PROJECT_VERSION}`
- COMPANY_NAME       - Your company name (no defaults)
- COMPANY_COPYRIGHT  - ${COMPANY_NAME} (C) Copyright ${CURRENT_YEAR} is default
- COMMENTS           - ${NAME} v${VERSION_MAJOR}.${VERSION_MINOR} is default
- ORIGINAL_FILENAME  - ${NAME} is default
- INTERNAL_NAME      - ${NAME} is default
- FILE_DESCRIPTION   - ${NAME} is default
