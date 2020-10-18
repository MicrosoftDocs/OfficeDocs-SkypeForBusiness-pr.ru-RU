---
title: Повторная активация сервера после закрытия портов в IIS мастером настройки безопасности
description: Повторно активируйте сервер после закрытия портов в IIS мастером настройки безопасности.
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
ms.openlocfilehash: d824845a7f89c28087a7b5d180a6ed017cb47ade
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579055"
---
# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="25e95-103">Повторная активация сервера после закрытия портов в IIS мастером настройки безопасности</span><span class="sxs-lookup"><span data-stu-id="25e95-103">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25e95-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="25e95-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="25e95-105">Некоторые роли Lync Server 2013 выполняют веб-службы на порте служб IIS 4443.</span><span class="sxs-lookup"><span data-stu-id="25e95-105">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="25e95-106">При запуске мастера развертывания Lync Server, Bootstrapper.exe или с помощью командлета **Enable – CsComputer** создается исключение в брандмауэре и открывается порт.</span><span class="sxs-lookup"><span data-stu-id="25e95-106">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="25e95-107">Если затем запустить мастер настройки безопасности Windows Server 2008 R2 (или другие сценарии усиления защиты), порт 4443 будет заблокирован, а внешние клиенты не смогут обращаться к веб-службам.</span><span class="sxs-lookup"><span data-stu-id="25e95-107">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="25e95-108">Чтобы повторно открыть порт, можно напрямую изменить исключение брандмауэра или повторно активировать сервер.</span><span class="sxs-lookup"><span data-stu-id="25e95-108">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="25e95-109">Повторная активация сервера с помощью мастера развертывания</span><span class="sxs-lookup"><span data-stu-id="25e95-109">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="25e95-110">На странице мастера развертывания Lync Server нажмите **выполнить** рядом с **шагом 2: Установка или удаление компонентов Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="25e95-110">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="25e95-111">На странице **Установка компонентов Lync Server** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="25e95-111">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="25e95-112">На странице **Выполнение команд**, когда состояние задачи отображается как "Завершено", нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="25e95-112">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="25e95-113">Вы также можете использовать bootstrapper.exe или <STRONG>Enable-CsComputer</STRONG> для повторной активации сервера.</span><span class="sxs-lookup"><span data-stu-id="25e95-113">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

