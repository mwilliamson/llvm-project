get_property(LLDB_ALL_PLUGINS GLOBAL PROPERTY LLDB_PLUGINS)

add_lldb_tool(lldb-test
  FormatUtil.cpp
  lldb-test.cpp
  SystemInitializerTest.cpp

  LINK_LIBS
    lldbBase
    lldbBreakpoint
    lldbCore
    lldbDataFormatters
    lldbExpression
    lldbHost
    lldbInitialization
    lldbInterpreter
    lldbSymbol
    lldbTarget
    lldbUtility
    ${LLDB_ALL_PLUGINS}
    ${host_lib}

  LINK_COMPONENTS
    Support
  )

target_include_directories(lldb-test PRIVATE ${LLDB_SOURCE_DIR}/source)
target_include_directories(lldb-test PRIVATE ${LLDB_BINARY_DIR}/source)
