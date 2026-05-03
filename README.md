## Part I


1. Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).
Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.
	
 ```bash
 git init
 ```
подсказка: Using 'master' as the name for the initial branch. This default branch name 
подсказка: is subject to change. To configure the initial branch name to use in all 
подсказка: of your new repositories, which will suppress this warning, call: 
подсказка:  
подсказка: 	git config --global init.defaultBranch <name> 
подсказка:  
подсказка: Names commonly chosen instead of 'master' are 'main', 'trunk' and 
подсказка: 'development'. The just-created branch can be renamed via this command: 
подсказка:  
подсказка: 	git branch -m <name> 
Инициализирован пустой репозиторий Git в /home/marsi/MarsiSomeone/tasks/lab02/.git/ 

```bash
git config --global user.name MarsiSomeone
git config --global user.email sirlovaolga@gmail.com
git remote add origin https://github.com/MarsiSomeone/lab02.0.git
git branch -m master main
```

```bash
touch READMW.md
git status
```
Текущая ветка: main

Еще нет коммитов

Неотслеживаемые файлы:
  (используйте «git add <файл>...», чтобы добавить в то, что будет включено в коммит)
	READMW.md
	lab02/

индекс пуст, но есть неотслеживаемые файлы
(используйте «git add», чтобы проиндексировать их)
it add READMW.md 
mgit commit -m"add README"
[main (корневой коммит) 66e2eab] add README
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 READMW.md

Перечисление объектов: 4, готово.
Подсчет объектов: 100% (4/4), готово.
При сжатии изменений используется до 2 потоков
Сжатие объектов: 100% (2/2), готово.
Запись объектов: 100% (3/3), 304 байта | 304.00 КиБ/с, готово.
Всего 3 (изменений 1), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/MarsiSomeone/lb2.git
   c362cac..7e0e352  master -> master

```bash
git push origin main
```

Username for 'https://github.com': MarsiSomeone
Password for 'https://MarsiSomeone@github.com': 
Перечисление объектов: 3, готово.
Подсчет объектов: 100% (3/3), готово.
Запись объектов: 100% (3/3), 218 байтов | 218.00 КиБ/с, готово.
Всего 3 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To https://github.com/MarsiSomeone/lab02.0.git
 * [new branch]      main -> main

    
2. Создайте файл hello_world.cpp в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу Hello world на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку using namespace std;.
```bash    
    cat > hello_world.cpp <<EOF
> #include <iostream>    
>  
#include <iostream>    
using namespace std;  
int main()
{cout<<"aaa"<<endl; return 0;}  
> EOF
```


    
    
3. Добавьте этот файл в локальную копию репозитория.
```bash
git add hello_world.cpp
```
    
4. Закоммитьте изменения с осмысленным сообщением.
    
```bash    
git commit -m"add hello_world"
```
[main f3008fd] add hello_world
 1 file changed, 7 insertions(+)
 create mode 100644 hello_world.cpp

    
5. Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение Hello world from @name, где @name имя пользователя.
```bash
    nano hello_world.cpp
	#include <iostream>        
	#include <string>
	using namespace std;  
	int main()
	{
	string n;
	cout<<"Enter ypur name: "<<endl;
	cin>>n;
	cout<<"Hello world from "<<n <<endl; 
	return 0;
	}  
```

6. Закоммитьте новую версию программы. Почему не надо добавлять файл повторно git add?

```bash
    git commit -a -m"upgrade hello_world"
```
[main fd8bbdd] upgrade hello_world
 1 file changed, 10 insertions(+), 6 deletions(-)
git add можно повторно не добавлять т. к. -a автоматически добавляет все изменения в файлах, которые уже были добавлены в репозиторий ранее
    

7. Запуште изменения в удалёный репозиторий.

	```bash
    git push origin main
	```
Username for 'https://github.com': MarsiSomeone
Password for 'https://MarsiSomeone@github.com': 
Перечисление объектов: 7, готово.
Подсчет объектов: 100% (7/7), готово.
При сжатии изменений используется до 2 потоков
Сжатие объектов: 100% (6/6), готово.
Запись объектов: 100% (6/6), 768 байтов | 256.00 КиБ/с, готово.
Всего 6 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To https://github.com/MarsiSomeone/lab02.0.git
   66e2eab..fd8bbdd  main -> main

    
8. Проверьте, что история коммитов доступна в удалёный репозитории.

## Part II

Note: Работать продолжайте с теми же репоззиториями, что и в первой части задания.

1. В локальной копии репозитория создайте локальную ветку patch1.

```bash    
    git branch 
```
* main
   ```bash
    git checkout -b patch1
   ```
Переключились на новую ветку «patch1»


    
2. Внесите изменения в ветке patch1 по исправлению кода и избавления от using namespace std;.

```bash
    nano hello_world.cpp
                            
#include <iostream>
#include <string>
int main(){

std::string n;
std::cout<<"Enter name: ";
std::cin >> n;
std::cout<<std::endl<<"Hello world from "<<n<<std::endl;
 return 0;}
```
3. commit, push локальную ветку в удалённый репозиторий.
    
```bash    
git commit -a -m"upgrade hello_world patch1"
```
[patch1 d11b9c9] upgrade hello_world patch1
 1 file changed, 7 insertions(+), 9 deletions(-)
    git push -u origin patch1 
Username for 'https://github.com': MarsiSomeone
Password for 'https://MarsiSomeone@github.com': 
Перечисление объектов: 5, готово.
Подсчет объектов: 100% (5/5), готово.
При сжатии изменений используется до 2 потоков
Сжатие объектов: 100% (3/3), готово.
Запись объектов: 100% (3/3), 419 байтов | 209.00 КиБ/с, готово.
Всего 3 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
remote: 
remote: Create a pull request for 'patch1' on GitHub by visiting:
remote:      https://github.com/MarsiSomeone/lab02.0/pull/new/patch1
remote: 
To https://github.com/MarsiSomeone/lab02.0.git
 * [new branch]      patch1 -> patch1
branch 'patch1' set up to track 'origin/patch1'.



4. Проверьте, что ветка patch1 доступна в удалёный репозитории.
    
    
5. Создайте pull-request patch1 -> master.
    
    
6. В локальной копии в ветке patch1 добавьте в исходный код комментарии.
```bash
   nano hello_world.cpp
    
      //main function
    int main(){
    //world execute.(me)
    std::string n;//variabre
    std::cout<<"Enter name: ";//output comment
    std::cin >> n;//input function
    std::cout<<std::endl<<"Hello world from "<<n<<std::endl;//final output
     return 0;}
```     

7. commit, push.

```bash    
git commit -a -m"upgrade hello_world patch1 second time"
```
[patch1 bf35661] upgrade hello_world patch1 second time
 1 file changed, 7 insertions(+), 8 deletions(-)

```bash
git push -u origin patch1
``` 
Username for 'https://github.com': MarsiSomeone
Password for 'https://MarsiSomeone@github.com': 
Перечисление объектов: 5, готово.
Подсчет объектов: 100% (5/5), готово.
При сжатии изменений используется до 2 потоков
Сжатие объектов: 100% (3/3), готово.
Запись объектов: 100% (3/3), 460 байтов | 460.00 КиБ/с, готово.
Всего 3 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To https://github.com/MarsiSomeone/lab02.0.git
   d11b9c9..bf35661  patch1 -> patch1
branch 'patch1' set up to track 'origin/patch1'.



8. Проверьте, что новые изменения есть в созданном на шаге 5 pull-request
    
    
9. В удалённый репозитории выполните слияние PR patch1 -> master и удалите ветку patch1 в удаленном репозитории.
    
    
10. Локально выполните pull.
    
```bash
	git pull
```
Уже актуально.

    
    С помощью команды git log просмотрите историю в локальной версии ветки master.

```bash
    git log
```
commit bf356618732412b5d42553bae20bf4f789cec362 (HEAD -> patch1, origin/patch1)
Author: MarsiSomeone <sirlovaolga@gmail.com>
Date:   Sun May 3 12:49:00 2026 +0300

    upgrade hello_world patch1 second time

commit d11b9c923000117a6725fba190b160c02fd5532e
Author: MarsiSomeone <sirlovaolga@gmail.com>
Date:   Sun May 3 12:40:28 2026 +0300

    upgrade hello_world patch1

commit fd8bbdd00cb1abd792a92e47ee8fa789d6256631 (origin/main, main)
Author: MarsiSomeone <sirlovaolga@gmail.com>
Date:   Sun May 3 12:12:55 2026 +0300

    upgrade hello_world

commit f3008fd6d8ba336717d9f50c2245f4cfa3110160
Author: MarsiSomeone <sirlovaolga@gmail.com>
Date:   Sun May 3 01:25:34 2026 +0300

    add hello_world

commit 66e2eab1323ea76d9318a7fc283b93df98c5239b
Author: MarsiSomeone <sirlovaolga@gmail.com>
Date:   Sun May 3 01:10:23 2026 +0300

    add README
(END)


    
Удалите локальную ветку patch1.

```bash
    git checkout main
```
Переключились на ветку «main»

```bash
    git branch -d patch
```
warning: deleting branch 'patch1' that has been merged to
         'refs/remotes/origin/patch1', but not yet merged to HEAD
Ветка patch1 удалена (была bf35661).

    

## Part III

Note: Работать продолжайте с теми же репоззиториями, что и в первой части задания.

1. Создайте новую локальную ветку patch2. Переключились на новую ветку «patch2»

```bash
git checkout -b patch2
```
Переключились на новую ветку «patch2»
     
    
2. Измените code style с помощью утилиты clang-format. Например, используя опцию -style=Mozilla.

```bash	
cat hello_world.cpp 
//main function
int main(){
//world execute.(me)
std::string n;//variabre
std::cout<<"Enter name: ";//output comment
std::cin >> n;//input function
std::cout<<std::endl<<"Hello world from "<<n<<std::endl;//final output
return 0;}

clang-format -i -style=Mozilla hello_world.cpp 
cat hello_world.cpp 

#include <iostream>
#include <string>
// main function
int
main()
{
  // world execute.(me)
  std::string n;               // variabre
  std::cout << "Enter name: "; // output comment
  std::cin >> n;               // input function
  std::cout << std::endl
            << "Hello world from " << n << std::endl; // final output
  return 0;
}
```


    
3. commit, push, создайте pull-request patch2 -> master.

```bash
git commit -a -m"upgrade hello_world"
```   
[patch2 19407b1] upgrade hello_world
 1 file changed, 2 insertions(+)

 ```bash
 git push -u origin patch2 
 ```
Username for 'https://github.com': MarsiSomeone
Password for 'https://MarsiSomeone@github.com': 
Перечисление объектов: 12, готово.
Подсчет объектов: 100% (12/12), готово.
При сжатии изменений используется до 2 потоков
Сжатие объектов: 100% (10/10), готово.
Запись объектов: 100% (12/12), 1.31 КиБ | 672.00 КиБ/с, готово.
Всего 12 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
remote: 
remote: Create a pull request for 'patch2' on GitHub by visiting:
remote:      https://github.com/MarsiSomeone/lab02.0/pull/new/patch2
remote: 
To https://github.com/MarsiSomeone/lab02.0.git
 * [new branch]      patch2 -> patch2
branch 'patch2' set up to track 'origin/patch2'.

    
4. В ветке master в удаленном репозитории измените комментарии, например, расставьте знаки препинания, переведите комментарии на другой язык.

```bash
#include <iostream>
#include <string>
//главная функция
int main(){
//world execute.(me)
std::string n;//переменная
std::cout<<"Enter name: ";//функция выводв
std::cin >> n;//функция ввода
std::cout<<std::endl<<"Hello world from "<<n<<std::endl;//итоговый вывод
return 0;}
```
    
5. Убедитесь, что в pull-request появились конфликтны.Для этого локально выполните pull + rebase (точную последовательность команд, следует узнать самостоятельно). Исправьте конфликты.

```bash
git fetch origin
```
remote: Enumerating objects: 11, done.
remote: Counting objects: 100% (11/11), done.
remote: Compressing objects: 100% (7/7), done.
remote: Total 7 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
Распаковка объектов: 100% (7/7), 2.97 КиБ | 304.00 КиБ/с, готово.
Из https://github.com/MarsiSomeone/lab02.0
   fd8bbdd..f3fd746  main       -> origin/main


```bash   
git rebase origin/main
```
Автослияние hello_world.cpp
КОНФЛИКТ (содержимое): Конфликт слияния в hello_world.cpp
error: не удалось применить коммит fa8fcae... upgrade hello_world
подсказка: Resolve all conflicts manually, mark them as resolved with
подсказка: "git add/rm <conflicted_files>", then run "git rebase --continue".
подсказка: You can instead skip this commit: run "git rebase --skip".
подсказка: To abort and get back to the state before "git rebase", run "git rebase --abort".
Не удалось применить коммит fa8fcae... upgrade hello_world


```bash
nano hello_world.cpp 
#include <iostream>
#include <string>

//главная функция
int main(){
//world execute.(me)
std::string n;//переменная
std::cout<<"Enter name: ";//функция выводв
std::cin >> n;//функция ввода
std::cout<<std::endl<<"Hello world from "<<n<<std::endl;//итоговый вывод
return 0;}

     git add hello_world.cpp 
     git rebase --continue
```
[отделённый HEAD a98e578] upgrade hello_world
 1 file changed, 1 insertion(+)
Успешно перемещён и обновлён refs/heads/patch2.
    
6. Сделайте force push в ветку patch2
```bash    
git push --force-with-lease origin patch2
```
Username for 'https://github.com': MarsiSomeone
Password for 'https://MarsiSomeone@github.com': 
Перечисление объектов: 5, готово.
Подсчет объектов: 100% (5/5), готово.
При сжатии изменений используется до 2 потоков
Сжатие объектов: 100% (3/3), готово.
Запись объектов: 100% (3/3), 329 байтов | 329.00 КиБ/с, готово.
Всего 3 (изменений 1), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/MarsiSomeone/lab02.0.git
 + fa8fcae...a98e578 patch2 -> patch2 (forced update)


7. Убедитель, что в pull-request пропали конфликтны.
    
    
8. Вмержите pull-request patch2 -> master.
    
    
