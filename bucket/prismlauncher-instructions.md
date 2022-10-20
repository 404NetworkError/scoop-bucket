https://prismlauncher.org/wiki/development/build-instructions/#windows

# Link Shell #
https://aka.ms/vs/15/release/vc_redist.x64.exe
https://aka.ms/vs/15/release/vc_redist.x86.exe
https://schinagl.priv.at/nt/hardlinkshellext/HardLinkShellExt_X64.exe
# Link Shell #

https://github.com/git-for-windows/git/releases/download/v2.37.3.windows.1/Git-2.37.3-64-bit.exe
https://az764295.vo.msecnd.net/stable/74b1f979648cc44d385a2286793c226e611f59e7/VSCodeSetup-x64-1.71.2.exe
https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools

https://github.com/msys2/msys2-installer/releases/download/2022-09-04/msys2-x86_64-20220904.exe
setx /M path "C:\msys64\mingw32\bin;%path%"
https://github.com/adoptium/temurin17-binaries/releases/download/jdk-17.0.4.1%2B1/OpenJDK17U-jdk_x64_windows_hotspot_17.0.4.1_1.msi
	Make sure that "Set JAVA_HOME variable" is enabled in the Adoptium installer.

pacman -Syu pactoys git unzip
	Run twice
pacboy -S toolchain:p cmake:p ninja:p qt6-base:p qt6-5compat:p qt6-svg:p qt6-imageformats:p quazip-qt6:p extra-cmake-modules:p ccache:p

# Ignore #
wget https://github.com/ccache/ccache/releases/download/v4.6.3/ccache-4.6.3-windows-x86_64.zip
unzip ./ccache-4.6.3-windows-x86_64.zip
cp ./ccache-4.6.3-windows-x86_64/ccache.exe ../../../mingw32/bin/
# Ignore #

git clone --recursive https://github.com/PrismLauncher/PrismLauncher.git
cd PrismLauncher

cmake -Bbuild -DCMAKE_INSTALL_PREFIX=install -DENABLE_LTO=ON -DLauncher_QT_VERSION_MAJOR=6 -DCMAKE_CXX_COMPILER_LAUNCHER=ccache -DCMAKE_EXPORT_COMPILE_COMMANDS=ON -DCMAKE_BUILD_TYPE=Debug
cmake --build build -j6
cmake --install build
cmake --install build --component portable

cp ../../../../mingw32/bin/libcrypto-1_1.dll ../../../../mingw32/bin/libssl-1_1.dll ./install/
