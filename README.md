# devops-netology

## ДЗ "Инструменты Git"


1. Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.
    >aefead2207ef7e2aa5dc81a34aedf0cad4c32545

    >How: "git show aefea"

2. Какому тегу соответствует коммит 85024d3
    >v0.12.23

    >How: git show 85024d3

3. Сколько родителей у коммита b8d720? Напишите их хеши.
    >Два:<br> 
    >56cd7859e (56cd7859e05c36c06b56d013b55a252d0bb7e158)<br>
    >9ea88f22f (9ea88f22fc6269854151c571162c5bcf958bee2b)
    
    >How: git show b8d720 -> В описании gh сутствует запись о мерже "Merge: 56cd7859e 9ea88f22f"

4. Перечислите хеши и комментарии всех коммитов которые были сделаны между тегами v0.12.23 и v0.12.24
 
    >33ff1c03b (tag: v0.12.24) v0.12.24<br>
    >b14b74c49 [Website] vmc provider links<br>
    >3f235065b Update CHANGELOG.md<br>
    >6ae64e247 registry: Fix panic when server is unreachable<br>
    >5c619ca1b website: Remove links to the getting started guide's old location<br>
    >06275647e Update CHANGELOG.md<br>
    >d5f9411f5 command: Fix bug when using terraform login on Windows<br>
    >4b6d06cc5 Update CHANGELOG.md<br>
    >dd01a3507 Update CHANGELOG.md<br>
    >225466bc3 Cleanup after v0.12.23 release<br>
    >85024d310 (tag: v0.12.23) v0.12.23 
    
    >How: 
    >Вариант 1 - git log v0.12.24 -> Видим все что между ними.
    >Вариант 2 - git log --oneline v0.12.23..v0.12.24 (не видим коммита с тегом v0.12.23, только тот, что после него) -> git show --oneline v0.12.23
    > Для конкретно данного задания Вариант 1 быстрее.

5. Найдите коммит в котором была создана функция func providerSource, ее определение в коде выглядит так 
func providerSource(...) (вместо троеточего перечислены аргументы).
    >5af1e6234ab6da412fb8637393c5a17a1b293663
    
    >How: git log -S "func providerSource("

1. Найдите все коммиты в которых была изменена функция globalPluginDirs

    >35a058fb3 main: configure credentials from the CLI config file
    >c0b176109 prevent log output during init
    >8364383c3 Push plugin discovery down into command package
    
    >How: git log -S globalPluginDirs --oneline

2. Кто автор функции synchronizedWriters
    >Author: Martin Atkins <mart@degeneration.co.uk>

    >How: git log -S globalPluginDirs --oneline (берем последний хэш и смотрим информацию по нему) git show 8364383c3 (другие коммиты были сделаны позже другим человеком)




## Файлы, которые будут пропущены благодаря terraform/.gitignore

- Все файлы внутри скрытой директории .terraform, которая находится на любой глубине вложения диретории terraform
- Файлы с расширенеим tfstate
- Файлы, содержащие в имени .tfstate.
- Файл crash.log
- Все файлы с расширением tfvars
- Файлы override.tf override.tf.json terraform.rc .terraformrc
- Файлы, который оканчиваются на _override.tf _override.tf.json
