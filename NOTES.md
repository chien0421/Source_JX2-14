<!-- Ghi chú cá nhân tạm thời -->
# Nhóm quan trọng nhất (đọc trong tháng đầu)

## Đọc trong tháng đầu      → dữ liệu cốt lõi của gameplay
item/
skill/
npc/
player/
task/
missions/
droprate/

## Đọc sau khi hiểu gameplay core   → Liên quan PvP và bang hội
battles/
newbattles/
camp/
StateChess/
tongsetting/

## Nhóm hệ thống vận hành
reload_script_list.txt      → cơ chế reload script nóng
timer_task.txt              → scheduler nhiệm vụ theo thời gian
systemtimetask.txt
system_notice.txt

#
- Có hai thư mục online_activies và online_activites, cần xác định thư mục nào thực sự được load.

# 
- skill_process_callback_s.lua có khả năng là callback xử lý skill phía server, rất quan trọng cho AI BOT.

#
- autoexec.1.100.lua có thể là script patch/version-specific, cần kiểm tra sau khi hiểu autoexec.lua.

#
- settings/reload_script_list.txt là whitelist hot reload.
- Event online có thể reload nóng.
- Core gameplay có thể cần restart server sau khi sửa.
- Thiết kế tính năng mới nên theo mẫu head.lua + npc.lua + item/.