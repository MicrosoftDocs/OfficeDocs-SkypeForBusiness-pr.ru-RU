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
ms.openlocfilehash: 388a39c81af2f7e3ca4e0c61f468b283deaa7a4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>Повторная активация сервера после закрытия портов в IIS мастером настройки безопасности

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

Некоторые роли Lync Server 2013 выполняют веб-службы на порте служб IIS 4443. При запуске мастера развертывания Lync Server, загрузчика. exe или с помощью командлета **Enable – CsComputer** создается исключение в брандмауэре и открывается порт. Если затем запустить мастер настройки безопасности Windows Server 2008 R2 (или другие сценарии усиления защиты), порт 4443 будет заблокирован, а внешние клиенты не смогут обращаться к веб-службам. Чтобы повторно открыть порт, можно напрямую изменить исключение брандмауэра или повторно активировать сервер.

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

