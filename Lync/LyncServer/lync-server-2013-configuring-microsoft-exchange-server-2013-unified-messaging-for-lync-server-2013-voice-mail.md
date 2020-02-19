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
ms.openlocfilehash: 33c506e8b9f1201ad9382e361afc376590c6feca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a>Настройка единой системы обмена сообщениями Microsoft Exchange Server 2013 для голосовой почты Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-04_

Microsoft Lync Server 2013 позволяет использовать сообщения голосовой почты, хранящиеся в Microsoft Exchange Server 2013; Эти сообщения голосовой почты будут отображаться как сообщения электронной почты в папках "Входящие" пользователей. Эта возможность также была обнаружена в выпусках Lync Server и Exchange для 2010. Тем не менее, процесс настройки единой системы обмена сообщениями упрощен в выпусках 2013, благодаря появлением компонента маршрутизатора вызовов единой системы обмена сообщениями. Этот компонент устанавливается на сервере клиентского доступа Exchange 2013, а все вызовы единой системы обмена сообщениями Exchange (например, голосовой почты) сначала проходят через маршрутизатор вызовов, а затем перенаправляются на соответствующий сервер почтовых ящиков.

Если вы уже настроили межсерверную проверку подлинности между Lync Server 2013 и Exchange 2013, то готовы настроить единую систему обмена сообщениями. Для этого необходимо сначала создать и назначить новую абонентскую схему единой системы обмена сообщениями на сервере Exchange. Например, следующие две команды (выполняются в командной консоли Exchange) настраивают новую абонентскую абонентскую группы для Exchange:

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

В первой команде в примере параметр VoIPSecurity и значение параметра "Secured" указывают на то, что сигнальный канал шифруется с помощью протокола TLS. Уритипе "SipName" указывает, что сообщения будут отправлены и получены с помощью протокола SIP, а Каунтрйоррегионкоде 1 указывает на то, что абонентская абонентская абонентская область применяется к нам.

Во второй команде значение параметра, передаваемое параметру Конфигурединкаунтрйоррегионграупс, определяет группы внутри страны, которые можно использовать с этой абонентской группой. Значение параметра "Anywhere,\*\*,\*" задает следующее:

  - Имя группы ("Anywhere")

  - Параметр allowednumberstring (\*— подстановочный знак, указывающий на то, что любая числовая строка разрешена)

  - Параметр dialnumberstring (\*— подстановочный знак, указывающий на то, что любой набранный номер разрешен)

  - Параметр textcomment (\*— подстановочный знак, указывающий на то, что любая Текстовая команда разрешена)

<div>


> [!NOTE]  
> При создании новой абонентской группы также будет создана политика почтовых ящиков по умолчанию.



</div>

После создания и настройки новой абонентской группы необходимо добавить новую абонентскую схему на сервер единой системы обмена сообщениями, а затем изменить режим запуска этого сервера. в частности, необходимо присвоить режиму запуска значение "Dual". Обе эти задачи можно выполнить в командной консоли Exchange:

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

После настройки сервера единой системы обмена сообщениями необходимо выполнить командлет Enable-ExchangeCertificate, чтобы убедиться, что сертификат Exchange применяется к службе единой системы обмена сообщениями.

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

После правильного назначения сертификата необходимо остановить и перезапустить службу MsExchangeUM на сервере единой системы обмена сообщениями. Эту службу необходимо остановить и перезапустить при каждом изменении режима запуска.

После завершения настройки сервера единой системы обмена сообщениями можно настроить маршрутизатор вызовов единой системы обмена сообщениями.

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

Так как режим запуска изменился, необходимо остановить и перезапустить службу MsExchangeUMCR на компьютере, на котором размещается маршрутизатор вызовов единой системы обмена сообщениями.

Чтобы завершить настройку единой системы обмена сообщениями, необходимо создать политику почтовых ящиков единой системы обмена сообщениями и затем использовать эту политику, чтобы разрешить пользователям единую систему обмена сообщениями. Вы можете создать политику почтовых ящиков с помощью следующей команды:

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

Вы также можете включить для пользователя единую систему обмена сообщениями с помощью следующей команды:

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

В предыдущей команде параметр Extensions представляет добавочный номер телефона пользователя. В этом примере у пользователя есть добавочный номер 100.

После включения почтового ящика пользователь kenmyer@litwareinc.com должен иметь возможность использовать единую систему обмена сообщениями Exchange. Чтобы убедиться, что пользователь может подключаться к единой системе обмена сообщениями Exchange, выполните командлет [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) в командной консоли Lync Server.

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Если у вас есть второй пользователь, для которого включена поддержка единой системы обмена сообщениями, можно воспользоваться командлетом [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) , чтобы проверить, может ли второй пользователь оставить сообщение голосовой почты для первого пользователя.

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

