###########################################################
## CONFIGURATION
###########################################################

include_directories(${CMAKE_CURRENT_SOURCE_DIR})

add_compile_options(-g -O3 -Wall -Werror) 

if(APPLE)
  add_compile_options(-std=c11) 
else()
  add_compile_options(-std=gnu11)
  link_libraries(m)  
endif()

link_libraries(pthread)


###########################################################
## DEPENDENCIES
###########################################################

find_package(PkgConfig REQUIRED)


###########################################################  
## SUBDIRECTORIES
###########################################################

add_subdirectory(common)

add_subdirectory(pipe)

add_subdirectory(fifo)  

add_subdirectory(shm)

add_subdirectory(domain)

add_subdirectory(mq)
