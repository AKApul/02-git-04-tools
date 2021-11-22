# 02-git-04-tools
1. Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.

полный хэш:
aefead2207ef7e2aa5dc81a34aedf0cad4c32545
комментарий коммита:
Update CHANGELOG.md

получен командой:
git show aefea
хэш также может быть получен командой:
git rev-parse aefea




2. Какому тегу соответствует коммит 85024d3?

tag: v0.12.23

получен командой:
git show 85024d3

3. Сколько родителей у коммита b8d720? Напишите их хеши.

2 родителя, хэши:
^1:56cd7859e05c36c06b56d013b55a252d0bb7e158
^2:9ea88f22fc6269854151c571162c5bcf958bee2b

Получено командой:
git log b8d720 --graph
также можно посмотреть хэши командами:
git show b8d720^1
git show b8d720^2


4. Перечислите хеши и комментарии всех коммитов которые были сделаны между тегами v0.12.23 и v0.12.24.

33ff1c03b (tag: v0.12.24) v0.12.24
b14b74c49 [Website] vmc provider links
3f235065b Update CHANGELOG.md
6ae64e247 registry: Fix panic when server is unreachable
5c619ca1b website: Remove links to the getting started guide's old location
06275647e Update CHANGELOG.md
d5f9411f5 command: Fix bug when using terraform login on Windows
4b6d06cc5 Update CHANGELOG.md
dd01a3507 Update CHANGELOG.md
225466bc3 Cleanup after v0.12.23 release

Получено командой:
git show v0.12.23..v0.12.24 --oneline --no-patch


5. Найдите коммит в котором была создана функция func providerSource, ее определение в коде выглядит так func providerSource(...) (вместо троеточего перечислены аргументы).

хэш коммита 8c928e835

Получено командой:
git log -S"func providerSource(" --oneline

6. Найдите все коммиты в которых была изменена функция globalPluginDirs.

35a058fb3
c0b176109
8364383c3

Получено командой:
git log -S"globalPluginDirs" --oneline --pretty=format:"%h"

7.Кто автор функции synchronizedWriters?

Martin Atkins

Получено командой (по более ранней дате определили кто был автором):
git log -S"func synchronizedWriters(" --pretty=format:"%an %ad"
