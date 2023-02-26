# ❖ restore-win-bootloader
Восстановление загрузчика Windows <br>

*Небольшой Guide для удобства.*

## Команды

**Diskpart** <br>
Открываем Diskpart и смотрим список дисков
```
diskpart
lis dis
```
Выбираем диск который нужен
```
sel dis 0
```
Смотрим список *Volumes* <br>
Выбираем *EFI* раздел
```
list vol
sel vol
```

В моем случае это Volume 8
```
sel vol 8
```

Назначаем метку и выходим из утилиты
```
assign letter=S
exit
```

Восстанавливаем загрузчик в режиме UEFI
```
bcdboot C: /s S: /f UEFI
```
*C:* - Диск с ОС <br>
*/s* - Системный раздел EFI <br>
*/f* - Firmware type (UEFI or ALL)

**Загрузчик восстановлен :)**