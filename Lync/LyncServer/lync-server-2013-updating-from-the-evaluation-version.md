---
title: 'Lync Server 2013: обновление из ознакомительной версии'
description: 'Lync Server 2013: обновление из ознакомительной версии.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 340badf9f5d2506c50cf8c03faa82223eabbd5af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546255"
---
# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>Обновление ознакомительной версии Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-20_

Если вы установили оценочную версию Microsoft Lync Server 2013, вам, в конечном итоге, потребуется обновить установленную лицензионную копию программного обеспечения; Это связано с тем, что срок действия ознакомительной версии истечет через 180 дней после ее установки. Однако вам не нужно будет полностью удалять ознакомительную версию, а затем устанавливать лицензионную. Вместо этого после получения действительного ключа лицензирования можно обновить оценочную версию Lync Server 2013, выполнив следующую процедуру на каждом компьютере, работающем в качестве сервера переднего плана Lync Server, директора или пограничного сервера. Обратите внимание на то, что вам не нужно обновлять компьютеры с другими ролями сервера, например сервера мониторинга или сервера архивации.

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>Обновление с ознакомительной версии Microsoft Lync Server 2013

Чтобы обновить компьютер с ознакомительной версии Lync Server 2013 до лицензионной версии программного обеспечения, выполните следующие действия:

**Обновление с ознакомительной версии Microsoft Lync Server 2013**

1.  Войдите на компьютер как локальный администратор.

2.  Нажмите кнопку **Пуск**, выберите **все программы**, **Microsoft Lync Server 2013**и щелкните **Lync Server Management Shell**.

3.  В командной консоли Lync Server введите следующую команду и нажмите клавишу ВВОД:
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    Обратите внимание на то, что вам может потребоваться указать полный путь к файлу server.msi. Этот файл можно найти в папке Setup файла установки мультимедиа для тома Lync Server.

4.  После завершения работы программы установки введите в командной строке следующую команду и нажмите клавишу ВВОД.
    
        Enable-CsComputer

5.  Повторите эту процедуру для любого другого сервера переднего плана, директора или пограничного сервера под управлением пробной копии Lync Server. Эту процедуру также следует выполнить на всех серверах филиалов, развернутых с помощью файлов установки мультимедиа Lync Server.

Если вы не уверены в том, что пробная версия Lync Server запущена на определенном компьютере, можно проверить, выполнив следующую команду в командной консоли Lync Server:

    Get-CsServerVersion

Командлет [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) проанализирует локальный компьютер и выдаст одно из следующих сообщений.

  - , Что на компьютере установлен ключ корпоративного лицензирования Lync Server, то есть обновление не требуется.

  - , Что установлен ключ лицензии на пробную версию Lync Server, то есть компьютер необходимо обновить.

  - На компьютере не требуется ключ многократной установки. Обновление с ознакомительной версии до лицензионной требуется только на серверах переднего плана, Директорах и пограничных серверах.

</div>

</div>

<span> </span>

</div>

</div>

</div>

