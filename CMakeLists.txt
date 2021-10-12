set(BACKENDS
    "backends/imgui_impl_opengl3.cpp"
    "backends/imgui_impl_opengl3.h"
    "backends/imgui_impl_glfw.cpp"
    "backends/imgui_impl_glfw.h"
)

add_library(ImGui
    "imconfig.h"
    "imgui.h"
    "imgui.cpp"
    "imgui_stdlib.cpp"
    "imgui_stdlib.h"
    "imgui_draw.cpp"
    "imgui_internal.h"
    "imgui_widgets.cpp"
    "imstb_rectpack.h"
    "imstb_textedit.h"
    "imstb_truetype.h"
    "imgui_demo.cpp"
    "imgui_tables.cpp"

    ${BACKENDS}
)

target_include_directories(ImGui PRIVATE
    .
    ${CMAKE_SOURCE_DIR}/engine/vendor/glfw/include
    ${CMAKE_SOURCE_DIR}/engine/vendor/glad/include
)

set_target_properties(ImGui PROPERTIES FOLDER dependencies)
