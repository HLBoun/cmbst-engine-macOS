cmake_minimum_required(VERSION 4.2.1)
project(CmbstEngine)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_OSX_DEPLOYMENT_TARGET "26" CACHE STRING "Minimum OS X deployment version" FORCE)

find_package(glfw3 3.4 REQUIRED)
find_package(glm REQUIRED)
find_package(Vulkan REQUIRED)


add_executable(${PROJECT_NAME} src/main.cpp)

target_link_libraries(${PROJECT_NAME}
      PUBLIC
      ${VULKAN_LIBRARIES}
      ${OPENGL_LIBRARIES}
      ${GLFW3_LIBRARIES}
      #      /opt/homebrew/Cellar/glfw/3.4/lib/libglfw3.a
      /opt/homebrew/Cellar/glfw/3.4/lib/libglfw.3.4.dylib
      /opt/homebrew/Cellar/glm/1.0.3/lib/libglm.dylib
      /Users/legendboun/VulkanSDK/1.4.335.1/macOS/lib/libvulkan.1.4.335.dylib
)

target_include_directories(${PROJECT_NAME}
      PUBLIC
      /Users/legendboun/VulkanSDK/1.4.335.1/macOS/include
      /opt/homebrew/Cellar/glm/1.0.3/include
      /opt/homebrew/Cellar/glfw/3.4/include
)

