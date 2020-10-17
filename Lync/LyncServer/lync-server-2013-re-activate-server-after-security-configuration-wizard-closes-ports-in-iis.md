---
title: Повторная активация сервера после закрытия портов в IIS мастером настройки безопасности
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a72bfcf9facfeaa3ca943275d9cdcb3b1ac7705
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512046"
---
# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>Повторная активация сервера после закрытия портов в IIS мастером настройки безопасности

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

Некоторые роли Lync Server 2013 выполняют веб-службы на порте служб IIS 4443. При запуске мастера развертывания Lync Server, Bootstrapper.exe или с помощью командлета **Enable – CsComputer** создается исключение в брандмауэре и открывается порт. Если затем запустить мастер настройки безопасности Windows Server 2008 R2 (или другие сценарии усиления защиты), порт 4443 будет заблокирован, а внешние клиенты не смогут обращаться к веб-службам. Чтобы повторно открыть порт, можно напрямую изменить исключение брандмауэра или повторно активировать сервер.

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>Повторная активация сервера с помощью мастера развертывания

1.  На странице мастера развертывания Lync Server нажмите **выполнить** рядом с **шагом 2: Установка или удаление компонентов Lync Server**.

2.  На странице **Установка компонентов Lync Server** нажмите кнопку **Далее**.

3.  На странице **Выполнение команд**, когда состояние задачи отображается как "Завершено", нажмите кнопку **Готово**.
    
    <div>
    

    > [!NOTE]
    > Вы также можете использовать bootstrapper.exe или <STRONG>Enable-CsComputer</STRONG> для повторной активации сервера.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

