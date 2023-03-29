cmake_minimum_required(VERSION 2.8)
project(LLP3 C)

set(CMAKE_C_STANDARD 11)

include_directories(xpath_parser/include)
include_directories(xpath_parser/include/parser)
include_directories(xpath_parser/include/io)
include_directories(xpath_parser/include/structure)
include_directories(db/include)
include_directories(proto)
include_directories(proto/nanopb)

add_executable(LLP3 server.c
        proto/message.pb.c
        proto/nanopb/pb_encode.c
        proto/nanopb/pb_decode.c
        proto/nanopb/pb_common.c)
add_executable(LLP3_1 client.c
        proto/message.pb.c
        proto/nanopb/pb_encode.c
        proto/nanopb/pb_decode.c
        proto/nanopb/pb_common.c)
add_subdirectory(xpath_parser)
target_link_libraries(LLP3 Xpath_lib)
target_link_libraries(LLP3_1 Xpath_lib)
add_subdirectory(db)
target_link_libraries(LLP3 Database_lib)
target_link_libraries(LLP3_1 Database_lib)
