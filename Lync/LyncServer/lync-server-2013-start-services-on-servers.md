---
title: 'Lync Server 2013: запуск служб на серверах'
description: 'Lync Server 2013: запуск служб на серверах.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c238d7ddbba66604314d146a2e7f86eaa85eeb9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541915"
---
# <a name="start-services-on-servers-for-lync-server-2013"></a>Запуск служб на серверах для Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-09-03_

Для успешного выполнения этой процедуры необходимо войти в систему с учетной записью, которая является членом группы RTCUniversalServerAdmins или имеет соответствующие разрешения. Дополнительные сведения о делегировании разрешений представлены в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

После установки локального хранилища конфигурации на серверах установите компоненты Lync Server 2013 и настройте сертификаты на сервере переднего плана или сервере переднего плана, необходимо запустить службы Lync Server 2013 на сервере. Используйте следующую процедуру для запуска служб на каждом сервере переднего плана в развертывании.

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>Запуск служб на сервере переднего плана или в стандартном выпуске сервера

1.  В мастере развертывания Lync Server на странице **Lync server 2013** нажмите **выполнить** рядом с **шагом 4: Start Services**.

2.  На странице **Запуск служб** нажмите кнопку **Далее** , чтобы запустить службы Lync Server на сервере.

3.  После того как все службы будут успешно запущены, на странице **Выполнение команд** нажмите кнопку **Готово**.
    
    <div>
    

    > [!IMPORTANT]  
    > Использование команды для запуска служб на сервере — это лучший способ, позволяющий получить подтверждение того, что службы действительно запущены. Однако он может не отражать фактическое состояние служб. Рекомендуется использовать шаг <STRONG>Service Status (Optional)</STRONG> (Состояние службы (дополнительно)) сразу после шага <STRONG>Запуск служб</STRONG>, чтобы открыть консоль управления (MMC) и убедиться в том, что все службы успешно запущены. Если какая – либо служба Lync Server не запущена, можно щелкнуть ее правой кнопкой мыши в консоли MMC и выбрать команду <STRONG>Пуск</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

