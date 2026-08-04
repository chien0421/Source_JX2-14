# Callback System

## Source

* script/global/globalcallback.lua

## Confirmed Callbacks

* AddItemCallBack(nItemIndex, nPlayerIndex)
* RemoveItemCallBack(nItemIndex, nBelonerIndex)

## Architecture

Engine C++ gọi trực tiếp các hàm Lua theo tên cố định.

## Rules

* Không đổi tên callback.
* Không đổi chữ ký hàm.
* Không throw error chưa bắt trong callback.

## Notes

Callback hiện tại chuyển tiếp sang hệ thống log vật phẩm giá trị.
