# Installing SFML libraries on Windows 11 from source

## 1. Basic install
### 1.1 Installing cmake-3.23.0-rc5-windows-x86_64.msi
> Cmake_path_config.png

![alt text](readme_screenshot/cmake_path_config.png)
![alt text](readme_screenshot/chose_cmake_path.png)

### 1.2 Installing mingw-get-setup.exe
> Recommended install MinGW files to C:\SFML directory

![alt text](readme_screenshot/mingw_inst.png)
![alt text](readme_screenshot/chose_all_basics_components.png)

### 1.3 Setup Path variables
> Click on **properties**

![alt text](readme_screenshot/go_to_my_comp_right_click.png)

> Click on advance system settings

![alt text](readme_screenshot/advanced_sys_sett.png)

> Click on **environment variables**

![alt text](readme_screenshot/click_on_advanced_sys_variables.png)

> Choose **Path** variable and click on **edit**

![alt text](readme_screenshot/edit_Path_var.png)

> Click on **New** button and add "C:\MinGW" ,
Then in the same way add "C:\Program Files\cmake-3.23.0-rc4-windows-x86_64"
Your system variables should look like:

![alt text](readme_screenshot/add_path.png)

## 2. Install SFML from source
> Download SFM lib from git [repository](https://github.com/SFML/SFML/archive/refs/heads/master.zip) 

> Unzip SFML lib to convenient place like "C:\Users\YourName\Desktop\"

> You will get lib source folder "C:\Users\YourName\Desktop\SFML-2.5.1-sources"

> In "C:\Users\YourName\Desktop\SFML-2.5.1-sources" create another folder "C:\Users\YourName\Desktop\SFML-2.5.1-sources\Fresh_Build" to generate cmake files

> Run cmd from Windows11 menu

![alt text](readme_screenshot/find_cmd.png)

> Type cmake-gui

![alt text](readme_screenshot/cmake-gui1.png)

> configure cmake-gui and click "configure" 

![alt text](readme_screenshot/cmake-gui_config.png)

> Change CMAKE_INSTALL_PREFIX from "C:/Program Files (x86)/SFML" to "C:/SFML"

> Decide what LIBS you need if you need shared libraries BUILD_SHARED_LIBS ✅  should be on,
else SFML_USE_STATIC_STD_LIBS ✅ , but you can't choose bought

![alt text](readme_screenshot/lib_dll.png)

> After configuring cmake variables, click on "generate" button and wait until it complete 

![alt text](readme_screenshot/generate.png)

> To install all generated bin to "C/SFML" directory, open cmd and type "mingw32-make install" 

> After installing SFML you will get folder with bin folder

![alt text](readme_screenshot/sfml_bin.png)

> Add "C:\SFML\bin" to Path

![alt text](readme_screenshot/SFMLtoPath.png)

## 2. Testing
> Now you have SFML lib

> To testing whether all works fine use this Cmake. 

> Simple build project and run executable file