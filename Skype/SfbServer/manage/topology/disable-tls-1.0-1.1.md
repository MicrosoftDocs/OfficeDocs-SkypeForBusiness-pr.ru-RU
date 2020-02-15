---
title: Отключение протокола TLS 1.0/1.1 в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Сводка: подготовка и реализация отключения TLS 1,0 и 1,1 в средах.'
ms.openlocfilehash: 0a25060463ed3b67db8ca523171c2bc48660293d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42012752"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Отключение протокола TLS 1.0/1.1 в Skype для бизнеса Server 2015

В этой статье представлены необходимые рекомендации по подготовке и реализации отключения TLS 1,0 и 1,1 в средах. Этот процесс требует тщательного планирования и подготовки. Внимательно изучите все сведения, приведенные в этой статье, как сделать план отключение TLS 1,0 и 1,1 для вашей организации. Обратите внимание на то, что существует множество внешних зависимостей и условий подключения, которые могут быть затронуты при отключении TLS 1.0/1.1, поэтому рекомендуется использовать подробные сведения о планировании и тестировании.

## <a name="in-this-article"></a>В этой статье

- [Фон и область](#background)
- [Необходимые условия и процесс](#prerequisites-and-process)
- [Расширенные сценарии развертывания](#advanced-deployment-scenarios)

## <a name="background"></a>Общие сведения

Основными факторами для предоставления поддержки протоколов TLS 1,0 и 1,1 отключить поддержку протоколов локальной среды Skype для бизнеса Server являются отраслевые стандарты безопасности PCI и федеральные стандарты обработки информации. Дополнительные сведения о требованиях PCI можно найти [здесь](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Корпорация Майкрософт не может предоставить указания относительно того, требуется ли Организация для соблюдения этих или других требований. Необходимо определить, требуется ли отключить TLS 1,0 и/или 1,1 в средах.

Корпорация Майкрософт [выпустила](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)технический документ по протоколу TLS, и мы также рекомендуем использовать фоновое чтение, доступное в данном [блоге Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).

## <a name="supportability-scope"></a>Область поддержки

*Область* — это границы поддержки. *Полное тестирование и поддержка* означает, что мы полностью поддерживаем Отключение протокола TLS 1,0 и 1,1 для перечисленных версий продуктов. *В настоящее время исследование* означает только то, что; Мы активно изучаем, как перевод этих продуктов в область для поддержки отключения TLS. *Вне области видимости* означает, что эти версии продуктов не поддерживают отключение протокола TLS 1,0 или 1,1 и не будут работать, с указанными исключениями.

### <a name="fully-tested-and-supported-servers"></a>Полностью протестированные и Поддерживаемые серверы

- Skype для бизнеса Server 2019 CU1 17.0.2046.123 (июнь 2019) или более поздней версии
- Skype для бизнеса Server 2015 CU9 6.0.9319.548 (Май 2019) или более поздней версии в Windows Server 2012 (с обновлением базы знаний [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или замены), 2012 R2 или 2016.
- Обновление для Skype для бизнеса Server 2015 на месте с помощью CU9 6.0.9319.548 (Май 2019) или более поздней версии в Windows Server 2008 R2, 2012 (с обновлением KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или обновлением для замены) или 2012 R2.
- Подключение к Exchange и Outlook Web App с Exchange Server 2010 с пакетом обновления 3 (SP3) RU19 или более поздней версии [, руководство](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Устройство для обеспечения связи в филиалах (SBA) с помощью Skype для бизнеса Server 2015 CU6 HF2 или более поздней версии (уточните у поставщика, что они упакованы в обновления аппропиате и сделаны доступными для вашего устройства).
- Сервер для обеспечения связи в филиалах (SBS) с Skype для бизнеса Server 2015 CU6 HF2 или более поздней версии
- Lync Server 2013 **только пограничная роль**, это связано с тем, что пограничная роль не зависит от Windows Fabric 1,0.

### <a name="fully-tested-and-supported-clients"></a>Полностью протестированные и поддерживаемые клиенты

- Клиентское приложение Lync 2013 (Skype для бизнеса) для настольных ПК, MSI и C2R, включая базовые [15.0.5023.1000 и более поздние версии](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Клиент для настольных ПК Skype для бизнеса 2016, MSI [16.0.4678.1000 или более поздней версии](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), включая Basic
- Skype для бизнеса 2016 щелкните, чтобы запустить требуется обновление за [апрель 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) : 
    - Ежемесячное и полугодое целевое значение\.,\.16\.0 9126 2152 или выше
    - Половина ежегодного и отложенного канала, 16\.0\.8431\.2242 или выше
- Skype для бизнеса на Mac 16,15 или более поздней версии
- Skype для бизнеса для iOS и Android 6,19 или более поздней версии
- Комнаты Microsoft Teams (ранее известной как SRS для системы комнат Skype v2) 4.0.64.0 (декабрь 2018) или более поздней версии
- Обновление Surface Hub для Team Edition на основе KB4499162 (Май 2019, сборка ОС 15063,1835) или более поздней версии
- Skype Web App 2015 CU6 HF2 или более поздней версии (поставляется с сервером)

### <a name="currently-being-investigated"></a>В настоящее время выполняется исследование

- Панель мониторинга качества звонков (Новая установка после TLS 1,0, 1,1 отключена, см. ниже) *
 
### <a name="out-of-scope"></a>Вне области поддержки

За исключением случаев, когда отмечено, следующие продукты недоступны для поддержки отключения TLS 1.0/1.1 и не будут работать в среде, где отключен протокол TLS 1,0 и 1,1. Что означает: Если вы по-прежнему можете использовать серверы или клиенты вне области, их необходимо обновить или удалить, если вам нужно отключить протокол TLS 1.0/1.1 в любом месте локального развертывания Skype для бизнеса Server.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 или более ранняя
- Lync для Mac 2011
- Lync 2013 для мобильных устройств, iOS, iPad, Android и Windows Phone
- Клиент магазина Windows для Lync "MX"
- Система комнат Lync (неизвестное SRSv1). LRS достиг конца поддержки 9 октября 2018 и не будет обновлен для поддержки TLS 1,2.
- Все клиенты Lync 2010
- Lync Phone Edition — обновленные [рекомендации.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)
- Устройство для обеспечения связи в филиалах 2013 (SBA) или сервер для обеспечения связи в филиалах (SBS)
- Cloud Connector Edition (CCE)
- Skype для бизнеса для Windows Phone

### <a name="exceptions"></a>Исключения

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 использует зависимость от Windows Fabric версии 1,0.  На этапе проектирования Lync Server 2013 была выбрана Windows Fabric 1,0 для своей привлекательной и новой распределенной архитектуры для обеспечения репликации, высокой доступности и отказоустойчивости.  Со временем Skype для бизнеса Server и Windows Fabric значительно улучшили эту совместную архитектуру с значительным повторным проектированием в последующих версиях.  В качестве примера для текущего сервера Skype для бизнеса 2015 используется Windows Fabric 3,0.

К сожалению, Windows Fabric 1,0 не **поддерживает TLS 1,2.  Тем не менее, Lync Server 2013 будет обновлен для работы с протоколом TLS 1,2**. Это будет присутствовать в следующем накопительном пакете обновления для Lync Server 2013.  Мы предоставляем поддержку протокола TLS 1,2, чтобы включить сценарии совместной работы, миграции, Федерации и гибридной среды.

Если вашей организации требуется отключить TLS 1,0 и 1,1, и в настоящее время вы используете Lync Server 2013, рекомендуем начать процесс планирования с возможностью обновления на месте или параллельной миграции (новые пулы, перемещение пользователей) в Skype для Business Server 2015 или более поздней версии.  Или вы можете ускорить переход на Skype для бизнеса Online.

#### <a name="call-quality-dashboard"></a>Панель мониторинга качества звонка

Локальная панель мониторинга качества звонков в настоящее время зависит от протокола TLS 1,0 во время новой установки (при первом выполнении установки в локальной среде).  В настоящее время мы изучаем эту проблему и планируем выпустить исправление в ближайшем будущем.  Если вы планируете установить CQD, а также отключите TLS 1,0, рекомендуем сначала выполнить установку CQD, а затем перейдите к отключению TLS 1,0.

#### <a name="third-party-devices"></a>Сторонние устройства

На сторонних устройствах, таких как телефоны 3PIP, видеоконференций, обратные прокси-серверы и подсистемы балансировки нагрузки, обязательно проверьте поддержку протокола TLS 1,2, тщательно протестируйте и при необходимости обратитесь к поставщику.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Рекомендации по Федерации при отключении TLS 1.0/1.1 на пограничных серверах

Необходимо тщательно спланировать и оценить влияние отключения TLS 1.0/1.1 на пограничных серверах.  После отключения протокола TLS 1,0 и 1,1 вы можете обнаружить, что другие организации не смогут выполнять Федерацию с вашей организацией.

Вы можете отказаться от использования протоколов TLS 1.0/1.1 на пограничных серверах для обеспечения обратной совместимости с неисправленными (SfB 2015, Lync 2013) или более старыми (2010) внешними системами.

Корпорация Майкрософт не может предоставить советы или рекомендации относительно того, попадает ли пограничная сеть (или любая сеть) в соответствии со стандартом PCI; , которые должны быть определены отдельной компанией.

Skype для бизнеса Online поддерживает протокол TLS 1,2 на сегодняшний день, поэтому не требуется воздействовать на гибридную среду/Федерацию с Online.

PIC (общедоступное подключение к службе обмена мгновенными сообщениями) для службы потребителей Skype: мы не будем ожидать, что протокол TLS 1.0/1.1 не будет влиять на [Подключение Skype](../../deploy/deploy-skype-connectivity.md); Шлюзы Microsoft PIC уже поддерживают TLS 1,2.

## <a name="prerequisites-and-process"></a>Необходимые условия и процесс

За исключением отмеченных выше случаев, когда протоколы TLS 1,0 и 1,1 отключены серверами, не включенными в область, клиенты и устройства будут работать правильно или вообще. Это может означать, что необходимо приостановить и дождаться получения обновленных руководств от Майкрософт. После того как вы удовлетворены всеми требованиями и запланировать пропуски, продолжите.

На высоком уровне, в то время как Skype для бизнеса Server 2019 готов к выполнению процедуры установки, Skype для бизнеса Server 2015 потребует установки CU9, применения предварительных обновлений к .NET и SQL, развертывания разделов реестра, необходимых для использования, и, наконец, отдельного Округление обновлений конфигурации ОС (например, отключение TLS 1,0 и 1,1 с помощью импорта файлов реестра). Критически важно полностью установить все необходимые компоненты, в том числе Skype для бизнеса Server 2015 CU6 HF2, перед отключением TLS 1,0 и 1,1 на любом сервере в вашей среде. Для каждого Skype для бизнеса Server, включая пограничные роли и SQL Server, требуются обновления. Кроме того, убедитесь, что все поддерживаемые клиенты (в области) обновлены до требуемых минимальных версий. Не забудьте также обновить рабочие станции управления.

Мы хотим подписаться к обычному порядку операций "Внутренняя часть" для обновления серверов Skype для бизнеса. Рассматриваете пулы директоров, сохраняемые чат и связанные пулы обычным образом. Порядок и методы обновления описаны [здесь](topology.md) и [здесь](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>Процесс высокого уровня

1. Перед настройкой рабочих серверов протестируйте все действия, описанные в лаборатории.
2. Создайте резервную копию и сохраните копию экспортируемого реестра на каждом отдельном сервере, который необходимо обновить. Вы не можете обмениваться реестрами между серверами; они содержат уникальные ключи на уровне компьютера.
3. Обновите все серверы Skype для бизнеса 2015 до CU9 или более поздней версии. Для Skype для бизнеса Server 2019 выполните обновление до CU1 или более поздней версии.
4. Установите все необходимые компоненты на все серверы.
5. Развертывайте разделы реестра, необходимые для использования.
6. Убедитесь, что все клиенты в области обновлены.
7. Отключите TLS 1,0 и 1,1 с помощью импорта реестра.
8. Убедитесь, что рабочие нагрузки работают должным образом.
    - Если возникли проблемы, устраните неполадки и устраните или
    - Восстановление реестра из шага 2 для повторного включения TLS 1,0 и 1,1
9. Проверка того, что используется только протокол TLS 1,2.

### <a name="install-prerequisites-to-all-servers"></a>Установка необходимых компонентов для всех серверов

Перед отключением протокола TLS 1,0 и 1,1 на уровне операционной системы в развертывании Skype для бизнеса Server 2015 необходимо выполнить полное обновление зависимости. Ниже приведены минимальные версии, поддерживающие TLS 1,2. Перед отключением TLS 1,0 и 1,1 разверните все необходимые обновления для каждого сервера Skype для бизнеса в вашей среде.

- Skype для бизнеса Server 2015 CU9 6.0.9319.548 (Май 2019) или более поздней версии
- [.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) или более поздней версии с включенной функцией SchUseStrongCrypto в реестре (приведенной ниже)
- SQL должен быть обновлен на всех серверах Skype для бизнеса 2015 и в конце. Сначала обновите SQL Server Enterprise Edition, а затем соответствующие Фес. 
    - [SQL server 2014 с пакетом обновления 1 (SP1), CU5](https://support.microsoft.com/help/3130926), выше/sql Server 2012 (SP2) + CU16 или выше/ [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)или выше/SQL Server 2014 с пакетом обновления 2 (SP2)
     - [Собственный клиент SQL Server для SQL Server 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Драйвер Microsoft ODBC 11 для SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)или более поздней версии
     - [Общие объекты управления для SQL Server 2014 с пакетом обновления 2 (SP2)](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes для SQL Server 2014 с пакетом обновления 2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Основные действия по установке предварительных требований в рекомендуемом порядке операций

1. Установите обновление CU9 для Skype для бизнеса Server на все серверы. 
    1. Установите обновление для компонентов, использующих обновление.
    2. Обновление баз данных в соответствии с документированными процедурами. Для Skype для бизнеса Server 2015, ознакомьтесь со статьей KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. Проверка функциональности продукта в развертывании перед переходом с других изменений.
2. Скачайте автономный установщик .NET 4,7. 
    1. Ссылкой[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Убедитесь, что службы Skype для бизнеса Server 2015 на сервере переднего плана остановлены.
    3. Ссылкой[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. EX (стандартный выпуск):```Stop-CsWindowsService```
    5. EX (корпоративный выпуск):```Invoke-CsComputerFailover```
    6. Запустите пакет установщика.
    7. Перезагрузите сервер.
3. Обновите SQL Express 2014 на всех серверах. 
    1. Ссылкой[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Загрузка SQL 2014 с пакетом обновления 2 
        - Ссылкой[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Скопируйте установочный носитель в папку на сервере (пример: C:\ 01_2014SqlSp2).
    4. Проверка остановки служб 2015 Skype для бизнеса Server на сервере переднего плана 
        - EX (стандартный выпуск):```Stop-CsWindowsService```
        - EX (корпоративный выпуск):```Invoke-CsComputerFailover```
    5. Открытие командной строки администратора и обновление всех установленных компонентов и экземпляров 
        - Пример: C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/КС/Иакцептсклсерверлиценсетермс/Актион = Patch/Аллинстанцес
4. Обновление собственного клиента SQL. 
    1. Ссылка: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Загрузка из[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Убедитесь, что на сервере переднего плана остановлены службы 2015 для Skype для бизнеса Server. 
        - EX (стандартный выпуск):```Stop-CsWindowsServices```
        - EX (корпоративный выпуск):```Invoke-CsComputerFailover```
    4. Остановка выполнения экземпляров SQL 
        - Пример```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Пример```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - EX (только для выпуска Standard Edition):```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Установите обновление.
5. Обновите драйвер ODBC 11 для SQL Server, чтобы включить поддержку протокола TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).
    1. Скачайте [драйвер ODBC 11 для SQL Server — Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).
    2. Убедитесь, что службы Skype для бизнеса Server 2015 на сервере переднего плана остановлены.
        - Пример (стандартный выпуск):```Stop-CsWindowsService```
        - Пример (корпоративный выпуск):```Invoke-CsComputerFailover```
    3. Установите обновление.
6. Развертывайте разделы реестра, необходимые для использования.

### <a name="pre-requisite-registry-keys"></a>Разделы реестра, необходимые для предварительной версии

Скопируйте или вставьте следующий тест в блокнот и переименуйте Тлспререк. reg или имя вашего выбора, а затем выполните импорт:

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

Для SQL Server в случае пулов Enterprise Edition предварительные требования и отключение протокола TLS должны рассматриваться как любые обновления SQL или ОС; Ссылка на:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Несмотря на то, что вы можете объединять как необходимые, так и дополнительные действия по отключению приложений и TLS, настоятельно рекомендуем применить все предварительные требования, прежде чем переходить к отключению TLS 1,0 и 1,1 на уровне операционной системы. Рекомендуемый подход — подготовить среду, развертывая все необходимые компоненты, проверяя, правильно ли работают все рабочие нагрузки и как ожидается, а затем отключать протокол TLS 1.0/1.1 позже.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Отключение TLS 1,0 и 1,1 с помощью импорта реестра

Перед выполнением дальнейших действий убедитесь, *что выполнены все необходимые условия и обновленные серверы Skype для бизнеса*.

Скопируйте приведенный ниже текст в файл блокнота и переименуйте его в **тлсдисабле. reg**:

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

Импортируйте reg файл на каждый сервер, на котором необходимо отключить TLS 1,0 и 1,1. Перезагрузите сервер. После возврата служб в оперативный режим перейдите на следующий сервер. Подход к пулам Enterprise Edition — это то же самое, что и обновление операционной системы.

Вы могли заметить, что мы сделали больше, чем просто отключать TLS 1,0 и 1,1 здесь. Мы поддерживаем Переупорядочение комплекта шифров (как показано выше) и отключение некоторых устаревших слабых шифров. В первый раз мы официально поддерживали эти изменения в SCHANNEL и API шифрования в Skype для бизнеса Server, и важно отметить, что эти изменения поддерживаются и в настоящее время проверены. Мы можем рассмотреть дополнительные конфигурации в будущем, но сейчас не изменяйте файл импорта реестра в своей реализации.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Проверка правильности работы рабочих нагрузок

После отключения протокола TLS 1,0 и 1,1 в среде убедитесь, что все основные рабочие нагрузки работают должным образом, например, & присутствия, подключения к службе мгновенных сообщений, вызовы P2P, Корпоративная голосовая связь и т. д.

**Проверка использования протокола TLS 1,2**

Чтобы ваша группа безопасности выполнила новый аудит трафика Skype для бизнеса, убедитесь, что старые протоколы TLS 1,0 и 1,1 больше не используются.

Кроме того, с помощью Internet Explorer можно проверить подключения TLS для веб-служб из Skype для бизнеса Server 2015 после отключения TLS 1,0 и TLS 1,1.

1. Запустите Internet Explorer.
2. Выберите **инструменты** > **Интернет свойства**.
3. Перейдите на вкладку **Дополнительно** .
4. В разделе **Параметры**прокрутите вниз.
5. Убедитесь, что протокол TLS 1,0, TLS 1,1 и TLS 1,2 включены.
6. Просмотрите URL-адрес внутренней веб-службы вашего пула SfB 2015 (должно успешно подключиться).
7. Вернитесь в Internet Explorer и отключите параметр для **использования протокола TLS 1,2** .
8. Снова просмотрите URL-адрес внутренней веб-службы SfB пула 2015 (должно произойти ошибка подключения).

![Свойства браузера](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Расширенные сценарии развертывания

Так как некоторые компоненты зависимости необходимы для поддержки протокола TLS 1,2 в Skype для бизнеса SER 2015, то установка с носителя RTM приведет к сбою в любой системе, где отключены TLS 1,0 и 1,1.

**Развертывание новых серверов Standard Edition или пулов Enterprise Edition после отключения TLS 1,0 и 1,1 в вашей среде.**

**Вариант 1:** Используйте [смартсетуп](../../deploy/install/install-skype-for-business-server.md). Обратите внимание, что мы обновляем Смартсетуп в соответствии с обновленными двоичными двоичными файлами SQL в будущем CU, и в будущем будет обновлена эта статья.

**Вариант 2:** Предварительная установка локальных экземпляров SQL (RTCLOCAL и ЛИНКЛОКАЛ)

1. Скачайте и скопируйте SQL Express 2014 с пакетом обновления 2 (SQLEXPR_x64. exe) в локальную папку на FE. Предположим, что путь к папке <SQL_FOLDER_PATH>.
2. Запустите PowerShell или командную строку и перейдите к <SQL_FOLDER_PATH>.
3. Создайте экземпляр SQL RTCLOCAL, выполнив указанную ниже команду. Дождитесь завершения работы SQLEXPR_x64. exe, прежде чем продолжить выполнение:

    SQLEXPR_x64. exe/Q/ИАКЦЕПТСКЛСЕРВЕРЛИЦЕНСЕТЕРМС/УПДАТИНАБЛЕД = 0/ХИДЕКОНСОЛЕ/АКТИОН = Install/ФЕАТУРЕС = Скленгине, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin \ Администраторы"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automati
1. Создайте экземпляр SQL ЛИНКЛОКАЛ, выполнив указанную ниже команду. Дождитесь завершения работы SQLEXPR_x64. exe, прежде чем переходить к следующему шагу:

    SQLEXPR_x64. exe/Q/ИАКЦЕПТСКЛСЕРВЕРЛИЦЕНСЕТЕРМС/УПДАТИНАБЛЕД = 0/ХИДЕКОНСОЛЕ/АКТИОН = Install/ФЕАТУРЕС = Скленгине, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin \ Администраторы"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic
1. Запустите программу установки Skype для бизнеса Server 2015 RTM.
2. Выполните остальные действия из раздела предварительные требования выше.

**Вариант 3:** Кроме того, вы можете вручную заменить двоичные файлы в локальном каталоге установочного носителя следующим образом:

1. [Установка необходимых компонентов для Skype для бизнеса Server](../../deploy/install/install-prerequisites.md)  
2. Установите .NET 4,7: 
      - **Примечание:** Мы впервые предоставили поддержку .NET 4,7 в Skype для бизнеса Server 2015 CU5 (6.0.9319.281). Поэтому в последующих шагах ниже мы будем обновлять основные компоненты до выполнения основной установки.
      - Download: https://www.microsoft.com/download/details.aspx?id=55167. 
      - Ссылка: [программное обеспечение, которое следует установить перед развертыванием Skype для бизнеса Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Копирование файлов и папок ISO: 
    - С прикрепленным ISO-файлом ISO для Skype для бизнеса Server 2015 откройте корневой каталог диска, к которому он подключен, как (\) ex: D: в проводнике).
    - Скопируйте все папки и файлы в папку на локальном диске (например, C:\SkypeForBusiness2015ISO).
    - **Примечание:** Прежде чем устанавливать компоненты, некоторые файлы потребуется обновить для поддержки протокола TLS 1,2.
4. Замена пакетов MSI/EXE: 
    - Замените существующие пакеты MSI и EXE в папке/Setup/AMD64/установочного носителя на локальном компьютере.
    - SQL 2014 SP2 Express:https://www.microsoft.com/download/details.aspx?id=53167 
        - Переименуйте SQLEXPR_x64 на локальном компьютере и замените существующий файл в папке Setup/AMD64/на установочном носителе.
    - Собственный клиент SQL:https://www.microsoft.com/download/details.aspx?id=50402 
        - **Примечание:** Переименуйте его, если это необходимо, в sqlncli. msi, а затем замените существующий файл, существующий в папке Setup/AMD64/, на установочном носителе.
    - Объекты управления SQL:https://www.microsoft.com/download/details.aspx?id=53164 
        - **Примечание:** Пакет дополнительных компонентов содержит множество элементов, которые можно скачать. Выберите загрузку только Шаредманажементобжектс. msi.
        - **Примечание:** Замените существующий файл, существующий в папке Setup/AMD64/, на установочном носителе.
    - Типы SQL CLR:https://www.microsoft.com/download/details.aspx?id=53164 
        - **Примечание:** Пакет дополнительных компонентов содержит множество элементов, которые можно скачать. Выберите, чтобы загружать только Кклсисклртипес. msi
        - **Note**: замените существующий файл, существующий в папке Setup/AMD64/, на установочном носителе.
5. Установка основных компонентов: 
    - Запустите setup. exe из папки "Настройка/AMD64/" установочного носителя. Следуйте инструкциям по установке основных компонентов
    - Закройте основные компоненты.
6. Обновление основных компонентов: 
    - Скачайте установщик обновлений Skype для бизнеса.
    - Запустите установщик, чтобы обновить основные компоненты и установить счетчики производительности.
    - **Примечание:** При выпуске CU6HF2 в настоящее время функция автоматического обновления будет устанавливаться только до CU6. Таким образом, чтобы обновить основные компоненты до 6.0.9319.516, необходимо выполнить отдельное обновление.
    - Ссылкойhttps://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. Установка средств администрирования (необязательно): 
    - При этом будет установлено приложение Microsoft SQL Server 2012 Native Client, управляющие объекты SQL Server 2014 (x64) и Microsoft System CLR Types для SQL Server 2014 (x64), используя обновленные файлы. Кроме того, построитель топологий и панель управления Skype для бизнеса Server 2015 будут доступны на локальном компьютере.
8. Установка локального хранилища конфигурации (шаг 1): 
     - Откройте мастер развертывания, щелкните установить или обновить систему Skype для бизнеса Server и выберите пункт **выполнить** на шаге 1: Установка локального хранилища конфигурации.
     - В диалоговом окне **Установка локального хранилища конфигурации** нажмите кнопку **Далее** .
     ![Диалоговое окно установки локального хранилища конфигурации](../../media/local-configuration-store.png)
     - Просмотрите результаты и убедитесь, что состояние задачи завершено. Изучите полученный файл журнала, нажав кнопку **Просмотреть журнал**.
     ![Состояние задачи отображается как завершенное](../../media/local-configuration-task-completed.png)
     - Нажмите кнопку **Готово**.
9. Установка или удаление компонентов Skype для бизнеса Server (шаг 2):
    - Откройте мастер развертывания, выберите **установить или обновить систему Skype для бизнеса Server**и нажмите **выполнить** на шаге 2: Установка или удаление компонентов Skype для бизнеса Server
    - В диалоговом окне Настройка компонентов Skype для бизнеса Server нажмите кнопку **Далее** .
    ![окно "Настройка компонентов Skype для бизнеса Server"](../../media/set-up-skype-for-business-server-components-window.png)
    - Просмотрите журнал с помощью журнала просмотра и проверьте, что установка выполнена без проблем. 
    - Нажмите кнопку **Готово**.
10. Продолжите дополнительную установку и настройку (на этом шаге можно возобновить нормальную установку).
