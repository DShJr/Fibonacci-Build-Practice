# 🚀 Fibonacci-Build-Practice

## EN

```markdown
**Description:** A practical C++ project to consolidate programming fundamentals and master modern build methods. The program calculates and outputs the first five Fibonacci numbers to the console.

The project demonstrates **two different approaches to compilation (Build Systems)**:
1. **Manual Build** using the **g++** compiler.
2. **Automated Build** using the **CMake** build system generator.

As part of simultaneously learning the `Bash` language, all builds are executed via the console using `Bash` commands.

Both builds are rooted in the main project directory: `fibonacci_project`.
Creating the directory via console:

```bash
mkdir fibonacci_project
cd fibonacci_project
````

Inside, **two files are created**:

`main.cpp` - Contains the code for calculating the Fibonacci numbers.

`CMakeLists.txt` - Contains instructions for the CMake build process.

-----

## 📁 01\_Manual\_GPP\_Build (Manual Build using g++)

### Step 1.

**Code:** `main.cpp`
(Code content is correct)

### Step 2.

**Manual Build Instruction:**

To create both Debug and Release versions of the program from the `fibonacci_project` root directory, execute a single console command:

```bash
g++ main.cpp -o fibonacci_debug -g && g++ main.cpp -o fibonacci_release -O2
```

  * `g++`: Invokes the GCC compiler.
  * `-o`: Creates the executable file.
  * `-g`: Adds **debugging symbols** (Debug Mode).
  * `-O2`: Enables **code optimization** (Release Mode).

<!-- end list -->

```bash
# Execute the Debug version
./fibonacci_debug

# Execute the Release version (optimized)
./fibonacci_release
```

Consequently, after running `fibonacci_release`, the **console output will be**:

```bash
Fibonacci number 1: 0
Fibonacci number 2: 1
Fibonacci number 3: 1
Fibonacci number 4: 2
Fibonacci number 5: 3
```

-----

## ⚙️ 02\_CMake\_Build (Automated Build using CMake)

The build process takes place in a separate `build` directory.

### Step 1.

**Code:** `CMakeLists.txt`

```cmake
# Minimum required CMake version
cmake_minimum_required(VERSION 3.10)

# Project name
project(FibonacciProject)

# Check which build type is selected
if(CMAKE_BUILD_TYPE STREQUAL "Debug")
    # If the mode is Debug, create an executable with the _debug suffix
    add_executable(fibonacci_app_debug main.cpp)
else()
    # Otherwise (for Release and other modes), create an executable with the _release suffix
    add_executable(fibonacci_app_release main.cpp)
endif()
```

### Step 2.

**Automated Build Instruction using CMake:**

The build happens in a separate `build` directory to maintain source code cleanliness.

1.  Create and navigate into the build folder:

    ```bash
    mkdir build
    cd build
    ```

2.  Generate build files in **Debug** mode AND Compile:

    ```bash
    cmake -DCMAKE_BUILD_TYPE=Debug .. && cmake --build .
    ```

3.  Generate build files in **Release** mode AND Compile:

    ```bash
    cmake -DCMAKE_BUILD_TYPE=Release .. && cmake --build .
    ```

As a result, two files will appear in the `build` directory: `fibonacci_app_debug` and `fibonacci_app_release`.

```
```


---
## RU

# 🚀 Fibonacci-Build-Practice

**Описание:** Практический проект на C++ для закрепления работы с методами сборки. Программа вычисляет и выводит в консоль первые пять чисел Фибоначчи.

Проект разделён на две части **два разных подхода к компиляции**:
1. **Ручная сборка** с помощью компилятора **g++**.
2. **Автоматизированная сборка** с помощью генератора сборочных файлов **CMake**.

Для паралельного обучения работы с языком `Bash`, сборки делаю через консоль используя команды языка `Bash`.

Обе сборки располоежены в директории: `fibonacci_project`.
Создам эту директорию через консоль:

```Bash
mkdir fibonacci_project
cd fibonacci_project
```

В ней **создам два файла**:
`main.cpp` - Содержит код вычисления числа Фибоначчи.
`CMakeLists.txt` - Содержит инструкции для сборки CMake.

## 📁 01_Manual_GPP_Build (Ручная сборка через g++)

### Шаг 1.

**Создаю в VSCode файл `main.cpp`** с кодом вычисления числа Фибоначчи.

**Код:** `main.cpp`

```CPP
#include <iostream>

int main() {
    // Вычисляем число Фибоначчи
    double f1 = 0.0;
    double f2 = 1.0;
    double f3 = f1 + f2;
    double f4 = f2 + f3;
    double f5 = f3 + f4;

    // Выводим найденные числа в консоль
    std::cout << "Fibonacci number 1: " << f1 << std::endl;
    std::cout << "Fibonacci number 2: " << f2 << std::endl;
    std::cout << "Fibonacci number 3: " << f3 << std::endl;
    std::cout << "Fibonacci number 4: " << f4 << std::endl;
    std::cout << "Fibonacci number 5: " << f5 << std::endl;

    return 0;
}
```

### Шаг 2.
**Инструкция по ручной сборке:**

Для создания Debug и Release версий программы из корневой директории `fibonacci_project` выполняю одну команду (через консоль):

```Bash
g++ main.cpp -o fibonacci_debug -g && g++ main.cpp -o fibonacci_release -O2
```
`g++`- вызов компилятора GCC.
`-o` - создаёт исполняемый файл fibonacci_
`-g` - добавляет отладочные символы (Debug Mode).
`-O2` - включает оптимизацию кода (Release Mode).

```Bash
# Запуск отладочной (Debug) версии
./fibonacci_debug

# Запуск оптимизированной (Release) версии
./fibonacci_release
```

В итоге, после запуска `fibonacci_release` **в консоли отобразится вывод**:
```Bash
Fibonacci number 1: 0
Fibonacci number 2: 1
Fibonacci number 3: 1
Fibonacci number 4: 2
Fibonacci number 5: 3
```

## 📁 02_CMake_Build (Автоматизированная сборка через CMake)
Сборка происходит в отдельной директории `build`.

### Шаг 1.
**Создаю в VSCode файл `CMakeLists.txt`**

**Код:** `CMakeLists.txt`

```CPP
# Минимально необходимая версия CMake
cmake_minimum_required(VERSION 3.10)

# Название проекта
project(FibonacciProject)

# Проверка, какой режим сборки выбран
if(CMAKE_BUILD_TYPE STREQUAL "Debug")
    # Если режим - Debug, создать файл с суффиксом _debug
    add_executable(fibonacci_app_debug main.cpp)
else()
    # Иначе (для Release), создать файл с суффиксом _release
    add_executable(fibonacci_app_release main.cpp)
endif()
```

### Шаг 2.
**Инструкция по Автоматизированной сборке через CMake:**

Сборка происходит в отдельной директории `build` для сохранения чистоты исходного кода.
Эта директория создаётся в корневой директории `fibonacci_release`, в которой так же лежат `main.cpp` и `CMakeLists.txt`.

Так же воспользуемся консолью.

Создаём и перейдём в папку для сборки:

```Bash
mkdir build
cd build
```

Генерация файлов сборки в режиме **Debug** `&&`Компиляция и сборка:

```Bash
cmake -DCMAKE_BUILD_TYPE=Debug .. && cmake --build .
```

Генерация файлов сборки в режиме **Release** `&&`Компиляция и сборка:

```Bash
cmake -DCMAKE_BUILD_TYPE=Release .. && cmake --build .
```

В результате в директории `build` появятся два файла: `fibonacci_app_debug` и `fibonacci_app_release`.
