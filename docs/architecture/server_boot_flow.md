# Server Boot Flow

## Current Hypothesis

### Startup

1. GameServer.exe
2. script/global/autoexec.lua
3. script/global/globalcallback.lua
4. Register engine callbacks

### Player Login

1. playerloginin.lua
2. player_login_specail.lua
3. Enter world

### Gameplay Runtime

* skill_process_callback_s.lua
* common_callback.lua
* action_bar_callback.lua
* battlefield_callback.lua
* xvx_callback.lua

### Death / Revive

* player_death_punish.lua
* count_down_revive.lua
* npcdeath_trigger.lua

### Logout

* playerlogout.lua

## Verification Status

* [ ] autoexec.lua reviewed
* [ ] globalcallback.lua reviewed
* [ ] playerloginin.lua reviewed
* [ ] playerlogout.lua reviewed

<!-- settings/reload_script_list.txt -->
## Hot Reload System

### File

* settings/reload_script_list.txt

### Current Observation

* File chỉ chứa danh sách script được phép reload nóng.
* Hiện tại thấy các file event online qixi08.

### Implication

* Không phải mọi script đều reload được.
* Các module core (`global`, `lib`, `skill`) có thể yêu cầu restart server sau khi sửa.

<!--  -->
# Server Boot Flow

## Confirmed Flow

### 1. Engine Startup

GameServer.exe

### 2. Lua Entry Point

script/global/autoexec.lua

### 3. Script Loading

autoexec.lua thực hiện hàng loạt Include() để nạp:

* script/lib/*
* script/global/*
* script/misc/*
* các module gameplay khác

### 4. Callback Registration

script/global/globalcallback.lua định nghĩa các callback mà engine C++ sẽ gọi.

Ví dụ:

* AddItemCallBack
* RemoveItemCallBack

### 5. Runtime

Khi sự kiện xảy ra trong game, engine gọi callback Lua tương ứng.
