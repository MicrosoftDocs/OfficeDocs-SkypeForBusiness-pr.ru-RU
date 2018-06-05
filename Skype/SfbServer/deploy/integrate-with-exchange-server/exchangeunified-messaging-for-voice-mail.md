---
title: Настройка единой системы обмена сообщениями Exchange Server для голосовой почты Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/19/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Сводка: Настройка единой системы обмена сообщениями Exchange Server для Скайп Business Server голосовой почты.'
ms.openlocfilehash: 5cc8825e04e348004f4105d483eb7a92dd0e5c60
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569224"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-2015-voice-mail"></a>Настройка единой системы обмена сообщениями Exchange Server для голосовой почты Skype для бизнеса Server 2015
 
**Сводка:** Настройка единой системы обмена сообщениями Exchange Server для Скайп Business Server голосовой почты.
  
Скайп для Business Server 2015 позволяет иметь сообщения голосовой почты, хранящиеся в Exchange Server 2016 или Exchange Server 2013; Эти сообщения голосовой почты появится в виде сообщения электронной почты в почтовые ящики пользователей. 
  
Если вы уже настроили проверки подлинности сервер сервер между Скайп Business Server 2015, Exchange Server 2016 или Exchange Server 2013, затем вы готовы для настройки единой системы обмена сообщениями. Для этого необходимо сначала создать и Назначение новой единой системы обмена сообщениями абонентской группы на сервере Exchange. К примеру следующие команды (выполнять в командной консоли Exchange) настроить новый абонентскую цифра 3 для Exchange.
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

В первой команде в этом примере параметр VoIPSecurity и его значение "Secured" указывают, что сигнальный канал зашифрован с помощью протокола TLS. Значение "SipName" параметра URIType указывает, что сообщения будут отправляться и получаться посредством протокола SIP, а если для параметра CountryOrRegionCode выбрано значение "1", это свидетельствует о том, что абонентская группа применима для США.
  
Во второй команде значение, переданное в параметр ConfiguredInCountryOrRegionGroups, определяет группы внутри страны, которые можно использовать в этой абонентской группе. Значение параметра «в любом месте,\*,\*,\*"Задает следующее:
  
- Имя группы ("Anywhere")
    
- AllowedNumberString (\*, подстановочный знак, указывающего на то, что может любая строка номера)
    
- DialNumberString (\*, подстановочный знак, указывающего на то, что разрешен любой набранный номер)
    
- Параметр TextComment (\*, подстановочный знак, указывающего на то, что может Любая текстовая команда)
    
> [!NOTE]
> При создании новой абонентской группы создается также используемая по умолчанию политика почтовых ящиков. 
  
После создания и настройки новой абонентской группы необходимо добавить ее на сервере единой системы обмена сообщениями и затем изменить режим запуска этого сервера: в частности, задать режим запуска "Двойной". Необходимо выполнить оба эти операции в командной консоли Exchange:
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

После настройки единой системы обмена сообщениями сервера необходимо выполнить командлет Enable-ExchangeCertificate, чтобы убедиться, что сертификат Exchange применяется к службе единой системы обмена сообщениями:
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

После корректного назначения сертификата необходимо остановить и перезапустить службу MsExchangeUM на сервере единой системы обмена сообщениями. Эту службу необходимо останавливать и запускать после каждого изменения режима запуска.
  
По завершении настройки сервера единой системы обмена сообщениями можно настроить маршрутизатор вызовов в единую систему обмена сообщениями:
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

Поскольку режим запуска был изменен, необходимо остановить и перезапустить службу MsExchangeUMCR на том, компьютере, где размещен маршрутизатор вызовов в единую систему обмена сообщениями.
  
Для завершения настройки единой системы обмена сообщениями необходимо создать политику почтовых ящиков единой системы обмена мгновенными сообщениями, после чего использовать ее, чтобы разрешить пользователям работу с единой системой обмена сообщениями. Для создания политики почтовых ящиков можно использовать команду следующего вида:
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

Чтобы разрешить пользователям работу с единой системой обмена сообщениями, можно также использовать команду следующего вида:
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

В предыдущей команде параметр Extensions представляет добавочный номер телефона для пользователя. В этом примере добавочный номер пользователя — 100.
  
После активации почтового ящика пользователь kenmyer@litwareinc.com может работать с единой системой обмена сообщениями Exchange. Чтобы удостовериться, что пользователи могут подключаться к Exchange единой системы обмена СООБЩЕНИЯМИ с помощью командлета [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) из внутри Скайп для консоли Business Server:
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

При наличии второй пользователь, который был включен для единой системы обмена сообщениями можно использовать командлет [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) , чтобы убедиться, что этот второго пользователя можно оставить сообщение голосовой почты для первого пользователя.
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```