# Fuzzing xml2dcm utility

1. Install [AFL](https://github.com/mykter/afl-training/tree/master/quickstart#setup)


2. Build
    ```bash
    # Clone source-code from the Official DCMTK Github Mirror
    git clone https://github.com/DCMTK/dcmtk
    cd dcmtk

    # Switch to a specific version
    git checkout DCMTK-3.6.3

    # Apply a patch to change C/C++ compiler to afl-clang-fast/afl-clang-fast++ and to omit output
    patch -p1 < ~/dicom/docs/fuzzing/data/DCMTK-3.6.3.patch

    # Install dependencies
    sudo apt-get install libxml2-dev

    # Build
    mkdir build
    cd build
    cmake ..
    AFL_USE_ASAN=1 make xml2dcm  
    ```

3. Fuzz
    ```bash
    # Go to the folder with the xml2dcm binary
    cd bin/

    # Copy folder with corpus-file
    cp -r ~/dicom/docs/fuzzing/data/xml2dcm-in ./

    # Fuzz
    afl-fuzz -m none -i xml2dcm-in -o out -x ~/afl-2.52b/dictionaries/xml.dict ./xml2dcm @@
    ```


    