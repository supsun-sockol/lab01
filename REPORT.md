В конце файла приведена история терминала, в которой показаны все, введенные мной команды.
1) Скачал файл (шаг 326)
2) Разархиваровал (шаг 327)
3) Подсчитал, получил 18 файлов (шаг 328)
    для подсчета использовал функцию find, которая ищет файлы в данный директории, удвалетворяющие данным требованиям. Результат работы find я передвал функции "туалет", которая считала кол-во строчек, слов, символов. Нам нужно только число файлов - первое выведенные число. Иногда find выводила пустую директорию в начале, ее считать не нужно.
4) 66828 файлов всего ( шаг 332)
5) 296 заголовочных файлов (шаг 333), 13774 спипишных файлов (334), 52758 остальных. (335)
6) /home/Supsun/boost_1_69_0/boost/any.hpp (336)
7) вывел, приводить их здесь не буду, их слишком много (337)
8) скомпилировал (338, 339)
9) забыл команду, поэтому открыл консольный файловый менеджер и сделал все в нем (341)
10) вывел все файлы с их размером (это было в другом терминале, поэтому поверьте на слово)
11) вот список из 10  самых тяжелых файлов (343) 

4 ./boost_out/include/boost/accumulators/accumulators.hpp
4 ./boost_out/include/boost/accumulators/framework/accumulator_base.hpp
4 ./boost_out/include/boost/accumulators/framework/accumulator_concept.hpp
4 ./boost_out/include/boost/accumulators/framework/accumulators/external_accumulator.hpp
4 ./boost_out/include/boost/accumulators/framework/accumulators/reference_accumulator.hpp
4 ./boost_out/include/boost/accumulators/framework/accumulators/value_accumulator.hpp
4 ./boost_out/include/boost/accumulators/framework/external.hpp
4 ./boost_out/include/boost/accumulators/framework/features.hpp
4 ./boost_out/include/boost/accumulators/framework/parameters/accumulator.hpp
4 ./boost_out/include/boost/accumulators/framework/parameters/sample.hpp

  326 wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
  327  ls
  328  tar -xvf boost_1_69_0.tar.gz 
  329  cd boost_1_69_0/
  330  find ./ -maxdepth 1
  331  find ./ -maxdepth 1 |wc
  332  find ./ |wc
  333  find ./ -name "*.h" |wc
  334  find ./ -name "*.cpp" |wc
  335  find ./ -not -name "*.h" -not -name "*.cpp" |wc
  336  find ./ -name "any.hpp"
  337  grep -r "boost::asio" ./
  338  ./bootstrap.sh --prefix=boost_output
  339  ./b2 install
  340  ls
  341  mc
  342  cd ../boost_libs/
  343  find . -type f -exec ls -s {} \; | sort -n | head -10
  344  history
