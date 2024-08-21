ShaderToHeader is a tool used during the GlistEngine compilation process to convert shader files into character arrays that can be embedded directly into the source code. The generated code can be included using the `#include` preprocessor directive, and the corresponding constant `std::array` object will be available with the name of the file prefixed by `shader_`.

For example a file named `color_vert.glsl` will generate a header file named `color_vert.h`:

```cpp
#include "color_vert.h"

// shader_color_vert is defined as `constexpr std::array<const char, SIZE>`. Size being the length of the file.
// And can be used like so:
std::string str{shader_color_vert.data(), shader_color_vert.size()};
```
