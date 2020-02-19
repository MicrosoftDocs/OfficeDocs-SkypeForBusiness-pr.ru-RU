---
title: 'Lync Server 2013: обновление списка "разрешения" Outlook'
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
ms.openlocfilehash: 1e1f71d1ef0ebcb6bc5f8aee8875c013a24a4de0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>Обновление списка поддержки Outlook в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-07_

Вы можете убедиться, что надстройка "собрание по сети" для Microsoft Lync 2013 всегда остается включенной для пользователей, создав политику, которая включает ее в список управления надстройками для Outlook. Политика списка управления надстройками включается в файлы административных шаблонов Office для консоли управления групповыми политиками. Он создает раздел реестра в разделе политики\\\\\\программного обеспечения\\HKCU\\Microsoft\\Office\\15,0 Outlook15\\устойчивости AddinList. Вы можете добавить значение для укаддин. dll в этот ключ и настроить значение укаддин. dll так, чтобы оно всегда было включено и пользователи не могли отключить его вручную.

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>Добавление укаддин. dll в список надстроек Outlook

  - В раздел реестра AddinList, расположенный в разделе политики\\\\\\программного обеспечения\\HKCU\\Microsoft\\Office\\15,0 Outlook15\\устойчивости AddinList, добавьте следующее значение:
    
      - Тип реестра = REG\_СЗ
    
      - Имя = ucaddin.dll
    
      - Значение = 1 (указывает, что надстройка всегда включена и не управляется пользователем)

</div>

</div>

<span> </span>

</div>

</div>

</div>

