cmake_minimum_required(VERSION 3.2)

project(test-set-extractor)

add_executable(test-set-extractor test-set-extractor.cpp)
set_target_properties(test-set-extractor PROPERTIES LINK_FLAGS_RELEASE "-dead_strip")

target_include_directories(test-set-extractor
	PRIVATE ${PROJECT_INCLUDE_DIRS}
	PUBLIC ${Boost_INCLUDE_DIRS} ${OPENSSL_INCLUDE_DIR})
target_link_libraries(test-set-extractor pnwed ${OPENSSL_CRYPTO_LIBRARY} ${Boost_LIBRARIES})
