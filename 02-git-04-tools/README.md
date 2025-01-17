# Домашнее задание к занятию «Инструменты Git» - RomanG

### Цель задания

В результате выполнения задания вы:

* научитесь работать с утилитами Git;
* потренируетесь решать типовые задачи, возникающие при работе в команде. 

### Инструкция к заданию

1. Склонируйте [репозиторий](https://github.com/hashicorp/terraform) с исходным кодом Terraform.
2. Создайте файл для ответов на задания в своём репозитории, после выполнения прикрепите ссылку на .md-файл с ответами в личном кабинете.
3. Любые вопросы по решению задач задавайте в чате учебной группы.

------

## Задание

В клонированном репозитории:

1. Найдите полный хеш и комментарий коммита, хеш которого начинается на `aefea`.

```
git show aefea
aefead2207ef7e2aa5dc81a34aedf0cad4c32545
command: Fix bug with global `-v`/`-version`/`--version` flags introduced in 0.13.0beta2 [GH-25277]
```
   
3. Ответьте на вопросы.

* Какому тегу соответствует коммит `85024d3`?
```
git log --oneline -1 85024d3
85024d3100 (tag: v0.12.23) v0.12.23
```

* Сколько родителей у коммита `b8d720`? Напишите их хеши.
```
git log --graph b8d720

Merge: 56cd7859e0 9ea88f22fc
```

* Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами  v0.12.23 и v0.12.24.
```
git log --oneline v0.12.23..v0.12.24

33ff1c03bb960b332be3af2e333462dde88b279e (tag: v0.12.24) v0.12.24
b14b74c4939dcab573326f4e3ee2a62e23e12f89 [Website] vmc provider links
3f235065b9347a758efadc92295b540ee0a5e26e Update CHANGELOG.md
6ae64e247b332925b872447e9ce869657281c2bf registry: Fix panic when server is unreachable
5c619ca1baf2e21a155fcdb4c264cc9e24a2a353 website: Remove links to the getting started guide's old location
06275647e2b53d97d4f0a19a0fec11f6d69820b5 Update CHANGELOG.md
d5f9411f5108260320064349b757f55c09bc4b80 command: Fix bug when using terraform login on Windows
4b6d06cc5dcb78af637bbb19c198faff37a066ed Update CHANGELOG.md
dd01a35078f040ca984cdd349f18d0b67e486c35 Update CHANGELOG.md
225466bc3e5f35baa5d07197bbc079345b77525e Cleanup after v0.12.23 release
```

* Найдите коммит, в котором была создана функция `func providerSource`, её определение в коде выглядит так: `func providerSource(...)` (вместо троеточия перечислены аргументы).
```
git log -L :providerSource:provider_source.go

commit 8c928e83589d90a031f811fae52a81be7153e82f - создана
commit 5af1e6234ab6da412fb8637393c5a17a1b293663 - изменена
```

* Найдите все коммиты, в которых была изменена функция `globalPluginDirs`.
```
git log -L :globalPluginDirs:plugins.go

78b12205587fe839f10d946ea3fdc06719decb05
52dbf94834cb970b510f2fba853a5b49ad9b1a46
41ab0aef7a0fe030e84018973a64135b11abcd70
66ebff90cdfaa6938f26f908c7ebad8d547fea17
8364383c359a6b738a436d1b7745ccdce178df47 - здесь была создана
```

* Кто автор функции `synchronizedWriters`?
```
git log -S"synchronizedWriters"

commit 5ac311e2a91e381e2f52234668b49ba670aa0fe5
Author: Martin Atkins <mart@degeneration.co.uk>
Date:   Wed May 3 16:25:41 2017 -0700
```

*В качестве решения ответьте на вопросы и опишите, как были получены эти ответы.*
