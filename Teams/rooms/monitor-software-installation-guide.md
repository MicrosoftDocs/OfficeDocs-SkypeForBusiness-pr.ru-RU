---
title: Комнаты Microsoft Teams установки программного обеспечения
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Перенаправка Комнаты Teams в управляемые службы
f1keywords: ''
ms.openlocfilehash: 70209bcd60740f1d1e19b45b215b921396a6f0fd
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767563"
---
# <a name="monitor-device-software-installation"></a>Мониторинг установки программного обеспечения устройства

Для развертывания требуется, чтобы Комнаты Microsoft Teams устройства в Комнаты Microsoft Teams управляемых служб. Агент службы мониторинга используется с сертифицированными системами Microsoft Teams MTR и периферийными устройствами.

## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>Выполнение операций в качестве администратора устройства MTR

Для некоторых процедур настройки и установки требуется войти на устройство в качестве администратора.

Чтобы войти на устройство в качестве администратора (локальный администратор):

1. Убедитесь, что вы вешаете трубку на все текущие звонки и возвращаетесь на домашний экран.
1. В пользовательском интерфейсе Microsoft Teams комнаты выберите Еще **,** а затем выберите **Параметры**, где вам будет предложено вводить пароль локального администратора на устройстве (по умолчанию пароль **_sfb)._**
1. Выберите **Параметры**, а **затем** выберите Windows Параметры, чтобы получить доступ Windows в качестве локального администратора.  

1. В списке пользователей, отображаемом на экране Windows входа, выберите Администратор **(или** соответствующий локальный администратор вашего устройства).

> [!NOTE]
> Если компьютер является *доменом,* выберите Другой пользователь **,** затем используйте **.\admin** или имя пользователя локального администратора, настроенного на устройстве в качестве имени пользователя.  

Чтобы вернуться в приложение Microsoft Teams Комнаты после выполнения необходимых административных задач:

1. В Windows ***меню*** выйти из учетной записи администратора.
1. Вернись Microsoft Teams комнату, выбрав значок учетной записи пользователя в левой части экрана и выбрав Skype **.**

> [!NOTE]
> Если Skype нет в списке, выберите Другой пользователь, введите в качестве имени пользователя ***.\skype*** и войдите в нее.

## <a name="prerequisites"></a>Необходимые компоненты

Выполните эти процедуры, чтобы настроить оборудование перед процессом регистрации:

### <a name="adding-proxy-settings-optional"></a>Добавление параметров прокси-сервера (необязательно)

1. Войдите в систему от имени администратора, выполив действия в качестве администратора устройства [MTR.](#performing-operations-as-the-admin-user-of-the-mtr-device)
1. В поле Windows ***Поле** Search _ (нижний левый раздел экрана) введите _ *cmd** (длинное нажатие экрана или выбор вправо и выбор запуска от **_администратора)._**  
1. Выполнить следующую команду (важны двойные кавычка в конце команды):
   - При использовании одного ***прокси-сервера:*** bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL \_ PROXY : <proxyserver> <port> ""

      *Пример:* bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL \_ PROXY contosoproxy.corp.net:8080 ""
      

   - При использовании ***PAC-файла:*** bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url> ""

      
      *Пример:* bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT `http://contosoproxy.corp.net/proxy.pac` ""
      

### <a name="enabling-tpm-settings"></a>Включение параметров TPM

Если TPM на устройстве Intel NUC отключен, включите TPM на этих устройствах следующим образом:  

1. Подключите клавиатуру к nuc-устройству.  
1. Перезапустите устройство.  
1. Чтобы отобразить экран БИОН, быстро нажмите **F2.**  
1. Выберите **Дополнительные**.  
1. Выберите **Безопасность**.  
1. В правой части справа от справа в области "Функции безопасности" в включить **технологию Intel Platform Trust Technology.**  
1. Чтобы сохранить параметры, нажмите **F10**.  
1. В окне подтверждения выберите **Да**.  

## <a name="urls-required-for-communication"></a>URL-адреса, необходимые для связи

 > [!NOTE]
 > Весь сетевой трафик между агентом устройств MTR и службой Комнаты Microsoft Teams — портал службы Managed Services — SSL через порт 443.  См. [Office 365 URL-адреса и диапазоны IP-адресов — Microsoft 365 корпоративный | Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

Если в корпоративной среде  включен список разрешенных трафика, должны быть разрешены следующие hosts:

agent.rooms.microsoft.com<br>
global.azure-devices-provisioning.net<br>
gj3ftstorage.blob.core.windows.net<br>
iothubsgagwt5wgvwg6.azure-devices.net<br>
blobssgagwt5wgvwg6.blob.core.windows.net<br>
mmrstgnoamiot.azure-devices.net<br>
mmrstgnoamstor.blob.core.windows.net<br>
mmrprodapaciot.azure-devices.net<br>
mmrprodapacstor.blob.core.windows.net<br>
mmrprodemeaiot.azure-devices.net<br>
mmrprodemeastor.blob.core.windows.net<br>
mmrprodnoamiot.azure-devices.net<br>
mmrprodnoamstor.blob.core.windows.net

## <a name="process"></a>Процесс

Процесс регистрации включает в себя несколько этапов.  

1. На левой панели навигации Комнаты Microsoft Teams — портал управляемых служб , разбей [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/) Параметры и выберите  **Общие**.  
1. В *области Ключи для самостоятельной регистрации* выберите **Скачать** гиперссылки установщика, чтобы скачать программное обеспечение https://aka.ms/serviceportalagentmsi агента мониторинга.
1. Выберите **Скачать ключ**. Поместите файл ключа в **папку C:\Изюмина** на каждом устройстве, которое вы регистр хотите зарегистрировать.  
1. **Дополнительные:** Настройка параметров прокси-сервера для агента; См. [добавление параметров прокси-сервера (необязательно).](#adding-proxy-settings-optional)
1. Установите установщик агента (скачавший на шаге 2) на блоках MTR, задав MSI-файл локально на MTR-устройстве или с помощью обычного средства массовой публикации MSI-приложений на устройствах в вашей среде (групповая политика и т. д.).  
1. Помещение появится на портале в течение 5–10 минут. Если это не так, обратитесь к managedroomsupport@microsoft.com.  

![Рисунок 5](../media/software-installation-005.jpg)

## <a name="installation"></a>Установка

После скачивания установщика с портала Майкрософт (с портала или с помощью url-адреса AKA.ms выше) раздвите его содержимое, чтобы получить доступ к файлуManagedRoomsInstaller.msi **.**

Существует два режима установки: установка отдельных локальных компьютеров и режим массового развертывания (обычно с помощью групповой политики аналогичного метода). Мы рекомендуем устанавливать отдельные установщики для компьютеров, которые не имеют домена, или компьютеров, на которые вы не можете запускать установщики MSI удаленно.  

Из-за множества различных способов запуска MSI-приложений в режиме массового развертывания этот документ будет проходить установку только в индивидуальном режиме.  

 > [!NOTE]
 > Программа установщика работает одинаково независимо от того, в каком режиме она работает. Единственное различие заключается в том, что при установке пользователю не нужно нажимать кнопки "Далее" и "Закрыть" в режиме массового развертывания.  

## <a name="individual-devicemdashdomain-joined-walkthrough"></a>По руководство по регистрации домена для отдельных &mdash; устройств

1. Войдите на устройство в  качестве администратора— убедитесь, что выполняются действия, выполняемые администратором устройства.

1. Скопируйте следующие файлы на устройство MTR:

   - Поместите "Ключ для самостоятельной регистрации" (ранее скачавший с портала) в **каталог C:\Previouslyel** устройства.
   - **СкопируйтеManagedRoomsInstaller.msi** (ранее скачано с портала или AKA.MS) на устройство.

1. При запуске ***ManagedRoomsInstaller.msi** _, вы увидите экран Лицензионного соглашения. Прочитав соглашение, _**_ я принимаю условия лицензионного соглашения и нажимаю кнопку _ *Установить**.  

    Начнется установка программного Комнаты Microsoft Teams службы для мониторинга управляемых служб. Отображается запрос на повышение (запуск от прав администратора).
 1. Выберите ***Да***.

    Установка продолжится. Во время установки откроется окно консоли и начнется заключительный этап Комнаты Microsoft Teams — установка программного обеспечения для мониторинга управляемых служб.  

    > [!NOTE]
    > Не закрывай окно. После завершения установки в мастере отобразит кнопку "Готово".

## <a name="completing-enrollment"></a>Завершение регистрации

После завершения установки подождите 5–10 минут и обновите портал, и устройство будет указано в списке как состояние *ветвь.*

В *состоянии "Вместить"* состояние комнаты отображается и обновляется, но при этом не создаются оповещения и не создаются билеты на исследование.

Выберите комнату и выберите **Зарегистрировать,**  чтобы получать оповещения об инцидентах, билеты на исследование или сообщать об инциденте.

Для вопросов и проблем откройте на портале инцидент, о который сообщил клиент, или свяжитесь с managedroomsupport@microsoft.com.

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>Unenrolling and uninstalling monitoring software

Чтобы отокрепить устройство, удалите агент мониторинга с устройства MTR следующим образом:

1. На отслеживаемом устройстве войдите на устройство в качестве администратора. Выполните действия, которые *выполните* в качестве администратора устройства.
1. Скачайте сценарий сброса из [aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding).
1. Извлеким сценарий на устройстве и скопируйте путь.
1. Откройте PowerShell в качестве администратора: в поле **Windows*** Поле Поиск _ (в левой нижней части экрана) введите "Powershell" и щелкните правой кнопкой мыши _*_Windows PowerShell_**.
1. Выберите *"Запуск от администратора"* и примите запрос UAC.
1. Введите *Set-ExecutionPolicy –ExecutionPolicy RemoteSigned* , а затем нажмите **Y** при следующем запросе.  
1. В окне PowerShell введите полный путь к сценарию unzipped offboarding и **нажмите** ввод.

   Например:

   *C:\Users\admin\Downloads\MTRP \_ Device \_ Offboarding\MTRP \_ Device \_Offboarding.ps1*  

   При этом устройство будет обновлено по стандарту MTR пользователя, а агент мониторинга MTRP и файлы будут удаляться.

1. В левом меню на портале Комнаты Microsoft Teams – Управляемые службы выберите **Помещения**.  
1. В списке предоставленных помещений выберите комнату, которые вы хотите отокрепить, и выберите **Unenroll** (Открепить), чтобы прекратить получение оповещений об инцидентах или билетов на исследование, а также сообщить об инциденте.

## <a name="troubleshooting-table"></a>Устранение неполадок с таблицей

> [!NOTE]
> Все Комнаты Microsoft Teams — ошибки мониторинга управляемых служб регистрируются в определенном файле журнала событий с именем **Microsoft Managed Rooms.** 

### <a name="application-runtime-log-file-location-"></a>***Расположение файла журнала во время запуска приложений*** =  

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortal \_ Verbose \_ LogFile.log, где **x.x.x** — номер версии приложения.

|**Симптом**  |**Рекомендуемая процедура**  |
| :- | :- |
|<p>Вы получаете сообщение об ошибке с сообщением   </p><p>***ОШИБКА. Запустите это приложение с помощью** _ </p><p>*__повышенные привилегии_**  </p>|Запустите приложение с привилегированными привилегиями и попробуйте еще раз  |
|  |  |
|<p>Вы получаете сообщение об ошибке с сообщением   </p><p>***Не удается найти данные TPM***  </p>|Убедитесь, что на вашем устройстве включен модуль TPM (доверенный модуль платформы), включив его. Обычно это происходит в параметрах безопасности устройства БИЗ.  |
|  |  |
|<p>Вы получаете сообщение об ошибке  </p><p>` `***ОШИБКА: не найдена учетная запись локального пользователя с именем "Администратор" или "Skype"***  </p>|Убедитесь, что учетные записи пользователей существуют на сертифицированном устройстве Microsoft Teams room systems.  |
|  |  |
|Вы получаете сообщения об ошибках, которые не охватываются выше  |Предостановите копию журнала установки агенту Microsoft Teams службу поддержки. |