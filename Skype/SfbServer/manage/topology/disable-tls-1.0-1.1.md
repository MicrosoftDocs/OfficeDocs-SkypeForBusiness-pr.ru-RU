---
title: Отключение TLS 1.0/1.1 в Skype для бизнеса Server 2015
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
description: Сводка. Подготовка и реализация отключения TLS 1.0 и 1.1 в средах.
ms.openlocfilehash: 06ebc3f5821e8daa1c80633b25140a852f72097d
ms.sourcegitcommit: 4143ce9bd62e67ba09f89cedadfd65803bda5361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/28/2020
ms.locfileid: "49734297"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Отключение TLS 1.0/1.1 в Skype для бизнеса Server 2015

Цель этой статьи — предоставить необходимые инструкции по подготовке и внедрению отключения TLS 1.0 и 1.1 в средах. Этот процесс требует тщательного планирования и подготовки. Внимательно просмотрите все сведения из этой статьи при планировании отключения TLS 1.0 и 1.1 для организации. Обратите внимание, что существует множество внешних зависимостей и условий подключения, на которые может повлиять отключение TLS 1.0/1.1, поэтому необходимо тщательное планирование и тестирование.

## <a name="in-this-article"></a>В этой статье

- [Фон и область действия](#background)
- [Необходимые условия и процесс](#prerequisites-and-process)
- [Расширенные сценарии развертывания](#advanced-deployment-scenarios)

## <a name="background"></a>Общие сведения

The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards И Federal Information Processing Standards requirements. Дополнительные сведения о требованиях PCI можно [найти](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)здесь.  Корпорация Майкрософт не может предоставлять инструкции о том, требуется ли вашей организации соблюдать эти или другие требования. Необходимо определить, требуется ли отключение TLS 1.0 и/или 1.1 в средах.

Корпорация Майкрософт подготовила документ по [](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)TLS, доступный здесь, и мы также рекомендуем фоновые чтения, доступные в этом блоге [Exchange.](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)

## <a name="supportability-scope"></a>Область поддержки

*Область* относится к границам поддержки. *Полное тестирование и* поддержка означает, что мы полностью поддерживаем и протестировали отключение TLS 1.0 и 1.1 для перечисленных версий продуктов. *В настоящее время это* означает только это; Мы активно исследуем возможность применения этих продуктов для отключения поддержки TLS. *Выходит за рамки* означает, что эти версии продуктов не поддерживают отключение TLS 1.0 или 1.1 и не будут работать с указанными исключениями.

### <a name="fully-tested-and-supported-servers"></a>Полностью протестные и поддерживаемые серверы

- Skype для бизнеса Server 2019 CU1 17.0.2046.123 (июнь 2019 г.) или более высокий
- Skype для бизнеса Server 2015 CU9 6.0.9319.548 (май 2019 г.) или более высокий в Windows Server 2012 (с обновлением KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или более новым), 2012 R2 или 2016.
- На месте обновлен Skype для бизнеса Server 2015 с cu9 6.0.9319.548 (май 2019 г.) или более высокой версией в Windows Server 2008 R2, 2012 (с обновлением KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или более новым обновлением) или 2012 R2.
- Руководство по подключению и Outlook Web App Exchange с Exchange Server 2010 с sp3 RU19 или более высокой [](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)
- Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher
- Lync Server 2013 **Edge Role Only**, это происходит потому, что роль edge не имеет зависимости от Windows Fabric 1.0.

### <a name="fully-tested-and-supported-clients"></a>Полностью протестированные и поддерживаемые клиенты

- Настольный клиент Lync 2013 (Skype для бизнеса), MSI и C2R, в том числе базовый [15.0.5023.1000](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334) или более высокий
- Клиент Skype для бизнеса 2016 для настольных ПК, MSI [16.0.4678.1000](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)или более высокий, включая базовый
- Skype для бизнеса 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates: 
    - Monthly and Semi-Annual Targeted, 16 \. 0 \. 9126 \. 2152 or higher
    - Semi-Annual и Deferred Channel, 16 \. 0 \. 8431 \. 2242 или более поздних
- Skype для бизнеса на Mac 16.15 или более высокой
- Skype для бизнеса для iOS и Android 6.19 или более высоких версий
- Комнаты Microsoft Teams (ранее известные как Система комнат Skype V2 SRS V2) 4.0.64.0 (декабрь 2018 г.) или более высокий
- Обновление Surface Hub для выпуска Team на основе KB4499162 (май 2019 г., сборка ОС 15063.1835) или более высокого уровня
- Skype Web App 2015 CU6 HF2 или более высокого уровня (включает сервер)

### <a name="currently-being-investigated"></a>В настоящее время ведется исследование

- Панель мониторинга качества вызовов (новая установка после отключения TLS 1.0, 1.1, см. ниже)*
 
### <a name="out-of-scope"></a>Вне области поддержки

Если не отмечено, следующие продукты не находятся в области применения TLS 1.0/1.1 и не будут работать в среде, где отключены TLS 1.0 и 1.1. Что это означает: если вы по-прежнему используете серверы или клиенты вне области, их необходимо обновить или удалить, если требуется отключить TLS 1.0/1.1 в локальном развертывании Skype для бизнеса Server.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 или более низкий
- Lync для Mac 2011
- Lync 2013 для мобильных устройств — iOS, iPad, Android или Windows Phone
- Клиент Магазина Windows Lync "MX"
- Система комнат Lync (т. е. SRSv1). Поддержка LRS была достигнута 9 октября 2018 г. и не будет обновлена для поддержки TLS 1.2.
- Все клиенты Lync 2010
- Lync Phone Edition — обновленное [руководство здесь.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)
- Устройство для survivable Branch Appliance (SBA) или SBS на основе 2013 г.
- Cloud Connector Edition (CCE)
- Skype для бизнеса для Windows Phone

### <a name="exceptions"></a>Exceptions

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 принимает зависимость от Windows Fabric версии 1.0.  На этапе разработки для Lync Server 2013 Windows Fabric 1.0 была выбрана для привлекательных и новых распределенных архитектур, чтобы обеспечить репликацию, высокую доступность и устойчивость к сбоям.  Со временем и Skype для бизнеса Server, и Windows Fabric значительно улучшили эту совместную архитектуру и значительно перепроектировали ее в последующих версиях.  Например, в skype для бизнеса 2015 Server используется Windows Fabric 3.0.

К сожалению, Windows Fabric 1.0 **не поддерживает TLS 1.2.  Однако мы будем обновлять Lync Server 2013 для работы с TLS 1.2.** Это будет в следующем накопительном обновлении для Lync Server 2013.  Мы предоставляем поддержку TLS 1.2 для обеспечения сосуществования, миграции, федерации и гибридных сценариев.

Если вашей организации требуется отключить TLS 1.0 и 1.1 и в настоящее время вы используете Lync Server 2013, рекомендуем начать процесс планирования с возможностью обновления на месте или переноса на месте (новые пулы, перемещение пользователей) в Skype для бизнеса Server 2015 или более новой.  Или вы можете ускорить миграцию в Skype для бизнеса Online.

#### <a name="call-quality-dashboard"></a>Панель мониторинга качества звонка

В настоящее время на локальной панели мониторинга качества вызовов во время новой установки (при первой установке в локальной среде) есть зависимость от TLS 1.0.  We are currently investigating this issue and plan to release a fix in the near future.  Если планируется установить CQD и отключить TLS 1.0, рекомендуется сначала завершить установку CQD, а затем продолжить отключение TLS 1.0.

#### <a name="skype-for-business-sdn-manager"></a>Skype для бизнеса SDN Manager

Диспетчер SDN Skype для бизнеса, SQL база данных зависит от TLS 1.0 во время новой установки. Если вы планируете установить Skype для бизнеса SDN Manager с помощью SQL базы данных, а также отключить TLS 1.0, рекомендуем сначала завершить диспетчер SDN Skype для бизнеса, а затем продолжить отключение TLS 1.0. Если перед установкой TLS 1.0 был отключен, необходимо временно включить TLS 1.0 на сервере SQL Server, который будет использоваться для SQL skype for Business SDN Manager.

#### <a name="third-party-devices"></a>Сторонние устройства

На сторонних устройствах, таких как телефоны 3PIP, видеоконференция, обратные прокси-прокси и балансиры нагрузки, обязательно проверьте возможность поддержки TLS 1.2, тщательно протестировать и при необходимости свяжитесь с поставщиком.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Вопросы федерации при отключке TLS 1.0/1.1 на серверах

Необходимо тщательно спланировать и учитывать влияние отключения TLS 1.0/1.1 на ваши серверы.  После отключения TLS 1.0 и 1.1 вы можете обнаружить, что другие организации больше не смогут федерации с вашей организацией.

Вы можете оставить TLS 1.0/1.1 включенным на ваших серверах, чтобы обеспечить обратную совместимость с внешними системами без исправлений (SfB 2015, Lync 2013) или более старыми (2010).

Корпорация Майкрософт не может предоставлять советы или рекомендации относительно того, относится ли ваша побративная сеть (или любая сеть) к стандарту PCI; определяется отдельной компанией.

В настоящее время Skype для бизнеса Online может использовать TLS 1.2, поэтому влияние на гибридную среду и федерацию с Online не ожидается.

Pic (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity;](../../deploy/deploy-skype-connectivity.md) Шлюзы Microsoft PIC уже имеют TLS 1.2.

## <a name="prerequisites-and-process"></a>Необходимые условия и процесс

За исключением случаев, когда TLS 1.0 и 1.1 отключены вне области действия серверов, клиенты и устройства будут работать должным образом или вообще. Это может означать, что вам нужно приостановить и дождаться обновленных рекомендаций от Корпорации Майкрософт. После того как вы будете удовлетворены всеми требованиями и запланируйте устранение пробелов, продолжите работу.

На высоком уровне, пока Skype для бизнеса Server 2019 готов к установке, Skype для бизнеса Server 2015 требует установки CU9, применения необходимых обновлений к .NET и SQL, развертывания необходимых разделов реестра и, наконец, отдельного круга обновлений конфигурации ОС (т. е. отключения TLS 1.0 и 1.1 с помощью импорта файлов реестра). Очень важно завершить установку всех необходимых условий, включая Skype для бизнеса Server 2015 CU6 HF2, перед отключением TLS 1.0 и 1.1 на любом сервере в вашей среде. Для каждого сервера Skype для бизнеса, включая роль SQL серверов, требуются обновления. Также убедитесь, что все поддерживаемые (в области) клиенты обновлены до требуемой минимальной версии. Не забудьте обновить и рабочие станции управления.

Мы хотим следовать обычному порядку операций "изнутри" для обновления серверов Skype для бизнеса. Пулы директоров, сохраняемая беседа и сопряженные пулы обрабатываются так же, как обычно. Порядок и методы обновления [здесь](topology.md) и [здесь.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)

### <a name="high-level-process"></a>Высокоуровневый процесс

1. Перед настройкой производственных серверов протестировать все действия в лаборатории.
2. Скопируйте и сохраните копию экспортируемого реестра на каждом отдельном сервере, который требуется обновить. Нельзя совместное управление реестрами между серверами; они содержат уникальные ключи на основе компьютера.
3. Обновим все серверы Skype для бизнеса 2015 до cu9 или более высокого уровня. Для Skype для бизнеса Server 2019 обновим до cu1 или более высокого уровня.
4. Установите все необходимые условия на все серверы.
5. Развернем необходимые ключи реестра.
6. Убедитесь, что обновлены все клиенты, которые находятся в области действия.
7. Отключать TLS 1.0 и 1.1 с помощью импорта реестра.
8. Проверьте правильность работы рабочих нагрузок.
    - Если возникают проблемы, устранять и устранять неполадки, а также
    - Восстановление реестра из шага 2, чтобы повторно включить TLS 1.0 и 1.1
9. Проверьте, используется ли только TLS 1.2.

### <a name="install-prerequisites-to-all-servers"></a>Установка необходимых условий на все серверы

Перед отключением TLS 1.0 и 1.1 на уровне операционной системы в развертываниях Skype для бизнеса Server 2015 требуется тщательное обновление зависимостей. Ниже следующую версию можно использовать для поддержки TLS 1.2. Перед отключением TLS 1.0 и 1.1 разверните все необходимые обновления на каждом сервере Skype для бизнеса в вашей среде.

- Skype для бизнеса Server 2015 CU9 6.0.9319.548 (май 2019 г.) или более высокий
- [.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) или выше с включенным в реестре SchUseStrongCrypto (см. ниже)
- SQL должны быть обновлены на всех серверах и серверах Skype для бизнеса 2015. Сначала обновим пул Enterprise Edition SQL, а затем соответствующие FES. 
    - [SQL Server 2014 с sp1 + CU5](https://support.microsoft.com/help/3130926), или выше / SQL Server 2012 с sp2 + CU16 или выше / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), или выше / SQL Server 2014 с sp2
     - [SQL Server Native Client для SQL Server 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher
     - [Общие объекты управления для SQL Server 2014 с sp2](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes для SQL Server 2014 с sp2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Основные действия по установке необходимых условий в рекомендуемом порядке операций

1. Установите обновление Skype для бизнеса Server CU9 на все серверы. 
    1. Установите обновление компонентов с помощью обновления.
    2. Обновление баз данных в соответствии с задокументированными процедурами. Для Skype для бизнеса Server 2015 см. KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. Проверьте функциональные возможности продукта в развертывании, прежде чем двигаться дальше с любыми другими изменениями.
2. Скачайте автономный установщик .NET 4.7. 
    1. Справка: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Убедитесь, что службы Skype для бизнеса Server 2015 остановлены на сервере переднего сервера.
    3. Справка: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition): ```Stop-CsWindowsService```
    5. Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    6. Запустите пакет установщика.
    7. Перезагрузите сервер.
3. Обновление SQL Express 2014 на всех серверах. 
    1. Справка: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Загрузка SQL 2014 с sp2 
        - Справка: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Скопируйте установщик в папку на сервере (например, C:\01_2014SqlSp2)
    4. Убедитесь, что службы Skype для бизнеса Server 2015 остановлены на сервере переднего сервера 
        - Ex (Standard Edition): ```Stop-CsWindowsService```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    5. Откройте командную подсказку администратора и обновим все установленные компоненты и экземпляры 
        - Пример: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances
4. Обновление SQL Native Client. 
    1. Справка: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .
    2. Скачать с [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Убедитесь, что службы Skype для бизнеса Server 2015 остановлены на сервере переднего сервера. 
        - Ex (Standard Edition): ```Stop-CsWindowsServices```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    4. Остановка SQL установленных экземпляров 
        - Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (только Standard Edition): ```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Установите обновление.
5. Обновив драйвер ODBC 11 для SQL Server включить поддержку TLS 1.2 (KB [3135244).](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    1. Скачайте [драйвер ODBC 11 для SQL Server Windows.](https://www.microsoft.com/download/confirmation.aspx?id=36434)
    2. Убедитесь, что службы Skype для бизнеса Server 2015 остановлены на сервере переднего сервера.
        - Пример (Standard Edition): ```Stop-CsWindowsService```
        - Пример (Enterprise Edition): ```Invoke-CsComputerFailover```
    3. Установите обновление.
6. Развернем необходимые ключи реестра.

### <a name="pre-requisite-registry-keys"></a>Необходимые ключи реестра

Скопируйте или в paste следующий тест в Блокноте и переименуйте TLSPreReq.reg или имя по вашему выбору, а затем импортируйте:

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

Для SQL для пулов Enterprise Edition предварительные условия и отключение TLS должны рассматриваться как любые SQL обновления ОС; обратитесь к: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Несмотря на то, что действия, необходимые для приложения и отключения TLS, можно объединить, мы настоятельно рекомендуем применить все предварительные условия, прежде чем при этом отключать TLS 1.0 и 1.1 на уровне операционной системы. Лучше всего подготовить среду путем развертывания всех необходимых условий, проверки правильности и правильности работы рабочих нагрузок, а затем позднее отключить TLS 1.0/1.1.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Отключение TLS 1.0 и 1.1 с помощью импорта реестра

Прежде чем приступить к следующим шагам, убедитесь, что выполнены все необходимые условия *и обновлены skype для бизнеса Servers.*

Скопируйте следующий текст в файл Блокнота и переименуйте **его TLSDisable.reg:**

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

Импортировать REG-файл на каждый сервер, для которых необходимо отключить TLS 1.0 и 1.1. Перезагрузите сервер. После того как службы снова будут в сети, переходить на следующий сервер. Подход к пулам Enterprise Edition тот же, что и для любого обновления ОС.

Вы могли заметить, что мы не просто отключаем TLS 1.0 и 1.1. Мы поддерживаем переупорядочение cipher Suite (как показано выше) и отключение некоторых старых слабых шифров. Это первый раз, когда мы официально поддерживаем эти изменения В SCHANNEL и Crypto API в Skype для бизнеса Server, и важно отметить, что эти изменения поддерживаются и протестированы в настоящее время. В будущем мы можем рассмотреть дополнительные конфигурации, но пока не изменяйте файл импорта реестра в вашей реализации.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Проверка правильной работы рабочих нагрузок

После отключения TLS 1.0 и 1.1 убедитесь, что все основные рабочие нагрузки работают должным образом, например мгновенные & Присутствия, вызовы P2P, Корпоративная голосовая связь и т. д.

**Проверка использования только TLS 1.2**

Ваша группа безопасности должна выполнить новый аудит трафика Skype для бизнеса, чтобы убедиться, что более старые протоколы TLS 1.0 и 1.1 больше не используются.

Кроме того, вы можете использовать Internet Explorer для тестирования подключений TLS к веб-службам из Skype для бизнеса Server 2015 после отключения TLS 1.0 и TLS 1.1.

1. Запустите Internet Explorer.
2. Выберите **"Инструменты:**  >  **интернет-параметры".**
3. Выберите **вкладку "Дополнительные".**
4. В **области "Параметры"** прокрутите страницу вниз.
5. Убедитесь, что включены TLS 1.0, TLS 1.1 и TLS 1.2.
6. Перейдите по URL-адресу внутренней веб-службы пула SfB 2015 (должно быть успешно подключено).
7. Вернуться в Internet Explorer и отключить параметр "Использовать **только TLS 1.2".**
8. Снова просмотрите URL-адрес внутренней веб-службы пула SfB 2015 (не удается подключиться).

![Параметры интернета](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Расширенные сценарии развертывания

Поскольку для поддержки TLS 1.2 в Skype для бизнеса Server 2015 требуются некоторые предварительные условия для зависимостей, установка с RTM-носителя не будет работать в любой системе, где отключены TLS 1.0 и 1.1.

**Развертывание новых серверов Standard Edition или пулов Enterprise Edition после отключения TLS 1.0 и 1.1 в среде.**

**Вариант 1:** Используйте [SmartSetup.](../../deploy/install/install-skype-for-business-server.md) Обратите внимание, что мы обновляем SmartSetup с учетом обновленных SQL в будущем cu, а в будущем обновим эту статью.

**Вариант 2:** Предварительная установка локальных SQL (RTCLOCAL и LYNCLOCAL)

1. Скачайте и скопируйте SQL Express 2014 SP2 (SQLEXPR_x64.exe) в локализованную папку на fe. Предположим, путь к папке <SQL_FOLDER_PATH>.
2. Запустите PowerShell или командную <SQL_FOLDER_PATH>.
3. Создайте экземпляр RTCLOCAL SQL с помощью приведенной ниже команды. Подождите, пока SQLEXPR_x64.exe завершится, прежде чем ировать:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati
1. Создайте экземпляр LYNCLOCAL SQL с помощью приведенной ниже команды. Дождись SQLEXPR_x64.exe завершения, прежде чем ступить к следующему шагу:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT ="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic
1. Запустите установку Skype для бизнеса Server 2015 RTM.
2. Выполните оставшиеся действия из раздела предварительных условий выше.

**Вариант 3:** Вы также можете вручную заменить binaries в локальном каталоге установщика мультимедиа следующим образом:

1. [Установка необходимых условий для Skype для бизнеса Server](../../deploy/install/install-prerequisites.md)  
2. Установите .NET 4.7: 
      - **Примечание.** Мы впервые представили поддержку .NET 4.7 в Skype для бизнеса Server 2015 CU5 (6.0.9319.281). Поэтому на последующих шагах ниже мы обновим основные компоненты перед основной установкой.
      - Скачать: https://www.microsoft.com/download/details.aspx?id=55167 . 
      - Справка. [Программное обеспечение, которое должно быть установлено перед развертыванием Skype для бизнеса Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Копирование ISO-файлов и папок: 
    - При присоединении ISO-файла Skype для бизнеса Server 2015 откройте корневой каталог диска, вложенного в него (например, D: \) в проводнике.
    - Скопируйте все папки и файлы в папку на локальном диске (например, C:\SkypeForBusiness2015ISO).
    - **Примечание.** Перед установкой компонентов необходимо обновить некоторые файлы для поддержки TLS 1.2.
4. Замените пакеты MSI/EXE: 
    - Замените существующие пакеты MSI и EXE в папке /Setup/amd64/ установщика на локальном компьютере.
    - SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167 
        - Переименуем SQLEXPR_x64 на локальном компьютере и замените существующий файл в папке Setup/amd64/ установщика.
    - SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402 
        - **Примечание.** При необходимости переименуем его, чтобы sqlncli.msi, а затем замените существующий файл, существующий в папке Setup/amd64/ установщика.
    - SQL объектов управления: https://www.microsoft.com/download/details.aspx?id=53164 
        - **Примечание.** Пакет функций будет иметь множество элементов, которые можно скачать. Выберите для скачивания только SharedManagementObjects.msi.
        - **Примечание.** Замените существующий файл, существующий в папке Setup/amd64/ установщика.
    - SQL CLR: https://www.microsoft.com/download/details.aspx?id=53164 
        - **Примечание.** Пакет функций будет иметь множество элементов, которые можно скачать. Выберите для скачивания только CQLSysClrTypes.msi
        - **Примечание.** Замените существующий файл, существующий в папке Setup/amd64/ установщика.
5. Установите основные компоненты: 
    - Запустите Setup.exe из папки Setup/amd64/ установщика. Следуйте инструкциям по установке основных компонентов
    - Закроем основные компоненты.
6. Обновление основных компонентов: 
    - Скачайте установщик обновлений Skype для бизнеса.
    - Запустите установщик, чтобы обновить основные компоненты и установить счетчики производительности.
    - **Примечание.** В выпуске CU6HF2 функция автоматического обновления в настоящее время устанавливается только до CU6. Поэтому обновление необходимо запустить отдельно для обновления основных компонентов до версии 6.0.9319.516.
    - Справка: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. Установка средств администрирования (необязательно): 
    - Будет устанавливаться клиент Microsoft SQL Server 2012 Native Client, объекты управления SQL Server 2014 (x64) и типы CLR системы Microsoft System для SQL Server 2014 (x64) с использованием обновленных файлов. Кроме того, построитель топологий и панель управления Skype для бизнеса Server 2015 будут доступны на локальном компьютере.
8. Установка локального магазина конфигурации (шаг 1): 
     - Откройте мастер развертывания, щелкните "Установить или обновить систему  Skype для бизнеса Server" и выберите "Выполнить на шаге 1. Установка локального магазина конфигурации".
     - Нажмите **кнопку** "Далее" в диалоговом окне "Установка **локального магазина** конфигураций".
     ![Диалоговое окно "Установка локального магазина конфигураций"](../../media/local-configuration-store.png)
     - Просмотрите результаты и убедитесь, что состояние задачи завершено. Просмотрите итоговую папку журнала, щелкнув **"Просмотреть журнал".**
     ![Состояние задачи показывается как Завершено](../../media/local-configuration-task-completed.png)
     - Нажмите кнопку **Готово**.
9. Настройка или удаление компонентов Skype для бизнеса Server (шаг 2):
    - Откройте мастер развертывания, щелкните "Установить или обновить  систему Skype для бизнеса **Server"** и выберите "Выполнить на шаге 2. Настройка или удаление компонентов Skype для бизнеса Server"
    - Нажмите **кнопку** "Далее" в диалоговом окне "Настройка компонентов Skype для бизнеса Server".
    ![Окно "Настройка компонентов Skype для бизнеса Server"](../../media/set-up-skype-for-business-server-components-window.png)
    - Просмотрите журнал с помощью журнала просмотра и проверьте, что установка завершена без проблем. 
    - Нажмите кнопку **Готово**.
10. При необходимости продолжите дополнительную установку и настройку (на этом этапе можно возобновить обычные процедуры установки).
