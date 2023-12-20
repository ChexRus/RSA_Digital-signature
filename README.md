Пусть выбираются случайные большие простые числа Р и Q, равной длины, которые являются секретом. Данные числа образуют модуль N, используемый для нормирования результатов: N = P*Q.

Открытый ключ Ко выбирают случайным образом так, чтобы выполнялись условия:

1< Kо ≤ j(N),

НОД(Kо, j(N)) = 1 (числа Kо и j(N) взаимнопросты),

j(N)=(P-1)(Q-1),

где j(N) - функция Эйлера.

Далее, используя расширенный алгоритм Евклида, вычис­ляется секретный ключ Kс как обратный элемент к  Kо, такой, что

Kc * Ко ≡ 1 mod j(N) или Kc = Ко-1 mod(P-1)(Q-1).

Пусть отправитель хочет подписать сообщение М пе­ред его отправкой. Сначала сообщение М сжимают с помощью хэш-функции hп(*) в целое число m: m = h(М). В качестве хэш-функции, в рамках данной лабораторной можно использовать операцию алгоритма RSA и операцию xor (исключающее или): возведение блока открытого текста в степень, являющуюся открытым ключом Ko и сложение по xor с предыдущим значением хеш: m = (m Å (MiKo) mod N) mod N. 

Затем вычисляют цифровую подпись S под электронным докумен­том М, используя хэш-значение m и секретный ключ Kc: 

S = mKc mod N.

Числа (N, Ko, M, S) передается партнеру-получателю как электрон­ный документ М, подписанный цифровой подписью S.

После приема чисел получатель вычисляет хэш-зна­чение сообщения М двумя разными способами. Он восстанавливает хэш-значение m", применяя криптографическое преобразование подписи S с использованием открытого ключа Ko: m"=SKo mod N.

Кроме того, он находит результат хэширования принятого сообщения М с помощью такой же хэш-функции h(*): m’ = h(M).

Если соблюдается равенство вычисленных значений m’’ = m’, то получатель признает подлинность ЭЦП.
