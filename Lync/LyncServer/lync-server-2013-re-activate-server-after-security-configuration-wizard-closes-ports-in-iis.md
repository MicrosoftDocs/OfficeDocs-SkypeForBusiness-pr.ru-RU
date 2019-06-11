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

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="90dc5-102">Повторная активация сервера после закрытия портов в IIS мастером настройки безопасности</span><span class="sxs-lookup"><span data-stu-id="90dc5-102">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90dc5-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="90dc5-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="90dc5-104">Некоторые роли Lync Server 2013 работают на веб-службах на порте служб IIS 4443.</span><span class="sxs-lookup"><span data-stu-id="90dc5-104">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="90dc5-105">При выполнении мастера развертывания Lync Server, загрузчика. exe или с помощью командлета **Enable-кскомпутер** создается в брандмауэре исключение и открывается порт.</span><span class="sxs-lookup"><span data-stu-id="90dc5-105">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="90dc5-106">Если вы запустите мастер настройки безопасности Windows Server 2008 R2 (или другие сценарии защиты), порт 4443 будет заблокирован, а внешние клиенты не смогут обращаться к веб-службам.</span><span class="sxs-lookup"><span data-stu-id="90dc5-106">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="90dc5-107">Чтобы снова открыть порт, вы можете либо изменить исключение межсетевого экрана напрямую, либо повторно активировать сервер.</span><span class="sxs-lookup"><span data-stu-id="90dc5-107">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="90dc5-108">Повторная активация сервера с помощью мастера развертывания</span><span class="sxs-lookup"><span data-stu-id="90dc5-108">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="90dc5-109">На странице мастера развертывания Lync Server нажмите кнопку **выполнить** рядом с **шагом 2: Настройка или удаление компонентов Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="90dc5-109">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="90dc5-110">На странице **настройки серверных компонентов Lync** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="90dc5-110">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="90dc5-111">На странице **выполнение команд** после того, как состояние задачи отображается как завершенное, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="90dc5-111">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="90dc5-112">Вы также можете повторно активировать сервер с помощью загрузчика. exe или <STRONG>Enable-кскомпутер</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="90dc5-112">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

