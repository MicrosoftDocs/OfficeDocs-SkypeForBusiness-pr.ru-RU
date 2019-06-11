---
title: Повторная активация сервера после закрытия портов в IIS мастером настройки безопасности
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c939996c10c85141d3c3751ce84b0cf642007b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>Повторная активация сервера после закрытия портов в IIS мастером настройки безопасности

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

Некоторые роли Lync Server 2013 работают на веб-службах на порте служб IIS 4443. При выполнении мастера развертывания Lync Server, загрузчика. exe или с помощью командлета **Enable-кскомпутер** создается в брандмауэре исключение и открывается порт. Если вы запустите мастер настройки безопасности Windows Server 2008 R2 (или другие сценарии защиты), порт 4443 будет заблокирован, а внешние клиенты не смогут обращаться к веб-службам. Чтобы снова открыть порт, вы можете либо изменить исключение межсетевого экрана напрямую, либо повторно активировать сервер.

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>Повторная активация сервера с помощью мастера развертывания

1.  На странице мастера развертывания Lync Server нажмите кнопку **выполнить** рядом с **шагом 2: Настройка или удаление компонентов Lync Server**.

2.  На странице **настройки серверных компонентов Lync** нажмите кнопку **Далее**.

3.  На странице **выполнение команд** после того, как состояние задачи отображается как завершенное, нажмите кнопку **Готово**.
    
    <div>
    

    > [!NOTE]
    > Вы также можете повторно активировать сервер с помощью загрузчика. exe или <STRONG>Enable-кскомпутер</STRONG> .

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

