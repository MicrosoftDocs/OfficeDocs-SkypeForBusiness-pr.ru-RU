---
title: 'Lync Server 2013: обновление списка включения Outlook'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f44de6e3b7756935829b008c585474e08f6f9969
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>Обновление списка включения Outlook в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-01-07_

Вы можете сделать так, чтобы надстройка сетевого собрания для Microsoft Lync 2013 всегда оставалась включена для пользователей путем создания политики, которая включает ее в список управления надстройками для Outlook. Политика списка управления надстройками входит в файлы административных шаблонов Office для консоли управления групповыми политиками. Он создает раздел реестра в разделе политики\\\\\\программного обеспечения\\HKCU\\Microsoft\\Office\\15,0 Outlook15\\устойчивость аддинлист. Вы можете добавить в этот раздел значение укаддин. dll и настроить значение укаддин. dll так, чтобы оно всегда было включено и не могло вручную его отключить.

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>Добавление укаддин. dll в список надстроек для Outlook

  - В раздел реестра Аддинлист, который находится в разделе\\политики\\\\программного\\обеспечения\\HKCU\\Microsoft\\Office 15,0\\Outlook15 устойчивость аддинлист, добавьте следующее значение:
    
      - Тип реестра = REG\_СЗ
    
      - Name = укаддин. dll
    
      - Value = 1 (указывает, что надстройка всегда включена и не может управляться конечным пользователем)

</div>

</div>

<span> </span>

</div>

</div>

</div>

