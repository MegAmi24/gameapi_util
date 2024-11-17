## gameapi_util
A simple Python script to assist with managing RSDKv5/U projects.

![Screenshot of the main interface](/screenshots/main.png)

## Default Functions

- **Update All.cpp/All.hpp & CMake Project**
  - This function generates `All.cpp` & `All.hpp` includes and `Objects.cmake`.
  - Forward declarations are included in the header.

- **Generate public functions**
  - This function generates `PublicFunctions.hpp`. Entity events are not included.

- **Create new object**
  - Creates a new object in the specified directory.
  - After creation, you can optionally run `project_update` to generate new `All.cpp` and `All.hpp` files.

## gameapi_util_cfg
`gameapi_util_cfg.py` is used for configuring various things, such as - the path to your objects directory. Many options, are available:
```
GAME_PATH        = "src"
OBJECT_PATH_NAME = "Objects"
ALL_CODE_NAME    = "All.cpp"
ALL_HEADER_NAME  = "All.hpp"
PUB_FNS_PATH     = "PublicFunctions.hpp"
OBJECT_NAMESPACE = "GameLogic"

# cmake configuration
CMAKE_PATH = "Objects.cmake"
GAME_NAME  = "${GAME_NAME}" # The game directory to look into

OBJECT_PATH = f"{GAME_PATH}/{OBJECT_PATH_NAME}"
ALL_CPP_PATH = f"{OBJECT_PATH}/{ALL_CODE_NAME}"
ALL_HPP_PATH = f"{GAME_PATH}/{ALL_HEADER_NAME}"
```

You can also extend the main menu, with the `init` function. For example:
```
def init(window_in, util_in):
    global window, util
    window = window_in
    util   = util_in

    util.add_option('Validate objects', ens_obj_valid)
    util.add_option('Check status', do_status_check)
```

![Screenshot of the main interface, after being extended by gameapi_util_cfg.py](/screenshots/main_extended.png)
