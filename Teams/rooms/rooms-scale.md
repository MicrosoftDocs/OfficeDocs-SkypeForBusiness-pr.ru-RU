---
title: Развертывание комнат Microsoft Teams с помощью Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Узнайте, как развернуть комнаты Microsoft Teams в крупных развертываниях с помощью Microsoft Endpoint Configuration Manager.
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: 1d8fc0090264a7a39051cfedb9c3584a08e3ebb9
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662424"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>Развертывание комнат Microsoft Teams с помощью Microsoft Endpoint Configuration Manager

В этой статье вы можете получить всю необходимую информацию для создания развернутых помещений Microsoft Teams с помощью Microsoft Endpoint Configuration Manager.

С помощью простых в использовании методов, предоставляемых Configuration Manager, вы можете развернуть операционную систему и другие приложения на нескольких целевых устройствах.

Воспользуйтесь приведенной ниже инструкцией, чтобы настроить конфигурацию Configuration Manager и настроить образцы пакетов и сценариев, предоставленные в рамках этого руководства, при необходимости для вашей организации.

![Процесс развертывания комнат Microsoft Teams с помощью Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Это решение было протестировано только в развертываниях на основе Surface Pro. Следуйте инструкциям производителя для конфигураций, не основанных на Surface Pro.

## <a name="validate-prerequisites"></a>Проверка предварительных условий

Чтобы развернуть комнаты Microsoft Teams с помощью Configuration Manager, убедитесь, что вы соответствуете следующим требованиям и требованиям.

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Требования к Microsoft Endpoint Configuration Manager

-   Версия Microsoft EndPoint Configuration Manager должна быть не менее 1706 или выше. Рекомендуем использовать 1710 или более поздней. Ознакомьтесь [со службой поддержки Windows 10 в Configuration Manager,](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) чтобы узнать о версиях Windows 10, которые поддерживает Configuration Manager.

-   Необходимо установить поддерживаемую версию комплекта windows Assessment and Deployment Kit (ADK) для Windows 10. Просмотр версий [ADK Windows 10,](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) которые можно использовать с различными версиями Configuration Manager, и убедитесь, что в вашем развертывании есть правильная версия.

-   Системным серверам сайта должна быть назначена роль точки распространения, а изображения загрузки должны быть включены для поддержки среды выполнения [(PXE)](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) перед началом сетевого развертывания. Если поддержка PXE не включена, вы можете использовать для развертывания [загружаемый носители.](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network)

-   Учетная запись сетевого доступа должна быть настроена для поддержки новых сценариев развертывания на компьютере (без каретки). Дополнительные информацию о настройке учетной записи сетевого доступа см. в записях, [используемых в Configuration Manager.](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

-   Мы рекомендуем включить поддержку [многоуровневой](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)трансляции, если вы, вероятно, одновременно развернете одно и то же изображение комнат Microsoft Teams в нескольких блоках.

### <a name="networking-requirements"></a>Требования к сети

-   В вашей сети должен быть сервер DHCP, настроенный для автоматического распространения IP-адресов на подсетей, в которых будут развернуты единицы комнат Microsoft Teams.

    > [!NOTE]
    > Длительность аренду DHCP должна быть установлена на более длительный срок, чем длительность развертывания изображений. В противном случае развертывание может быть со сбойом.

-   Сеть, включая коммутаторы и виртуальные сети laNs (VLANs), должна быть настроена для поддержки PXE. Для получения дополнительных сведений о ip-помощнике и конфигурации PXE обратитесь к поставщику сети. Кроме того, вы можете использовать [загружаемый носители](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) для развертывания, если поддержка PXE не включена.

    > [!NOTE]
    > Для устройств Surface Pro загрузка из сети (загрузка PXE) поддерживается только при использовании адаптеров Ethernet или док-станции от Майкрософт. Сторонние адаптеры Ethernet не поддерживают загрузку PXE с Surface Pro. Дополнительные [сведения см. в адаптаторах Ethernet и развертывании Surface.](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment)

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>Настройка Microsoft Endpoint Configuration Manager для развертывания операционной системы

В этой статье предполагается, что у вас уже настроено здоровое развертывание Configuration Manager, а также не все действия, необходимые для развертывания и настройки Configuration Manager с нуля. Документация [и рекомендации по настройке](https://docs.microsoft.com/configmgr/) в Диспетчере конфигураций конечной точки Майкрософт — отличный ресурс. рекомендуем начать с этих ресурсов, если вы еще не развернули Configuration Manager.

Чтобы проверить правильность настройки компонентов OSD, следуйте инструкциям ниже.

### <a name="validate-and-upgrade-configuration-manager"></a>Проверка и обновление Configuration Manager

1.  В консоли Configuration Manager перейдите в **"Обновления** \> **администрирования и обслуживание".**

2.  Проверьте установленные сборки и соответствующие обновления, которые еще не установлены.

3.  Просмотр [поддержки Windows 10 в Configuration Manager;](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) если вам нужно обновить развертывание, выберите обновление, а затем выберите **"Скачать".**

4.  После завершения скачивания выберите обновление, а затем выберите **"Установить пакет обновления".**

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Настройка точек распространения для поддержки PXE и многомерных трансляций

1.  В консоли Configuration Manager перейдите в пункты **распространения** \> **"Администрирование".**

2.  Выберите сервер точки распространения, который будет обслуживать развертывание комнат Microsoft Teams, а затем выберите **"Свойства".**

3.  Выберите **вкладку PXE** и убедитесь, что включены следующие параметры:
    -   Включить поддержку PXE для клиентов
    -   Разрешить этой точке рассылки отвечать на входящие запросы PXE
    -   Включить поддержку неизвестного компьютера

4.  *Необязательно:* Чтобы включить многоуровневую поддержку, выберите вкладку **Multicast** и убедитесь, что включены следующие параметры:
    -   Включить мультикаст для одновременной отправки данных нескольким клиентам
    -   Настройка диапазона портов UDP по рекомендации вашей сетевой группы

### <a name="configure-the-network-access-account"></a>Настройка учетной записи сетевого доступа

1.  В консоли Configuration Manager перейдите к сайтам **конфигурации** сайта администрирования \>  \> и выберите сайт.

2.  В группе **"Параметры"** выберите **"Настройка распространения программного обеспечения для компонентов** \> **сайта".**

3.  Выберите вкладку **"Учетная запись сетевого доступа".** Настроив одну или несколько учетных записей, выберите **"ОК".**

> [!NOTE]
> Учетным записям не требуются какие-либо особые права, за исключением доступа к данному компьютеру из сети **прямо** на сервере точки распространения. Подходит общая учетная запись пользователя домена. Дополнительные сведения см. в [записях учетных записей, используемых в Configuration Manager.](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

### <a name="configure-a-boot-image"></a>Настройка изображения загрузки

1.  В консоли Configuration Manager  перейдите к изображениям загрузки операционной системы \> **библиотеки** \> **программного обеспечения.**

2.  Выберите **изображение загрузки (x64)** и выберите **"Свойства".**

3.  Выберите **вкладку "Источник данных"** и включите развертывание этого изображения загрузки из точки распространения с **поддержкой PXE.**

4.  Выберите **вкладку "Необязательные компоненты",** чтобы установить необходимые компоненты.

    1.  Выберите значок звездки и в поиске **по запросу HTML (WinPE-HTA)**

    2.  Чтобы **добавить поддержку** HTML-приложений к изображению загрузки, выберите "ОК".

5.  *Необязательно:* Чтобы настроить параметры развертывания, выберите вкладку **"Настройка".**
    -   В **этой службе можно включить поддержку (только** для тестирования), если вы хотите получить доступ к командной подсказке во время развертывания. Если эта возможность включена, вы можете в любой момент во время развертывания запустить командную команду, наключив **F8.**
    -   Вы также можете указать собственное фоновое изображение, которое будет отображаться во время развертывания. Чтобы задать изображение, в **выберите файл пользовательского фонового изображения (UNC-путь** и укажите фон).

6.  При запросе выберите **"Да"** и распространить обновленное изображение загрузки по точкам распространения.

Дополнительные сведения см. в [управлении загрузкой изображений с помощью Configuration Manager.](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images)

> [!NOTE]
> Вы можете создать usb-накопитель для загрузки, чтобы запускать последовательности задач Configuration Manager в средах, в которой нет поддержки PXE. В загружаемом носитле содержится только изображение загрузки, необязательные предзаписные команды и необходимые файлы, а также файлы в Configuration Manager, поддерживаюющие загрузку в Windows PE и подключение к Configuration Manager до конца процесса развертывания. Дополнительные сведения см. в теме ["Создание загружаемого носитела".](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)

## <a name="create-configuration-manager-packages"></a>Создание пакетов Configuration Manager

> [!IMPORTANT]
> Требуемая версия операционной системы для каждой версии установщика SRS изменяется в каждом выпуске MSI. Чтобы определить лучшую версию операционной системы для данного MSI-сервера, запустите сценарий установки консоли один раз. Подробнее см. в том, как развернуть [комнаты Microsoft Teams с помощью Microsoft Endpoint Configuration Manager.](rooms-scale.md)

Для развертывания и настройки комнат Microsoft Teams Manager требуется несколько пакетов.

Необходимо создать и настроить следующие пакеты, а затем распространить их в системах сайтов Configuration Manager, для которых назначена роль сервера точки распространения.

| **Имя пакета**                     | **Тип**               | **Описание**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 - SRS Application Package     | Пакет программного обеспечения       | Пакет комплекта для развертывания комнат Microsoft Teams                                      |
| SRS v2 — Пакет Sysprep             | Пакет программного обеспечения       | Пакет для настраиваемой Unattended.xml для настройки единиц комнат Microsoft Teams            |
| SRS v2 - Set-SRSComputerName Package | Пакет программного обеспечения       | Пакет для HTML-приложения (HTA) для назначения имени компьютера во время развертывания    |
| SRS v2: настройка установки SRS         | Пакет программного обеспечения       | Пакет для настройки развертывания приложения "Комнаты Microsoft Teams"                          |
| SRS версии 2 — пакет обновлений ОС          | Пакет программного обеспечения       | Пакет для развертывания обязательных обновлений операционной системы                                      |
| SRS v2 — пакет корневого сертификата    | Пакет программного обеспечения       | Необязательно: пакет для развертывания корневого сертификата (не требуется для подразделений, присоединительных к домену)  |
| Пакет агента мониторинга Майкрософт (SRS) 2 | Пакет программного обеспечения       | Необязательно: пакет для развертывания и настройки агента набора microsoft Operations Management Suite|
| SRS v2 - Фоновый пакет WinPE    | Пакет программного обеспечения       | Пакет для пользовательского фонового изображения для загрузки изображений                           |
| Windows 10 Корпоративная                | Изображение операционной системы | Пакет для файла установки операционной системы (install.wim)                          |
| Surface Pro                          | Пакет драйвера         | Пакет для драйверов устройств и микропрограмм для Microsoft Surface Pro                     |
| Surface Pro 4                        | Пакет драйвера         | Пакет для драйверов устройств и микропрограмм для Microsoft Surface Pro 4                   |

Дополнительные сведения см. [в сведениях о пакетах и программах в Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)

### <a name="create-folders-for-the-package-source-files"></a>Создание папок для исходных файлов пакета

Configuration Manager требует, чтобы исходные файлы пакетов были уорганы в определенную структуру папок при первом их созданном и обновлении.

Создайте следующую структуру папок на сайте центра администрирования Microsoft Endpoint Configuration Manager или основном сайте либо на сервере, который используется для обмена исходными файлами пакетов:

-   Пакет агента мониторинга Майкрософт (SRS) 2
-   SRS версии 2 — пакет обновлений ОС
-   SRS v2 — пакет корневого сертификата
-   SRS v2 - Set-SRSComputerName Package
-   SRS v2 - SRS Application Package
-   SRS v2: настройка установки SRS
-   SRS v2 — Пакет Sysprep
-   Драйверы
    -   Surface Pro
    -   Surface Pro 4
-   Операционные системы
    -   Windows 10 Корпоративная

> [!TIP]
> Вы также [](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) можете скачать и использовать ZIP-файл со структурой папок для пакетов, нужными сценариями и шаблоном последовательностей задач, которые нужно импортировать.

### <a name="create-the-monitoring-agent-package"></a>Создание пакета агента мониторинга

1. Скачайте агент мониторинга из <https://go.microsoft.com/fwlink/?LinkId=828603> .

2. Извлекать пакет в папку пакета агента мониторинга **(Майкрософт) SRS v2,** открыв окно команднойMMASetup-AMD64.exe **/C:**     в командной подсказке.

3. В консоли Configuration Manager перейдите **к** пакетам управления приложениями библиотеки программного обеспечения и выберите \>  \>  **"Создать пакет".**

4. Чтобы создать пакет, введите следующие данные:

   - Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong>

   - Производитель:<strong>Корпорация Майкрософт</strong>

   - Версия:<strong>8.1.11081.0</strong> (введите версию загруженного файла установки)

   - Выберите поле **"Этот пакет содержит исходные** файлы", введите путь к папке пакета агента мониторинга Майкрософт **(SRS 2) и** выберите "Далее". 

5. Выберите **"Не создавать программу",** а затем выберите **"Далее".**

6. Просмотрите **страницу подтверждения параметров** и выберите "Далее". 

7. Выберите **"Закрыть".**

### <a name="create-the-operating-system-updates-package"></a>Создание пакета обновлений операционной системы

1. В папке пакета обновлений **ОС (SRS версии 2)** создайте новый сценарий PowerShell с **именемInstall-SRSv2-OS-Updates.ps1.**

2. Скопируйте ниже сценарий в **Install-SRSv2-OS-Updates.ps1** сценарий. Вы также можете скачать сценарий Install-SRSv2-OS-Updates.ps1 [здесь.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. Скачайте обязательные пакеты Обновления Windows в ту же папку.
   > [!NOTE]
   > На момент публикации этой статьи требовалась только статья [KB4056892.](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) Проверьте, [нужно ли настраивать консоль](console.md)комнат Microsoft Teams, чтобы узнать, требуются ли другие обновления.

4. В консоли Configuration Manager перейдите **к** пакетам управления приложениями библиотеки программного обеспечения и выберите \>  \>  **"Создать пакет".**

5. Чтобы создать пакет, введите следующие данные:
   -   Имя: **SRS версии 2 — пакет обновлений ОС**
   -   Производитель: **Корпорация Майкрософт**
   -   Версия: **1.0.0**
   -   Выберите этот **пакет содержит исходные** файлы, введите путь к папке **SRS версии 2 — Пакет** обновлений ОС, а затем выберите **"Далее".**

6. Выберите **"Не создавать программу",** а затем выберите **"Далее".**

7. Просмотрите **страницу подтверждения параметров** и выберите "Далее". 

8. Выберите **"Закрыть".**

### <a name="create-the-root-certificate-package-optional"></a>Создание пакета корневого сертификата (необязательно)

Этот пакет создается для распространения корневого сертификата для устройств, которые не будут соединены с доменом Active Directory. Создайте этот пакет только в том случае, если применяются оба следующих условия:
-   Развертывание включает в себя локальное развертывание Lync или Skype для бизнеса Server.
-   Единицы комнат Microsoft Teams настроены для работы в группе, а не в составе домена.

1.  Скопируйте корневой сертификат в папку корневого пакета **сертификатов SRS v2.**

2.  В консоли Configuration Manager перейдите **к** пакетам управления приложениями библиотеки программного обеспечения и выберите \>  \>  **"Создать пакет".**

3.  Чтобы создать пакет, введите следующие данные:
    -   Имя: **SRS v2 — пакет корневого сертификата**
    -   Производитель: *название вашей организации*
    -   Версия: **1.0.0**
    -   Выберите этот **пакет, содержащий исходные** файлы, введите путь к папке **SRS v2 – Корневой** пакет сертификата и выберите **"Далее".**

4.  Выберите **"Не создавать программу",** а затем выберите **"Далее".**

5.  Просмотрите **страницу подтверждения параметров** и выберите "Далее". 

6.  Выберите **"Закрыть".**

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Создание пакета комплекта комплекта для развертывания комнат Microsoft Teams

1.  Скачайте последнюю версию комплекта **развертывания комнат Microsoft Teams** с рабочей станции и установите <https://go.microsoft.com/fwlink/?linkid=851168> его.

2.  Скопируйте содержимое **из C: \\ Program Files (x86) \\ Skype Room System Deployment Kit** в папку **SRS V2 - SRS Application Package.**

3.  В консоли Configuration Manager перейдите **к** пакетам управления приложениями библиотеки программного обеспечения и выберите \>  \>  **"Создать пакет".**

4.  Чтобы создать пакет, введите следующие данные:
    -   Имя: **SRS v2 — пакет приложения SRS**
    -   Производитель: **Корпорация Майкрософт**
    -   Версия: **3.1.104.0** (введите версию загруженного файла установки)
    -   Выберите этот **пакет содержит исходные** файлы, введите путь к папке **SRS V2 – SRS Application Package** и выберите **"Далее".**
5.  Выберите **"Не создавать программу",** а затем выберите **"Далее".**

6.  Просмотрите **страницу подтверждения параметров** и выберите "Далее". 

7.  Выберите **"Закрыть".**

### <a name="create-the-computer-name-assignment-package"></a>Создание пакета назначения имени компьютера

1.  В **SRS v2 - Set-SRSComputerName Package** folder (Пакет пакета) создайте новое HTML-приложение **с именем Set-SRSComputerName.hta.**

2.  Скопируйте следующий сценарий в файл **Set-SRSComputerName.hta.** Кроме того, здесь можно скачать файл Set-SRSComputerName.hta. [](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  В консоли Configuration Manager перейдите **к** пакетам управления приложениями библиотеки программного обеспечения и выберите \>  \>  **"Создать пакет".**

4.  Чтобы создать пакет, введите следующие данные:

    -   Имя: **SRS v2 - Set-SRSComputerName Package**

    -   Производитель: **Корпорация Майкрософт**

    -   Версия: **1.0.0**

    -   Выберите этот **пакет содержит исходные файлы,** введите путь к **SRS v2 - Set-SRSComputerName пакета** и выберите **Далее.**

5.  Выберите **"Не создавать программу",** а затем выберите **"Далее".**

6.  Просмотрите **страницу подтверждения параметров** и выберите "Далее". 

7.  Выберите **"Закрыть".**

### <a name="create-the-sysprep-package"></a>Создание пакета Sysprep

1. В **папке SRS v2 – Sysprep Package (Пакет Sysprep)** создайте новый XML-файл с **именемUnattend.xml.**

2. Скопируйте следующий текст в **Unattend.xml** файл. Кроме того, здесь можно скачать Unattend.xml [файл.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. В консоли Configuration Manager перейдите **к** пакетам управления приложениями библиотеки программного обеспечения и выберите \>  \>  **"Создать пакет".**

4. Чтобы создать пакет, введите следующие данные:
   -   Name: **SRS v2 - Sysprep Package**
   -   Производитель: **Корпорация Майкрософт**
   -   Версия: **1.0.0**
   -   Выберите поле **"Этот пакет содержит исходные** файлы", введите путь к папке **SRS v2 – Sysprep Package** и выберите "Далее". 
5. Выберите **"Не создавать программу",** а затем выберите **"Далее".**

6. Просмотрите **страницу подтверждения параметров** и выберите "Далее". 

7. Выберите **"Закрыть".**

### <a name="create-the-windows-10-enterprise-package"></a>Создание пакета Windows 10 Enterprise

1.  Получите носителей Windows 10 Корпоративный x64 и скопируйте **файл install.wim** в папку "Операционные системы **Windows \\ 10 Корпоративный".**

2.  В консоли Configuration Manager  перейдите к изображениям операционной системы "Библиотека программного обеспечения" и выберите \>  \>  **"Добавить изображение операционной системы".**

3.  Укажите путь к **файлу install.wim,** который вы только что скопировали, и выберите "Далее". 

4.  **Обновив поле "Версия"** в соответствие с номером сборки образа Windows 10 Enterprise, выберите "Далее". 

5.  Просмотрите **страницу "Сведения"** и выберите "Далее". 

6.  Выберите **"Закрыть".**

Дополнительные сведения см. в [видео "Управление изображениями ОС с помощью Configuration Manager".](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images)

### <a name="create-surface-pro-device-driver-packages"></a>Создание пакетов драйвера устройства Surface Pro

Комнаты Microsoft Teams поддерживаются как для Surface Pro, так и для Surface Pro 4. Необходимо создать пакет драйвера для каждой модели Surface Pro, которая у вас есть в вашей среде.

> [!IMPORTANT]
> Драйверы должны быть совместимы с сборкой Windows 10 Enterprise и комплектом комплекта для развертывания Microsoft Teams Rooms. Дополнительные сведения см. в сведениях о скачии последних [версиях версий версий](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) постройки и драйверов для устройств Surface и [настройке консоли.](console.md)

1.  Скачайте новейшие драйверы и программное обеспечение.
    -   Для Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484>
    -   Для Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498>

2.  Извлеките скачаный драйвер и микропрограммы. Откройте окно командной подсказки и введите в нее одну из следующих команд:
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  В консоли Configuration Manager перейдите **к** драйверам операционных систем библиотеки программного обеспечения и выберите \>  \>  **"Импорт драйвера".**

4.  Выберите "Импорт всех драйверов" на следующем сетевом пути **(UNC),** выберите папку-источник (например, C: _Sources Drivers Surface Pro), а затем выберите \\ \\ \\ **"Далее".**

5.  На странице **"Укажите** сведения о импортируемых драйверах" выберите все указанные драйверы, а затем выберите "Включить эти драйверы и разрешить их **установку компьютерами".**

6.  Выберите **"Категории",** создайте новую категорию, которая соответствует модели Surface, выберите "ОК", а затем выберите **"Далее".** 

7.  Выберите **"Новый пакет".**

8.  Укажите имя пакета, которое соответствует модели Surface Pro, введите путь к папке для хранения файлов пакета драйвера, выберите "ОК" и затем выберите **"Далее".**

9.  Убедитесь, **что на** странице загрузок не выбраны изображения загрузки, и выберите **"Далее".**

10. Выберите **"Закрыть".**

11. Перейдите  в драйверы операционных систем библиотеки программного обеспечения, выберите папку "Создать папку" и введите имя папки, которая соответствует модели Surface Pro, для которую вы только что импортировали \>  \> драйверы. **\>**

12. Переместить все импортируемые драйверы в созданную папку, чтобы упростить навигацию и работу.

> [!NOTE]
> Повторите те же действия для других моделей Surface Pro, которые у вас могут быть. Дополнительные сведения см. в [сведениях об управлении драйверами в Configuration Manager.](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers)

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Создание пакета конфигурации комнат Microsoft Teams

1.  В консоли Configuration Manager перейдите **к** пакетам управления приложениями библиотеки программного обеспечения и выберите \>  \>  **"Создать пакет".**

2.  Чтобы создать пакет, введите следующие данные:

    -   Имя: **SRS v2 — настройка пакета установки SRS**

    -   Производитель: **Корпорация Майкрософт**

    -   Версия: **1.0.0**

    -   Выберите этот **пакет содержит исходные** файлы, введите путь к **SRS v2 - Настройка папки установки SRS,** а затем выберите **"Далее".**

3.  Выберите **"Не создавать программу",** а затем выберите **"Далее".**

4.  Просмотрите **страницу подтверждения параметров** и выберите "Далее". 

5.  Выберите **"Закрыть".**



## <a name="distribute-configuration-manager-packages"></a>Распространение пакетов Configuration Manager

Все пакеты должны быть распределены на серверы, которые имеют роль точки распространения в иерархии Configuration Manager. Следуйте инструкциям ниже, чтобы начать распространение пакета.

1.  Распространение пакетов программного обеспечения.

    1.  В консоли Configuration Manager перейдите **к** пакетам управления приложениями \> **библиотеки** \> **программного обеспечения.** Выберите все пакеты программного обеспечения, которые вы хотите распространить, и выберите **"Распространение содержимого".**

    2.  Просмотрите список пакетов и выберите **"Далее".**

    3.  Добавьте в список все серверы точек рассылки (или группы точек рассылки, в зависимости от иерархии Configuration Manager), а затем выберите **"Далее".**

    4.  Выберите **"Далее",** а затем выберите **"Закрыть".**

2.  Распространение пакетов драйвера.

    1.  В консоли Configuration Manager перейдите **к** пакетам драйвера для операционной системы "Библиотека программного \>  \> **обеспечения".** Выберите все пакеты драйверов, которые вы хотите распространить, и выберите **"Распространение содержимого".**

    2.  Просмотрите список пакетов и выберите **"Далее".**

    3.  Добавьте в список все серверы точек рассылки (или группы точек рассылки, в зависимости от иерархии Configuration Manager), а затем выберите **"Далее".**

    4.  Выберите **"Далее",** а затем выберите **"Закрыть".**

3.  Распространение пакетов операционной системы.

    1.  В консоли Configuration Manager  перейдите к изображениям операционной системы "Библиотека программного \>  \> **обеспечения".** Выберите все изображения операционной системы, которые вы хотите распространить, и выберите **"Распространение содержимого".**

    2.  Просмотрите список пакетов и выберите **"Далее".**

    3.  Добавьте в список все серверы точек рассылки (или группы точек рассылки, в зависимости от иерархии Configuration Manager), а затем выберите **"Далее".**

    4.  Выберите **"Далее",** а затем выберите **"Закрыть".**

> [!NOTE]
> Распространение пакетов может занять некоторое время в зависимости от размера пакета, иерархии Configuration Manager, количества серверов точек рассылки и пропускной способности, доступной в сети.
> 
> Перед началом развертывания комнат Microsoft Teams необходимо распределить все пакеты.
> 
> Вы можете просмотреть состояние распространения пакета в консоли Configuration Manager, на панели **мониторинга** состояния \>  \> **распространения содержимого.**

## <a name="configuration-manager-task-sequences"></a>Последовательности задач Configuration Manager

С помощью Configuration Manager вы можете автоматизировать действия по развертыванию образа операционной системы на целевом компьютере с помощью последовательностей задач. Для автоматического развертывания комнат Microsoft Teams необходимо создать последовательность задач, которая ссылается на изображение загрузки, используемого для запуска целевого компьютера комнат Microsoft Teams, образа операционной системы Windows 10 корпоративная, а также любое другое содержимое, например другие приложения или обновления программного обеспечения.

### <a name="import-the-sample-task-sequence"></a>Импорт примеров последовательностей задач

Вы можете легко скачать и импортировать образец последовательности задач и настроить его в нужном порядке.

1.  [**Скачайте**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) образец последовательности задач и скопируйте скачаный ZIP-файл в общую папку.
2.  В консоли Configuration Manager  перейдите к последовательностям задач "Библиотека программного обеспечения" операционной системы, а затем выберите \>  \>  **"Импорт последовательности задач".**

3.  Выберите **"Обзор",** перейдите к общей папке, которая использовалась в шаге 1, выберите развертывание комнат **Microsoft Teams (ZIP-файл)** и затем выберите **"Далее".**

4.  Выберите действие **"Создать", а** затем выберите **"Далее".** 

5.  Подтвердив параметры, а затем выберите **"Далее".**

6.  Выберите **"Закрыть".**

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Проверьте правильность связей пакетов ссылок с каждым этапом последовательности задач.

1. Выберите последовательность импортируемых задач и выберите **"Изменить".**

    Откроется редактор последовательностей задач с каждым последовательным этапом, который необходимо развернуть и настроить в microsoft Teams Rooms.

2. Выполните все этапы и выполните рекомендуемые обновления.

   1. **Перезапустите в Windows PE:** перезагрузите компьютер и загрузите его в Windows PXE. Для этого шага не требуется никаких изменений.

   2. **Диск partition 0 — UEFI**: этот шаг протирает конфигурацию диска и создает разделы на основе настроенных параметров. Мы не рекомендуем вносить изменения в этот шаг.

   3. **Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.
      -  Это необязательный шаг, но его можно отключить только в том случае, если вы хотите управлять именой компьютера с помощью альтернативного процесса.
      -  Убедитесь, что выбран **пакет SRS v2 Set-SRSComputerName.** Если это не так, перейдите к пакету и выберите его.

   4. **Применение операционной** системы: на этом шаге заданы развертывание образа операционной системы и несмежный Sysprep answer file to use.
      -  Убедитесь, что выбран правильный файл образа операционной системы Windows 10 Корпоративная.
      -  Убедитесь, что для пользовательской установки включено использование неотвеченного или **Sysprep-ответа,** а также выбран пакет **SRS v2 - Sysprep Package.** Убедитесь, **что для** имени файла установлено **unattend.xml.**

   5. **Применение параметров Windows:** на этом этапе собираются сведения об установке Windows.
      -  Включите сведения о лицензировании и регистрации, включая ключ продукта, пароль локальной учетной записи администратора и часовой пояс (в зависимости от потребностей).

   6. **Применение параметров сети:** на этом этапе можно указать имя или доменное имя домена Active Directory или подразделение Active Directory.
      > [!NOTE]
      > Дополнительные рекомендации по развертыванию комнат Microsoft Teams в качестве участников домена Actve Directory см. в вопросах о присоединении к домену системы комнат [Skype.](domain-joining-considerations.md)
   7. **Применение драйверов:** Этот шаг и его подпрограммы используются для развертывания драйверов устройств и вычитаемого ПО на основе модели Surface Pro. Обновив каждый шаг, укажите соответствующий пакет драйвера, связанный с этим развертыванием.
      -   Каждый пакет драйвера настроен для использования фильтров WMI для развертывания соответствующих драйверов и постройки на основе моделей и моделей Surface Pro.
      -   Настоятельно рекомендуем не изменять конфигурацию этих драйверов, иначе развертывание может привести к сбой.

   8. **Настройка Windows и Configuration Manager:** на этом этапе развертывается и настраивается клиент Configuration Manager. Обновив этот шаг, укажите встроенный пакет клиента Configuration Manager.

   9. **Установка корневого** сертификата. Этот шаг распространяет корневой сертификат для устройств, не присоединивательных к домену, и поэтому является необязательным и отключен по умолчанию.
      -   В этом случае вам потребуется развернуть корневой сертификат в блоках комнат Microsoft Teams.
      -   Если вам нужно сделать это, убедитесь, что выбраны **SRS V2 —** пакет корневых сертификатов и отключение перенаправления **64-битной** файловой системы.

   10. **Установка и настройка** агента мониторинга. На этом этапе устанавливается 64-битная версия агента Microsoft Azure Monitor и настраивается подключение агента к рабочей области аналитики журналов.
       -   Этот шаг по умолчанию отключен. Этот шаг можно включить только в том случае, если вы собираетесь использовать агента мониторинга для отслеживания состояния комнат Microsoft Teams.
       -   Отредактйте этот шаг и обновите параметры командной строки, указав свой **ИД** рабочей области и **ключ рабочей области.**
       -   Дополнительные [сведения о получении ИД](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) рабочей области набора операций и первичного ключа см. в сведениях о настройке тестовых устройств для мониторинга Azure.
       -   Убедитесь, что выбраны пакет агента мониторинга Майкрософт **(SRS 2)** и отключено перенаправление **64-битной** файловой системы.
       -   Дополнительные сведения о мониторинге состояния развертывания комнат Microsoft Teams см. в планах управления комнатами Microsoft Teams с помощью [Azure Monitor,](azure-monitor-plan.md)развертывании управления комнатами [Microsoft Teams](azure-monitor-deploy.md) с помощью устройств Azure Monitor и управления устройствами комнат Microsoft Teams с помощью [Azure Monitor.](azure-monitor-manage.md)

   11. **Копирование SRS файлов конфигурации v2:** на этом этапе необходимые файлы настройки и настройки копируется из комплекта развертывания Microsoft Teams Rooms на локальный жесткий диск. Для этого шага не требуется никаких настроек.
       -   Убедитесь, что выбраны пакет приложений **SRS v2 — SRS Application Package** и **Disable 64-bit file system redirection (Отключить 64-битную** файловую систему).

   12. **Install-SRSv2-OS-Updates:** на этом этапе развертываются все обязательные обновления операционной системы, необходимые для развертывания комнат Microsoft Teams. Выполните указанные ниже действия.
       -   Проверьте, какие обновления необходимы для настройки консоли комнат [Microsoft Teams.](console.md)
       -   Убедитесь, что пакет обновлений ОС версии **2 (SRS версии 2)** включает все необходимые обновления.
       -   Убедитесь, что выбран **пакет обновлений SRS версии 2 —OS.**
       -   Убедитесь, что политика выполнения PowerShell настроена на **"Обход".**

   13. **Перезагрузите** компьютер: этот шаг перезагрузит компьютер после установки обязательных обновлений операционной системы. Для этого шага не требуется никаких настроек.

   14. **Настройка компонентов Windows:** на этом этапе настроены необходимые функции Windows. Для этого шага не требуется никаких настроек.

   15. **Перезагрузите** компьютер: этот шаг перезагрузит компьютер после настройки компонентов Windows. Для этого шага не требуется никаких настроек.

   16. **Добавить локального пользователя Skype:** на этом шаге создается локализованная учетная запись Skype, которая используется для автоматического входов в Windows и запуска приложения комнат Microsoft Teams. Этот шаг не связан с программным пакетом, и для него не требуется его настройка.

   17. **Настройка приложения SRS:** на этом этапе настроена установка приложения комнат Microsoft Teams для следующего загрузки операционной системы.
       -   Убедитесь, что выбраны **SRS v2 — настройка пакета установки SRS** и отключение перенаправления **64-битной** файловой системы.

> [!IMPORTANT]
> Очень важно, чтобы шаги последовательности задач были должны быть упорядочены в нужном порядке. Изменение порядка шагов или настройка дополнительных действий может нарушить развертывание.
>
> **Настройка приложения SRS** должна быть последним этапом в последовательности задач, иначе развертывание может привести к сбойу.

### <a name="create-deployment-for-the-task-sequence"></a>Создание развертывания для последовательности задач

1. Выберите последовательность задач, а затем выберите **"Развернуть".**

2. Чтобы **выбрать целевую** коллекцию для развертывания, выберите "Обзор".

3. Выберите **"Все неизвестные компьютеры"** и выберите "ОК". 

4. Выберите **"Далее".**

5. В **списке** "Назначение" **выберите "Доступен".**

6. В списке "Сделать доступными" выберите "Только мультимедиа" и **"PXE",** а затем выберите **"Далее".** 
   > [!WARNING]
   > Очень важно, чтобы **для назначения** было установлено значение "В **наличии".** Убедитесь, что **для назначения** **не** установлено **обязательное назначение.** Кроме того, убедитесь, что в области "Сделать доступными" выбраны только мультимедиа и **PXE.**
   >
   > Если установить для этих значений другое значение, все компьютеры могут получить изображение развертывания комнат Microsoft Teams при загрузке.
7. Не укажите расписание и выберите **"Далее".**

8. Не изменяя ничего в разделе **"Пользовательский интерфейс",** выберите **"Далее".**

9. Не изменяя ничего в разделе **"Оповещения",** выберите **"Далее".**

10. Не изменяя ничего в разделе **"Точки** распространения", выберите **"Далее".**

11. Подтвердив параметры, а затем выберите **"Далее".**

12. Выберите **"Закрыть".**

<a name="validate-and-troubleshoot-the-solution"></a>Проверка и устранение неполадок с решением
--------------------------------------

После завершения последовательностей задач Microsoft Endpoint Configuration Manager необходимо выполнить тестовый запуск, чтобы проверить возможность развертывания и настройки единиц помещения Microsoft Teams в последовательности задач.

1.  Подключите тестовое устройство к проводной сети с помощью одного из поддерживаемых адаптеров Ethernet или док-станции Surface. Если функция загрузки PXE не настроена для вашей среды, вы можете использовать [](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) изображение загрузки на USB-устройстве флэш-памяти, созданном ранее, для загрузки с USB и подключения к Configuration Manager.

2.  Доступ к пошива и начало загрузки PXE:

    1.  Убедитесь, что устройство Surface выключено.

    2.  Нажмите и удерживайте **кнопку "Вверх".**

    3.  Нажмите и отпустите **кнопку питания.**

    4.  Когда устройство начнет загрузку, отпустите **кнопку "Вверх".**

    5.  Выберите **конфигурацию загрузки.**

    6.  Выполните одно из следующих действий.

        -   Выберите **загрузку PXE** и перетащите ее в верхнюю часть списка. Кроме того, вы можете провести пальцем влево по сетевому адаптеру, чтобы сразу же загрузить устройство. Это не повлияет на порядок загрузки.
        -   Выберите USB-устройство флэш-памяти, которое содержит мультимедиа загрузки.

3.  Выберите **"Выйти"** и **"Перезапустить сейчас".**

4.  При запросе выберите ввод **для службы** загрузки сети.

5.  Windows PE загрузит в память, и запустится мастер последовательностей задач. Чтобы **продолжить, выберите** "Далее".

6.  Выберите последовательность задач, которую вы импортировали ранее, и выберите **"Далее".**

7.  После настройки диска вам будет предложено указать имя компьютера для устройства. В пользовательском интерфейсе будет отображаться рекомендуемое имя компьютера в зависимости от серийного номера устройства Surface Pro. Вы можете принять предложенное имя или указать новое. Следуйте инструкциям на экране назначения имени компьютера. Когда вы на **выберете "Принять",** начнется развертывание.

8.  Остальная часть процесса развертывания является автоматической, и пользователю больше не нужно ничего вводить.

9.  После завершения настройки устройства в последовательности задач развертывания вы увидите следующий экран конфигурации с запросом на настройку параметров приложения комнат Microsoft Teams.

    ![Экран начальной настройки для приложения комнат Microsoft Teams](../media/room-systems-scale-image2.png)

10.  Подключите Surface Pro к консоли комнат Microsoft Teams и настройте параметры приложения.

11.  Проверьте возможности, перечисленные в справке [по комнатам Microsoft Teams,](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) на развернутом устройстве.


Чтобы устранить неполадки при сбойной установке, проверьте файл **SMSTS.log,** в котором регистрются все действия, выполненные в последовательности задач Configuration Manager.

Файл SMSTS.log хранится по одному из нескольких путей в зависимости от этапа построения. В таблице ниже идентифицировать путь к файлу SMSTS.log.


| **Этап развертывания**                                                            | **Путь к журналу последовательностей задач**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE до формата HDD                                                        | X: \\ \\ SMS-сообщения в Windows \\ Temp \\             |
| WinPE после формата HDD                                                         | В. \\ _SMSTaskSequence \\ записи \\ SMS-сообщений \\ smstslog.log    |
| Развернута операционная система до установки агента Configuration Manager | в. \\ _SMSTaskSequence \\ записи \\ SMS-сообщений \\ smstslog.log    |
| Развернуты операционная система и агент Configuration Manager                   | %windir% \\ System32 \\ ccm \\ регистрет \\ Smstslog \\ SMSts.log |
| Последовательность задач завершена                                                | %windir% \\ System32 \\ ccm \\ \\ регистрет smsts.log           |

> [!TIP]
> Во время последовательности задач можно в любой момент выбрать **F8,** чтобы открыть консоль команд, а затем получить доступ к файлу SMSTS.log.

Чтобы устранить проблемы с загрузкой PXE, проверьте два файла журнала на сервере Configuration Manager, которые имеют определенные действия с PXE:

-   **Pxecontrol.log,** который находится в каталоге журналов установки Configuration Manager

-   **Smspxe.log**, расположенный в каталоге MP

Полный список файлов журнала, которые можно использовать для дальнейшего устранения неполадок при [](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)установке Configuration Manager, см. в справочнике по файлу журнала Диспетчера конфигураций Microsoft.
