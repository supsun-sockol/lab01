    Скачайте библиотеку boost с помощью утилиты wget. Адрес для скачивания https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz.
1) Ввод:wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boo      st_1_69_0.tar.gz
2) Вывод: куча технической инфы
    Разархивируйте скаченный файл в директорию ~/boost_1_69_0
1) Ввод: tar -xf boost_1_69_0.tar.gz
2) Вывод: отсутствует
    Подсчитайте количество файлов в директории ~/boost_1_69_0 не включая вложенные директории.
1) Ввод: find ./ -maxdepth 1 | wc
2) Вывод 19 19 209
> -maxdepth задает максивальную глубину поиска

> 19 это включая саму директорию, поэтому ответ 18

> wc выводит кол-во строк, слов, букв

    Подсчитайте количество файлов в директории ~/boost_1_69_0 включая вложенные директории.
1) Ввод: find ./ | wc
2) Вывод: 66829   66832 3286648
> ответ 66828

    Подсчитайте количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp).
1) Ввод: find ./ -name "*.h" |wc
2) Вывод:296     296   11738
1) Ввод: find ./ -name "*.cpp" |wc
2) Вывод: 13774   13774  647953
1) Ввод: find ./ -not -name "*.h" -not -name "*.cpp" |wc
2) Вывод: 52759   52762 2626957
    Найдите полный пусть до файла any.hpp внутри библиотеки boost.
1) Ввод: find ./ -name "any.hpp"
2) Вывод:
* ./include/boost/any.hpp
* ./include/boost/spirit/home/support/algorithm/any.hpp
* ./include/boost/xpressive/detail/utility/any.hpp
* ./include/boost/hana/any.hpp
* ./include/boost/hana/fwd/any.hpp
* ./include/boost/proto/detail/any.hpp
* ./include/boost/fusion/include/any.hpp
* ./include/boost/fusion/algorithm/query/any.hpp
* ./include/boost/fusion/algorithm/query/detail/any.hpp
* ./include/boost/type_erasure/any.hpp
> Ответ: ~/boost_1_69_0/include/boost/any.hpp

    Выведите в консоль все файлы, где упоминается последовательность boost::asio.
1) Ввод: grep -r "boost::asio" ./
2) Вывод: очень много вского
> grep позволяет осуществить поиск внутри файла

    Скомпилирутйе boost. Можно воспользоваться инструкцией или ссылкой.
1) Ввод: 
* ./bootstrap.sh --prefix=boost_output
* ./b2 install

2) Вывод: неперевариваемое колличество бесполезной для меня информации

    Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs.
1) Ввод:
* mkdir ~/boost-libs
* mv boost_output/ ~/boost-libs/

2) Вывод: ничего

    Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.

1)Ввод: ls -Rgh
2)Вывод: на консоли появляется 67 тысяч строк со всеми файлами в нашей папке, приводить их здесь я не буду

    Найдите топ10 самых "тяжёлых".

1) Ввод: find . -type f -exec ls -s {} \; | sort -n | head -10
> find ищет все файлы, ls -s выводит информацию о них sort -n сортирует по размеру, head -10 выводит топ 10

2) Вывод:
* ./boost_out/include/boost/accumulators/accumulators.hpp
* ./boost_out/include/boost/accumulators/framework/accumulator_base.hpp
* ./boost_out/include/boost/accumulators/framework/accumulator_concept.hpp
* ./boost_out/include/boost/accumulators/framework/accumulators/external_accumulator.hpp
* ./boost_out/include/boost/accumulators/framework/accumulators/reference_accumulator.hpp
* ./boost_out/include/boost/accumulators/framework/accumulators/value_accumulator.hpp
* ./boost_out/include/boost/accumulators/framework/external.hpp
* ./boost_out/include/boost/accumulators/framework/features.hpp
* ./boost_out/include/boost/accumulators/framework/parameters/accumulator.hpp
* ./boost_out/include/boost/accumulators/framework/parameters/sample.hpp
