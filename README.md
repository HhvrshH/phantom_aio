# PHANTOM AIO

Written by: @hvrsh (TG)

Channel: https://t.me/hashvers (TG)

---

**Automation on BAS for exchanges in the Phantom wallet**

**Setup when launching `phantom_aio.xml`:**

**Setup when launching `phantom_aio.xml`:**

1. Use Finger Switcher - whether to use fingerprints.
   1. Finger Print Key - if **1** is enabled, you need to enter a key to obtain fingerprints, which can be purchased here - https://fingerprints.bablosoft.com/
2. Threads - number of threads launched simultaneously.
3. Mode - operation mode
   1. Swaps - swaps SOL in one direction to a randomly selected token from the `data.json` file. The swap range for SOL is specified in the `data.json` file under the parameter `swapAmounts.Swaps`.
   2. Sizes - cyclic swap (SOL->Token Token->SOL) to a random token from the list in the `data.json` file. The swap range for this mode is set in % in the `data.json` file under the parameter `swapAmounts.Sizes`.
   3. Drip Initiation - Phantom quest completion and Drip registration.
   4. Drip Daily - collecting daily Droplets on accounts.
      1. If `Legendary lock in` is enabled, it will attempt to open the chest.
      2. If `Donate to Projects` is enabled, it will subscribe to projects and donate to them.

4. Swap Count - range of swap counts.
5. Sleep(in sec) - Sleep range. Do not set the lower value too low (below 10 sec.).
6. Clear DoneList - After successful completion or insufficient balance, private keys are written to the `done_list.txt` file so that the software understands which accounts it has passed and which ones it has not, in case you interrupt its work or the thread terminates with an error. If you need to rerun all wallets (for example, a new day) - select Yes.
7. Wallet shuffle - whether to shuffle wallets.
8. Proxy Type - proxy type.


 **Setup in the `data.json` file:**

  `minimalBalance` - the minimum balance on addresses for swaps (do not set below 0.01!).

  `tokens` - list of tokens participating in swaps. Enter new tickers carefully, checking their case. For example, the ticker for the Bonk token is not in uppercase as it is commonly accepted. This is important, as an incorrect ticker can lead to unwanted swaps.
 
  `swapAmounts.Swaps` - setting the swap range in `Swaps` mode. In SOL.
 
  `swapAmounts.Sizes` - setting the range for swaps in `Sizes` mode in percentages. Swaps will occur for the selected percentage of the address balance in SOL.
 
  `moralis_api` - API key for checking balances on addresses. The free Default key is sufficient. Obtain it here - https://admin.moralis.io/settings
 
  `retry`- maximum number of retries in case of a failed swap.

  `howMuchSpendDropletsInPersentage` - range in percentage of how much Droplets can be spent on donations to projects from `projects.txt`

  `howMuchSpendDropletsforEachProject` - range in the amount of how much to donate to each of the projects. if [0,0] is specified, only subscription to the project will be made, otherwise subscription + donation will be made.

 **Files for operation**

 `private.txt` - Specify either private keys or seed phrases. If there are several active wallets under a seed phrase, be sure to specify which one to use by adding the ordinal number of the address after the seed phrase. (example in the file)

 `proxy.txt` - proxies, selected line by line.

 `data.json` - additional settings.
 
 `projects.txt` - list with the exact names of projects to be processed.
 

---

**Автоматизация на БАСе для обменов в кошельке Phantom**

**Настройка при запуске `phantom_aio.xml`:**

1. Use Finger Switcher - использовать ли отпечатки.
	1. Finger Print Key - в случае включения **1** нужнно вести ключ для получения отпечатков, покупается тут - https://fingerprints.bablosoft.com/
2. Threads - количество потоков запущеных одновременно.
3. Mode  - режим работы
	1. Swaps - свап SOL в одну сторону в рандомно выбраный токен с файла `data.json`. Диапазон значений для свапа указывается  в файле `data.json` параметр `swapAmounts.Swaps`.
	2. Sizes - цикличный свап(SOL->Токен Токен->SOL) в рандомный токен с списка в файле `data.json`. Диапазон свапа для этого режима задается в % в файле `data.json` параметр `swapAmounts.Sizes`.
   3. Drip Initiation - выполнение квеста Phantom и регистрация Drip.
   4. Drip Daily - сбор дейли Droplets на аккаунтах.
      1. Если включено `Legendary lock in`  будет пробовать открывать сундук
      2. Если Включено `Donate to Projects` будет подписываться на проекты и донатить им.

4. Swap Count - диапазон количества свапов.
5. Sleep(in sec) - диапазон Сна. Нижние значение не ставить слишком малое(ниже 10 сек.).
6. Clear DoneList - После успешного выполнения или отсутствия достаточного баланаса в файл `done_list.txt` записываются приватники, чтобы софт понимал какие аккаунты он прошел а какие нет, в случае если вы прервали его работу или поток завершится с ошибкой. Если нужно прогнать все кошельки заново(новый день к примеру) - выбираем Yes.
7. Wallet shuffle - делать ли перемешивание кошельков.
8. Proxy Type - тип прокси.


 **Настройка файла `data.json`:**

  `minimalBalance` - минимальный баланс на адресах для совершения свапов(ниже 0,01 не ставить!).
 
  `tokens` - список токенов которые будут участвовать в свапах. Вводим новые тикеты осторожно, проверяем его регистр. К примеру тикет токена Bonk идет не заглавными как это принято. Это важно, неправильный тикет может привести к нежелательному свапу.
 
  `swapAmounts.Swaps` - настройка диапазона свапа в режиме работы `Swaps`. В SOL.
 
  `swapAmounts.Sizes` - настройка диапазона для свапа в режиме `Sizes` в процентах. Будет происходить свап на выбраное количество процентов от всего баланса адреса в SOL.
 
  `moralis_api` - апи ключ для проверки балансов на адресах. Достаточно бесплатного Default. Брать тут - https://admin.moralis.io/settings
 
  `retry`- максимальное количество повторений при неудачном свапе.

  `howMuchSpendDropletsInPersentage` - диапазон в процентах сколько можно потратить Droplets на донаты проектам с `projects.txt`

  `howMuchSpendDropletsforEachProject` - диапазон в количистве столько донатить каждому из проектов. если будет указано [0,0] то будет сделана тольоко подписка на проект, иначе подписка + донат.

 **Файлы для работы**

 `private.txt` - Указывать можно как и приватники так и сид-фразы. если под сид-фразой есть несоклько активных кошельков, обязательно указывать какой выбирать, добавив после сид-фразы порядковый номер адреса.(пример в файле)

 `proxy.txt` - прокси, выбираюся построчно.

 `data.json` - дополнительные настройки.
 
 `projects.txt` - список с точным названием проектов что будут обрабатывватся.