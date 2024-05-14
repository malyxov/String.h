# String.h
Implementation of the string.h library in the C programming language with some additions (with its own implementation of the sprintf and sscanf functions)

## Запуск

   ```bash
   cd src/
   make
  ```

## Makefile
- `test` - компиляция и тесты основынх функций библиотеки string.h;
- `test_sharp` - компиляция и тесты cпециальных функций обработки строк (вдохновленные классом String в языке C#);
- `test_sprintf` - компиляция и тесты функции sprintf;
- `test_sscanf` - компиляция и тесты функции sscanf;
- `gcov_report` - покрытие кода, основная цель(файл `index.html` в папке `.\report`);
- `clang_test` - проверка стиля кода Google style;
- `clean`- очистка каталога.
