# StandartStakeSwap
База с интерфейсом, для скриптов из свапов и стейков
# канал [@SwissScripts](https://t.me/SwissScripts)

### Windows:
устанавливаем web3 (pip/pip3 install web3), запускаем main.py (часто можно двойным щелчком)

### Linux:
аналогично


Гиперпараметры 
1) Gas: газ в баксах, лучше ставить 0.3 - 0.5
2) Time between : время в минутах между тразакциями
3) Random time : доля от time between, между которой и нулем будет колебаться дополнительное ожидание
4) New - задел на будущее, для сканирования кошельков, что б не совершать лишних апрувов. Сейчас жмем, что б была синей.

Модули
1) тип - свапы : просто вводим число. 1 свап = eth -> usd - > eth. Получается (3 транзакции)*колво + 1. Объем для ВСЕХ свапов один, указывается в первом окне\n
2) тип - стейкинг : вводим объем в долларах и где возможно число процентов которые вернутся обратно

1) Скрипт читает активированные модули и формирует из них случайную цепочку для каждого кошелька
2) Если модуль возвращает False (ошибка) скрипт перестраивает цепочку без модуля и обрезает ее сзади.

## Добавление модулей

В скрипт можно добавить модули свапа или стейкинга. Для этого:
1) Добавляем их описание в appSettings.json
2) Добавляем модули в папку Modules
   
## Все добавляемые модули должны соответствовать стандартам

1) acc - объект от Web3.Account
2) function_out - вывод в терминал, используем вместо print
3) return_percent - процент возврата, всегда меньше 70

на примере моих модулей - все понятно

Модуль swap - 3 функции:

1) eth_usd(acc,function_out,volume_in_usd,gas=0.4)
2) usd_eth(acc, function_out, volume_in_usd, gas=0.4)
3) approve(acc,function_out,gas=0.3)


Модуль stake - 1 функция:
1) perform(acc,function_out,volume_in_usd,return_percent,gas=0.5) - для модулей с одолжением
2) perform(acc,function_out,volume_in_usd,gas=0.5) - без одолжения

# Большая просьба - скидывать ошибки в канал или в личку [@MrTwisterXXXL](https://t.me/MrTwisterXXXL)
Донат 
### 0x8C978623722807c06A215499eb039D4d4bEC7eF9
