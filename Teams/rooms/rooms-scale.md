---
title: Развертывание Комнаты Microsoft Teams с помощью Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Узнайте, как развертывать Комнаты Microsoft Teams в крупных развертываниях с помощью Microsoft Endpoint Configuration Manager.
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
ms.openlocfilehash: 27cd37df8516973ddf9fbe6401a1e4c21ce01e0a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731578"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>Развертывание Комнаты Microsoft Teams с помощью Microsoft Endpoint Configuration Manager

В этой статье вы можете получить все необходимые сведения для Комнаты Microsoft Teams развертывания с помощью Microsoft Endpoint Configuration Manager.

С помощью простых в использовании методов, предоставляемых Configuration Manager, вы можете развернуть операционную систему и другие приложения на нескольких целевых устройствах.

Используйте подход, который приведен ниже, чтобы проецировать конфигурацию Configuration Manager и настроить образцы пакетов и сценариев, предоставленные в рамках этого руководства, при необходимости для вашей организации.

![Комнаты Microsoft Teams с помощью Configuration Manager.](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Это решение было протестировано только в Surface Pro развертываниях на базе Surface Pro. Следуйте инструкциям производителя для конфигураций, которые не основаны на Surface Pro.

## <a name="validate-prerequisites"></a>Проверка предварительных условий

Чтобы развернуть Комнаты Microsoft Teams с помощью Configuration Manager, убедитесь, что вы соответствуете следующим требованиям и требованиям.

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Microsoft Endpoint Configuration Manager требования

-   Microsoft Endpoint Configuration Manager версия должна быть не менее 1706 или выше. Рекомендуем использовать 1710 или более поздней. Ознакомьтесь со Windows 10 в [Configuration Manager,](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) чтобы узнать о Windows 10, поддерживаемой Configuration Manager.

-   Необходимо установить поддерживаемую версию Windows и комплект развертывания (ADK) для Windows 10. Просмотр версий Windows 10 [ADK,](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) которые можно использовать с различными версиями Configuration Manager, и убедитесь, что в развертывании используется правильная версия.

-   Системным серверам сайтов должна быть назначена роль точки распространения, а изображения загрузки должны быть включены для поддержки среды предварительного выполнения [(PXE),](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) чтобы включить сетевые развертывания. Если поддержка PXE не включена, вы можете использовать [загружаемые носители](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) для развертывания.

-   Учетная запись сетевого доступа должна быть настроена для поддержки новых сценариев развертывания на компьютере (без метала). Дополнительные информацию о настройке учетной записи сетевого доступа см. в записях учетных записей, [используемых в Configuration Manager.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

-   Если вы, [](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)вероятно, развернете одно и то же изображение Комнаты Microsoft Teams в нескольких единицах одновременно, мы рекомендуем включить поддержку многоядерных трансляций.

### <a name="networking-requirements"></a>Требования к сети

-   В вашей сети должен быть сервер DHCP, настроенный для автоматического распространения IP-адресов на подсеть, в Комнаты Microsoft Teams будут развернуты единицы.

    > [!NOTE]
    > Длительность аренды DHCP должна быть установлена на более длительный срок, чем длительность развертывания изображений. В противном случае может произойть сбой развертывания.

-   Сеть, включая коммутаторы и виртуальные сети laNs (VLANs), должна быть настроена для поддержки PXE. Дополнительные сведения о помощнике по IP-адресам и конфигурации PXE можно найти у поставщика сети. Кроме того, вы можете использовать загружаемые [носители](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) для развертывания, если поддержка PXE не включена.

    > [!NOTE]
    > Для Surface Pro устройств загрузка из сети (загрузка PXE) поддерживается только при использовании адаптеров Ethernet или док-станции от Майкрософт. Сторонние адаптеры Ethernet не поддерживают загрузку PXE с помощью Surface Pro. Дополнительные [сведения см. в теме Адаптеры Ethernet и развертывание Surface.](/surface/ethernet-adapters-and-surface-device-deployment)

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>Настройка Microsoft Endpoint Configuration Manager для развертывания операционной системы

В этой статье предполагается, что у вас уже есть нормальное развертывание Configuration Manager, и не подробно подробно данная статья посвящена развертыванию и настройке Configuration Manager с нуля. Документация [и инструкции по](/configmgr/) настройке Microsoft Endpoint Configuration Manager — отличный ресурс; рекомендуем начать с этих ресурсов, если вы еще не развернули Configuration Manager.

Чтобы проверить правильность настройки компонентов развертывания операционной системы (OSD), следуйте инструкциям ниже.

### <a name="validate-and-upgrade-configuration-manager"></a>Проверка и обновление Configuration Manager

1.  В консоли Configuration Manager перейдите в **центр обновления** \> **администрирования и обслуживания**.

2.  Проверьте установленные сборки и соответствующие обновления, которые еще не установлены.

3.  Просмотрите [службу поддержки Windows 10 в Configuration Manager;](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) Если вам нужно обновить развертывание, выберите обновление, а затем выберите **Скачать**.

4.  После завершения скачивания выберите обновление и выберите Установить **пакет обновления**.

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Настройка точек распространения для поддержки PXE и многомерных трансляций

1.  В консоли Configuration Manager перейдите к пункту **Точки** \> **распространения администрирования**.

2.  Выберите сервер точек рассылки, который будет служить развертыванию Комнаты Microsoft Teams, и выберите **Свойства**.

3.  Выберите **вкладку PXE** и убедитесь, что включены следующие параметры:
    -   Включить поддержку PXE для клиентов
    -   Разрешить этой точке рассылки отвечать на входящие запросы PXE
    -   Включить поддержку неизвестного компьютера

4.  *Необязательно:* Чтобы включить многоядерную поддержку, на вкладке **Multicast** убедитесь, что включены следующие параметры:
    -   Включить многоуровневую передачу данных для одновременной отправки данных в несколько клиентов
    -   Настройка диапазона портов UDP в процентах от рекомендации вашей сетевой группы

### <a name="configure-the-network-access-account"></a>Настройка учетной записи сетевого доступа

1.  В консоли Configuration Manager перейдите на сайт **конфигурации сайта** \> **администрирования** \> и выберите сайт.

2.  В группе **Параметры** выберите **Настроить распространение** программного обеспечения компонентов \> **сайта**.

3.  Выберите **вкладку Учетная запись сетевого** доступа. Настроив одну или несколько учетных записей, а затем выберите **ОК.**

> [!NOTE]
> Для учетных записей не требуются специальные права, за исключением доступа к этому компьютеру из сети **прямо** на сервере точек рассылки. Подходит общую учетную запись пользователя домена. Дополнительные сведения см. в [записях учетных записей, используемых в Configuration Manager.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

### <a name="configure-a-boot-image"></a>Настройка изображения загрузки

1.  В консоли Configuration Manager перейдите к **загрузке изображений загрузки** операционной системы библиотеки \>  \> **программного обеспечения**.

2.  Выберите **Загрузка изображения (x64)** и **свойства**.

3.  Выберите **вкладку Источник данных** и включите развернуть это изображение загрузки из точки распространения с поддержкой **PXE.**

4.  Выберите **вкладку Необязательные компоненты,** чтобы установить необходимые компоненты.

    1.  Выберите значок звезды и в поиске **по запросу HTML (WinPE-HTA)**

    2.  Чтобы **добавить поддержку** HTML-приложения к изображению загрузки, выберите ОК.

5.  *Необязательно:* Чтобы настроить параметры развертывания, выберите **вкладку Настройка.**
    -   В этой службе можно включить поддержку **(только тестирование),** если вы хотите получить доступ к командной подсказке во время развертывания. Если эта возможность включена, вы можете запустить командную команду, выбрав **F8** в любое время во время развертывания.
    -   Вы также можете указать пользовательское фоновое изображение, которое будет отображаться во время развертывания. Чтобы задать изображение, вите Укажите пользовательский файл фонового изображения **(UNC-путь** и выберите фон).

6.  При запросе выберите **Да** и распространить обновленное изображение загрузки по точкам распространения.

Дополнительные сведения см. в теме [Управление загрузкой изображений с помощью Configuration Manager.](/configmgr/osd/get-started/manage-boot-images)

> [!NOTE]
> Вы можете создать загружаемый USB-носители, чтобы запускать последовательности задач Configuration Manager для среды, в которой нет поддержки PXE. В загружаемом файле содержится только изображение загрузки, необязательные предварительные команды и необходимые файлы, а также файлы-файлы Configuration Manager, которые поддерживают загрузку в Windows PE и подключение к Configuration Manager для остальной части процесса развертывания. Дополнительные сведения см. в [теме Создание загружаемых мультимедиа.](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)

## <a name="create-configuration-manager-packages"></a>Создание пакетов Configuration Manager

> [!IMPORTANT]
> Требуемая версия операционной системы для каждой версии установщика SRS изменяется с каждым выпуском MSI. Чтобы определить версию операционной системы для данного MSI-сервера, запустите сценарий настройки консоли один раз. Дополнительные информации см. в [Комнаты Microsoft Teams с помощью Microsoft Endpoint Configuration Manager.](rooms-scale.md)

Configuration Manager требуется несколько пакетов для развертывания и настройки Комнаты Microsoft Teams единиц.

Вам нужно создать и настроить следующие пакеты, а затем распространить их в системы сайтов Configuration Manager, для которых назначена роль сервера точки распространения.

| **Имя пакета**                     | **Тип**               | **Описание**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| Пакет приложений SRS v2 — SRS     | Пакет программного обеспечения       | Пакет для пакета Комнаты Microsoft Teams развертывания                                      |
| SRS v2 — пакет Sysprep             | Пакет программного обеспечения       | Пакет для настраиваемой Unattended.xml для настройки Комнаты Microsoft Teams единиц            |
| Пакет Set-SRSComputerName SRS Set-SRSComputerName SRS | Пакет программного обеспечения       | Пакет для HTML-приложения (HTA) для назначения имени компьютера во время развертывания    |
| SRS v2 — настройка настройки SRS         | Пакет программного обеспечения       | Пакет для настройки развертывания приложения Комнаты Microsoft Teams приложений                          |
| SRS версии 2 — пакет обновлений ОС          | Пакет программного обеспечения       | Пакет для развертывания обязательных обновлений операционной системы                                      |
| SRS v2 — корневой пакет сертификата    | Пакет программного обеспечения       | Необязательно: пакет для развертывания корневого сертификата (не требуется для подразделений, присоединимых к домену)  |
| Пакет SRS для Microsoft Monitoring Agent 2 | Пакет программного обеспечения       | Необязательно: пакет для развертывания и настройки агента Microsoft Operations Management Suite|
| SRS v2 — фоновый пакет WinPE    | Пакет программного обеспечения       | Пакет для пользовательского фонового изображения для загрузки изображений                           |
| Windows 10 Корпоративная                | Изображение операционной системы | Пакет для установщика операционной системы (install.wim)                          |
| Surface Pro                          | Пакет драйвера         | Пакет для драйверов устройств и программного обеспечения для Microsoft Surface Pro                     |
| Surface Pro 4                        | Пакет драйвера         | Пакет для драйверов устройств и фирменого ПО для Microsoft Surface Pro 4                   |

Дополнительные сведения см. в [теме Пакеты и программы в Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)

### <a name="create-folders-for-the-package-source-files"></a>Создание папок для исходных файлов пакета

Configuration Manager требует, чтобы исходные файлы пакетов были уорганы в определенную структуру папок при их первом и обновлении.

Создайте следующую структуру папок на сайте Microsoft Endpoint Configuration Manager администрирования или основном сайте либо на серверной папке, используемой для создания исходных файлов пакетов:

-   Пакет SRS для Microsoft Monitoring Agent 2
-   SRS версии 2 — пакет обновлений ОС
-   SRS v2 — корневой пакет сертификата
-   Пакет SRS для Set-SRSComputerName 2
-   Пакет приложений SRS v2 — SRS
-   SRS v2 — настройка настройки SRS
-   SRS v2 — пакет Sysprep
-   Драйверы
    -   Surface Pro
    -   Surface Pro 4
-   Операционные системы
    -   Windows 10 Корпоративная

> [!TIP]
> Вы также [можете](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) скачать и использовать ZIP-файл, который содержит структуру папок для пакетов, нужные сценарии и шаблон последовательности задач, которые нужно импортировать.

### <a name="create-the-monitoring-agent-package"></a>Создание пакета агента мониторинга

1. Скачайте агент мониторинга из <https://go.microsoft.com/fwlink/?LinkId=828603> .

2. Извлекать пакет в папку **SRS v2 – Microsoft Monitoring Agent Package** (Пакет), открыв окно команднойMMASetup-AMD64.exe **/C:** в командной подсказке.

3. В консоли Configuration Manager  перейдите к пакету управления приложениями библиотеки программного обеспечения \>  \> и выберите **Создать пакет**.

4. Введите следующую информацию для создания пакета:

   - Имя:<strong>SRS v2 — пакет Microsoft Monitoring Agent</strong>

   - Производитель:<strong>Корпорация Майкрософт</strong>

   - Версия:<strong>8.1.11081.0</strong> (введите версию загруженного установного файла)

   - Выберите этот **пакет содержит исходные файлы,** введите путь к **SRS v2 - Microsoft Monitoring Agent Пакет** и выберите **Далее**.

5. Выберите **Не создавать программу**, а затем выберите **Далее**.

6. Просмотрите **страницу Подтверждение параметров** и выберите **Далее.**

7. Выберите **Закрыть**.

### <a name="create-the-operating-system-updates-package"></a>Создание пакета обновлений операционной системы

1. В **папке Пакет обновления ОС SRS версии 2** создайте новый сценарий PowerShell с именем **Install-SRSv2-OS-Updates.ps1.**

2. Скопируйте сценарий ниже в **Install-SRSv2-OS-Updates.ps1** сценарий. Кроме того, вы можете скачать сценарий Install-SRSv2-OS-Updates.ps1 [отсюда](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
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
3. Скачайте обязательные пакеты Windows обновления в ту же папку.
   > [!NOTE]
   > На момент публикации этой статьи требовался только [KB4056892.](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) Чтобы [узнать, требуется ли Комнаты Microsoft Teams,](console.md)проверьте, требуются ли какие-либо другие обновления.

4. В консоли Configuration Manager  перейдите к пакету управления приложениями библиотеки программного обеспечения \>  \> и выберите **Создать пакет**.

5. Введите следующую информацию для создания пакета:
   -   Имя: **SRS версии 2 — пакет обновлений ОС**
   -   Производитель: **Корпорация Майкрософт**
   -   Версия: **1.0.0**
   -   Выберите этот **пакет содержит исходные файлы,** введите путь к папке Пакет обновлений ОС **SRS версии 2 и** затем выберите **Далее**.

6. Выберите **Не создавать программу**, а затем выберите **Далее**.

7. Просмотрите **страницу Подтверждение параметров** и выберите **Далее.**

8. Выберите **Закрыть**.

### <a name="create-the-root-certificate-package-optional"></a>Создание корневого пакета сертификата (необязательно)

Этот пакет создается для распространения корневого сертификата для устройств, которые не будут соединены с доменом Active Directory. Создайте этот пакет только в том случае, если применяются оба следующих условия:
-   Развертывание включает в себя локальное развертывание Lync или Skype для бизнеса Server.
-   Комнаты Microsoft Teams настроены для работы в группе, а не в составе домена.

1.  Скопируйте корневой сертификат в **папку SRS v2 — корневой пакет сертификата.**

2.  В консоли Configuration Manager  перейдите к пакету управления приложениями библиотеки программного обеспечения \>  \> и выберите **Создать пакет**.

3.  Введите следующую информацию для создания пакета:
    -   Имя: **SRS v2 — корневой пакет сертификата**
    -   Производитель: *название вашей организации*
    -   Версия: **1.0.0**
    -   Выберите этот **пакет содержит исходные** файлы, введите путь к папке **SRS v2 —** Корневой пакет сертификата, а затем выберите **Далее**.

4.  Выберите **Не создавать программу**, а затем выберите **Далее**.

5.  Просмотрите **страницу Подтверждение параметров** и выберите **Далее.**

6.  Выберите **Закрыть**.

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Создание пакета Комнаты Microsoft Teams развертывания

1.  Скачайте последнюю версию набора Комнаты Microsoft Teams **из** <https://go.microsoft.com/fwlink/?linkid=851168> и установите его на рабочий станции.

2.  Скопируйте содержимое **из C: \\ Program Files (x86) \\ Skype Room System Deployment Kit** в папку пакетов приложений **SRS v2 — SRS.**

3.  В консоли Configuration Manager  перейдите к пакету управления приложениями библиотеки программного обеспечения \>  \> и выберите **Создать пакет**.

4.  Введите следующую информацию для создания пакета:
    -   Имя: **SRS v2 — пакет приложения SRS**
    -   Производитель: **Корпорация Майкрософт**
    -   Версия: **3.1.104.0** (введите версию загруженного установного файла)
    -   Выберите этот **пакет содержит исходные** файлы, введите путь к папке Пакет приложений **SRS v2 – SRS,** а затем выберите **Далее**.
5.  Выберите **Не создавать программу**, а затем выберите **Далее**.

6.  Просмотрите **страницу Подтверждение параметров** и выберите **Далее.**

7.  Выберите **Закрыть**.

### <a name="create-the-computer-name-assignment-package"></a>Создание пакета назначения имени компьютера

1.  В **папке пакетов SRS v2 – Set-SRSComputerName создайте** новое HTML-приложение **с именем Set-SRSComputerName.hta.**

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
3.  В консоли Configuration Manager  перейдите к пакету управления приложениями библиотеки программного обеспечения \>  \> и выберите **Создать пакет**.

4.  Введите следующую информацию для создания пакета:

    -   Имя: **SRS v2 - Set-SRSComputerName Package**

    -   Производитель: **Корпорация Майкрософт**

    -   Версия: **1.0.0**

    -   Выберите этот **пакет содержит исходные файлы,** введите путь к **SRS v2 - Set-SRSComputerName Пакет** и выберите **Далее**.

5.  Выберите **Не создавать программу**, а затем выберите **Далее**.

6.  Просмотрите **страницу Подтверждение параметров** и выберите **Далее.**

7.  Выберите **Закрыть**.

### <a name="create-the-sysprep-package"></a>Создание пакета Sysprep

1. В **папке SRS v2 – Sysprep Package (Пакет Sysprep)** создайте новый XML-файл с именем **Unattend.xml.**

2. Скопируйте следующий текст в **Unattend.xml** файл. Кроме того, вы можете скачать Unattend.xml [здесь.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
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
3. В консоли Configuration Manager перейдите к **пакету управления** приложениями библиотеки программного обеспечения \>  \> и выберите **Создать пакет**.

4. Введите следующую информацию для создания пакета:
   -   Имя: **SRS v2 — пакет Sysprep**
   -   Производитель: **Корпорация Майкрософт**
   -   Версия: **1.0.0**
   -   Выберите этот **пакет содержит исходные** файлы, введите путь к папке **SRS v2 – Sysprep Package** и выберите **Далее**.
5. Выберите **Не создавать программу**, а затем выберите **Далее**.

6. Просмотрите **страницу Подтверждение параметров** и выберите **Далее.**

7. Выберите **Закрыть**.

### <a name="create-the-windows-10-enterprise-package"></a>Создание пакета Windows 10 Корпоративная

1.  Получите файл Windows 10 Корпоративная x64 и скопируйте **файл install.wim** в папку Windows 10 Корпоративная **операционных \\** систем.

2.  В консоли Configuration Manager перейдите в **библиотеку программного обеспечения** Операционные системы Изображения операционной системы , а затем \>  \> выберите Добавить **изображение операционной системы**.

3.  Укажите путь к только что **скопированную** копию WIM-файла и выберите **Далее.**

4.  **Обновив поле** Версия в соответствие с номером сборки изображения Windows 10 Корпоративная, а затем выберите **Далее**.

5.  Просмотрите **страницу Сведения** и выберите **далее**.

6.  Выберите **Закрыть**.

Дополнительные сведения см. в [теме Управление изображениями ОС с помощью Configuration Manager.](/configmgr/osd/get-started/manage-operating-system-images)

### <a name="create-surface-pro-device-driver-packages"></a>Создание Surface Pro драйвера устройства

Комнаты Microsoft Teams поддерживается как для Surface Pro, так и Surface Pro 4. Необходимо создать пакет драйвера для каждой модели Surface Pro в вашей среде.

> [!IMPORTANT]
> Драйверы должны быть совместимы с сборкой Windows 10 Корпоративная и пакетом Комнаты Microsoft Teams развертывания. Дополнительные сведения см. в дополнительных сведениях [Скачивание](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) последней версии постройки и драйверов для устройств Surface и [Настройка консоли.](console.md)

1.  Скачайте последние драйверы и программное обеспечение.
    -   Для Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Для Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498>

2.  Извлеките скачаный драйвер и программное обеспечение. Откройте окно командной подсказки и введите одну из следующих команд:
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro 4"`

3.  В консоли Configuration Manager перейдите к **драйверам операционных** систем библиотеки программного обеспечения \>  \> и выберите **Импорт драйвера**.

4.  Выберите Импортировать все драйверы по следующему сетевому пути **(UNC),** выберите папку-источник (например, C: \\ _Sources Drivers Surface Pro) и выберите \\ \\ **Далее**.

5.  На странице **Укажите сведения** об импортируемых драйверах выберите все указанные драйверы, а затем выберите Включить эти драйверы и разрешить их **установку компьютерам.**

6.  Выберите **Категории**, создайте новую категорию, которая соответствует модели Surface, выберите **ОК**, а затем выберите **Далее**.

7.  Выберите **Новый пакет**.

8.  Укажите имя пакета, которое соответствует модели Surface Pro, введите путь к папке для хранения файлов пакета драйвера, выберите **ОК**, а затем выберите **Далее**.

9.  **Убедитесь, что на** странице загрузки изображений не выбрано ни один загрузки изображений, а затем выберите **Далее**.

10. Выберите **Закрыть**.

11. Перейдите  в папку Драйверы операционных систем библиотеки программного обеспечения , выберите папку Создать папку и введите имя папки, которое соответствует модели Surface Pro, для которую вы только что \>  \> импортировали драйверы. **\>**

12. Переместить все импортируемые драйверы в только что созданную папку, чтобы упростить навигацию и работу.

> [!NOTE]
> Повторите эти же действия для Surface Pro моделей. Дополнительные сведения см. в [теме Управление драйверами в Configuration Manager.](/configmgr/osd/get-started/manage-drivers)

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Создание пакета Комнаты Microsoft Teams конфигурации

1.  В консоли Configuration Manager перейдите к **пакету управления** приложениями библиотеки программного обеспечения \>  \> и выберите **Создать пакет**.

2.  Введите следующую информацию для создания пакета:

    -   Имя: **SRS v2 — настройка пакета установки SRS**

    -   Производитель: **Корпорация Майкрософт**

    -   Версия: **1.0.0**

    -   Выберите этот **пакет содержит исходные** файлы, введите путь к **SRS v2 — Настройка папки SRS Setup** и затем выберите **Далее**.

3.  Выберите **Не создавать программу**, а затем выберите **Далее**.

4.  Просмотрите **страницу Подтверждение параметров** и выберите **Далее.**

5.  Выберите **Закрыть**.



## <a name="distribute-configuration-manager-packages"></a>Распространение пакетов Configuration Manager

Все пакеты должны быть распределены по серверам, для которые назначена роль точки распространения в иерархии Configuration Manager. Следуйте инструкциям ниже, чтобы начать распространение пакета.

1.  Распространение пакетов программного обеспечения.

    1.  В консоли Configuration Manager перейдите к пакету **управления** приложениями библиотеки \> **программного** \> **обеспечения**. Выберите все пакеты программного обеспечения, которые вы хотите распространить, и выберите **Распространение содержимого**.

    2.  Просмотрите список пакетов и выберите **Далее.**

    3.  Добавьте в список все серверы точек рассылки (или группы точек рассылки в зависимости от иерархии Configuration Manager), а затем выберите **Далее.**

    4.  Выберите **Далее**, а затем **закрыть**.

2.  Распространение пакетов драйверов.

    1.  В консоли Configuration Manager перейдите к пакету драйвера для операционной системы **библиотеки** \>  \> **программного обеспечения**. Выберите все пакеты драйверов, которые вы хотите распространить, и выберите **Распространение содержимого**.

    2.  Просмотрите список пакетов и выберите **Далее.**

    3.  Добавьте в список все серверы точек рассылки (или группы точек рассылки в зависимости от иерархии Configuration Manager), а затем выберите **Далее.**

    4.  Выберите **Далее**, а затем **закрыть**.

3.  Распространение пакетов операционной системы.

    1.  В консоли Configuration Manager перейдите к **рисункам операционной** системы библиотеки \>  \> **программного обеспечения**. Выберите все изображения операционной системы, которые вы хотите распространить, а затем выберите **Распространение содержимого**.

    2.  Просмотрите список пакетов и выберите **Далее.**

    3.  Добавьте в список все серверы точек рассылки (или группы точек рассылки в зависимости от иерархии Configuration Manager), а затем выберите **Далее.**

    4.  Выберите **Далее**, а затем **закрыть**.

> [!NOTE]
> Распространение пакета может занять некоторое время в зависимости от размера пакета, иерархии Configuration Manager, количества серверов точек рассылки и пропускной способности сети.
> 
> Перед началом развертывания нужно распределить все пакеты Комнаты Microsoft Teams разных единиц.
> 
> Состояние распространения пакета можно просмотреть в консоли Configuration  Manager в окте Мониторинг состояния содержимого \>  \> **о распространении.**

## <a name="configuration-manager-task-sequences"></a>Последовательности задач Configuration Manager

Последовательности задач с Configuration Manager используются для автоматизации действий по развертыванию образа операционной системы на целевом компьютере. Чтобы автоматически развернуть Комнаты Microsoft Teams, необходимо создать последовательность задач, которая ссылается на загрузку, используемую для запуска целевого компьютера Комнаты Microsoft Teams, образа операционной системы Windows 10 Корпоративная, которое вы хотите установить, и другого дополнительного содержимого, например других приложений или обновлений программного обеспечения.

### <a name="import-the-sample-task-sequence"></a>Импорт примера последовательности задач

Вы можете скачать и легко импортировать образец последовательности задач и настроить ее в нужное время.

1.  [**Скачайте**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) образец последовательности задач и скопируйте скачаный ZIP-файл в общую папку.
2.  В консоли Configuration Manager  перейдите в библиотеку программных систем Последовательности задач , а затем \>  \> выберите **Импорт последовательности задач**.

3.  Выберите **Обзор**, перейдите к общей папке, которая использовалась в шаге 1, выберите файл Комнаты Microsoft Teams развертывания **(EN-US).zip** и выберите **Далее**.

4.  Установите **для действия** действие **Создать,** а затем выберите **Далее**.

5.  Подтвердив параметры, а затем выберите **Далее**.

6.  Выберите **Закрыть**.

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Проверьте правильность связей пакетов ссылок с каждым этапом последовательности задач.

1. Выберите последовательность импортируемых задач и выберите **изменить**.

    Откроется редактор последовательностей задач, в который будут отображены все последовательные этапы, необходимые для развертывания и настройки Комнаты Microsoft Teams задач.

2. Выполните каждый шаг и выполните рекомендуемые обновления.

   1. **Перезапустить в Windows PE:** этот шаг перезагрузит компьютер, а затем Windows PXE. Для этого шага не требуется никаких изменений.

   2. **Диск раздела 0 – UEFI:** этот шаг протирает конфигурацию диска и создает разделы на основе настроенных параметров. Мы не рекомендуем вносить изменения в этот шаг.

   3. **Set SRS Computer Name**(Имя компьютера SRS). Этот этап включает HTML-приложение, которое предоставляет пользовательский интерфейс для установки имени компьютера Комнаты Microsoft Teams во время развертывания.
      -  Это необязательный шаг, но его можно отключить только в том случае, если вы хотите управлять именами компьютеров с помощью альтернативного процесса.
      -  Убедитесь, что выбран пакет **SRS v2 — Set-SRSComputerName.** Если это не так, перейдите к пакету и выберите его.

   4. **Применить операционную** систему: на этом шаге указаны изображение операционной системы, которое нужно развернуть, и неотвеченный файл ответа Sysprep.
      -  Убедитесь, что Windows 10 Корпоративная выбран правильный файл образа операционной системы.
      -  Убедитесь, что включено использование неотвеченного или **Sysprep-файла** ответа для настраиваемой установки и выбран пакет **SRS v2 — Sysprep.** Также убедитесь, **что** для имени файла **установленоunattend.xml**.

   5. **Применить Windows Параметры:** на этом этапе собираются сведения о Windows установке.
      -  У вас есть сведения о лицензировании и регистрации, включая ключ продукта, пароль учетной записи локального администратора и часовой пояс (в зависимости от потребностей).

   6. **Применение сетевого Параметры:** на этом этапе можно указать имя группы или домена Active Directory и подразделения.
      > [!NOTE]
      > Рекомендации [Skype](domain-joining-considerations.md) по развертыванию Комнаты Microsoft Teams как участников домена Actve Directory см. в Skype домене Системы комнат.
   7. **Применение драйверов:** Этот шаг и его подпрограммы используются для развертывания соответствующих драйверов устройств и программного обеспечения на основе Surface Pro модели. Обновив каждый шаг, укажите соответствующий пакет драйвера, связанный с этим развертыванием.
      -   Каждый пакет драйвера настроен для использования Windows WMI для развертывания соответствующих драйверов и постройки на основе модели Surface Pro управления.
      -   Настоятельно рекомендуем не изменять конфигурацию этих драйверов, иначе развертывание может привести к сбойу.

   8. **Настройка Windows и Configuration Manager.** На этом этапе развертывается и настраивается клиент Configuration Manager. Обновив этот шаг, укажите встроенный пакет клиента Configuration Manager.

   9. **Установка корневого** сертификата. Этот шаг распространяет корневой сертификат для устройств, не присоединиваых к домену, и поэтому является необязательным и по умолчанию отключен.
      -   В этом случае следует развернуть корневой сертификат в Комнаты Microsoft Teams единицам.
      -   Если вам нужно сделать это, убедитесь, что выбраны **SRS v2 —** пакет корневого сертификата и Отключение перенаправления **64-битной** файловой системы.

   10. **Установка и настройка** агента мониторинга. На этом этапе устанавливается 64-битная версия агента Microsoft Azure Monitor и настраивается подключение агента к рабочей области аналитики журналов.
       -   Этот шаг по умолчанию отключен. Этот шаг можно включить только в том случае, если вы собираетесь использовать агент мониторинга для отслеживания состояния Комнаты Microsoft Teams единиц.
       -   Отредактируете этот шаг и обновите параметры командной строки, указав свой **ИД рабочей** области и ключ **рабочей области.**
       -   Дополнительные [сведения о том,](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) как получить ИД рабочей области набора операций и первичный ключ, см. в настройках тестовых устройств для мониторинга Azure.
       -   Убедитесь, что выбраны **SRS v2 – Microsoft Monitoring Agent Пакет** и Отключить **64-битную** файловую систему.
       -   Дополнительные сведения о мониторинге состояния развертывания Комнаты Microsoft Teams см. в Комнаты Microsoft Teams управления проектами с помощью [Azure Monitor](azure-monitor-plan.md), Развертывание управления Комнаты Microsoft Teams с помощью [Azure Monitor](azure-monitor-deploy.md) и Управление устройствами Комнаты Microsoft Teams с помощью [Azure Monitor.](azure-monitor-manage.md)

   11. **Копирование SRS файлов конфигурации v2.** На этом этапе необходимые файлы настройки и конфигурации копируется из Комнаты Microsoft Teams на локальный жесткий диск. Для этого шага не требуется никаких настроек.
       -   Убедитесь, что выбраны **SRS v2 — пакет** приложений SRS и Отключение перенаправления **64-битной** файловой системы.

   12. **Install-SRSv2-OS-Updates:** на этом этапе развертываются все обязательные обновления операционной системы, необходимые для Комнаты Microsoft Teams развертывания. Выполните указанные ниже действия.
       -   Чтобы [узнать, какие обновления требуются, Комнаты Microsoft Teams](console.md) настроить консоль управления.
       -   Убедитесь, что пакет **обновлений ОС SRS версии 2** – OS содержит все необходимые обновления.
       -   Убедитесь, что выбран пакет **обновлений SRS версии 2** – OS.
       -   Убедитесь в том, что для политики выполнения PowerShell задано **"Обход"**.

   13. **Перезагрузить** компьютер: этот шаг перезагрузит компьютер после установки обязательных обновлений операционной системы. Для этого шага не требуется никаких настроек.

   14. **Настройка Windows** компонентов: на этом этапе настраиваются необходимые Windows компонентов. Для этого шага не требуется никаких настроек.

   15. **Перезагрузить** компьютер: этот шаг перезагрузит компьютер после Windows настройки функций. Для этого шага не требуется никаких настроек.

   16. **Добавить локального пользователя** Skype: на этом этапе создается локализованная учетная запись Skype, которая используется для автоматического Windows и запуска Комнаты Microsoft Teams приложения. Этот шаг не связан с программным пакетом, и для него не требуется его настройка.

   17. **Настройка приложения SRS.** На этом этапе Комнаты Microsoft Teams установки приложений для следующей загрузки операционной системы.
       -   Убедитесь, что выбраны **SRS v2 —** Настройка пакета установки SRS и Отключение перенаправления **64-битной** файловой системы.

> [!IMPORTANT]
> Очень важно, чтобы последовательность действий задачи была в предоставленной последовательности. Изменение порядка шагов или настройка дополнительных действий может привести к разрыву развертывания.
>
> **Настройка приложения SRS** должна быть последним этапом в последовательности задач, в противном случае развертывание может привести к сбойу.

### <a name="create-deployment-for-the-task-sequence"></a>Создание развертывания для последовательности задач

1. Выберите последовательность задач и выберите **развернуть**.

2. Чтобы **выбрать целевую** коллекцию для развертывания, выберите обзор.

3. Выберите **Все неизвестные компьютеры,** а затем **ОК**.

4. Нажмите **Далее**.

5. В **списке** **Назначение** выберите доступен.

6. В списке Сделать доступным  для следующего списка выберите только мультимедиа и **PXE,** а затем выберите **Далее.**
   > [!WARNING]
   > Очень важно, чтобы для **назначения** было установлено значение **Доступен**. Убедитесь, что **для** назначения **не установлено** **обязательное .** Кроме того, убедитесь, что в области Сделать доступными для следующих сетей выбраны только мультимедиа **и** **PXE.**
   >
   > Установка этих значений для других параметров может привести к тому, что все компьютеры получат изображение Комнаты Microsoft Teams развертывания при загрузке.
7. Не укажите расписание и выберите **Далее.**

8. Не изменяя ничего в разделе **Пользовательский интерфейс,** выберите **Далее**.

9. Не изменяя ничего в разделе **Оповещения,** и выберите **Далее**.

10. Не изменяя ничего в разделе **Точки распространения,** выберите **Далее**.

11. Подтвердив параметры, а затем выберите **Далее**.

12. Выберите **Закрыть**.

**Проверка и устранение неполадок решения**

После завершения Microsoft Endpoint Configuration Manager задач необходимо выполнить тестовый запуск, чтобы проверить, можно ли развернуть и Комнаты Microsoft Teams задач.

1.  Подключение тестового устройства к проводной сети с помощью одного из поддерживаемых адаптеров Ethernet или док-станции Surface. Если функциональность загрузки PXE еще не настроена для вашей среды, вы [](/configmgr/osd/deploy-use/create-bootable-media) можете использовать изображение загрузки на USB-устройстве флэш-памяти, созданном ранее, для загрузки с USB и подключения к Configuration Manager.

2.  Доступ к программному пошиву и инициировать загрузку PXE:

    1.  Убедитесь, что устройство Surface отключено.

    2.  Нажмите и удерживайте **кнопку "Вверх** громкости".

    3.  Нажмите и отпустите **кнопку** Питания.

    4.  Когда устройство начнет загрузку, отпустите **кнопку "Вверх** громкости".

    5.  Выберите **Конфигурация загрузки**.

    6.  Выполните одно из следующих действий.

        -   Выберите **загрузку PXE** и перетащите ее в верхнюю часть списка. Кроме того, вы можете провести пальцем влево по сетевому адаптеру, чтобы сразу же загрузить устройство. Это не повлияет на порядок загрузки.
        -   Выберите USB-устройство флэш-памяти, на которое вмещается загрузочный носитор.

3.  Выберите **Выход**, а затем **перезапустите**.

4.  При запросе выберите Ввод **для службы** загрузки сети.

5.  Windows Pe загрузит в память, и запустится мастер последовательностей задач. Чтобы **продолжить, выберите** Далее.

6.  Выберите последовательность задач, которую вы импортировали ранее, а затем выберите **Далее.**

7.  После настройки диска вам будет предложено указать имя компьютера для устройства. В пользовательском интерфейсе будет отображаться рекомендуемое имя компьютера в зависимости от серийного номера Surface Pro устройства. Вы можете принять предложенное имя или указать новое. Следуйте инструкциям на экране назначения имени компьютера. Когда вы **наберетсяе Принять,** начнется развертывание.

8.  Остальная часть процесса развертывания является автоматической, и пользователю больше не нужно вводить данные.

9.  После завершения настройки устройства в последовательности задач развертывания вы увидите следующий экран конфигурации с запросом на настройку Комнаты Microsoft Teams приложения.

    ![Экран начальной настройки для Комнаты Microsoft Teams приложения.](../media/room-systems-scale-image2.png)

10.  Подключите Surface Pro к консоли Комнаты Microsoft Teams и настройте параметры приложения.

11.  Проверьте возможности, перечисленные в Комнаты Microsoft Teams [справки,](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) на развернутом устройстве.


Чтобы устранить неполадки при установке, проверьте **файл SMSTS.log,** в котором регистрются все действия, выполненные в последовательности задач Configuration Manager.

Файл SMSTS.log хранится по одному из нескольких путей в зависимости от этапа сборки. В таблице ниже идентифицировать путь к файлу SMSTS.log.


| **Этап развертывания**                                                            | **Путь в журнале последовательностей задач**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| Формат WinPE до HDD                                                        | X: \\ Windows \\ \\ SMS-сообщения Temp.log \\             |
| WinPE после формата HDD                                                         | В. \\ _SMSTaskSequence \\ Журнал \\ SMS-сообщений \\ smstslog.log    |
| Развернута операционная система до установки агента Configuration Manager | в: \\ _SMSTaskSequence \\ Журнал \\ SMS-сообщений \\ smstslog.log    |
| Развернуты операционная система и агент Configuration Manager                   | %windir% \\ System32 \\ ccm \\ logs \\ Smstslog \\ smstslog smsts.log |
| Последовательность задач завершена                                                | %windir% \\ System32 \\ ccm \\ logs \\ smsts.log           |

> [!TIP]
> Вы можете в любой момент выбрать **F8** в последовательности задач, чтобы открыть консоль, а затем получить доступ к файлу SMSTS.log.

Чтобы устранить проблемы с загрузкой PXE, проверьте два файла журнала на сервере Configuration Manager, которые являются специфическими для действий PXE:

-   **Pxecontrol.log**, расположенный в каталоге журналов установки Configuration Manager

-   **Smspxe.log**, расположенный в каталоге MP точки управления Configuration Manager

Полный список файлов журналов, которые можно использовать для дальнейшего устранения неполадок при установке Configuration Manager, см. в Microsoft Endpoint Configuration Manager [журнале.](/configmgr/core/plan-design/hierarchy/log-files)
