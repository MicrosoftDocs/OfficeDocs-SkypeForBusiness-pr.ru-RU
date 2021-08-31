---
title: Отключение TLS 1.0/1.1 в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: Подготовка и реализация отключения TLS 1.0 и 1.1 в средах.
ms.openlocfilehash: 93ebf65101cd3e8ddc36a3a17e945035ad770d49
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731468"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Отключение TLS 1.0/1.1 в Skype для бизнеса Server 2015 г.

В этой статье вы можете подготовиться и реализовать отключение TLS 1.0 и 1.1 в средах. Этот процесс требует тщательного планирования и подготовки. Внимательно просмотрите все сведения в этой статье при планировании отключения TLS 1.0 и 1.1 для организации. Существует множество внешних зависимостей и условий подключения, на которые может повлиять отключение TLS 1.0/1.1, поэтому необходимо тщательное планирование и тестирование.

- [Фон и область](#background-and-scope)
- [Необходимые условия и процесс](#prerequisites-and-process)
- [Расширенные сценарии развертывания](#advanced-deployment-scenarios)

## <a name="background-and-scope"></a>Фон и область

Основными драйверами для предоставления TLS 1.0 и 1.1 отключения поддержки для Skype для бизнеса Server локальной службы являются Совет по стандартам безопасности индустрии платежных карт (PCI) и требования к федеральным стандартам обработки информации. Дополнительные сведения о требованиях PCI можно найти [здесь.](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)  Корпорация Майкрософт не может предоставить рекомендации о том, требуется ли вашей организации придерживаться этих или других требований. Необходимо определить, требуется ли отключить TLS 1.0 и/или 1.1 в средах.

Корпорация Майкрософт подготовила белый [](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)документ по TLS, доступный здесь, и мы также рекомендуем фоновое чтение, доступное в этом Exchange [блоге](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).

## <a name="supportability-scope"></a>Область поддержки

*Область* относится к границам поддержки. *Полное тестирование и* поддержка означает, что мы полностью поддерживаем и протестировали отключение TLS 1.0 и 1.1 для перечисленных версий продукта. *В настоящее время ведется расследование* означает именно это; мы активно исследуем возможность применения этих продуктов в области поддержки отключения TLS. *Выход из области* означает, что эти версии продуктов не поддерживают отключение TLS 1.0 или 1.1 и не будут работать, за указанными исключениями.

### <a name="fully-tested-and-supported-servers"></a>Полностью протестированная и поддерживаемая серверы

- Skype для бизнеса Server 2019 cu1 17.0.2046.123 (июнь 2019 г.) или выше
- Skype для бизнеса Server 2015 cu9 6.0.9319.548 (май 2019 г.) или выше на Windows Server 2012 (с обновлением KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или замеса), 2012 R2 или 2016.
- На месте обновлено Skype для бизнеса Server 2015 г., с cu9 6.0.9319.548 (май 2019 г.) или более высокой на Windows Server 2008 R2, 2012 г. (с обновлением KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) или с замеса) или R2 2012 г.
- Exchange Подключение и Outlook Web App с Exchange Server 2010 SP3 RU19 или выше, руководство [здесь](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Уцелевшие устройства филиала (SBA) с Skype для бизнеса Server 2015 CU6 HF2 или выше (подтвердите у поставщика, что они упаковал соответствующие обновления и были доступны для вашего устройства)
- Выживший сервер филиалов (SBS) с Skype для бизнеса Server 2015 CU6 HF2 или выше
- Lync Server 2013 **Edge Role Only**, это потому, что роль Edge не имеет зависимости Windows Fabric 1.0.

### <a name="fully-tested-and-supported-clients"></a>Полностью протестированная и поддерживаемая клиенты

- Lync 2013 (Skype для бизнеса) Настольный клиент, MSI и C2R, включая Базовые [15.0.5023.1000 или более](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Skype для бизнеса 2016 настольный клиент MSI [16.0.4678.1000](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)или выше, включая Basic
- Skype для бизнеса 2016 нажмите кнопку Выполнить Требуй обновлений за апрель [2018](/officeupdates/release-notes-office365-proplus) г.: 
    - Ежемесячные и Semi-Annual, 16 \. 0 \. 9126 \. 2152 или более
    - Semi-Annual и отложенный канал, 16 \. 0 \. 8431 \. 2242 или более
- Skype для бизнеса Mac 16.15 или выше
- Skype для бизнеса для iOS и Android 6.19 или выше
- Комнаты Microsoft Teams (ранее Skype система номеров V2 SRS V2) 4.0.64.0 (декабрь 2018 г.) или выше
- Surface Hub версии Team на основе KB4499162 (май 2019 г., сборка ОС 15063.1835) или выше
- Skype Веб-приложение 2015 CU6 HF2 или выше (корабли с сервером)

### <a name="currently-being-investigated"></a>В настоящее время проводится расследование

- Панель мониторинга качества вызовов (новая установка после отключения TLS 1.0, 1.1 см. ниже)*
 
### <a name="out-of-scope"></a>Вне области поддержки

Кроме отмеченных, следующие продукты не находятся в области поддержки отключения TLS 1.0/1.1 и не будут работать в среде, в которой отключены TLS 1.0 и 1.1. Это означает, что если вы по-прежнему используете серверы или клиенты, которые по-прежнему используются вне области, их необходимо обновить или удалить, если требуется отключить TLS 1.0/1.1 в любом месте развертывания Skype для бизнеса Server локальном развертывании.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 или более низкий
- Lync для Mac 2011
- Lync 2013 для Mobile — iOS, iPad, Android или Windows Phone
- Клиент Lync "MX" Windows Store
- Lync Room System (a.k.a. SRSv1). LRS достигла конца поддержки 9 октября 2018 г. и не будет обновляться для поддержки TLS 1.2.
- Все клиенты Lync 2010
- Lync Телефон Edition — обновленное руководство [здесь](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- 2013 на основе сохранившихся ветвейных устройств (SBA) или выживаемого сервера филиала (SBS)
- Cloud Connector Edition (CCE)
- Skype для бизнеса на Windows Phone

### <a name="exceptions"></a>Исключения

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 зависит от Windows Fabric версии 1.0.  На этапе разработки Lync Server 2013 Windows Fabric 1.0 была выбрана для его убедительной и новой распределенной архитектуры для обеспечения репликации, высокой доступности и допуска неисправностей.  Со временем Skype для бизнеса Server и Windows Fabric значительно улучшили эту совместную архитектуру с существенным перепроектом в последующих версиях.  Например, Skype для бизнеса 2015 server использует Windows Fabric 3.0.

К сожалению, Windows Fabric 1.0 **не поддерживает TLS 1.2.  Тем не менее, мы будем обновлять Lync Server 2013 для работы с TLS 1.2**. Это будет в следующем накопительном обновлении для Lync Server 2013.  Мы предоставляем поддержку TLS 1.2 для обеспечения совместной жизни, миграции, федерации и гибридных сценариев.

Если вашей организации требуется отключить TLS 1.0 и 1.1, а вы в настоящее время используете Lync Server 2013, рекомендуем приступить к планированию с возможностью переноса обновления на месте или переноса (новые пулы, перемещение пользователей) в Skype для бизнеса Server 2015 или более.  Или вы можете ускорить миграцию до Skype для бизнеса Online.

#### <a name="call-quality-dashboard"></a>Панель мониторинга качества звонка

Панель мониторинга качества вызовов локального вызова в настоящее время имеет зависимость от TLS 1.0 во время новой установки (при первой установке в локальной среде).  В настоящее время мы исследуем эту проблему и планируем выпустить исправление в ближайшем будущем.  Если планируется установить CQD, а также отключить TLS 1.0, рекомендуется сначала завершить установку CQD, а затем приступить к отключению TLS 1.0.

#### <a name="skype-for-business-sdn-manager"></a>Skype для бизнеса Диспетчер SDN

Skype для бизнеса Диспетчер SDN с SQL базы данных имеет зависимость от TLS 1.0 при новой установке. Если вы планируете установить Skype для бизнеса SDN Manager с помощью SQL базы данных, а также отключить TLS 1.0, рекомендуется сначала выполнить Skype для бизнеса SDN Manager, а затем приступить к отключению TLS 1.0. В случае отключения TLS 1.0 до установки необходимо временно включить TLS 1.0 в SQL Server сервере, который будет использоваться для Skype для бизнеса базы данных SDN Manager SQL.

#### <a name="third-party-devices"></a>Сторонние устройства

На сторонних устройствах, таких как телефоны 3PIP, видеоконференциалы, обратные прокси-службы и балансиры нагрузки, убедитесь, что они могут поддерживать TLS 1.2, тщательно протестировать и при необходимости обратиться к поставщику.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Соображения Федерации при отключении TLS 1.0/1.1 на edge-серверах

Необходимо тщательно планировать и учитывать влияние отключения TLS 1.0/1.1 на серверы Edge.  После отключения TLS 1.0 и 1.1 вы можете обнаружить, что другие организации больше не смогут федератироваться с вашей организацией.

Для поддержания обратной совместимости с не исправленными (SfB 2015, Lync 2013) или более старыми (2010) внешними системами может быть включено TLS 1.0/1.1.

Корпорация Майкрософт не может предоставить советы или рекомендации относительно того, относится ли ваша сеть Edge (или к какой-либо сети) к стандарту PCI; которые должны определяться отдельной компанией.

Skype для бизнеса Он-лайн способен TLS 1.2 сегодня, поэтому никакого влияния на гибридную и федерацию с Online не ожидается.

Pic (Public Im Connectivity) для службы Skype: Мы не ожидаем отключения TLS 1.0/1.1 для Skype [подключения;](../../deploy/deploy-skype-connectivity.md) Шлюзы MICROSOFT PIC уже способны к TLS 1.2.

## <a name="prerequisites-and-process"></a>Необходимые условия и процесс

Кроме случаев, когда отмечено выше, после отключения серверов TLS 1.0 и 1.1 клиенты и устройства будут работать должным образом или вообще. Это может означать, что необходимо приостановить и дождаться обновленных указаний от Корпорации Майкрософт. После того как вы будете удовлетворены тем, что вы соответствуете всем требованиям и имеете план устранения пробелов, продолжайте.

На высоком уровне, в то время как Skype для бизнеса Server 2019 г. готов к процедуре при установке, Skype для бизнеса Server 2015 г. потребуется установить CU9, применяя предварительные обновления к .NET и SQL, развертывание ключей реестра предварительных условий и, наконец, отдельный раунд обновлений конфигурации ОС (например, отключение TLS 1.0 и 1.1 с помощью импорта файлов реестра). Крайне важно завершить установку всех необходимых условий, включая Skype для бизнеса Server 2015 ГФ2 CU6, до отключения TLS 1.0 и 1.1 на любом сервере в вашей среде. Каждый Skype для бизнеса сервер, включая роль Edge и SQL backends, требует обновлений. Кроме того, убедитесь, что все поддерживаемые (в области) клиенты были обновлены до необходимых минимальных версий. Не забудьте также обновить рабочие станции управления.

Мы хотим следовать обычному порядку операций "наизнано" для обновления Skype для бизнеса серверов. Относитесь к пулам Director, сохраняемой беседе и парным пулам таким же образом, как обычно. Порядок и методы обновления здесь [и](topology.md) [здесь.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)

### <a name="high-level-process"></a>Процесс высокого уровня

1. Проверьте все действия в лаборатории перед настройкой производственных серверов.
2. Копирование и сохранение копии экспортируемого реестра на каждом отдельном сервере, который будет обновляться. Вы не можете обмениваться реестрами между серверами; они содержат уникальные клавиши на основе машин.
3. Обновление всех Skype для бизнеса серверов 2015 г. до уровня CU9 или выше. В Skype для бизнеса Server 2019 г. обновление до уровня CU1 или выше.
4. Установите все необходимые условия на все серверы.
5. Развертывание необходимых ключей реестра.
6. Убедитесь, что все клиенты в области обновляются.
7. Отключить TLS 1.0 и 1.1 с помощью импорта реестра.
8. Проверка того, что рабочие нагрузки функционируют так, как ожидалось.
    - Если возникают проблемы, устранение и устранение неполадок или
    - Восстановление реестра со 2-й ступени для повторного включить TLS 1.0 и 1.1
9. Проверьте, используется ли только TLS 1.2.

### <a name="install-prerequisites-to-all-servers"></a>Установка необходимых условий для всех серверов

Перед отключением TLS 1.0 и 1.1 на уровне операционной системы в развертываниях 2015 Skype для бизнеса Server требуется масштабное обновление зависимости. Ниже приводится минимум версий, которые могут поддерживать TLS 1.2. Перед отключением TLS 1.0 и 1.1 развертывайте все необходимые обновления на каждом сервере Skype для бизнеса среды.

- Skype для бизнеса Server 2015 cu9 6.0.9319.548 (май 2019 г.) или выше
- [платформа .NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) или выше с включенной в реестр SchUseStrongCrypto (приведено ниже)
- SQL должны быть обновлены на всех серверах и Skype для бизнеса 2015 года. Сначала выпуск Enterprise пул SQL, а затем соответствующие FEs. 
    - [SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), или выше / SQL Server 2012 SP2 + CU16 или выше / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), или выше / SQL Server 2014 SP2
     - [SQL Server Native Client за SQL Server 2012 г.](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Драйвер Microsoft ODBC 11 для SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)или выше
     - [Общие объекты управления для SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes для SQL 2014 SP2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Основные действия по установке предварительных условий в рекомендуемом порядке операций

1. Установите обновление Skype для бизнеса Server CU9 на все серверы. 
    1. Установите обновление на компоненты с помощью обновления.
    2. Обновление баз данных в соответствии с задокументированными процедурами. За Skype для бизнеса Server 2015 г. см. в [3061064.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    3. Проверка функциональных возможностей продукта в развертывании до перехода к любым другим изменениям.
2. Скачайте автономный установщик .NET 4.7. 
    1. Справочные материалы: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Убедитесь Skype для бизнеса Server что службы 2015 года остановлены на переднем сервере.
    3. Справочные материалы: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (выпуск Standard):```Stop-CsWindowsService```
    5. Ex (выпуск Enterprise):```Invoke-CsComputerFailover```
    6. Запустите пакет установщика.
    7. Перезагрузите сервер.
3. Обновление SQL Express 2014 на всех серверах. 
    1. Справочные материалы: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Загрузка SQL 2014 SP2 
        - Справочные материалы: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Скопируйте носителя установки в папку на сервере (Ex: C:\01_2014SqlSp2)
    4. Убедитесь Skype для бизнеса Server что службы 2015 года остановлены на сервере переднего конца 
        - Ex (выпуск Standard):```Stop-CsWindowsService```
        - Ex (выпуск Enterprise):```Invoke-CsComputerFailover```
    5. Откройте командный запрос администратора и обновим все установленные компоненты и экземпляры 
        - Пример: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances
4. Обновление SQL Native Client. 
    1. Справка. [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .
    2. Загрузка из [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Убедитесь Skype для бизнеса Server что службы 2015 года остановлены на сервере переднего конца. 
        - Ex (выпуск Standard):```Stop-CsWindowsServices```
        - Ex (выпуск Enterprise):```Invoke-CsComputerFailover```
    4. Остановка SQL установленных экземпляров 
        - Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (выпуск Standard только):```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Установите обновление.
5. Обновление драйвера ODBC 11 для SQL Server включить поддержку TLS 1.2 (KB [3135244).](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    1. Скачайте [драйвер ODBC 11 для SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).
    2. Убедитесь Skype для бизнеса Server что службы 2015 года остановлены на переднем сервере.
        - Пример (выпуск Standard):```Stop-CsWindowsService```
        - Пример (выпуск Enterprise):```Invoke-CsComputerFailover```
    3. Установите обновление.
6. Развертывание необходимых ключей реестра.

### <a name="pre-requisite-registry-keys"></a>Клавиши предварительного реестра

Скопируйте или вклейте следующий тест в Блокнот и переименуйте TLSPreReq.reg или имя по вашему выбору, а затем импортируйте:

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

Для SQL для выпуск Enterprise пулов необходимо рассматривать предварительные условия и отключение TLS как любые SQL или обновления ОС; обратитесь к:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](./patch-or-update-a-back-end-or-standard-edition-server.md)

Хотя необходимое приложение и действия по отключению TLS можно объединить, мы настоятельно рекомендуем применять все необходимые условия перед началом работы с отключением TLS 1.0 и 1.1 на уровне операционной системы. Оптимальный подход заключается в подготовке среды путем развертывания всех необходимых условий, проверки правильности и правильности всех рабочих нагрузок, а затем отключения TLS 1.0/1.1 в более позднее время.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Отключение TLS 1.0 и 1.1 с помощью импорта реестра

Прежде чем приступить к следующим шагам, убедитесь, что вы выполнили все необходимые условия и *обновили Skype для бизнеса Серверы*.

Скопируйте следующий текст в Блокнот и переименуйте **его в TLSDisable.reg:**

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

Импорт файла .reg на каждом сервере, который необходимо отключить TLS 1.0 и 1.1. Перезагрузите сервер. После того как службы вернулись в режиме онлайн, переехав на следующий сервер. Подход для выпуск Enterprise пулов тот же, что и для любого обновления ОС.

Возможно, вы заметили, что мы делаем больше, чем просто отключение TLS 1.0 и 1.1 здесь. Мы поддерживаем повторное заказ cipher Suite (как показано выше) и отключение некоторых старых слабых шифров. Мы впервые официально поддерживаем эти изменения в API SCHANNEL и Crypto на Skype для бизнеса Server, и важно отметить, что эти изменения являются единственными, которые мы поддерживаем и протестировали в настоящее время. Мы можем рассмотреть дополнительные конфигурации в будущем, но пока, пожалуйста, не измените файл импорта реестра в реализации.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Проверка того, что рабочие нагрузки функционируют так, как ожидалось

После отключения TLS 1.0 и 1.1 в вашей среде убедитесь, что все основные рабочие нагрузки будут работать так, как ожидалось, такие как присутствие в чате &, вызовы P2P, Корпоративная голосовая связь и т.д.

**Проверка использования только TLS 1.2**

Чтобы убедиться, что старые протоколы TLS 1.0 и 1.1 больше не используются, группа безопасности выполнит новый аудит трафика Skype для бизнеса, чтобы убедиться, что старые протоколы TLS 1.0 и 1.1 больше не используются.

Кроме того, можно использовать Internet Explorer для тестирования подключений TLS к веб-службам с Skype для бизнеса Server 2015 г. после отключения TLS 1.0 и TLS 1.1.

1. Запуск Internet Explorer.
2. Выберите **Параметры**  >  **Интернета Средства**.
3. Выберите вкладку **Дополнительно**.
4. В **Параметры** прокрутите вниз.
5. Убедитесь, что включены TLS 1.0, TLS 1.1 и TLS 1.2.
6. Просмотрите URL-адрес внутренней веб-службы пула SfB 2015 (должен успешно подключиться).
7. Возвращайтесь в Internet Explorer и отключайте параметр **только для использования TLS 1.2.**
8. Снова просмотрите URL-адрес внутренней веб-службы пула SfB 2015 (если не удастся подключиться).

![Параметры Интернета.](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Расширенные сценарии развертывания

Так как для поддержки TLS 1.2 в Skype для бизнеса Server 2015 г. необходимы некоторые обязательные условия для зависимостей, установка из RTM-мультимедиа не будет работать в любой системе, где отключены TLS 1.0 и 1.1.

**Развертывание новых выпуск Standard или выпуск Enterprise пулов после отключения TLS 1.0 и 1.1 в среде.**

**Вариант 1:** Используйте [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Обратите внимание, что мы обновляем SmartSetup для размещения обновленных SQL в будущем ТС, а в будущем обновим эту статью.

**Вариант 2:** Предварительная установка локальных экземпляров SQL (RTCLOCAL и LYNCLOCAL)

1. Скачайте и скопируйте SQL Express 2014 SP2 (SQLEXPR_x64.exe) в локализованную папку fe. Допустим, путь папки <SQL_FOLDER_PATH>.
2. Запустите PowerShell или командную подсказку и перейдите <SQL_FOLDER_PATH>.
3. Создайте экземпляр RTCLOCAL SQL, запуская команду ниже. Подождите, SQLEXPR_x64.exe закончится перед началом.

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install=FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL/TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati
1. Создайте экземпляр LYNCLOCAL SQL, запуская команду ниже. Подождите, SQLEXPR_x64.exe завершится, прежде чем приступить к следующему шагу:

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install=FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL/TCPENABLED=1 /SQLSVCACCOUNT ="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic
1. Запуск Skype для бизнеса Server RTM 2015.
2. Следуйте оставшимся шагам из раздела предварительных условий выше.

**Вариант 3:** Кроме того, можно вручную заменить бинарии в локальном каталоге мультимедиа установки следующим образом:

1. [Установка необходимых условий для Skype для бизнеса Server](../../deploy/install/install-prerequisites.md)  
2. Установка .NET 4.7: 
      - **Примечание:** Впервые мы представили поддержку .NET 4.7 в Skype для бизнеса Server 2015 cu5 (6.0.9319.281). Таким образом, в последующих шагах ниже мы будем обновлять основные компоненты до основной установки.
      - Скачать: https://www.microsoft.com/download/details.aspx?id=55167 . 
      - Справка. Программное обеспечение, которое должно быть установлено перед [развертыванием Skype для бизнеса Server 2015 г.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Копирование файлов ISO/папок: 
    - При присоединении Skype для бизнеса Server 2015 isO откройте корневой каталог диска, который он присоединен как (Ex: D: \) in File Explorer).
    - Скопируйте все папки и файлы в папку на локальном диске (Ex: C:\SkypeForBusiness2015ISO).
    - **Примечание:** Перед установкой компонентов необходимо обновить некоторые файлы для поддержки TLS 1.2.
4. Замените пакеты MSI/EXE: 
    - Замените существующие пакеты MSI и EXE в папке установки/amd64/на локальной машине.
    - SQL 2014 SP2 Express:https://www.microsoft.com/download/details.aspx?id=53167 
        - Переименовать SQLEXPR_x64 на локальном компьютере и заменить существующий файл в папке Установки/amd64/средства установки.
    - SQL Native Client:https://www.microsoft.com/download/details.aspx?id=50402 
        - **Примечание:** Переименуй это, sqlncli.msi, а затем замените существующий файл, существующий в папке Setup/amd64/of the installation media.
    - SQL Объекты управления:https://www.microsoft.com/download/details.aspx?id=53164 
        - **Примечание:** Пакет функций будет иметь множество элементов, которые можно скачать. Выберите для загрузки SharedManagementObjects.msi только.
        - **Примечание:** Замените существующий файл, существующий в папке установки/amd64/.
    - SQL Типы CLR:https://www.microsoft.com/download/details.aspx?id=53164 
        - **Примечание:** Пакет функций будет иметь множество элементов, которые можно скачать. Выберите для загрузки CQLSysClrTypes.msi только
        - **Примечание.** Замените существующий файл, существующий в папке установки/amd64/.
5. Установка основных компонентов: 
    - Запустите Setup.exe из папки Установки/amd64/средства установки. Следуйте инструкциям по установке основных компонентов
    - Закрыть основные компоненты.
6. Обновление основных компонентов: 
    - Скачайте Skype для бизнеса установщик обновления.
    - Запустите установщик, чтобы обновить основные компоненты и установить счетчики производительности.
    - **Примечание:** С выпуском CU6HF2 функция автоматического обновления в настоящее время устанавливается только до CU6. Поэтому для обновления основных компонентов до 6.0.9319.516 необходимо запустить отдельно.
    - Справка: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. Установка средств администрирования (необязательный): 
    - Это установит Microsoft SQL Server 2012 родной клиент, объекты управления SQL Server 2014 (x64) и типы CLR системы Майкрософт для SQL Server 2014 (x64) с помощью обновленных файлов. Кроме того, панель Skype для бизнеса Server топологии 2015 г. будет доступна на локальной машине.
8. Установка локального магазина конфигурации (шаг 1): 
     - Откройте мастер развертывания, нажмите кнопку Установить или обновить Skype для бизнеса Server и нажмите кнопку **Выполнить** на шаге 1: Установка локального магазина конфигурации.
     - Нажмите **кнопку Далее** в диалоговом окне **Install Local Configuration Store.**
     ![Установите диалоговое окно Локального магазина конфигурации.](../../media/local-configuration-store.png)
     - Просмотрите результаты и убедитесь, что состояние задачи завершено. Просмотрите результативный файл журнала, нажав **журнал Представления**.
     ![Состояние задачи показывается как Завершено.](../../media/local-configuration-task-completed.png)
     - Нажмите кнопку **Готово**.
9. Настройка или удаление Skype для бизнеса Server компонентов (шаг 2):
    - Откройте мастер развертывания, щелкните Установите или **Skype для бизнеса Server систему** и нажмите кнопку **Выполнить** на шаге 2: Настройка или удаление Skype для бизнеса Server компонентов
    - Нажмите **кнопку Далее** в диалоговом окне Настройка Skype для бизнеса Server компонентов.
    ![окно Настройка Skype для бизнеса Server компонентов.](../../media/set-up-skype-for-business-server-components-window.png)
    - Просмотрите журнал с помощью журнала View Log и проверьте, завершена ли установка без проблем. 
    - Нажмите кнопку **Готово**.
10. Приступить к дополнительной установке и конфигурации по мере необходимости (на данном этапе можно возобновить обычные процедуры установки).