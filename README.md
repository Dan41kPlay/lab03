# Homework
## by: Daniel Zakirov (IU8-23)

Представьте, что вы стажер в компании "Formatter Inc.".

### Задание 1
Вам поручили перейти на систему автоматизированной сборки **CMake**.
Исходные файлы находятся в директории [formatter_lib](formatter_lib).
В этой директории находятся файлы для статической библиотеки *formatter*.
Создайте `CMakeList.txt` в директории [formatter_lib](formatter_lib),
с помощью которого можно будет собирать статическую библиотеку *formatter*.

See the file [CMakeLists.txt](formatter_lib/CMakeLists.txt)

```bash
$ cd formatter_lib
$ cmake -B build .
-- Configuring done (0.0s)
-- Generating done (0.0s)
-- Build files have been written to: /home/dp/Documents/sem02_TP/lab03/formatter_lib/build
$ cmake --build build
[ 50%] Building CXX object CMakeFiles/formatter.dir/formatter.cpp.o
[100%] Linking CXX static library libformatter.a
[100%] Built target formatter
```

### Задание 2
У компании "Formatter Inc." есть перспективная библиотека,
которая является расширением предыдущей библиотеки. Т.к. вы уже овладели
навыком созданием `CMakeList.txt` для статической библиотеки *formatter*, ваш 
руководитель поручает заняться созданием `CMakeList.txt` для библиотеки 
*formatter_ex*, которая в свою очередь использует библиотеку *formatter*.

See the file [CMakeLists.txt](formatter_ex_lib/CMakeLists.txt)

```bash
$ cd formmater_ex_lib
$ cmake -B build .
-- Configuring done (0.0s)
-- Generating done (0.0s)
-- Build files have been written to: /home/dp/Documents/sem02_TP/lab03/formatter_ex_lib/build
$ cmake --build build
[ 50%] Built target formatter
[ 75%] Building CXX object CMakeFiles/formatter_ex.dir/formatter_ex.cpp.o
[100%] Linking CXX static library libformatter_ex.a
[100%] Built target formatter_ex
```

### Задание 3
Конечно же ваша компания предоставляет примеры использования своих библиотек.
Чтобы продемонстрировать как работать с библиотекой *formatter_ex*,
вам необходимо создать два `CMakeList.txt` для двух простых приложений:
* *hello_world*, которое использует библиотеку *formatter_ex*;
* *solver*, приложение которое испольует статические библиотеки *formatter_ex* и *solver_lib*.

#### hello_world_application

See the file [CMakeLists.txt](hello_world_application/CMakeLists.txt)

```bash
$ cd hello_world_application
$ cmake -B build .
-- Configuring done (0.0s)
-- Generating done (0.0s)
-- Build files have been written to: /home/dp/Documents/sem02_TP/lab03/hello_world_application/build
$ cmake --build build
[ 33%] Built target formatter
[ 66%] Built target formatter_ex
[ 83%] Building CXX object CMakeFiles/hello_world.dir/hello_world.cpp.o
[100%] Linking CXX executable hello_world
[100%] Built target hello_world
```

#### solver_lib

See the file [CMakeLists.txt](solver_lib/CMakeLists.txt)

```bash
$ cd solver_lib
$ cmake -B build .
-- Configuring done (0.0s)
-- Generating done (0.0s)
-- Build files have been written to: /home/dp/Documents/sem02_TP/lab03/solver_lib/build
$ cmake --build build
[ 50%] Building CXX object CMakeFiles/solver_lib.dir/solver.cpp.o
[100%] Linking CXX static library libsolver_lib.a
[100%] Built target solver_lib
```

#### solver_application

See the file [CMakeLists.txt](solver_application/CMakeLists.txt)

```bash
$ cd solver_application
$ cmake -B build .
-- Configuring done (0.0s)
-- Generating done (0.0s)
-- Build files have been written to: /home/dp/Documents/sem02_TP/lab03/solver_application/build
$ cmake --build build
[ 12%] Building CXX object solver_lib/CMakeFiles/solver_lib.dir/solver.cpp.o
[ 25%] Linking CXX static library libsolver_lib.a
[ 25%] Built target solver_lib
[ 50%] Built target formatter
[ 75%] Built target formatter_ex
[ 87%] Linking CXX executable solver
[100%] Built target solver
```
