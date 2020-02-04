---
title: 'Lync Server 2013: Настройка единой системы обмена сообщениями Microsoft Exchange Server 2013 для Lync Server 2013 Голосовая почта'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 367f4cc517771f51d7a1452293ad9803075d285f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a>Настройка единой системы обмена сообщениями Microsoft Exchange Server 2013 для Microsoft Lync Server 2013 для голосовой почты

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-04_

Microsoft Lync Server 2013 позволяет использовать голосовые сообщения, хранящиеся в Microsoft Exchange Server 2013; Эти голосовые сообщения будут отображаться как сообщения электронной почты в ящиках пользователей. Эта возможность также была обнаружена в выпусках 2010 для Lync Server и Exchange; Однако процесс настройки этого параметра "Единая система обмена сообщениями" упрощен в выпусках 2013, благодаря введению компонента маршрутизатора UM. Этот компонент установлен на сервере клиентского доступа Exchange 2013, а все вызовы к единой системе обмена сообщениями Exchange (например, голосовой почте) сначала пересылаются через маршрутизатор вызовов, а затем перенаправляются на соответствующий сервер почтовых ящиков.

Если вы уже настроили проверку подлинности "сервер-сервер" между Lync Server 2013 и Exchange 2013, вы можете настроить единую систему обмена сообщениями. Для этого необходимо сначала создать и назначить новую абонентскую группу единой системы обмена сообщениями на сервере Exchange. Например, эти две команды (выполняются из командной консоли Exchange) настраивают новый 3-значный абонентский тариф для Exchange:

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

В первой команде в этом примере параметр VoIPSecurity и его значение "Secured" указывают, что сигнальный канал зашифрован с помощью протокола TLS. Значение "SipName" параметра URIType указывает, что сообщения будут отправляться и получаться посредством протокола SIP, а если для параметра CountryOrRegionCode выбрано значение "1", это свидетельствует о том, что абонентская группа применима для США.

Во второй команде значение, переданное в параметр ConfiguredInCountryOrRegionGroups, определяет группы внутри страны, которые можно использовать в этой абонентской группе. Значение параметра "везде\*\*",\*"," задает указанные ниже значения.

  - Имя группы ("Anywhere")

  - Алловеднумберстринг (\*— подстановочный знак, указывающий на то, что любая строка с цифрами разрешена)

  - Диалнумберстринг (\*— подстановочный знак, указывающий на то, что все номера разрешены)

  - Тексткоммент (\*— подстановочный знак, указывающий на то, что какая-либо из текстовых команд разрешена)

<div>


> [!NOTE]  
> При создании новой абонентской группы создается также используемая по умолчанию политика почтовых ящиков.



</div>

После создания и настройки новой абонентской группы необходимо добавить ее на сервере единой системы обмена сообщениями и затем изменить режим запуска этого сервера: в частности, задать режим запуска "Двойной". Вы можете выполнять обе эти задачи в командной консоли Exchange:

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

После того как вы настроили сервер единой системы обмена сообщениями, необходимо выполнить командлет Enable-ExchangeCertificate, чтобы убедиться в том, что сертификат Exchange применен к службе единой системы обмена сообщениями:

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

После корректного назначения сертификата необходимо остановить и перезапустить службу MsExchangeUM на сервере единой системы обмена сообщениями. Эту службу необходимо останавливать и запускать после каждого изменения режима запуска.

По завершении настройки сервера единой системы обмена сообщениями можно настроить маршрутизатор вызовов в единую систему обмена сообщениями:

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

Поскольку режим запуска был изменен, необходимо остановить и перезапустить службу MsExchangeUMCR на том, компьютере, где размещен маршрутизатор вызовов в единую систему обмена сообщениями.

Для завершения настройки единой системы обмена сообщениями необходимо создать политику почтовых ящиков единой системы обмена мгновенными сообщениями, после чего использовать ее, чтобы разрешить пользователям работу с единой системой обмена сообщениями. Для создания политики почтовых ящиков можно использовать команду следующего вида:

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

Чтобы разрешить пользователям работу с единой системой обмена сообщениями, можно также использовать команду следующего вида:

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

В предыдущей команде параметр Extensions представляет добавочный номер телефона для пользователя. В этом примере добавочный номер пользователя — 100.

После активации почтового ящика пользователь kenmyer@litwareinc.com может работать с единой системой обмена сообщениями Exchange. Вы можете убедиться, что пользователь может подключаться к UM-среде Exchange, запустив в командной консоли Lync Server командлет [Test – ксексумконнективити](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) .

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

При наличии второго пользователя, которому разрешена работа с единой системой обмена сообщениями, можно с помощью командлета [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) проверить, может ли второй пользователь оставлять сообщения голосовой почты для первого пользователя.

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

