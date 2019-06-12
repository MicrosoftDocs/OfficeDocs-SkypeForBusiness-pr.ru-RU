---
title: 'Lync Server 2013: Просмотр сведений о политике конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8dc9174356b1d5f8e5c6316ef761c51db1eb969
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-policy-information-in-lync-server-2013"></a>Просмотр сведений о политике конференц-связи в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

В панели управления Lync Server 2013 вы можете управлять реализацией конференций в развертывании с помощью политик конференц-связи. Сюда относятся следующие политики конференц-связи:

  - Глобальная политика, созданная по умолчанию при развертывании Lync Server 2013.

  - Необязательная политика уровня сайта и пользовательского уровня, которую можно создать и использовать для определения способа реализации конференции для конкретных сайтов или пользователей.

<div>

## <a name="to-view-conferencing-policy-settings"></a>Просмотр параметров политики конференций

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите **Конференц** -связь, а затем — **Политика Конференц**-связи.

4.  На странице **Политика конференц-связи** дважды щелкните политику, которую вы хотите просмотреть.

5.  В окне " **Изменение фильтра файлов**" выберите **Показать подробности...** флажок.
    
    Диалоговое окно " **изменение политики конференц-связи" \<— открывается параметр политики\> ** , в котором отображаются параметры выбранной политики. Подробнее о настройке параметров можно узнать в разделе [Создание или изменение политики конференц-связи в Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a>Просмотр политик конференц-связи с помощью командлетов Windows PowerShell

Политики Конференции можно просмотреть с помощью Windows PowerShell и командлета Get-КсконференЦингполици. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-view-conferencing-policies"></a>Просмотр политик конференц-связи

  - Чтобы просмотреть сведения обо всех политиках конференц-связи, введите следующую команду в командной консоли Lync Server Management Shell и нажмите клавишу ВВОД.
    
        Get-CsConferencingPolicy
    
    Команда возвращает примерно следующую информацию:
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Get-ксконференЦингполици](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

