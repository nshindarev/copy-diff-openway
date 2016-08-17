# CopyDiff 

Утилита CopyDiff
 
Имеется три директории source_dir, target_dir и diff_dir.

Необходимо написать утилиту, которая копировала бы в diff_dir файлы из source_dir, которые отличаются от одноименных файлов в target_dir.

Для всех файлов source_dir (и рекурсивно для всех файлов ее субдиректорий) нужно выполнить следующие действия:
    Пусть source_dir\relative_path\file - файл из source_dir, где relative_path - путь к файлу относительно директории source_dir, file - имя файла.
    Если файл target_dir\relative_path\file не существует, то скопировать файл source_dir\relative_path\file в diff_dir\relative_path\file.
    Иначе, если файлы target_dir\relative_path\file и source_dir\relative_path\file отличаются, то тоже скопировать файл source_dir\relative_path\file в файл diff_dir\relative_path\file.

Алгоритм сравнения файлов:
                Если дата и размер файлов совпадают, то считать, что они одинаковые.
                Если дата у файлов разная, но размер одинаковый, произвести бинарное сравнение содержимого файлов.
                Иначе размер разный, и файлы, очевидно, разные
                
При этом необходимо предусмотреть возможность расширения утилиты дополнительными фильтрами (возможность копировать только те файлы, которые соответствуют условиям) и реализовать фильтр «Антивирус», который не позволят копировать файл, если в нем встречается определенная последовательность байт.
Задача на качество кода, необходимо использовать практики ООП, уделить внимание возможному изменению/расширению логики в будущем, а также обработке ошибок, написанию юнит-тестов.
Кроме того необходимо предоставить скрипт сборки приложения (с помощью Maven или Gradle). 

Разработку  необходимо вести на Java, для копирования файлов не рекомендуется использование сторонних библиотек.

usage:  аргументы для запуска утилиты
 -dest_dir <arg>     Путь по которому будут сохранены итоговые файлы
 -help               Отобразить информацию о параметрах запуска приложения
 -source_dir <arg>   Путь, содержащий исходную сравниваемую структуру файлов
 -target_dir <arg>   Путь, содержащий структуру файлов с которой сравниваем исходную
