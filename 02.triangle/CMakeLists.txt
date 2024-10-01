# CMake의 최소 버전 설정
cmake_minimum_required(VERSION 3.10)

# 프로젝트 이름 및 사용 언어 설정
project(triangle)

# C++ 표준 설정
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# OpenGL 라이브러리 찾기
find_package(OpenGL REQUIRED)

# GLEW, GLFW, GLM 라이브러리 경로 찾기
find_package(GLEW REQUIRED)
find_package(glfw3 REQUIRED)
find_package(glm REQUIRED)

# 소스 파일 설정
set(SOURCES
    main.cpp # 여기에 메인 소스 파일을 추가합니다
)

# 실행 파일 생성
add_executable(triangle ${SOURCES})
include_directories(triangle ../include)

# 라이브러리 연결
target_link_libraries(triangle
    OpenGL::GL
    GLEW::GLEW
    glfw
#   glm
)
