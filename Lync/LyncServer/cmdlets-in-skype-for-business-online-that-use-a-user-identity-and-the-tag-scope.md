﻿---
title: Командлеты, использующие удостоверение пользователя и область тегов
TOCTitle: Командлеты, использующие удостоверение пользователя и область тегов
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56270537
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Командлеты, использующие удостоверение пользователя и область тегов

 

_**Дата изменения раздела:** 2015-06-22_

Командлеты **Grant-Cs**, которые предназначены для назначения политик пользователям, требуют два идентификатора: удостоверение пользователя (параметр Identity) и идентификатор политики уровня пользователя (параметр PolicyName). Например, чтобы назначить политику голосовой связи RedmondVoicePolicy пользователю Ken Myer, выполните следующую команду:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

При назначении политик пользователям необходимо помнить о двух моментах. Во-первых, назначать можно только политики уровня пользователя. Назначить пользователю глобальную политику невозможно. Например, следующая команда вернет ошибку:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

Выполнение этой команды завершится ошибкой, так как назначать пользователю глобальную политику не требуется. Чтобы включить пользователя в сферу действия глобальной политики, достаточно просто не назначать ему политику уровня пользователя. Если она ему не назначена, он автоматически подпадает под действие глобальной политики.

> [!NOTE]
> Иногда необходимо ввести в область действия глобальной политики пользователя, которому уже назначена политика уровня пользователя. В таком случае необходимо отменить это назначение с помощью следующей команды, которая назначает пользователю пустую политику:<br />
> Grant-CsVoicePolicy –Identity &quot;Ken Myer&quot; –PolicyName $Null


Во-вторых, помните о том, что политики уровня пользователя создаются в области тегов. Однако в имени такой политики можно опускать тег **prefix**. Следующие две команды идентичны:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

Чтобы вернуть идентификаторы всех политик уровня пользователя (или политик определенного типа, например голосовой связи), выполните следующую команду:

    Get-CsVoicePolicy -Filter "tag:*"

В следующих командлетах задействованы как идентификатор пользователя, так и область тегов:

  - [Grant-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientPolicy)

  - [Grant-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsConferencingPolicy)

  - [Grant-CsDialPlan](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsDialPlan)

  - [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

  - [Grant-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsHostedVoicemailPolicy)

  - [Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy)

## См. также

#### Концепции

[Удостоверения, области и клиенты](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Командлеты Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

