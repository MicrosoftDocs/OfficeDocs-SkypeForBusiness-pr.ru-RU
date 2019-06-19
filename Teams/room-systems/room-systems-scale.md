---
title: Развертывание комнат Microsoft Teams с помощью System Center Configuration Manager
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection: M365-voice
description: Ознакомьтесь с этой статьей, чтобы узнать о том, как развертываются комнаты Microsoft Teams при больших масштабах развертывания.
ms.openlocfilehash: 9a5bfd888d3d70703245841a8744449854c6ffb8
ms.sourcegitcommit: 3197f3ffca2b2315be9fd0c702ccc8c87383c893
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2019
ms.locfileid: "35062373"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a>Развертывание комнат Microsoft Teams с помощью System Center Configuration Manager

В этой статье приведены все необходимые сведения для создания развертывания комнат Microsoft Teams с помощью System Center Configuration Manager.

Благодаря простым в использовании методам, предоставляемым System Center Configuration Manager, вы можете развернуть операционную систему и другие приложения на нескольких целевых устройствах.

Используйте описанный ниже подход, чтобы пошагово настроить конфигурацию Configuration Manager, и настройте образцы пакетов и сценарии, предоставленные в этом руководстве для вашей организации.

![Процесс развертывания комнат Microsoft Teams с помощью Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Это решение было проверено только с развертываниями на основе Surface Pro. Следуйте указаниям производителя для конфигураций, которые не основаны на Surface Pro.

## <a name="validate-prerequisites"></a>Проверка предварительных требований

Для развертывания комнат Microsoft Teams с помощью Configuration Manager убедитесь, что выполняются следующие необходимые условия и требования.

### <a name="system-center-configuration-manager-requirements"></a>Требования System Center Configuration Manager

-   Версия System Center Configuration Manager должна составлять не менее 1706 или выше. Рекомендуем использовать 1710 или более поздней версии. Чтобы узнать о версиях Windows 10, поддерживаемых Configuration Manager, ознакомьтесь со статьей [поддержки Windows 10 в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) .

-   Должна быть установлена поддерживаемая версия комплекта средств для развертывания и оценки Windows (ADK) для Windows 10. Ознакомьтесь с версиями [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) , которые можно использовать с различными версиями Configuration Manager, и убедитесь в том, что развертывание включает соответствующую версию.

-   Серверам системы сайта должна быть назначена роль точки распространения, и для [поддержки удаленной загрузки для развертывания в среде предзагрузочной среды (PXE)](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) необходимо включить образы загрузки. Если поддержка PXE не включена, вы можете использовать [загрузочный носитель](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) для развертывания.

-   Учетная запись сетевого доступа должна быть настроена для поддержки новых сценариев развертывания компьютера (исходного состояния). Дополнительные сведения о настройке учетной записи для доступа к сети можно найти [в статье Управление учетными записями для доступа к содержимому в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

-   Мы рекомендуем включить [поддержку многоадресной рассылки](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), если вы наверняка хотите развернуть один и тот же образ Microsoft Teams в нескольких блоках одновременно.

### <a name="networking-requirements"></a>Требования к сети

-   В сети должен быть сервер DHCP (Dynamic Host Configuration Protocol), настроенный для автоматического распространения IP-адресов в подсети, в которых будут развернуты единицы комнаты Microsoft Teams.

    > [!NOTE]
    > Продолжительность аренды DHCP должна быть больше, чем продолжительность развертывания образа. В противном случае развертывание может завершиться ошибкой.

-   Сеть, в том числе коммутаторы и виртуальные ЛВС (VLAN), должна быть настроена для поддержки PXE. За дополнительными сведениями о модулях поддержки IP и конфигурации PXE обратитесь к поставщику сети. Кроме того, если поддержка PXE не включена, вы можете использовать [загрузочный носитель](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) для развертывания.

    > [!NOTE]
    > Для устройств Surface Pro Загрузка из сети (PXE) поддерживается только при использовании адаптера Ethernet или стыковочных станций от корпорации Майкрософт. Сторонние адаптеры Ethernet не поддерживают загрузку PXE с Surface Pro. Дополнительные сведения см. в разделе [адаптеры Ethernet и развертывание Surface](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a>Настройка System Center Configuration Manager для развертывания операционной системы

В этой статье предполагается, что у вас уже есть работоспособное развертывание System Center Configuration Manager, а не все этапы, необходимые для развертывания и настройки Configuration Manager с нуля. [Документация и руководство по конфигурации](https://docs.microsoft.com/sccm/) в System Center Configuration Manager — это отличный ресурс. Если вы еще не развернули Диспетчер конфигураций, мы рекомендуем вам приступить к этим ресурсам.

Чтобы убедиться в правильности настройки функций развертывания операционной системы (OSD), выполните указанные ниже инструкции.

### <a name="validate-and-upgrade-configuration-manager"></a>Проверка и обновление Configuration Manager

1.  На консоли Configuration Manager перейдите в раздел **Администрирование** \> **обновлений и обслуживание**.

2.  Проверьте установленную сборку и применимые обновления, которые еще не установлены.

3.  Ознакомьтесь со [службой поддержки Windows 10 в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Если вам нужно обновить развертывание, выберите обновление, которое вы хотите установить, и нажмите кнопку **скачать**.

4.  После завершения загрузки выберите обновление и щелкните **установить пакет обновления**.

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Настройка точек распространения для поддержки PXE и многоадресной рассылки

1.  На консоли Configuration Manager перейдите в раздел **точки распространения** **администрирования** \> .

2.  Выберите сервер точки распространения, который будет обслуживать развертывание комнат Microsoft Teams, и нажмите кнопку **Свойства**.

3.  Откройте вкладку **PXE** и убедитесь, что включены следующие параметры:
    -   Включение поддержки PXE для клиентов
    -   Разрешить этой точке распространения отвечать на входящие запросы PXE
    -   Включение неизвестной поддержки компьютера

4.  *Необязательно:* Чтобы включить поддержку многоадресной рассылки **** , откройте вкладку Многоадресная рассылка и убедитесь, что включены следующие параметры:
    -   Одновременная отправка данных нескольким клиентам с помощью многоадресной рассылки
    -   Настройка диапазона UDP-портов согласно рекомендациям сетевой группы

### <a name="configure-the-network-access-account"></a>Настройка учетной записи доступа к сети

1.  На консоли Configuration Manager перейдите на \> **сайт** **конфигурации сайта** **администрирования** \> , а затем выберите сайт.

2.  В группе **Параметры** выберите пункт Настройка \> **распространения программного обеспечения** **компонентов сайта** .

3.  Откройте вкладку **учетная запись сетевого доступа** . Настройте одну или несколько учетных записей, а затем нажмите кнопку **ОК**.

> [!NOTE]
> Для учетных записей не требуются никакие специальные права, Кроме того, чтобы **получить доступ к этому компьютеру прямо из сети** на сервере точки распространения. Будет подходящимся универсальная учетная запись пользователя домена. Дополнительные сведения [можно найти в разделе Управление учетными записями для доступа к содержимому в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

### <a name="configure-a-boot-image"></a>Настройка загрузочного образа

1.  В консоли Configuration Manager перейдите в раздел **загрузочные образы** **операционной системы** \> для **разработчиков программного обеспечения** \> .

2.  Выберите пункт **загрузочный образ (x64)** и нажмите кнопку **свойства**.

3.  Откройте вкладку **источник данных** и включите **развертывание этого загрузочного образа из точки распространения с поддержкой PXE**.

4.  Выберите вкладку **Дополнительные компоненты** , чтобы установить необходимые компоненты:

    1.  Щелкните значок звездочки и выполните поиск по запросу **HTML (WinPE-HTA)**

    2.  Нажмите кнопку **ОК** , чтобы добавить поддержку HTML-приложений в загрузочный образ.

5.  *Необязательно:* Чтобы настроить взаимодействие с развертыванием, откройте вкладку **Настройка** .
    -   Включите **поддержку команд (только для проверки)** , если вы хотите получать доступ к командной строке во время развертывания. Если этот параметр включен, вы можете запустить командную команду, выбрав **F8** в любое время развертывания.
    -   Вы также можете указать собственное фоновое изображение, которое будет отображаться во время развертывания. Чтобы задать изображение, включите параметр **задать настраиваемый файл фонового изображения (путь UNC** и выберите фоновый рисунок).

6.  При появлении запроса выберите **Да** , чтобы распространить обновленный образ загрузки на точки распространения.

Дополнительные сведения можно найти [в разделе Управление загрузочными образами с помощью System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).

> [!NOTE]
> Вы можете создать загрузочный USB-носитель для запуска развертываний на основе последовательности задач Configuration Manager для сред без поддержки PXE. Загрузочный носитель включает только загрузочный образ, необязательные команды предзапуска и их обязательные файлы, а также двоичные данные Configuration Manager для поддержки загрузки в Windows PE и подключения к Configuration Manager для оставшейся части процесса развертывания. Дополнительные сведения [можно найти в разделе Создание загрузочного носителя](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).

## <a name="create-configuration-manager-packages"></a>Создание пакетов Configuration Manager

> [!IMPORTANT]
> Обязательная версия операционной системы для каждой версии установщика SRS меняется при каждом выпуске MSI-файла. Чтобы определить самую подходящее версию операционной системы для данного MSI-файла, запустите сценарий настройки консоли один раз. Дополнительные сведения можно найти в разделе [развертывание комнат Microsoft Teams с помощью System Center Configuration Manager](room-systems-scale.md).

Для развертывания и настройки единиц измерения в Microsoft Teams Configuration Manager требуется несколько пакетов.

Вам необходимо создать и настроить указанные ниже пакеты, а затем распространить их на системы сайта Configuration Manager, которым назначена роль сервера точки распространения.

| **Имя пакета**                     | **Тип**               | **Описание**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 — Пакет приложения SRS     | Пакет программного обеспечения       | Пакет для пакета развертывания комнат Microsoft Teams                                      |
| SRS v2 — Пакет Sysprep             | Пакет программного обеспечения       | Упаковка для настраиваемого файла Unattend. XML для настройки комнат в Microsoft Teams            |
| Пакет Срскомпутернаме v2-Set- | Пакет программного обеспечения       | Упаковка для приложения HTML (HTA) для присвоения имени компьютера во время развертывания    |
| SRS v2 — Настройка настройки SRS         | Пакет программного обеспечения       | Пакет для настройки развертывания приложения "комнаты Microsoft Teams"                          |
| Пакет обновлений для SRS v2-OS          | Пакет программного обеспечения       | Пакет для развертывания обязательных обновлений операционной системы                                      |
| SRS v2 — Пакет корневых сертификатов    | Пакет программного обеспечения       | Дополнительный пакет для развертывания корневого сертификата (не требуется для устройств, подключенных к домену)  |
| SRS v2 — Пакет агента наблюдения (Майкрософт) | Пакет программного обеспечения       | Дополнительный пакет для развертывания и настройки агента Microsoft Operations Management Suite|
| Фоновый пакет для SRS v2-WinPE    | Пакет программного обеспечения       | Упаковка для настраиваемого фонового изображения для использования с образами загрузки                           |
| Windows 10 корпоративный                | Образ операционной системы | Пакет для установочного файла операционной системы (Install. wim)                          |
| Surface Pro                          | Пакет драйвера         | Упаковка драйверов устройств и встроенного по для Microsoft Surface Pro                     |
| Surface Pro 4                        | Пакет драйвера         | Упаковка драйверов устройств и встроенного по для Microsoft Surface Pro 4                   |

Дополнительные сведения можно найти [в разделе пакеты и программы в System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).

### <a name="create-folders-for-the-package-source-files"></a>Создание папок для исходных файлов пакета

Configuration Manager требует, чтобы файлы исходного кода были упорядочены в определенной структуре папок при их создании и обновлении.

Создайте следующую структуру папок на сайте центра администрирования System Center Configuration Manager или на основном сайте или на сервере общего доступа, который вы используете для размещения исходных файлов пакетов.

-   SRS v2 — Пакет агента наблюдения (Майкрософт)
-   Пакет обновлений для SRS v2-OS
-   SRS v2 — Пакет корневых сертификатов
-   Пакет Срскомпутернаме v2-Set-
-   SRS v2 — Пакет приложения SRS
-   SRS v2 — Настройка настройки SRS
-   SRS v2 — Пакет Sysprep
-   Дисков
    -   Surface Pro
    -   Surface Pro 4
-   Операционные системы
    -   Windows 10 корпоративный

> [!TIP]
> Кроме того, вы можете [скачать](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) и использовать ZIP-файл, содержащий структуру папок для пакетов, необходимые сценарии и шаблон последовательности задач, которые нужно импортировать.

### <a name="create-the-monitoring-agent-package"></a>Создание пакета агента наблюдения

1. Скачайте агент мониторинга из <https://go.microsoft.com/fwlink/?LinkId=828603>.

2. Чтобы извлечь пакет в папку **пакета SRS v2 — Microsoft Monitoring Agent** , откройте окно командной строки и введите **MMASetup-AMD64. exe/c:** в командной строке.

3. На консоли Configuration Manager перейдите в раздел \> **пакеты** \> **управления приложениями** **библиотеки программного обеспечения** , а затем выберите команду **создать пакет**.

4. Введите указанные ниже сведения, чтобы создать пакет.

   - Name<strong>(имя): SRS v2 — Пакет агента наблюдения (Майкрософт)</strong>

   - Производитель<strong>: Корпорация Майкрософт</strong>

   - Version<strong>: 8.1.11081.0</strong> (введите версию скачанного установочного файла)

   - Установите флажок **Этот пакет включает исходные файлы** , введите путь к папке, которая входит в **состав пакета обновления SRS v2 — Microsoft Monitoring Agent** , и нажмите кнопку **Далее**.

5. Установите переключатель не **создавать программу**, а затем нажмите кнопку **Далее**.

6. Просмотрите страницу **Подтверждение параметров** и нажмите кнопку **Далее**.

7. Нажмите кнопку **Закрыть**.

### <a name="create-the-operating-system-updates-package"></a>Создание пакета обновлений операционной системы

1. В папке **пакета обновления SRS v2-OS** создайте новый сценарий PowerShell с именем **Install-SRSv2-OS-Updates. ps1**.

2. Скопируйте приведенный ниже сценарий в сценарий **Install-SRSv2-OS-Updates. ps1** . Кроме того, вы можете скачать сценарий Install-SRSv2-OS-Updates. ps1 [отсюда](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
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
3. Скачайте в ту же папку обязательные пакеты обновления для Windows.
   > [!NOTE]
   > На момент публикации этой статьи требовалось только [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) . Установите флажок [настроить консоль комнат Microsoft Teams](console.md), чтобы узнать, требуются ли какие-либо другие обновления.

4. На консоли Configuration Manager перейдите в раздел \> **пакеты** \> **управления приложениями** **библиотеки программного обеспечения** , а затем выберите команду **создать пакет**.

5. Введите указанные ниже сведения, чтобы создать пакет.
   -   Name (имя): **SRS v2 — пакет обновлений операционной системы**
   -   Производитель: Корпорация **Майкрософт**
   -   Версия: **1.0.0**
   -   Установите флажок **Этот пакет включает исходные файлы** , введите путь к папке **пакета обновления SRS v2-OS** , а затем нажмите кнопку **Далее**.

6. Установите переключатель не **создавать программу**, а затем нажмите кнопку **Далее**.

7. Просмотрите страницу **Подтверждение параметров** и нажмите кнопку **Далее**.

8. Нажмите кнопку **Закрыть**.

### <a name="create-the-root-certificate-package-optional"></a>Создание пакета корневого сертификата (необязательно)

Этот пакет создается для распространения корневого сертификата для устройств, которые не будут присоединены к домену Active Directory. Этот пакет следует создавать только в том случае, если действуют оба указанных ниже условия.
-   Развертывание включает в себя локальный Lync или Skype для бизнеса Server.
-   Элементы комнат Microsoft Teams настроены для работы в Рабочей группе, а не участника домена.

1.  Скопируйте корневой сертификат в папку " **SRS v2 – корневой пакет сертификатов** ".

2.  На консоли Configuration Manager перейдите в раздел \> **пакеты** \> **управления приложениями** **библиотеки программного обеспечения** , а затем выберите команду **создать пакет**.

3.  Введите указанные ниже сведения, чтобы создать пакет.
    -   Name (имя): **SRS v2 — Пакет корневого сертификата**
    -   Изготовитель: *название своей организации*
    -   Версия: **1.0.0**
    -   Установите флажок **Этот пакет включает исходные файлы** , введите путь к папке с пакетом **SRS v2 – корневой сертификат** и нажмите кнопку **Далее**.

4.  Установите переключатель не **создавать программу**, а затем нажмите кнопку **Далее**.

5.  Просмотрите страницу **Подтверждение параметров** и нажмите кнопку **Далее**.

6.  Нажмите кнопку **Закрыть**.

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Создание комплекта для развертывания комнат Microsoft Teams

1.  Скачайте последнюю версию комплекта для **развертывания комнат Microsoft Teams** из <https://go.microsoft.com/fwlink/?linkid=851168>и установите ее на рабочую станцию.

2.  Скопируйте содержимое из **файла C:\\Program Files (x86\\) из набора средств для развертывания системы комнаты Skype** в папку **пакета приложения SRS v2 — SRS** .

3.  На консоли Configuration Manager перейдите в раздел \> **пакеты** \> **управления приложениями** **библиотеки программного обеспечения** , а затем выберите команду **создать пакет**.

4.  Введите указанные ниже сведения, чтобы создать пакет.
    -   Name (имя): **SRS v2 — Пакет приложения SRS**
    -   Производитель: Корпорация **Майкрософт**
    -   Version: **3.1.104.0** (введите версию скачанного установочного файла)
    -   Установите флажок **Этот пакет включает исходные файлы** , введите путь к папке **SRS v2 — Пакет приложения SRS** и нажмите кнопку **Далее**.
5.  Установите переключатель не **создавать программу**, а затем нажмите кнопку **Далее**.

6.  Просмотрите страницу **Подтверждение параметров** и нажмите кнопку **Далее**.

7.  Нажмите кнопку **Закрыть**.

### <a name="create-the-computer-name-assignment-package"></a>Создание пакета назначения имени компьютера

1.  В папке **пакета SRS v2-Set-срскомпутернаме** создайте новое HTML-приложение с именем **Сет-срскомпутернаме. hta** .

2.  Скопируйте приведенный ниже сценарий в файл **Сет-срскомпутернаме. hta** . Кроме того, вы можете загрузить файл Сет-срскомпутернаме. hta [отсюда](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
    ```
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
3.  На консоли Configuration Manager перейдите в раздел \> **пакеты** \> **управления приложениями** **библиотеки программного обеспечения** , а затем выберите команду **создать пакет**.

4.  Введите указанные ниже сведения, чтобы создать пакет.

    -   Name (имя): " **SRS v2 — Установка и срскомпутернаме** "

    -   Производитель: Корпорация **Майкрософт**

    -   Версия: **1.0.0**

    -   Установите флажок **Этот пакет включает исходные файлы** , введите путь к папке **пакета SRS v2-Set-срскомпутернаме** , а затем нажмите кнопку **Далее**.

5.  Установите переключатель не **создавать программу**, а затем нажмите кнопку **Далее**.

6.  Просмотрите страницу **Подтверждение параметров** и нажмите кнопку **Далее**.

7.  Нажмите кнопку **Закрыть**.

### <a name="create-the-sysprep-package"></a>Создание пакета Sysprep

1. В папке **пакета SRS v2 – Sysprep** создайте новый XML-файл с именем **Unattend. XML** .

2. Скопируйте приведенный ниже текст в файл **Unattend. XML** . Кроме того, вы можете загрузить файл Unattend. XML [отсюда](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
   ```
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
3. На консоли Configuration Manager перейдите в раздел \> **пакеты** \> **управления приложениями** **библиотеки программного обеспечения** , а затем выберите команду **создать пакет**.

4. Введите указанные ниже сведения, чтобы создать пакет.
   -   Name **(имя): SRS v2 — Пакет Sysprep**
   -   Производитель: Корпорация **Майкрософт**
   -   Версия: **1.0.0**
   -   Установите флажок **Этот пакет включает исходные файлы** , введите путь к папке **пакета SRS v2 – Sysprep** и нажмите кнопку **Далее**.
5. Установите переключатель не **создавать программу**, а затем нажмите кнопку **Далее**.

6. Просмотрите страницу **Подтверждение параметров** и нажмите кнопку **Далее**.

7. Нажмите кнопку **Закрыть**.

### <a name="create-the-windows-10-enterprise-package"></a>Создание пакета Windows 10 Корпоративная

1.  Получите носитель с Windows 10 корпоративный x64 и скопируйте файл **install. wim** в папку **Windows 10 Корпоративная\\для операционной системы** .

2.  В консоли Configuration Manager перейдите в раздел **** \> **** **библиотеки** \> программного обеспечения операционной системы и выберите пункт **Добавить образ операционной системы**.

3.  Укажите путь к файлу **install. wim** , который вы только что скопировали, и нажмите кнопку **Далее**.

4.  Обновите поле **Version** в соответствии с номером сборки для корпоративного образа Windows 10, а затем нажмите кнопку **Далее**.

5.  Ознакомьтесь со страницей **сведения** и нажмите кнопку **Далее**.

6.  Нажмите кнопку **Закрыть**.

Дополнительные сведения можно найти [в разделе Управление образами операционной системы с помощью System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).

### <a name="create-surface-pro-device-driver-packages"></a>Создание пакетов драйверов устройств Surface Pro

Комнаты Microsoft Teams поддерживаются как для Surface Pro, так и для Surface Pro 4. Для каждой модели Pro Surface, имеющейся в вашей среде, нужно создать пакет драйверов.

> [!IMPORTANT]
> Драйверы должны быть совместимы с версией Windows 10 Корпоративная сборка и пакетом развертывания комнат Microsoft Teams. Дополнительные сведения можно найти [в разделе Загрузка новейшего встроенного по и драйверов для устройств Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) и [Настройка консоли](console.md).

1.  Загрузите последние версии драйверов и встроенного по.
    -   Для Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Для Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498>

2.  Извлеките загруженный драйвер и встроенное по. Откройте окно командной строки и введите в командной строке одну из указанных ниже команд.
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  На консоли Configuration Manager перейдите в раздел **драйверы** **операционной системы** \> **библиотеки** \> , а затем выберите команду **импортировать драйвер**.

4.  Выберите **импортировать все драйверы в следующем сетевом пути (UNC)**, выберите исходную папку (например, C\\: _саурцес\\Drivers\\Pro), а затем нажмите кнопку **Далее**.

5.  На странице **Определение сведений для импортированных драйверов** выберите все указанные в списке драйверы и установите флажок **включить эти драйверы и разрешить компьютерам устанавливать их**.

6.  Выберите **категории**, создайте новую категорию, соответствующую модели Surface, нажмите кнопку **ОК**, а затем нажмите кнопку **Далее**.

7.  Выберите команду **создать пакет**.

8.  Укажите имя пакета, соответствующее модели Surface Pro, введите путь к папке, в которой нужно сохранить файлы пакета драйверов, нажмите кнопку **ОК**, а затем нажмите кнопку **Далее**.

9.  На странице **образы загрузки** убедитесь, что не выбраны образы загрузки, а затем нажмите кнопку **Далее**.

10. Нажмите кнопку **Закрыть**.

11. Перейдите к разделу **драйверы** \> **операционной системы** \> **библиотеки программного обеспечения** , выберите пункт ** \> создать**папку и введите имя папки, соответствующей модели Surface Pro, для которой вы только что импортировали драйверы.

12. Переместите все импортированные драйверы в созданную папку, чтобы упростить навигацию и операцию.

> [!NOTE]
> Повторите эти действия для других моделей Surface Pro, которые вы можете использовать. Дополнительные сведения можно найти [в разделе Управление драйверами в System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Создание пакета конфигурации комнат Microsoft Teams

1.  На консоли Configuration Manager перейдите в раздел \> **пакеты** \> **управления приложениями** **библиотеки программного обеспечения** , а затем выберите команду **создать пакет**.

2.  Введите указанные ниже сведения, чтобы создать пакет.

    -   Name (имя): **SRS v2 — Настройка пакета установки SRS**

    -   Производитель: Корпорация **Майкрософт**

    -   Версия: **1.0.0**

    -   Установите флажок **Этот пакет включает исходные файлы** , введите путь к службе **SRS v2 — Настройка папки настройки SRS** и нажмите кнопку **Далее**.

3.  Установите переключатель не **создавать программу**, а затем нажмите кнопку **Далее**.

4.  Просмотрите страницу **Подтверждение параметров** и нажмите кнопку **Далее**.

5.  Нажмите кнопку **Закрыть**.



## <a name="distribute-configuration-manager-packages"></a>Распространение пакетов Configuration Manager

Все пакеты должны быть распределены на серверы, которым назначена роль точки распространения в иерархии Configuration Manager. Следуйте приведенным ниже инструкциям, чтобы инициировать распространение пакетов.

1.  Распространение пакетов программного обеспечения.

    1.  На консоли Configuration Manager перейдите в раздел \> **пакеты** \> **управления приложениями** **библиотеки программного обеспечения** . Выберите все пакеты программного обеспечения, которые вы хотите распространить, а затем выберите команду **распространить содержимое**.

    2.  Просмотрите список пакетов и нажмите кнопку **Далее**.

    3.  Добавьте в список всех серверов точки распространения (или групп точек распространения, в зависимости от иерархии Configuration Manager) и нажмите кнопку **Далее**.

    4.  Нажмите кнопку **Далее**, а затем — кнопку **Закрыть**.

2.  Распространение пакетов драйверов.

    1.  В консоли Configuration Manager перейдите в раздел **пакеты драйверов** \> **операционных систем** \> **библиотеки программного обеспечения** . Выберите все пакеты драйверов, которые вы хотите распространить, а затем выберите команду **распространить содержимое**.

    2.  Просмотрите список пакетов и нажмите кнопку **Далее**.

    3.  Добавьте в список всех серверов точки распространения (или групп точек распространения, в зависимости от иерархии Configuration Manager) и нажмите кнопку **Далее**.

    4.  Нажмите кнопку **Далее**, а затем — кнопку **Закрыть**.

3.  Распространение пакетов операционной системы.

    1.  В консоли Configuration Manager перейдите к образам **** \> **операционной системы**, заданной в **библиотеке** \> программного обеспечения. Выберите все образы операционной системы, которые вы хотите распространить, а затем выберите команду **распространить содержимое**.

    2.  Просмотрите список пакетов и нажмите кнопку **Далее**.

    3.  Добавьте в список всех серверов точки распространения (или групп точек распространения, в зависимости от иерархии Configuration Manager) и нажмите кнопку **Далее**.

    4.  Нажмите кнопку **Далее**, а затем — кнопку **Закрыть**.

> [!NOTE]
> Распространение пакетов может занять некоторое время, в зависимости от размера пакета, иерархии Configuration Manager, количества серверов точки распространения и пропускной способности, доступной в сети.
> 
> Все пакеты должны быть распределены, прежде чем вы сможете развернуть один из комнат Microsoft Teams.
> 
> Вы можете просмотреть состояние распространения пакетов на консоли Configuration Manager, перейдя в режим **наблюдения за** \> состоянием **распространения** \> **содержимого**.

## <a name="configuration-manager-task-sequences"></a>Последовательности задач Configuration Manager

Для автоматизации шагов по развертыванию образа операционной системы на конечном компьютере используются последовательности задач с помощью System Center Configuration Manager. Чтобы развернуть единицу измерения Microsoft Teams автоматически в автоматическом режиме, создайте последовательность задач, которая ссылается на образ загрузки, который используется для запуска конечного компьютера с операционной системой комнат Microsoft Teams, который вы хотите установить, и все другое дополнительное содержимое, например другие приложения или обновления программного обеспечения.

### <a name="import-the-sample-task-sequence"></a>Импорт последовательности примеров задач

Вы можете скачать и легко импортировать примерную последовательность задач и настроить ее в соответствии с вашими потребностями.

1.  [**Скачайте**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) пример последовательности задач и Скопируйте загруженный ZIP-файл в общее расположение.
2.  В консоли Configuration Manager перейдите в раздел **последовательности задач**для \> **операционных систем** \> **библиотеки программного обеспечения** , а затем щелкните **Импорт последовательности задач**.

3.  Нажмите кнопку **Обзор**, перейдите к папке, которую вы использовали в действии 1, выберите файл **развертывания Microsoft Teams (EN-US). zip** , а затем нажмите кнопку **Далее**.

4.  Задайте для параметра **действие** **создать новый**и нажмите кнопку **Далее**.

5.  Подтвердите параметры и нажмите кнопку **Далее**.

6.  Нажмите кнопку **Закрыть**.

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Убедитесь, что пакеты ссылок правильно связаны с каждым шагом последовательности задач.

1. Выберите импортированную последовательность задач и нажмите кнопку **изменить**.

    Откроется редактор последовательности задач, в котором выводятся все последовательные шаги, необходимые для развертывания и настройки единицы комнаты Microsoft Teams.

2. Пошаговое руководство и выполнение рекомендуемых обновлений:

   1. **Перезагрузите компьютер в среде Windows PE**: это действие перезапускается, а затем загружается в среду PXE Windows. Для этого шага никаких изменений не требуется.

   2. **Разбить на разделы диск 0 — UEFI**: на этом этапе производится очистка конфигурации диска и создание секций на основе настроенных параметров. Мы рекомендуем не вносить никаких изменений в этот этап.

   3. **Задайте имя компьютера SRS**. Этот шаг включает HTML-приложение, которое предоставляет пользовательский интерфейс, чтобы задать имя компьютера для устройства Microsoft Teams в процессе развертывания.
      -  Это необязательный шаг, но его можно отключить только в том случае, если вы хотите управлять именованием компьютеров с помощью альтернативного процесса.
      -  Убедитесь в том, что установлен пакет **SRS v2-Set-срскомпутернаме** . В противном случае перейдите к пакету и выберите его.

   4. **Применение операционной системы**: на этом этапе задается образ операционной системы, который нужно развернуть, и файл ответов для автоматического использования Sysprep.
      -  Убедитесь, что выбран правильный файл образа операционной системы Windows 10 корпоративный.
      -  Убедитесь в том, что **для выборочной установки используется автоматический или файл ответов Sysprep** , и выбран **пакет SRS v2-Sysprep** . Кроме того, убедитесь, что для **имени файла** задано значение **Unattend. XML**.

   5. **Применение параметров Windows**. на этом этапе собираются сведения о установке Windows.
      -  Предоставьте сведения о лицензировании и регистрации, включая ключ продукта, пароль учетной записи локального администратора и часовой пояс (в зависимости от ваших потребностей).

   6. **Примените параметры сети**. на этом шаге вы можете указать доменную рабочую группу или имя домена Active Directory и подразделение.
      > [!NOTE]
      > Для получения рекомендуемых действий, которые необходимо выполнить при развертывании комнат Microsoft Teams в качестве членов домена Актве, вы можете присоединиться к [домену системы комнаты Skype](domain-joining-considerations.md) .
   7. **Применение драйверов.** Этот шаг и вложенные шаги используются для развертывания применимых драйверов устройств и микропрограмм на основе имеющейся модели Surface Pro. Обновите каждый шаг, чтобы указать соответствующий пакет драйвера, связанный с этим развертыванием.
      -   Каждый пакет драйвера настроен на использование фильтров инструментария управления Windows (WMI) для развертывания соответствующих драйверов и микропрограмм на основе модели Surface Pro.
      -   Настоятельно не рекомендуется изменять конфигурацию этих драйверов, в противном случае развертывание может завершиться сбоем.

   8. **Настройка Windows и Configuration Manager**: на этом шаге развертывается и настраивается клиент Configuration Manager. Обновите этот шаг, чтобы указать встроенный клиентский пакет Configuration Manager.

   9. **Установка корневого сертификата**. Этот этап распространяет корневой сертификат для устройств, не присоединенных к домену, и поэтому является необязательным и отключенным по умолчанию.
      -   Включите это действие, если вам нужно развернуть корневой сертификат в единицах комнат Microsoft Teams.
      -   Если вы хотите выполнить этот шаг, убедитесь, что выбран **пакет корневого сертификата SRS v2** и отключено перенаправление **64-разрядной файловой системы** .

   10. **Установка и настройка агента наблюдения**: на этом этапе устанавливается 64-разрядная версия агента монитора Microsoft Azure и настраивается агент для подключения к рабочей области в службе анализа журналов.
       -   Этот шаг отключен по умолчанию. Этот этап следует активировать только в том случае, если вы собираетесь использовать агент наблюдения для наблюдения за работоспособностью модулей комнат Microsoft Teams.
       -   Измените этот шаг и обновите параметры командной строки, указав **идентификатор рабочей области** и **ключ рабочей области**.
       -   Дополнительные сведения о том, как получить идентификатор рабочей области Operations Management Suite и первичный ключ, можно найти в разделе [Настройка тестовых устройств для мониторинга Azure](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) .
       -   Убедитесь, что выбран **пакет агента наблюдения за SRS v2 (Майкрософт** ) и отключено перенаправление **64-разрядной файловой системы** .
       -   Дополнительные сведения о наблюдении за работоспособностью развертывания комнат Microsoft Teams можно найти в разделе Планирование управления комнатами Microsoft Teams [с помощью монитора Azure](azure-monitor-plan.md), [развертывание Microsoft Teams Management с помощью монитора Azure](azure-monitor-deploy.md) и [Управление Microsoft Teams закомнаты устройства с монитором Azure](azure-monitor-manage.md).

   11. **Копирование файлов конфигурации SRS v2**: на этом этапе выполняется копирование необходимых файлов настройки и конфигурации из комплекта средств развертывания комнат Microsoft Teams на локальный жесткий диск. Для этого шага настройка не требуется.
       -   Убедитесь, что установлен **пакет приложения SRS v2** и отключено перенаправление **64-разрядной файловой системы** .

   12. **Install-SRSv2-OS-Updates: на**этом этапе развертываются все обязательные обновления операционной системы, необходимые для развертывания комнат Microsoft Teams. Выполните следующие действия.
       -   Установите флажок [настроить консоль Microsoft Teams](console.md) , чтобы узнать, какие обновления требуются.
       -   Убедитесь, что **пакет обновлений для SRS v2 – OS** содержит все необходимые обновления.
       -   Убедитесь, что установлен **пакет обновления SRS v2 – OS** .
       -   Убедитесь, что для политики выполнения PowerShell задано значение **обход**.

   13. **Перезагрузите компьютер**. это действие перезагружает компьютер после установки обязательных обновлений операционной системы. Для этого шага настройка не требуется.

   14. **Настройка компонентов Windows**: на этом этапе настраиваются необходимые компоненты Windows. Для этого шага настройка не требуется.

   15. **Перезагрузка компьютера**: после настройки компонентов Windows компьютер перезагружается. Для этого шага настройка не требуется.

   16. **Добавить местного пользователя Skype**: на этом этапе создается локальная учетная запись Skype, используемая для автоматического входа в Windows, и запуска приложения Microsoft Teams комнаты. На этом этапе отсутствует связанный с ним пакет программного обеспечения, и для него не требуется настройка.

   17. **Настройка и настройка приложения SRS**. на этом этапе производится установка приложения Microsoft Teams для следующей загрузки операционной системы.
       -   Убедитесь в том, что для **SRS v2 установлен флажок Настройка пакета настройки SRS** и отключено перенаправление **64-разрядной файловой системы** .

> [!IMPORTANT]
> Очень важно, чтобы шаги последовательности задач должны быть в указанном порядке. Изменение порядка шагов или Настройка дополнительных шагов может привести к сбою развертывания.
>
> **Настройка и настройка шага приложения SRS** должна быть последним шагом последовательности задач, в противном случае развертывание может завершиться сбоем.

### <a name="create-deployment-for-the-task-sequence"></a>Создание развертывания для последовательности задач

1. Выберите последовательность задач, а затем нажмите кнопку **развернуть**.

2. Нажмите кнопку **Обзор** , чтобы выбрать целевую коллекцию для развертывания.

3. Выберите **все неизвестные компьютеры** и нажмите кнопку **ОК**.

4. Нажмите кнопку **Далее**.

5. В раскрывающемся списке **Цель** выберите пункт **доступно** .

6. Выберите **только носители и PXE** в списке **сделать доступным ниже** , а затем нажмите кнопку **Далее**.
   > [!WARNING]
   > Очень важно, чтобы **Цель** настроилась как **доступная**. Убедитесь, что для **цели** **не** задано значение **обязательно**. Кроме того, убедитесь в том, что вы выбрали **только носители и PXE** в разделе **сделать доступным для следующих вариантов**.
   >
   > Установка этих значений для других пользователей может привести к тому, что все компьютеры будут получать образ развертывания комнат Microsoft Teams при загрузке.
7. Не указывайте расписание и нажмите кнопку **Далее**.

8. Не изменяйте что-либо в разделе **взаимодействие с пользователем** и нажмите кнопку **Далее**.

9. Не изменяйте что-либо в разделе " **оповещения** " и нажмите кнопку **Далее**.

10. Не изменяйте ничего в разделе **точки распространения** и нажмите кнопку **Далее**.

11. Подтвердите параметры и нажмите кнопку **Далее**.

12. Нажмите кнопку **Закрыть**.

<a name="validate-and-troubleshoot-the-solution"></a>Проверка и устранение неполадок с решением
--------------------------------------

После того как вы закончите последовательности задач System Center Configuration Manager, вам потребуется выполнить тестовый запуск, чтобы убедиться в том, что последовательность задач может развернуть и настроить единицы комнаты Microsoft Teams.

1.  Подключите тестовое устройство к проводной сети, используя один из поддерживаемых адаптеров Ethernet или стыковочный элемент Surface. Если функция загрузки PXE не настроена для вашей среды, вы можете использовать образ загрузки, [созданный ранее](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) , для загрузки с USB-диска и подключения к Configuration Manager.

2.  Получить доступ к встроенному по и инициировать загрузку PXE:

    1.  Убедитесь, что питание устройства Surface выключено.

    2.  Нажмите и удерживайте кнопку **** "Громкость".

    3.  Нажмите и отпустите кнопку **Power** .

    4.  После того как устройство начнет загрузку, отпустите кнопку увеличить **уровень громкости** .

    5.  Выберите **Конфигурация загрузки**.

    6.  Выполните одно из следующих действий:

        -   Выберите **загрузку PXE**и перетащите ее в верхнюю часть списка. Вы также можете начать прокрутку влево на сетевом адаптере для немедленной загрузки устройства. Это не повлияет на порядок загрузки.
        -   Выберите USB-накопитель, на котором находится загрузочный носитель.

3.  Нажмите кнопку **выход**и выберите **Перезапустить сейчас**.

4.  При появлении соответствующего запроса нажмите кнопку **Ввод** для загрузки по сети.

5.  Windows PE будет загружена в память, и начнется Мастер последовательности задач. Нажмите кнопку **Далее** , чтобы продолжить.

6.  Выберите последовательность задач, которую вы импортировали ранее, и нажмите кнопку **Далее**.

7.  После применения конфигурации диска вам будет предложено указать имя компьютера для устройства. Пользовательский интерфейс будет отображать рекомендуемое имя компьютера на основе серийного номера устройства Surface Pro. Вы можете либо оставить предложенное имя, либо указать новое. Следуйте указаниям на экране назначения имени компьютера. После нажатия на кнопку " **сохранить**" начинается развертывание.

8.  Оставшаяся часть процесса развертывания будет автоматически и не запрашивает ввод данных пользователем.

9.  После того как последовательность задач развертывания завершит настройку устройства, отобразится следующее окно конфигурации с запросом на настройку параметров приложения в комнатах Microsoft Teams.

    ![Экран начальной настройки для приложения Microsoft Teams комнаты](../media/room-systems-scale-image2.png)

10.  Подключите Surface Pro к консоли Microsoft Teams и настройте параметры приложения.

11.  Убедитесь в том, что возможности, указанные в разделе " [комнаты Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) ", работают на развернутом устройстве.


Для устранения неполадок, связанных с неудачной установкой, проверьте файл **смстс. log** , в котором регистрируются все действия, выполненные в последовательности задач Configuration Manager.

Файл СМСТС. log хранится в одном из нескольких путей в зависимости от этапа процесса сборки. Убедитесь, что в приведенной ниже таблице указан путь к файлу СМСТС. log.


| **Этап развертывания**                                                            | **Путь к журналу последовательностей задач**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| Среда WinPE для форматирования жесткого диска                                                        | X:\\Windows\\temp\\смстслог\\смстс. log             |
| Среда WinPE после форматирования жесткого диска                                                         | C:\\_смстасксекуенце\\журналы\\смстслог\\смстс. log    |
| Операционная система развернута перед установкой агента Configuration Manager | c:\\_смстасксекуенце\\журналы\\смстслог\\смстс. log    |
| Операционная система и развернутый агент диспетчера конфигураций                   | % WINDIR%\\system32\\журналы\\\\CCM смстслог\\смстс. log |
| Выполнение последовательности задач завершено                                                | % WINDIR%\\system32\\смстс\\журнал\\событий CCM           |

> [!TIP]
> Вы можете в любое время нажать клавишу **F8** в течение последовательности задач, чтобы открыть консоль командной строки, а затем получить доступ к файлу смстс. log.

Для устранения проблем с загрузкой PXE проверьте два файла журнала на сервере Configuration Manager, которые относятся к действиям PXE.

-   **Пксеконтрол. log**, расположенный в каталоге журналов установки Configuration Manager

-   **Смспксе. log**, расположенный в каталоге журналов точки управления Configuration Manager (MP)

Полный список журнальных файлов, которые можно использовать для дальнейшего устранения неполадок, возникающих при установке Configuration Manager, приведены [в статье файлы журнала в System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).
