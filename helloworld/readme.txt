cd build
cmake -DCMAKE_TOOLCHAIN_FILE=D:\libs\Huawei\Sdk\openharmony\10\native\build\cmake\ohos.toolchain.cmake -DOHOS_ARCH=armeabi-v7a -DOHOS_STL=c++_shared .. -G Ninja
//cmake -DCMAKE_TOOLCHAIN_FILE=D:\libs\Huawei\Sdk\openharmony\10\native\build\cmake\ohos.toolchain.cmake -DOHOS_ARCH=arm64-v8a -DOHOS_STL=c++_shared .. -G Ninja
cmake --build .