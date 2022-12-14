# Вопрос 11
## Распространенные типы уязвимостей и атак на блокчейн-сети

- Атака 51%

- Атака Eclipse
Она же атака затмения – особый тип кибератаки, когда хакер формирует искусственную область возле одного нода для контроля его действий. Злоумышленник перенаправляет исходящие и входящие данные с целевого узла на свои собственные, отделяя обманутого пользователя от реальной сети.

- Атака Сивиллы (Сибиллы)
Узел в блокчейне  приобретает несколько сущностей. Она основывается на том, что сеть не может достоверно различать физические машины.

- Атака Финни
Первым получателем биткоин-транзакции был Хэл Финни и именно он первым заговорил о запуске биткоина. Он также был первым, кто предположил возможность двойной атаки на сеть.

Финни Хак – это тип атаки с двойными расходами, что может произойти, когда человек принимает неподтвержденную транзакцию в сети. Финни объяснил, что майнер может сгенерировать блок, в который он включит транзакцию с адреса A на другой адрес B, где оба адреса принадлежат ему. Затем вы произведете еще один платеж в той же валюте, отправив с адреса A на адрес C (который принадлежит другому пользователю).

- Атака маршрутизации
Это тип атаки, возможный при внедрении постороннего программного обеспечения в работу клиент-провайдера. Несмотря на то, что узлы в сети блокчейна разбросаны по разным уголкам планеты, разные интернет-провайдеры сообщаются между собой и могут оказывать воздействие на сеть.

- Атака-гонка
Еще один тип двойного расходования. Неопытные и торопливые продавцы могут отдать товар даже при неудачной попытке перевода средств, поскольку была сама попытка транзакции. Некоторые предприниматели используют “быстрые платежи” без необходимого подтверждения при небольших суммах. В кошельке принимающей стороны такая транзакция будет “в обработке”, а у адресанта – “не подтверждено”.

- Атаки по уязвимостям криптографических функций
Следствием человеческого фактора называют ошибки в коде, обнаружив которые, злоумышленник может взломать всю сеть.

- Намеренное переполнение очереди транзакций
Такой случай впервые произошел в уже далеком 2015-м году. Coinwallet.eu проводила стресс-тест блокчейн-сети первой криптовалюты, отправляя несколько тысяч транзакций на обработку. Так компания хотела разрешить дискуссию в сообществе по поводу размера блока реестра. Через месяц F2Pool совершил подобные манипуляции, проведя более 80 тысяч транзакций за небольшой промежуток времени.

- Отказ в обслуживании
Так называемые DDoS-атаки строятся на отправке большого количества идентичных запросов.


# Вопрос 19
## Проблема двойной траты, параметры транзакции, пропускная способность сети

Двойное расходование — повторная продажа (отчуждение) одних и тех же активов. Обычно речь идёт о системах электронных платежей, которым органично присуща возможность копирования состояния, что позволяет сделать несколько платежей из одного и того же стартового состояния.

Принципиально иная ситуация при операциях с цифровыми товарами — всегда есть возможность продажи идентичной копии. При этом каждый покупатель получает полную копию товара, и это не считается мошенничеством. Но легкость копирования и идентичность копий становится серьёзной проблемой для схем цифровых денег, аналогичных наличным. Цифровая «монета» для свободной передачи должна иметь форму файла. Но цифровой файл легко копируется. Обладатель «монеты» может передавать её копии большому количеству продавцов в уплату за товары. Каждый получатель легко убедится, что полученный файл полностью соответствует стандарту, но не будет уверен, что такой же копией не расплатились с другим продавцом.

### Предотвращение
Все платёжные системы, кроме криптовалют, являются централизованными — имеют центральное (административное) звено, где обеспечивается контроль допустимости той или иной операции. При этом основой для принятия решений служит информация самого администратора, а не информация, предоставляемая плательщиком. Поэтому копирование плательщиком состояния платёжной системы позволяет лишь сформировать двойные траты, но действительное исполнение будет происходить в порядке поступления распоряжений в банк, и часть из них окажется отклонённой из-за недостатка средств.


### На основе блокчейна
В децентрализованных платёжных системах нет контролирующего органа. Для предотвращения двойного расходования было предложено объединять транзакции в блоки, которые выстраивают в непрерывные цепочки — формируют блокчейн. Для получения права на добавление блока надо доказать выполнение работы (Proof of work). Проверка цепочки позволяет убедиться, что та же «электронная монета» не тратилась ранее. Фактически, транзакцию удостоверяет тот узел, который включает её в блок. Любые другие транзакции с этой же «электронной монетой» и этим же владельцем теперь система будет игнорировать. Позднее были предложены схемы, где вместо доказательства работы применяется доказательство доли владения. *Главная цель построения блокчейна — предоставить критерий для достижения консенсуса о том, какую версию транзакций считать верной.* Система находится в безопасности, пока самая крупная часть ее вычислительных ресурсов находится под совокупным контролем честных участников.

Информация в блокчейне открыта для всех. Но контрагенты могут проверить лишь наличие у отправителя активов на некоторый момент времени в прошлом. Если несколько платежей, передающих один и тот же актив, сделать достаточно быстро, то информация о них ещё не получит подтверждения (не попадёт в очередной блок или не будет иным образом легитимизирована) и каждый из получателей будет уверен в правомерности транзакций. Лишь после того, как одна из транзакций (не обязательно выполненная первой по времени) будет подтверждена, остальные транзакции с этим же активом уже не будут действительными. Но есть вероятность, что из-за временного разветвления цепочки блоков в параллельных ветках могут находиться транзакции, которые по-разному распоряжаются одним и тем же активом. Каждая из веток равноправна, не является ошибочной. В процессе формирования новых блоков какая-то из веток станет длиннее. Она получит преимущество, а короткая ветка отомрёт и все транзакции, находящиеся в её блоках, нужно будет вновь размещать в блоках. Так как одна из версий спорной транзакции останется в ранее сформированном блоке, то версия транзакции из «умершей» ветки при попытке добавить её в новый блок будет отвергнута. Вероятность существования параллельных цепочек крайне мала и экспоненциально уменьшается с ростом длины цепочки. Таким образом, чем больше подтверждений имеет транзакция, тем менее вероятна отмена транзакции из-за отмирания содержащей её цепочки. Поэтому сделки с нулевым подтверждением потенциально рискованные и многие продавцы устанавливают требование на минимальное количество подтверждений. *Как правило, шесть подтверждений представляют собой хороший баланс между временем ожидания всех подтверждений и уверенностью в том, что транзакция не будет фальсифицирована.*

Как при майнинге, так и при форжинге при наличии у злоумышленника контроля над достаточно большой долей эмиссии имеется существенная вероятность «тайного» выстраивания длинных параллельных цепочек блоков. После их публикации в сети главной будет признана более длинная цепочка. Отмена цепочки блоков может приводить к признанию недействительными транзакций, даже подтвержденных несколькими блоками, и к последующей «повторной» передаче актива уже другому получателю.

При концентрации в одних руках свыше 50 % суммарной мощности майнинга возможно выстраивание параллельной цепочки произвольной длины, что позволяет гарантированно изменить получателя в транзакциях владельца сконцентрированной мощности (атака «Double Spending» или «атака 51 %»). Если подконтрольная мощность меньше 50 %, то вероятность успеха экспоненциально снижается с каждым подтверждением.

Даже если атака двойного расходования будет успешной, это не приведёт к:

изменению размера вознаграждения за генерацию блока;
изменению суммарного количества криптовалюты;
нарушению функционирования сети;
тратам активов, которые ранее не принадлежали злоумышленнику.

## Параметры транзацкции
- Хеш транзакции-Для анализа информации, доступной по уникальному идентификатору.

- Статус транзакции.

- Блок
Каждый следующий блок включает хеш предыдущего, обеспечивая многочисленные, взаимоудостоверяющие и неизменяемые «бэкапы» информации. Чем больше блоков в сети вообще и чем большее число их содержит сведения о движении ваших средств, тем надёжнее средства защищены.

- Timestamp

- Параметры транзакции (transaction action)
Это блок из нескольких параметров, который рассказывает об архитектуре транзакции: какие средства откуда поступили, куда ушли, какой сервис при этом задействовался и так далее.

Зачем нужны:

Для расширенного анализа транзакций, а также получения некоторых сведений о состоянии сети.

- Value
Объем транзакции, сколько средств было переведено.
Оценить состояние сети и его динамику; понять, во что обходится та или иная операция с точки зрения комиссии.

- Лимит и использование газа, элементы комиссии

Оценить состояние сети и оптимальность параметров транзакции.

- Input data
