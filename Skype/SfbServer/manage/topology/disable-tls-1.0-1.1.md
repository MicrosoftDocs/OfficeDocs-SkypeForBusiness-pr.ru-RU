---
title: Отключение TLS 1.0/1.1 в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Сводка: подготовка и реализация отключения TLS 1,0 и 1,1 в среде.'
ms.openlocfilehash: ce158aeaa84e00367b265404fe3d3407606f4759
ms.sourcegitcommit: f3b698379eb663202ce127eeaf6c07328c166556
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2019
ms.locfileid: "38077442"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Отключение TLS 1.0/1.1 в Skype для бизнеса Server 2015

Цель этой статьи — предоставить необходимые рекомендации для подготовки и реализации отключения TLS 1,0 и 1,1 в своей среде. Для этого процесса требуется тщательное планирование и подготовка. Внимательно ознакомьтесь со всеми сведениями, приведенными в этой статье, чтобы сделать план отключение TLS 1,0 и 1,1 для вашей организации. Обратите внимание на то, что существует множество внешних зависимостей и условий подключения, которые могут быть затронуты при отключении TLS 1.0/1.1, поэтому гарантируется всестороннее планирование и тестирование.

## <a name="in-this-article"></a>В этой статье

- [Фон и область](#background)
- [Необходимые условия и процесс](#prerequisites-and-process)
- [Сценарии расширенного развертывания](#advanced-deployment-scenarios)

## <a name="background"></a>Общие сведения

Основными драйверами для предоставления TLS 1,0 и 1,1 Отключение поддержки Skype для Business Server в локальной среде – это рекомендации по стандартам и стандартам системы безопасности, предоставляемые стандартом и федеральным требованиям к обработке информации. Дополнительные сведения о требованиях к шине PCI можно найти [здесь](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Корпорация Майкрософт не может предоставить рекомендации о том, требуется ли организациям соблюдать эти или другие требования. Необходимо определить, требуется ли отключение TLS 1,0 и/или 1,1 в среде.

Корпорация Майкрософт [выпустила](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)технический документ по протоколу TLS, и мы рекомендуем вам также рекомендовать фоновое чтение, доступное в этом [блоге Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).

## <a name="supportability-scope"></a>Область поддержки

*Область действия* — это границы поддержки. *Полностью протестированные и поддерживаемые* устройства обеспечивают полную поддержку и отключение TLS 1,0 и 1,1 для указанных версий продукта. *В настоящее время исследование* означает только это. Мы активно изучаем эти продукты в рамках поддержки отключения TLS. *За пределами области* — эти версии продуктов не поддерживают отключение TLS 1,0 или 1,1 и не будут работать, с указанными исключениями.

### <a name="fully-tested-and-supported-servers"></a>Полностью протестированные и Поддерживаемые серверы

- Skype для бизнеса Server 2019 CU1 17.0.2046.123 (июнь 2019) или более позднюю версию
- Skype для бизнеса Server 2015 CU9 6.0.9319.548 (Май 2019) или более новой версии на Windows Server 2012 (с обновлением KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или замены), 2012 R2 или 2016.
- Обновление для Skype для бизнеса Server 2015 на месте с помощью CU9 6.0.9319.548 (Май 2019) или более новой версии на Windows Server 2008 R2, 2012 (с KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или заменой обновления) или 2012 R2.
- Подключение к Exchange и Outlook Web App с Exchange Server 2010 SP3, RU19 или более новой версии [, руководство](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Бесперебойно работающее устройство филиала (СБА) с помощью Skype для Business Server 2015 CU6 HF2 или более позднюю версию (уточните у поставщика, что он содержит пакеты аппропиате обновления и стали доступны для вашего устройства).
- Бесперебойно работающий сервер филиалов (SBS) с помощью Skype для бизнеса Server 2015 CU6 HF2 или более новой
- Lync Server 2013 **Edge**, это связано с тем, что роль Edge не имеет зависимости от Windows Fabric 1,0.

### <a name="fully-tested-and-supported-clients"></a>Полностью протестированные и поддерживаемые клиенты

- Клиентское приложение Lync 2013 (Skype для бизнеса) для настольных систем, MSI и C2R, включая Basic [15.0.5023.1000 или более позднюю версию](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Классическое приложение Skype для бизнеса 2016, MSI [16.0.4678.1000 или более позднюю версию](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), включая Basic
- Для использования Skype для бизнеса 2016 нажмите кнопку, чтобы установить обновление за [апрель 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) : 
    - Ежемесячно и одновременная Целевая\.версия\.:\.16 0 9126 2152 или выше.
    - Полуфабрикаты и отложенный канал, 16\.0\.8431\.2242 или выше
- Skype для бизнеса на компьютерах Mac 16,15 и более новых версий
- Skype для бизнеса для iOS и Android 6,19 или более новой
- Комнаты Microsoft Teams (ранее известные как система помещения в Skype v2 SRS v2) 4.0.64.0 (декабрь 2018) или более позднюю версию
- Обновление Surface Hub для Team Edition на основе KB4499162 (Май 2019, OS Build 15063,1835) или более позднюю версию
- Skype Web App 2015 CU6 HF2 или более позднюю версию (поставляется с сервером)

### <a name="currently-being-investigated"></a>В настоящее время изучаются

- Панель мониторинга качества звонка (Новая установка после TLS 1,0, 1,1 отключена, см. ниже) *
 
### <a name="out-of-scope"></a>За пределами области

Если не указано иное, указанные ниже продукты не поддерживаются службой TLS 1.0/1.1 и не будут работать в среде, в которой отключены протоколы TLS 1,0 и 1,1. Что это означает. Если вы по-прежнему можете использовать сервер или клиенты вне области, вы должны обновить или удалить их, если вам нужно отключить TLS 1.0/1.1 в любом месте в локальной среде Skype для бизнеса Server.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 или более низкая
- Lync для Mac 2011
- Lync 2013 для мобильных устройств — iOS, iPad, Android и Windows Phone
- Клиент магазина Windows для Lync "MX"
- Система комнат в Lync (она является известной SRSv1). ЛРС достиг конца поддержки 9 октября 2018 г. и не будет обновлен для поддержки TLS 1,2.
- Все клиенты Lync 2010
- Lync Phone Edition — обновлены [рекомендации.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)
- Устройство с бесперебойной подразделением 2013 (СБА) или сервер в бесперебойной подразделении (SBS).
- Cloud Connector Edition (КЦЕ)
- Skype для бизнеса для Windows Phone

### <a name="exceptions"></a>Исключения

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 использует зависимость от Windows Fabric версии 1,0.  На этапе проектирования для Lync Server 2013 вы выбрали Windows Fabric 1,0 для своей привлекательной и новой распределенной архитектуры для обеспечения репликации, высокой доступности и отказоустойчивости.  С течением времени как в Skype для бизнеса Server, так и в Windows Fabric значительно улучшилась архитектура совместной работы с значительной повторной разработкой в последующих версиях.  Например, текущий сервер Skype для бизнеса 2015 использует Windows Fabric 3,0.

К сожалению, Windows Fabric 1,0 **не поддерживает TLS 1,2.  Однако мы будем обновлять Lync Server 2013 для работы с TLS 1,2**. Это будет вскоре в следующем накопительном обновлении для Lync Server 2013.  Мы предоставляем поддержку протокола TLS 1,2 для поддержки сценариев совместного существования, миграции, Федерации и гибридности.

Если в вашей организации требуется отключить TLS 1,0 и 1,1, а в настоящее время вы используете Lync Server 2013, мы рекомендуем начать процесс планирования, в результате чего вам может потребоваться выполнить миграцию на месте (новые пулы, переместить пользователей) в Skype для Business Server 2015 или более новой.  Кроме того, вы можете ускорить переход на Skype для бизнеса Online.

#### <a name="call-quality-dashboard"></a>Панель мониторинга качества вызовов

Локальная панель качества звонков в настоящее время имеет зависимость TLS 1,0 во время новой установки (при первом запуске в локальных средах).  В настоящее время мы изучаем эту проблему и планируем снять исправление в ближайшем будущем.  Если вы планируете установить CQD, а также отключите TLS 1,0, рекомендуем сначала завершить установку CQD, а затем продолжить работу с TLS 1,0 отключение.

#### <a name="third-party-devices"></a>Сторонние устройства

На сторонних устройствах, таких как 3PIPные телефоны, видеоконференции, обратные прокси-серверы и подсистемы балансировки нагрузки, проверьте, правильно ли включена поддержка TLS 1,2 и будьте внимательны и при необходимости обратитесь к поставщику.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Рекомендации по интеграции при отключении TLS 1.0/1.1 на пограничных серверах

Вам необходимо тщательно спланировать и продумать последствия отключения TLS 1.0/1.1 на пограничных серверах.  После отключения протокола TLS 1,0 и 1,1 вы можете обнаружить, что другие организации не смогут выполнять Федерацию с вашей организацией.

Для обеспечения обратной совместимости с неисправленными (SfB 2015, Lync 2013) или более ранними (2010) внешними системами на серверах пограничного сервера может быть включена поддержка TLS 1.0/1.1.

Корпорация Майкрософт не может предоставить советы и рекомендации относительно того, попадает ли сеть с пограничным подключением (или любую сеть) на стандарт PCI. которое должно быть определено отдельной компанией.

Skype для бизнеса Online поддерживает TLS 1,2 прямо сейчас, поэтому не нужно воздействовать на гибридный или федерацию с Online.

PIC (общедоступная служба обмена мгновенными сообщениями) с службой потребителей Skype: мы не рекомендуем отключить TLS 1.0/1.1, чтобы повлиять на [связь в Skype](../../deploy/deploy-skype-connectivity.md); Шлюзы Microsoft PIC уже поддерживают TLS 1,2.

## <a name="prerequisites-and-process"></a>Необходимые условия и процесс

За исключением случаев, описанных выше, после того как протоколы TLS 1,0 и 1,1 отключены от сервера, клиенты и устройства будут работать правильно или вообще. Это может означать, что вы должны приостановить и дождаться получения обновленного руководства от корпорации Майкрософт. После того, как вы удовлетворены всеми требованиями и планируете пропуски, продолжайте.

На высоком уровне, в то время как Skype для бизнеса Server 2019 готов к выполнению процедуры установки, в Skype для бизнеса Server 2015 потребуется установить CU9, применить обновленные компоненты к .NET и SQL, развернуть необходимые разделы реестра и, наконец, отдельные округлить обновления конфигурации ОС (например, отключение TLS 1,0 и 1,1 с помощью импорта файлов реестра). Очень важно, чтобы вы закончите установку всех необходимых компонентов, включая Skype для бизнеса Server 2015 CU6 HF2, прежде чем отключить TLS 1,0 и 1,1 на любом сервере в вашей среде. Каждый сервер Skype для бизнеса, в том числе роль Edge и SQL, требует обновления. Кроме того, убедитесь, что все поддерживаемые клиенты (в области) обновлены до требуемых минимальных версий. Не забудьте также обновить рабочие станции управления.

Мы должны подписаться на обычное выполнение операций "Inside" для обновления серверов Skype для бизнеса. Сосчитайте, что пулы, сохраняемые и парные видеоконференции и Объединенные пулы будут рассматриваться так же, как и обычно. [Здесь](topology.md) описаны [порядок и методы обновления.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)

### <a name="high-level-process"></a>Процесс высокого уровня

1. Перед настройкой рабочих серверов протестируйте все этапы в лаборатории.
2. Создавайте резервные копии и сохраняйте копии экспортируемого реестра на каждом отдельном сервере, который нужно обновить. Вы не можете обмениваться реестрами между серверами; они содержат уникальные ключи на компьютере.
3. Обновите все серверы Skype для бизнеса 2015 до CU9 или более новой версии. Для Skype для бизнеса Server 2019 выполните обновление до CU1 или более новой версии.
4. Установите все необходимые компоненты на все серверы.
5. Развертывайте разделы реестра, необходимые для предварительной проверки.
6. Убедитесь, что все клиенты в области обновления обновлены.
7. Отключите TLS 1,0 и 1,1 с помощью импорта реестра.
8. Убедитесь, что рабочие нагрузки работают должным образом.
    - Если возникли проблемы, устраните неполадки и устраните или
    - Восстановление реестра из шага 2 для повторного включения TLS 1,0 и 1,1
9. Убедитесь, что используется только протокол TLS 1,2.

### <a name="install-prerequisites-to-all-servers"></a>Установка предварительных требований для всех серверов

Перед отключением TLS 1,0 и 1,1 на уровне операционной системы в версии Skype для бизнеса Server 2015 требуется обширное Обновление зависимостей. Ниже приведены минимальные версии, которые могут поддерживать TLS 1,2. Прежде чем приступить к отключению TLS 1,0 и 1,1, выполните развертывание всех необходимых обновлений для каждого сервера Skype для бизнеса в своей среде.

- Skype для бизнеса Server 2015 CU9 6.0.9319.548 (Май 2019) или более позднюю версию
- [.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) или более новая версия с включенной счусестронгкрипто в реестре (приведенной ниже).
- SQL должен быть обновлен на всех серверах Skype для бизнеса 2015 и на всех концах. Сначала обновите SQL для пула Enterprise Edition, а затем соответствующие Фес. 
    - SQL Server 2014 с пакетом обновления 1 + CU5 ([ссылка](https://support.microsoft.com/help/3130926)) или выше/sql Server 2012 2 + CU16 или выше/sql Server 2014 RTM + CU12 ([Link](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)) или выше/SQL Server 2014 SP2
     - Собственный клиент SQL Server для SQL Server 2012 ([ссылка](https://www.microsoft.com/download/details.aspx?id=50402))
     - Драйвер Microsoft ODBC 11 для SQL Server ([ссылка](https://www.microsoft.com/download/details.aspx?id=36434)) или более позднюю версию
     - Общие управляющие объекты для SQL Server 2014 с пакетом обновления 2 (SP2) ([ссылка](https://www.microsoft.com/download/details.aspx?id=42295))
     - Склсисклртипес для SQL Server 2014 с пакетом обновления 2 (SP2) ([ссылка](https://www.microsoft.com/download/details.aspx?id=42295))

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Основные действия по установке предварительных требований в рекомендованном порядке операций

1. Установите обновление CU9 на сервере Skype для бизнеса на все серверы. 
    1. Установите обновление для компонентов, использующих средство обновления.
    2. Обновление баз данных в соответствии с описанными процедурами. Сведения о Skype для бизнеса Server 2015 можно найти в статьях KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. Проверка функций продукта в развертывании перед переходом вперед с другими изменениями.
2. Скачайте автономный установщик .NET 4,7. 
    1. Справки[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Убедитесь в том, что службы Skype для бизнеса Server 2015 остановлены на сервере переднего плана.
    3. Справки[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. EX (стандартный выпуск):```Stop-CsWindowsService```
    5. EX (выпуск Enterprise Edition):```Invoke-CsComputerFailover```
    6. Запустите установочный пакет.
    7. Перезагрузите сервер.
3. Обновите SQL Express 2014 на всех серверах. 
    1. Справки[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Загрузите SQL 2014 с пакетом обновления 2 
        - Справки[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Копирование установочного носителя в папку на сервере (ex: C:\ 01_2014SqlSp2)
    4. Убедитесь в том, что службы Skype для бизнеса Server 2015 остановлены на сервере переднего плана 
        - EX (стандартный выпуск):```Stop-CsWindowsService```
        - EX (выпуск Enterprise Edition):```Invoke-CsComputerFailover```
    5. Открытие командной строки администратора и обновление всех установленных компонентов и экземпляров 
        - Пример: C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/КС/Иакцептсклсерверлиценсетермс/Актион = Patch/Аллинстанцес
4. Обновите собственный клиент SQL. 
    1. Ссылка: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Скачать из[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Убедитесь в том, что службы Skype для бизнеса Server 2015 остановлены на сервере переднего плана. 
        - EX (стандартный выпуск):```Stop-CsWindowsServices```
        - EX (выпуск Enterprise Edition):```Invoke-CsComputerFailover```
    4. Остановка выполнения экземпляров SQL 
        - Пример```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Пример```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - EX (только в стандартном выпуске):```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Установите обновление.
5. Обновите драйвер ODBC 11 для SQL Server, чтобы включить поддержку TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).
    1. Скачайте [драйвер ODBC 11 для SQL Server — Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).
    2. Убедитесь в том, что службы Skype для бизнеса Server 2015 остановлены на сервере переднего плана.
        - Пример (стандартный выпуск):```Stop-CsWindowsService```
        - Пример (Enterprise Edition):```Invoke-CsComputerFailover```
    3. Установите обновление.
6. Развертывайте разделы реестра, необходимые для предварительной проверки.

### <a name="pre-requisite-registry-keys"></a>Разделы реестра, необходимые для предварительной версии

Скопируйте и вставьте в блокнот следующий тест, а затем переименуйте Тлспререк. reg или выберите нужное имя, а затем выполните импорт.

```
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

Если вы хотите использовать SQL для пулов Enterprise Edition, предварительные требования и отключение TLS должны рассматриваться как любые обновления SQL или ОС. Ссылка на:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Несмотря на то, что вы можете объединять как необходимые, так и необходимые шаги для отключения TLS 1,0 и 1,1 на уровне операционной системы, мы настоятельно рекомендуем применять все предварительные требования. Лучший подход — подготовить среду, развертывая все необходимые компоненты, предварительно проверяя, правильно ли работают все задачи, а затем продолжать работу с протоколом TLS 1.0/1.1 позже.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Отключите TLS 1,0 и 1,1 с помощью импорта реестра

Перед тем как перейти к следующим действиям, *Убедитесь, что выполнены все необходимые условия и обновленные серверы Skype для бизнеса*.

Скопируйте приведенный ниже текст в файл "Блокнот" и переименуйте его в **тлсдисабле. reg**:

```
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

Импортируйте reg файл на каждый сервер, на котором вы хотите отключить TLS 1,0 и 1,1. Перезагрузите сервер. После того как службы снова поступают в сеть, перейдите на следующий сервер. Подход для пулов предприятий выпуска — это то же самое, что и при обновлении операционной системы.

Возможно, вы заметили, что мы делаем больше всего, чем просто отключение TLS 1,0 и 1,1. Мы поддерживаем повторный заказ комплекта шифров (как показано выше) и отключение некоторых устаревших слабых шифров. Это первое, что мы официально поддерживали эти изменения в SCHANNEL и API шифрования в Skype для бизнеса Server, и важно отметить, что эти изменения поддерживаются только нами и были протестированы в настоящее время. В будущем мы можем использовать дополнительные конфигурации, но сейчас не изменяйте файл импорта реестра в своей реализации.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Проверка правильности функционирования рабочих нагрузок

После отключения протоколов TLS 1,0 и 1,1 в среде убедитесь, что все основные рабочие нагрузки работают должным образом, например мгновенные сообщения & присутствии, звонки P2P, корпоративный голос и т. д.

**Только проверка подлинности TLS 1,2**

Убедитесь, что ваша группа безопасности выполняет новый аудит трафика Skype для бизнеса, чтобы убедиться, что старые протоколы TLS 1,0 и 1,1 больше не используются.

Кроме того, вы можете использовать Internet Explorer для проверки подключений TLS для веб-служб из Skype для бизнеса Server 2015 после отключения TLS 1,0 и TLS 1,1.

1. Запустите браузер Internet Explorer.
2. В **меню Сервис** > выберите пункт**Свойства браузера**.
3. Откройте вкладку **Дополнительно** .
4. В разделе **Параметры**прокрутите вниз.
5. Убедитесь в том, что TLS 1,0, TLS 1,1 и TLS 1,2 включены.
6. Просмотрите URL-адрес внутренней веб-службы SfB пула 2015 (он должен быть успешно подключен).
7. Вернитесь в Internet Explorer и отключите параметр для **использования протокола TLS 1,2** .
8. Просматривайте URL-адрес внутренней веб-службы SfB пула 2015 еще раз (не подключаться).

![Свойства браузера](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Сценарии расширенного развертывания

Поскольку некоторые условия для зависимостей должны поддерживать TLS 1,2 в Skype для бизнеса SER 2015, при установке с носителя RTM на любой системе, где отключены TLS 1,0 и 1,1, произойдет сбой.

**Развертывание новых серверов стандартных выпусков или пулов корпоративных выпусков после отключения TLS 1,0 и 1,1 в среде.**

**Вариант 1:** Используйте [смартсетуп](../../deploy/install/install-skype-for-business-server.md). Обратите внимание на то, что мы обновляем Смартсетуп, чтобы разместить обновленные двоичные файлы SQL в будущем SP1, и будет обновлять эту статью в будущем.

**Вариант 2:** Предварительная установка локальных экземпляров SQL (РТКЛОКАЛ и ЛИНКЛОКАЛ)

1. Скачайте и скопируйте SQL Express 2014 с пакетом обновления 2 (SQLEXPR_x64. exe) в локальную папку на FE. Пусть <путь к папке SQL_FOLDER_PATH>.
2. Запустите PowerShell или командную команду и перейдите в раздел <SQL_FOLDER_PATH>.
3. Создайте экземпляр SQL РТКЛОКАЛ, выполнив команду ниже. Дождитесь завершения работы SQLEXPR_x64. exe, прежде чем продолжить.

    SQLEXPR_x64. exe/Q/ИАКЦЕПТСКЛСЕРВЕРЛИЦЕНСЕТЕРМС/УПДАТИНАБЛЕД = 0/ХИДЕКОНСОЛЕ/АКТИОН = Install/ФЕАТУРЕС = Скленгине, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS =
1. Создайте экземпляр SQL ЛИНКЛОКАЛ, выполнив команду ниже. Дождитесь завершения работы SQLEXPR_x64. exe, прежде чем переходить к следующему действию:

    SQLEXPR_x64. exe/Q/ИАКЦЕПТСКЛСЕРВЕРЛИЦЕНСЕТЕРМС/УПДАТИНАБЛЕД = 0/ХИДЕКОНСОЛЕ/АКТИОН = Install/ФЕАТУРЕС = Скленгине, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin \ Администраторы" = ""/BROWSERSVCSTARTUPTYPE = "/AGTSVCACCOUNT" NTAUTHORITY\NetworkService
1. Запустите настройку Skype для бизнеса Server 2015 RTM.
2. Следуйте дальнейшим инструкциям из раздела необходимые условия.

**Вариант 3:** Кроме того, вы можете вручную заменить двоичные файлы в локальной папке установочных файлов, как описано ниже.

1. [Установка предварительных требований для Skype для бизнеса Server](../../deploy/install/install-prerequisites.md)  
2. Установка .NET 4,7: 
      - **Примечание.** Мы впервые предоставили поддержку .NET 4,7 в Skype для бизнеса Server 2015 CU5 (6.0.9319.281). Поэтому в последующих шагах, описанных ниже, мы будем обновлять основные компоненты до основной установки.
      - Файл для https://www.microsoft.com/download/details.aspx?id=55167скачивания:. 
      - Справка: [программное обеспечение, которое должно быть установлено перед развертыванием Skype для бизнеса Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Копирование файлов и папок ISO: 
    - С помощью встроенного ISO-файла Skype для Business Server 2015 откройте корневой каталог диска, подключенного к нему как (например,\) D: в проводнике).
    - Копирование всех папок и файлов в папку на локальном диске (например: C:\SkypeForBusiness2015ISO).
    - **Примечание.** Перед установкой компонентов необходимо обновить некоторые файлы для поддержки протокола TLS 1,2.
4. Замените пакеты MSI/EXE. 
    - Замените существующие пакеты MSI и EXE в папке/Setup/AMD64/установочного носителя на локальном компьютере.
    - SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167 
        - Переименуйте SQLEXPR_x64 на локальном компьютере и замените существующий файл в папке Настройка/AMD64/на установочном носителе.
    - Собственный клиент SQL:https://www.microsoft.com/en-us/download/details.aspx?id=50402 
        - **Примечание.** Переименуйте этот файл, если это необходимо, на SQLNCLI. msi, а затем замените на установочный носитель существующий.
    - Объекты управления SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Примечание.** Пакет дополнительных компонентов содержит множество элементов, которые можно загрузить. Выберите загрузить только Шаредманажементобжектс. msi.
        - **Примечание.** Замените существующий файл, существующий в папке Настройка/AMD64/на установочном носителе.
    - Типы SQL CLR:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Примечание.** Пакет дополнительных компонентов содержит множество элементов, которые можно загрузить. Выберите, чтобы загрузить только Кклсисклртипес. msi
        - **Примечание**. Замените существующий файл, который находится в папке Настройка/AMD64/на установочном носителе.
5. Установка основных компонентов: 
    - Запустите setup. exe из папки "Настройка/AMD64/" установочного носителя. Следуйте инструкциям по установке основных компонентов
    - Закройте основные компоненты.
6. Обновление основных компонентов: 
    - Скачайте установщик обновлений Skype для бизнеса.
    - Запустите установщик, чтобы обновить основные компоненты и установить счетчики производительности.
    - **Примечание.** По мере выпуска CU6HF2 в настоящее время функция автоматического обновления будет устанавливаться только в CU6. Таким образом, средство обновления необходимо запускать отдельно, чтобы обновить основные компоненты до 6.0.9319.516.
    - Справкиhttps://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015
7. Установка средств администрирования (необязательно): 
    - Это приведет к установке собственного клиента Microsoft SQL Server 2012 Native Client, управляющих объектов SQL Server 2014 (x64) и Microsoft System CLR Types для SQL Server 2014 (x64) с помощью обновленных файлов. Кроме того, построитель топологии Skype для бизнеса Server 2015 и панель управления будут доступны на локальном компьютере.
8. Установка локального хранилища конфигураций (этап 1): 
     - Откройте мастер развертывания, щелкните Установка или обновление системы Skype для бизнеса Server и выберите пункт **выполнить** на шаге 1: Установка локального хранилища конфигураций.
     - В диалоговом окне **Установка хранилища локальных конфигураций** нажмите кнопку **Далее** .
     ![Диалоговое окно «Установка хранилища локальных конфигураций»](../../media/local-configuration-store.png)
     - Проверьте результаты и убедитесь, что состояние задачи завершено. Просмотрите итоговый файл журнала, нажав кнопку **Просмотреть журнал**.
     ![Состояние задачи — "завершено"](../../media/local-configuration-task-completed.png)
     - Нажмите **Готово**.
9. Настройка и удаление компонентов сервера Skype для бизнеса (шаг 2):
    - Откройте мастер развертывания, щелкните **Установка или обновление системы Skype для бизнеса Server**и выберите пункт **выполнить** на этапе 2: Настройка или удаление компонентов Skype для бизнеса Server
    - В диалоговом окне Настройка компонентов сервера Skype для бизнеса нажмите кнопку **Далее** .
    ![окно "Настройка компонентов Skype для бизнеса Server"](../../media/set-up-skype-for-business-server-components-window.png)
    - Просмотрите журнал с помощью журнала и убедитесь, что настройка завершилась без проблем. 
    - Нажмите **Готово**.
10. Продолжайте устанавливать и настраивать дополнительные требования (на этом этапе вы можете продолжить обычную процедуру установки).
