﻿---
title: Создание каталогов конференций (обязательно)
TOCTitle: Создание каталогов конференций (обязательно)
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/ru-ru/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63232642
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Создание каталогов конференций (обязательно)

 

_**Дата изменения раздела:** 2014-10-03_

Каталоги конференций поддерживают сопоставление между буквенно-цифровым идентификатором собрания, с помощью которого участник присоединяется к конференции при использовании Lync 2013, и состоящим только из цифр идентификатором конференции, с помощью которого участник конференции с телефонным подключением присоединяется к этой конференции. Формат идентификатора конференции:

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

Создание нескольких каталогов конференций позволяет использовать для конференций короткие идентификаторы, пока не будет создано значительное количество конференций. В организациях со стандартным количеством конференций на пользователя рекомендуется создавать по одному каталогу конференций для каждых 999 пользователей в пуле. Это правило позволит сохранить короткие идентификаторы конференций. Однако когда количество каталогов конференций (по пулам) превышает 9, длина идентификатора конференции будет увеличиваться для поддержки дополнительных конференций.

## Создание каталога конференции

1.  В Командная консоль Lync Server введите следующий командлет:
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    Например, следующий командлет создает каталог конференции с идентификатором 42, размещенный в пуле atl-cs-001.litwareinc.com:
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

## См. также

#### Концепции

[Требования к связи с телефонным подключением в Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  

#### Другие ресурсы

[New-CsConferenceDirectory](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsConferenceDirectory)

