---
title: Отключить протокол TLS 1.0/1.1 в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: heidip
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Сводка: Подготовка к и реализовать отключение TLS 1.0 и 1.1 в вашей среде.'
ms.openlocfilehash: dc835a68e47f9fac6036724d92ad336ead795e50
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012935"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Отключить протокол TLS 1.0/1.1 в Скайп для Business Server 2015

В этой статье предназначен для предоставления необходимых рекомендаций для подготовки и реализации отключение TLS 1.0 и 1.1 в вашей среде. Этот процесс требует тщательного планирования и подготовки. Тщательно проверьте все сведения в этой статье при принятии плана для отключения TLS 1.0 и 1.1 для вашей организации. Обратите внимание на то, что существует множество внешние зависимости и подключения к условия, которые могут повлиять на работу отключение TLS 1.0/1.1, необходимо сделать так тщательного планирования и тестирования.

## <a name="in-this-article"></a>В этой статье

- [Фон и область действия](#background)
- [Необходимые условия и процесс](#prerequisites-and-process)
- [Расширенные сценарии развертывания](#advanced-deployment-scenarios)

## <a name="background"></a>Общие сведения

Основной факторами для предоставления TLS 1.0 и 1.1 отключить поддержку для Скайп для Business Server локальной перечислены требования к Совет стандартов безопасности индустрии платежных карт (PCI) и федеральных стандартов обработки информации. Требования к PCI Дополнительные сведения можно найти [здесь](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Корпорация Майкрософт не предоставляет рекомендации на ли вашей организации должны соблюдать эти или другие требования. Необходимо определить, если он необходим позволяет отключить TLS 1.0 и 1.1 в вашей среде.

Майкрософт разработала Технический документ на TLS доступные [здесь](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), поэтому рекомендуется также фоновом режиме чтения недоступны в этом [блоге Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).

## <a name="supportability-scope"></a>Область технической поддержке

*Область* относится к границам технической поддержке. Для Скайп для Business Server локальной *в области действия* означает, что мы полностью поддерживает и проверены отключение TLS 1.0 и 1.1 для версии перечисленных продуктов. *В настоящее время изучению* означает, что только что; активно ведется расследование, внедрение этих продуктов в область действия для отключения поддержки TLS. *Из области действия* означает, что эти версии продукта не поддерживают отключение TLS 1.0 или 1.1 и не будут работать, за исключением указанных.

### <a name="fully-tested-and-supported-servers"></a>Полностью протестированы и поддерживаемые серверы

- Skype для бизнеса Server 2019
- Скайп для Business Server 2015 CU6 HF2 6.0.9319.516 ([Обновить 2018 марта](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) и выше на: 
    - Windows Server 2012 (с 3140245 КБ или заменяющего обновления), 2012 R2 или 2016
- Скайп обновления на месте для 2015 Business Server, с CU6 HF2 и более высоких прав для 
    - Windows Server 2008 R2, 2012 г. (с статья БАЗЫ знаний [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или заменяющее обновление) или 2012 R2
- Подключение к Exchange и Outlook Web App с Exchange Server 2010 с пакетом обновления 3 RU19 или более поздней версии, руководство [здесь](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Устройство для обеспечения связи в филиалах (SBA) с Скайп для Business Server 2015 CU6 HF2 или более поздней версии (проверьте с поставщиком, что они упакованных обновлений appropiate и доступному для устройства)
- Сервер для обеспечения связи в филиалах (SBS) с Скайп для Business Server 2015 CU6 HF2 или более поздней версии
- Lync Server 2013 **Только роли пограничного сервера**, это, поскольку роль пограничного отсутствуют зависимости на Windows Fabric 1.0.


### <a name="fully-tested-and-supported-clients"></a>Полностью протестированы и поддерживаемые клиенты

- Настольный клиент Lync 2013 (Скайп для бизнеса), MSI и C2R, включая Basic [15.0.5023.1000 и последующие версии](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Скайп для бизнеса 2016 настольный клиент, MSI [16.0.4678.1000 и последующие версии](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), включая Basic
- Скайп для бизнеса, 2016 нажмите кнопку Запуск, требуют обновления [2018 апреля](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) : 
    - Ежемесячно и точками годовая нацелено 16\.0\.9126\.2152 и выше
    - Годовая точками и отложенный канала, 16\.0\.8431\.2242 и выше
- Скайп для бизнеса на Mac 16.15 и более поздней версии
- Скайп для деловых операций ввода-вывода и Android 6.19 и выше
- Скайп Web App 2015 CU6 HF2 и выше (поставляется с сервера)

### <a name="currently-being-investigated"></a>В настоящее время изучению

#### <a name="devices"></a>Устройства

- Система комнаты Lync (известной как SRSv1)
- Комнат группами Майкрософт
- Контактной сервера-концентратора
- на основе 2015, устройство для обеспечения связи в филиалах (SBA) или сервера обеспечения связи в филиалах (SBS)

#### <a name="other"></a>Другое

- Вызов мониторинга качества (были отключены с новой установки после TLS 1.0, 1.1, см) *
 
### <a name="out-of-scope"></a>Из области действия

Если не указано иное следующих продуктов не входящих в область для TLS 1.0/1.1 отключить поддержку и не будет работать в среде, где были отключены TLS 1.0 и 1.1.  Это означает: Если вы по-прежнему использовать вне области серверы или клиенты, необходимо обновить или удалить эти поля, если требуется отключить протокол TLS 1.0/1.1 в любом месте вашего Скайп for Business Server локальное развертывание.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 и нижний край
- Lync для Mac 2011
- Lync 2013 для мобильных устройств - операций ввода-вывода, iPad, Android или Windows Phone
- Клиент Lync «MX» для магазина Windows
- Все клиенты Lync 2010
- Lync Phone Edition - обновлено руководство [здесь](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- 2013 на основе устройство для обеспечения связи в филиалах (SBA) или сервера обеспечения связи в филиалах (SBS)
- Облако соединителя Edition (системы CCE)
- Skype для бизнеса для Windows Phone

### <a name="exceptions"></a>Исключения

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 зависит Windows Fabric версии 1.0.  На этапе разработки для Lync Server 2013 Windows Fabric 1.0 был выбран для привлекательные и новые распределенной архитектуры для обеспечения репликации, высокая доступность и устойчивость к сбоям.  Со временем обоих Скайп Business Server и Windows Fabric значительно повысили Эта архитектура совместного с значительные повторно проектирование в последующих версиях.  Текущий Скайп для Business 2015 Server использует Windows Fabric 3.0, например.

К сожалению Windows Fabric 1.0 **не поддерживает TLS 1.2.  Тем не менее, мы будет обновляться Lync Server 2013 для работы с тактовой частотой 1,2 TLS**. Это должен быть выпущен в далее накопительные пакеты обновления для Lync Server 2013.  Мы предлагаем поддержки TLS 1.2 для включения совместная работа, переноса, федерации и гибридных сценариев.

Если вы уже используете Lync Server 2013 вашей организации требуется отключить протокол TLS 1.0 и 1.1, рекомендуется начать в процессе планирования, существует возможность в некоторых случаях требуется обновление на месте или рядом друг с другом перенос (новые пулы, перемещение пользователей) в Скайп для Business Server 2015 или более поздней версии.  Или воспользуйтесь для ускорения миграции для Скайп для бизнеса в Интернет.

#### <a name="call-quality-dashboard"></a>Панель мониторинга качества вызовов

Панель мониторинга качества звонков в локальной в настоящее время имеет зависимости от TLS 1.0 во время новой установки (установка в вашей локальной среды первый раз).  Мы в настоящее время ведется расследование этой проблемы и планирование для освобождения исправление в ближайшем будущем.  При планировании установки CQD и также отключить TLS 1.0 рекомендуется сначала завершить установку CQD и нажмите Продолжить отключение TLS 1.0.

#### <a name="third-party-devices"></a>Устройствами сторонних производителей

На устройствах сторонних производителей, таких как телефоны 3PIP видео-конференций, обратных прокси-серверов и подсистем балансировки нагрузки, не забудьте проверить технической поддержке TLS 1.2, тщательно проверьте и обратитесь к поставщику и при необходимости.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Сведения о выполнении федерации при отключении TLS 1.0/1.1 на пограничных серверах

Необходимо тщательно спланировать и рассмотрите влияние отключения TLS 1.0/1.1 на пограничных серверах.  После TLS 1.0 и 1.1 отключены, может оказаться, что других организаций больше не смогут в федерацию с вашей организации.

Может выбрать для хранения TLS 1.0/1.1 включен на пограничных серверах для обеспечения обратной совместимости с не исправленный (SfB 2015, Lync 2013) или более старые внешними системами (2010).

Корпорация Майкрософт не предоставляет советы и рекомендации на ли вашей пограничной сети (или любую сеть) попадает в разделе PCI standard; который необходимо определить в отдельных компании.

Скайп для бизнеса в Интернет способен TLS 1.2 в настоящее время, без воздействия на гибридные/федерацию с Online не ожидается.

PIC (общедоступной службы обмена Мгновенными сообщениями) к службе Скайп потребителей: не ожидается, что отключение TLS 1.0/1.1 влияние [Подключения к Скайп](../../deploy/deploy-skype-connectivity.md); Шлюзы PIC Microsoft уже может 1.2 TLS.

## <a name="prerequisites-and-process"></a>Необходимые условия и процесс

Если не указано иное, после TLS 1.0 и 1.1 отключенных вне области серверов, клиентов и устройств будет работать неправильно или вообще, за исключением. Это означает, что необходимо приостановить и дождитесь обновлено руководство корпорации Майкрософт. Как только вы удовлетворены соответствовать всем требованиям и составить план адрес перерывов в работе, продолжить работу.

На высоком уровне во время Скайп для Business Server 2019 готова к процедуре во время установки Скайп для Business Server 2015 требуется установить HF2 CU6, необходимые предварительные обновление .NET и SQL, развертывание необходимого реестра и наконец отдельных обновляет Round конфигурации операционной системы (то есть отключение TLS 1.0 и 1.1 с помощью импорта файла реестра). Очень важно выполнить установку необходимых, включая Скайп для Business Server 2015 CU6 HF2, перед отключение TLS 1.0 и 1.1 на любом сервере в вашей среде. Каждый Скайп для Business server, включая роли пограничного сервера и серверных системах SQL требует обновления. Кроме того, убедитесь, что минимальные требуемые версии были обновлены все поддерживаемые клиенты (в области). Не забудьте обновить также рабочие станции управления.

Мы хотим следуйте обычным порядке операций «внутри выход» для обновления Скайп для серверов организаций. Рассматривать пулов, сохраняемого чата и сопоставленных пулов директоров в точно так же, как обычно. Порядок и методов обновления рассматривается [здесь](topology.md) и [здесь](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>Высокоуровневый процесс

1. Проверьте все действия, описанные в лабораторной среде перед настройкой рабочих серверах.
2. Резервное копирование и сохранения копии экспортированного реестра на всех отдельного сервера, который требуется обновить. Не могут совместно использовать значений между серверами; они содержат уникальные ключи компьютера.
3. Обновление всех Скайп для серверов Business 2015 CU6 HF2 или выше. (Для Скайп для Business Server 2019 необходима не накопительный пакет обновления)
4. Установите все необходимые компоненты на все серверы.
5. Разверните разделы реестра, необходимых компонентов.
6. Убедитесь, что все клиенты в области обновляются.
7. Отключите протокол TLS 1.0 и 1.1 с помощью реестра импорта.
8. Убедитесь, что рабочие нагрузки работают должным образом.
    - Если возникли проблемы, устранение неполадок и устранить, или
    - Восстановление реестра в шаге 2, чтобы повторно включить TLS 1.0 и 1.1
9. Убедитесь, что используется только протокол TLS 1.2.

### <a name="install-prerequisites-to-all-servers"></a>Установка необходимых компонентов на всех серверах

Широкое зависимостей обновление не требуется, перед началом работы для отключения TLS 1.0 и 1.1 на уровне операционной системы в вашей Скайп для развертываний Business Server 2015. Ниже приведены минимальные версий, помогающие обеспечить TLS 1.2. Разверните все необходимые обновления на каждый Скайп для Business server в среде, прежде чем начать, отключение TLS 1.0 и 1.1.

- Скайп для Business Server 2015 CU6 HF2 6.0.9319.516 ([Обновить 2018 марта](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) или более поздней версии
- [.NET framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) или выше с SchUseStrongCrypto, включенных в реестр (представлены ниже)
- Необходимо обновить SQL на всех Скайп для бизнеса 2015 серверов и серверных системах. Обновление серверных системах SQL Enterprise Edition пула во-первых, затем их соответствующих FEs. 
    - SQL Server 2014 с пакетом обновления 1 + накопительным пакетом обновления 5 ([ссылки](https://support.microsoft.com/help/3130926)) или выше / CU16 + SQL Server 2012 с пакетом обновления 2 или выше / SQL Server 2014 RTM + CU12 ([ссылки](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) или более поздней версии / с пакетом обновления 2 для SQL Server 2014 г.
    - Собственный клиент SQL Server для SQL Server 2012 ([ссылки](https://www.microsoft.com/en-us/download/details.aspx?id=50402))
    - Драйвер ODBC Microsoft 11 для SQL Server ([ссылки](https://www.microsoft.com/en-us/download/details.aspx?id=36434)) или более поздней версии
    - Общие объекты управления для SQL Server 2014 г., с пакетом обновления 2 ([ссылки](https://www.microsoft.com/en-in/download/details.aspx?id=42295))
    - SQLSysClrTypes для SQL server 2014 с пакетом обновления 2 ([ссылки](https://www.microsoft.com/en-in/download/details.aspx?id=42295))

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Основные действия для установки необходимых компонентов в Рекомендуемая последовательность операций

1. Установка Скайп для Business Server CU6HF2 (6.0.9319.516) обновление на все серверы. 
    1. Установите обновление для компонентов с помощью программы обновления.
    2. Обновление баз данных в соответствии с документированным процедур. Инструкции по описаны на [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).
    3. Проверьте функциональные возможности продуктов в развертывании, прежде чем продолжать другие изменения.
2. Загрузить .NET 4.7 автономного установщика. 
    1. Ссылка:[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)
    2. Убедитесь, что Скайп для служб Business Server 2015 останавливаются на сервере переднего плана.
    3. Ссылка:[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition): Stop-CsWindowsServices
    5. Ex (Enterprise Edition): Invoke-CsComputerFailover
    6. Запустите пакет установки.
    7. Перезагрузите сервер.
3. Обновление SQL Express 2014 г. на всех серверах. 
    1. Ссылка:[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Загрузить пакет обновления 2 для SQL 2014 г. 
        - Ссылка:[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)
    3. Скопируйте установочного носителя в папку на сервере (например: C:\01_2014SqlSp2)
    4. Обеспечить Скайп Business Server 2015 остановлен служб на сервере переднего плана 
        - Ex (Standard Edition): Stop-CsWindowsService
        - Ex (Enterprise Edition): Invoke-CsComputerFailove
    5. Откройте командную строку администратора и обновление всех установленных компонентов и экземпляров 
        - Пример: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action = исправление строки.
4. Обновите собственного клиента SQL. 
    1. Ссылка: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Загрузите из[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)
    3. Обеспечить Скайп Business Server 2015 остановлен служб на сервере переднего плана. 
        - Ex (Standard Edition): Stop-CsWindowsServices
        - Ex (Enterprise Edition): Invoke-CsComputerFailove
    4. Остановка установленных запуск экземпляров SQL 
        - Пример: «RTCLOCAL MSSQL$» Get-Service | Остановить служва
        - Пример: «LYNCLOCAL MSSQL$» Get-Service | Остановить служва
        - Ex (Standard Edition только): Get-Service «RTC MSSQL$» | Остановить служва
    5. Установите обновление.
5. Обновите драйвер ODBC 11 для SQL Server. 
    1. Ссылка: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Загрузите из[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)
    3. Убедитесь, что Скайп для служб Business Server 2015 останавливаются на сервере переднего плана 
        - Ex (Standard Edition): Stop-CsWindowsService
        - Ex (Enterprise Edition): Invoke-CsComputerFailove
    4. Установите обновление.
6. Разверните разделы реестра, необходимых компонентов.

### <a name="pre-requisite-registry-keys"></a>Необходимые предварительные реестра

Копирование и вставка следующего теста в Блокнот и переименуйте TLSPreReq.reg или имя собственное, а затем импортировать:

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

Для SQL назад, отключить концов пулы Enterprise Edition, необходимые условия и TLS следует рассматривать как бы все SQL и операционная система обновления; Обратитесь к:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Хотя можно сочетать необходимых приложений и отключение действия TLS, мы настоятельно рекомендуем применить все необходимые компоненты перед тем как продолжить отключение TLS 1.0 и 1.1 на уровне операционной системы. Подготовка среды развертывания все необходимые компоненты, проверка, что все рабочие нагрузки работает правильно и надлежащим образом, а затем отключите переходом с TLS 1.0/1.1 позднее будет best practice подход.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Отключить протокол TLS 1.0 и 1.1 с помощью реестра импорта

Перед началом дальнейшие действия, *Убедитесь, что выполнены все необходимые условия и обновление Скайп для серверов организаций*.

Скопируйте следующий текст в файл Блокнота и переименуйте его **TLSDisable.reg**:

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

Импортируйте REG-файл на каждом сервере, который вы хотите отключить TLS 1.0 и 1.1. Перезагрузите сервер. После службы оперативный, перемещение к следующему серверу. Подход для пулов Enterprise Edition — это же может занять все обновления операционной системы.

Вы могли заметить, что это делается больше, чем просто отключение TLS 1.0 и 1.1 здесь. Мы это вспомогательные шифрования Suite, изменять порядок (как показано выше) и отключение некоторых старых слабые шифры. В первый раз мы официально поддерживаемые эти изменения SCHANNEL и API шифрования на Скайп для Business Server и важно Обратите внимание на то, что эти изменения являются единственными мы поддержки и тестирования в данный момент. Мы рассмотрим дополнительных конфигураций в будущем, но в данный момент, не изменяйте файл импорта реестра в реализации.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Убедиться, что рабочие нагрузки работают должным образом

После TLS 1.0 и 1.1 отключены в вашей среде, убедитесь, что все основные рабочие нагрузки работают должным образом, такие как обмен мгновенными Сообщениями & сведения о присутствии, P2P вызовов корпоративной голосовой связи и т.д.

**Проверить, используется только протокол TLS 1.2 (en)**

У группы безопасности выполнение новых аудита Скайп для бизнес-трафика, чтобы убедиться, что старые протоколы TLS 1.0 и 1.1 больше не используется.

Кроме того можно использовать Internet Explorer для проверки подключений TLS для веб-служб из Скайп Business Server 2015 после отключения TLS 1.0 и TLS 1.1.

1. Запустите браузер Internet Explorer.
2. Выбор **инструментов** > **Свойства обозревателя**.
3. Перейдите на вкладку **Дополнительно** .
4. В разделе **Параметры**прокрутите список вниз.
5. Убедитесь, что включены TLS 1.0, TLS 1.1 и TLS 1.2.
6. Обзор внутренних Web URL-адрес службы пула SfB 2015 (должен установить связь).
7. Вернитесь в Internet Explorer и отключить возможность **использования TLS 1.2** только.
8. Обзор внутренних Web URL-адрес службы SfB 2015 пула еще раз (не сможет выполнить подключение).

![Свойства обозревателя](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Расширенные сценарии развертывания

Так как некоторые компоненты зависимость требуются для поддержки TLS 1.2 в Скайп для бизнеса пользователе 2015, установка с носителя RTM завершится ошибкой в любой системе, где были отключены TLS 1.0 и 1.1.

**Развертывание новых серверов Standard Edition или пулы Enterprise Edition после TLS 1.0 и 1.1 отключены в вашей среде.**

**Вариант 1:** С помощью [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Обратите внимание, что мы обновления SmartSetup для учета обновленные двоичные файлы SQL в будущем накопительный пакет обновления за и будут обновляться в этой статье.

**Вариант 2:** Предварительная установка экземпляров SQL (RTCLOCAL и LYNCLOCAL)

1. Загрузите и скопируйте SQL Express 2014 с пакетом обновления 2 (SQLEXPR_x64.exe) в локальной папке на FE. Предположим, <SQL_FOLDER_PATH> путь папки.
2. Запустите PowerShell или командной строки и перейдите к <SQL_FOLDER_PATH>.
3. Создайте экземпляр RTCLOCAL SQL с помощью следующей команды. Подождите, пока завершится SQLEXPR_x64.exe перед тем как:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = Установка/КОМПОНЕНТЫ = SQLEngine, средств режим = RTCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = «NT AUTHORITY\NetworkService» /SQLSYSADMINACCOUNTS = «Builtin\ Администраторы» /BROWSERSVCSTARTUPTYPE = «Automatic» /AGTSVCACCOUNT = «NTAUTHORITY\NetworkService» /SQLSVCSTARTUPTYPE = автомати
1. Создайте экземпляр LYNCLOCAL SQL с помощью следующей команды. Подождите, пока завершится SQLEXPR_x64.exe перед переходом к следующему шагу:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = Установка/КОМПОНЕНТЫ = SQLEngine, средств режим = LYNCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = «NT AUTHORITY\NetworkService» /SQLSYSADMINACCOUNTS = «Builtin\ Администраторы» /BROWSERSVCSTARTUPTYPE = «Automatic» /AGTSVCACCOUNT = «NTAUTHORITY\NetworkService» /SQLSVCSTARTUPTYPE = автоматический
1. Запустите Скайп для программы установки, Business Server 2015 RTM.
2. Выполните остальные действия в предыдущем разделе необходимых компонентов.

**Вариант 3:** Могут также вручную замените двоичные файлы в каталог мультимедиа локальной установки следующим образом:

1. [Установка необходимых компонентов для Скайп для Business Server](../../deploy/install/install-prerequisites.md)  
2. 2. Установка .NET 4.7: 
      - **Примечание:** Мы впервые представлена поддержка 4.7 .NET в Скайп для Business Server 2015 накопительным пакетом обновления 5 + (6.0.9319.281). Таким образом на последующих этапах ниже мы будет обновляться основные компоненты до основной установки.
      - Загрузка: https://www.microsoft.com/en-us/download/details.aspx?id=55167.
      - Ссылка: [программное обеспечение, которое должны быть установлены перед Скайп для развертывания Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Скопируйте файлы/папки ISO: 
    - С помощью Скайп для Business Server 2015 ISO подключенное, откройте корневой каталог диска, подключенный как (Ex: D:\) в File Explorer.
    - Скопируйте все папки и файлы в папку на локальном диске (например: C:\SkypeForBusiness2015ISO).
    - **Примечание:** Перед установкой компонентов, некоторые файлы необходимо обновить для поддержки TLS 1.2.
4. Замените пакеты MSI и exe-ФАЙЛ: 
    - Замена существующих пакетов MSI и exe-ФАЙЛ в папку/amd64 / / Setup установочного носителя на локальном компьютере.
    - SQL Express с пакетом обновления 2 2014 г.:https://www.microsoft.com/en-us/download/details.aspx?id=53167 
        - Измените имя на SQLEXPR_x64 на локальном компьютере и заменить существующий файл в установки/amd64/папки с установочного носителя.
    - Собственный клиент SQL:https://www.microsoft.com/en-us/download/details.aspx?id=50402 
        - **Примечание:** Переименование это при необходимости sqlncli.msi, а затем заменить существующий файл, который существует в установки/amd64/папки с установочного носителя.
    - Объекты AMO SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Примечание:** Пакет дополнительных компонентов будут иметь много элементов, которые можно загрузить. Выберите только для загрузки SharedManagementObjects.msi.
        - **Примечание:** Заменить существующий файл, который существует в установки/amd64/папки с установочного носителя.
    - Типы SQL CLR:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Примечание:** Пакет дополнительных компонентов будут иметь много элементов, которые можно загрузить. Выберите только для загрузки CQLSysClrTypes.msi
        - **Примечание**: заменить существующий файл, который существует в установки/amd64/папки с установочного носителя.
5. Установите основные компоненты: 
    - Запустите Setup.exe из программы установки и amd64/папки с установочного носителя. Следуйте инструкциям, чтобы установить компоненты ядра
    - Закройте основные компоненты.
6. Обновление основных компонентов: 
    - Загрузите Скайп для установки обновлений бизнеса.
    - Программа установки обновления основных компонентов и установить счетчики производительности.
    - **Примечание:** По состоянию на выпуск CU6HF2 функция автоматического обновления в настоящее время только предназначенным для установки до CU6. Таким образом средство обновления необходимо выполнить отдельно для обновления основных компонентов 6.0.9319.516.
    - Ссылка:https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015
7. Установка средств администрирования (необязательно): 
    - Будет выполнена установка собственного клиента Microsoft SQL Server 2012, 2014 управляющих объектов SQL Server (x64) и системные типы CLR для SQL Server 2014 (x64) с использованием обновленных файлов. Кроме того Скайп для Business Server 2015 Topology Builder и панель управления, будут доступны на локальном компьютере.
8. Установка локального хранилища конфигурации (шаг 1): 
     - Откройте мастер развертывания, выберите установить или обновление Скайп для бизнес-системы сервера и выберите команду **выполнить** в шаге 1: Установка локального хранилища конфигурации.
     - Нажмите кнопку **Далее** в диалоговом окне **Установка локального хранилища конфигурации** .
     ![Диалоговое окно Установка локального хранилища конфигурации](../../media/local-configuration-store.png)
     - Проанализируйте результаты и убедитесь, что состояние задачи завершено. Просмотрите созданный файл журнала, нажав кнопку **Просмотреть журнал**.
     ![Состояние задачи отображается как завершено](../../media/local-configuration-task-completed.png)
     - Нажмите **Готово**.
9. Установка и удаление Скайп для бизнес-компоненты сервера (шаг 2):
    - Откройте мастер развертывания, выберите **установить или обновление Скайп для бизнес-системы сервера**и нажмите кнопку **Запуск** на шаге 2: Установка и удаление Скайп для бизнеса серверных компонентов
    - Нажмите кнопку **Далее** в задать копирование Скайп для диалогового окна Business серверных компонентов.
    ![Задайте копирование Скайп для бизнеса серверных компонентов окна](../../media/set-up-skype-for-business-server-components-window.png)
    - Просмотр журнала с помощью просмотреть журнал и проверки, установка завершена без проблем. 
    - Нажмите **Готово**.
10. Дополнительные установки и конфигурации в соответствии с требованиями (можно возобновить процедуры обычной установки на этом этапе).
