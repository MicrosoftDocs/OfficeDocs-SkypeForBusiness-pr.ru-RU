---
title: Предложен Создание каталогов конференций
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b053e4f09bdf5c497e1cbf929698c7084111cc7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509256"
---
# <a name="recommended-create-conference-directories"></a>Предложен Создание каталогов конференций

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-10-03_

Каталоги конференций поддерживают сопоставление буквенно-цифрового идентификатора собраний, который участник использует для присоединения к Конференции при использовании Lync 2013, и идентификатор одноранговой конференции, который используется участником конференц-связи с телефонным подключением для присоединения к Конференции. Формат идентификатора конференции:

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

Создание нескольких каталогов конференций позволяет использовать для конференций короткие идентификаторы, пока не будет создано значительное количество конференций. В организациях со стандартным количеством конференций на пользователя рекомендуется создавать по одному каталогу конференций для каждых 999 пользователей в пуле. Это правило позволит сохранить короткие идентификаторы конференций. Тем не менее, если число каталогов конференций (в пулах) превышает 9, длина идентификатора конференции увеличится для поддержки дополнительных конференций.

<div>

## <a name="creating-a-conference-directory"></a>Создание каталога конференций

1.  В командной консоли Lync Server введите следующий командлет:
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    Например, в следующем примере создается каталог конференций с идентификатором 42, размещенном в пуле atl-cs-001.litwareinc.com:
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>См. также


[Требования к конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  


[New — CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

