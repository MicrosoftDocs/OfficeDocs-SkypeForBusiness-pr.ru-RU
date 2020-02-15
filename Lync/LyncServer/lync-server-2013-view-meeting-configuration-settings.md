---
title: 'Lync Server 2013: Просмотр параметров конфигурации собраний'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5daca87d47fdeb4bac46d83d48652037d75220b5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a>Просмотр параметров конфигурации собраний в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

В панели управления Lync Server 2013 вы можете использовать параметр конфигурации собраний для управления реализацией собраний в развертывании. К ним относятся следующие конфигурации собраний:

  - Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.

  - Дополнительные конфигурации на уровне сайта и на уровне пользователя, которые можно создавать и использовать для указания способа реализации собраний для конкретных сайтов или пользователей.

<div>

## <a name="to-view-meeting-configuration-settings"></a>Просмотр параметров конфигурации собраний

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Conferencing** (Конференц-связь), а затем **Meeting Configuration** (Конфигурация собрания).

4.  На странице **Meeting Configuration** (Конфигурация собраний) щелкните конфигурацию собраний, которую вы хотите просмотреть.

5.  В области **Edit File Filter** (Изменить фильтр файлов) установите флажок **Show Details…** (Показать сведения...).
    
    **Изменить конфигурацию собрания — \<политика\> ** открывает отображение параметров выбранной политики. Подробнее о настройке параметров можно узнать в статье [Создание или изменение коллекции параметров конфигурации собраний в Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о конфигурации собраний с помощью командлетов Windows PowerShell

Параметры конфигурации собраний можно просмотреть с помощью Windows PowerShell и командлета Get – CsMeetingConfiguration. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-view-meeting-configuration-information"></a>Просмотр сведений о конфигурации собраний

  - Чтобы просмотреть сведения обо всех параметрах конфигурации собраний, введите следующую команду в командной консоли Lync Server и нажмите клавишу ВВОД:
    
        Get-CsMeetingConfiguration
    
    Это приведет к возврату приблизительно такой информации:
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Get – CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

