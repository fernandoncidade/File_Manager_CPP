cmake_minimum_required(VERSION 3.29)
project(File_Manager)

set(CMAKE_CXX_STANDARD 17)

find_package(Qt6 COMPONENTS Core Gui Widgets Sql REQUIRED)

set(CMAKE_AUTOMOC ON)

# Defina o caminho da instalação do libxl (atualize para o caminho correto do seu ambiente)
#set(LIBXL_INCLUDE_DIR "C:/Users/ferna/PROJETOS/Projetos_CPP/File-Folder-Manager/File_Manager/cmake-build-debug/include_cpp")
#set(LIBXL_LIBRARY "C:/Users/ferna/PROJETOS/Projetos_CPP/File-Folder-Manager/File_Manager/cmake-build-debug/lib64/libxl.lib")

# Inclua o diretório de cabeçalhos do libxl
#include_directories(${LIBXL_INCLUDE_DIR})

set(CMAKE_PREFIX_PATH "C:/Qt/6.8.0/mingw_64")

add_executable(File_Manager File_Manager.cpp DirectoryAnalyzer.cpp DirectoryAnalyzer.h)

target_link_libraries(File_Manager ${MOC_SOURCES} Qt6::Core Qt6::Gui Qt6::Widgets Qt6::Sql)

#target_link_libraries(File_Manager Qt6::Core Qt6::Gui Qt6::Widgets Qt6::Sql ${LIBXL_LIBRARY})

if (WIN32)
    set_target_properties(File_Manager PROPERTIES LINK_FLAGS "-mwindows")  # Altere para -mwindows
endif()
