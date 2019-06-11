---
title: 'Lync Server 2013: запуск служб на серверах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0c0c14aea9966e61703e85dd2aff8a2e448d5eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a>Запуск служб на серверах для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-09-03_

Для успешного выполнения этой процедуры нужно войти в систему как пользователь, который является членом группы Рткуниверсалсерверадминс, или иметь соответствующие разрешения, делегированные. Дополнительные сведения о делегировании разрешений можно найти в разделе [разрешения на настройку делегатов раздела в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

После установки локального хранилища конфигураций на серверы установите компоненты Lync Server 2013 и настройте сертификаты на сервере переднего плана или на сервере переднего плана, на котором вы должны запустить службы Lync Server 2013 на сервере. Выполните описанные ниже действия, чтобы запустить службы на каждом сервере переднего плана в развертывании.

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>Запуск служб на стандартном выпуске или сервере переднего плана

1.  В мастере развертывания Lync Server на странице **Lync server 2013** нажмите кнопку **выполнить** рядом с **шагом 4: запуск служб**.

2.  На странице **Запуск служб** нажмите кнопку **Далее** , чтобы запустить службы Lync Server на сервере.

3.  После успешного запуска всех служб на странице **Выполнение команд** нажмите кнопку **Готово**.
    
    <div>
    

    > [!IMPORTANT]  
    > Команда для запуска служб на сервере — это наилучший способ сообщить о том, что на самом деле запущены службы. Однако он может не отражать фактическое состояние служб. Рекомендуем использовать <STRONG>состояние службы Step (необязательно)</STRONG> сразу после <STRONG>запуска службы</STRONG> , чтобы открыть консоль управления (MMC) и убедиться, что службы успешно запущены. Если какая-либо из служб Lync Server не запущена, вы можете щелкнуть ее правой кнопкой мыши в MMC и выбрать команду <STRONG>Пуск</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

