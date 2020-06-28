# МАИ - Вычислительная практика - 2ой курс
Здесь будет выкладываться всякий треш для практики
## MiniOS
### Файлы репозитория
_readme.md_ - этот текст

_source.zip_ - исходники MiniOS

_MiniOS doc_ - документация MiniOS

_compile.sh_ - автор не поленился и написал мини скрипт, который автоматизирует вашу собрку этой "прекрасной" ОС :3

_makefile_ - исправленный makefile (желательно не использовать его вручную, потому что процесс сборки MiniOS имеет свойство ломаться)

### Как собрать Это? ###

В исходном makefile, который находится в source.zip есть несколько ошибок, из-за которых зачастую эта ось не собирается. Для того, чтобы скомпилировать и использовать эту операционную систему необходимо сделать следующее:

0. **Установить Ubuntu 16.04 и обновить пакеты** (```sudo apt-get update```)
1. **Распаковать source.zip** и перейти к исходникам где находится makefile.
2. **Заменить makefile, на новый makefile**, который находится в этом репозитории.
3. К исходникам **добавить скрипт compile.sh** (также находится в этом репозитории).
4. В папке проекта **необходимо создать файл .gdbinit с содержанием “ set auto-load safe-path /”**
5. **Выполнить ряд команд** находясь в папке с исходниками:
```bash
sudo apt install gcc make nasm qemu cgdb grub
сhmod ugo+x run_qemu.sh
chmod ugo+x compile.sh
sudo ./compile.sh
sudo ./run_qemu.sh
```
Если у вас по каким-то причинам **не работает chmod** и его не получается установить, то делаете это:
```bash
sudo apt install gcc make nasm qemu cgdb grub
sudo bash ./compile.sh
sudo bash ./run_qemu.sh
```


Скрипт compile.sh скомпилирует ядро ос, образ и добавит в образ ядро.

Скрипт run_qemu.sh запустит ос в qemu

В итоге всех махинаций получается образ MiniOS - hdd.img. Как запустить его с флешки - я хз)

К слову, если вы отчаянный человек и решите хоть насколько то уйти от предложенного гайда, скорее всего у вас все сломается))) (речь идет не просто о соблюдении порядка команд, но и версии ос на которой можно собрать данную ос)
