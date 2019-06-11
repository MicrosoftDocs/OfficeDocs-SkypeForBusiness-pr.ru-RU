---
title: 'Lync Server 2013: развертывание системы комнат Lync на веб-портале администрирования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16fc5e7d0f136481ddce5d34de41268cb224822e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="5f532-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f532-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f532-103">_**Тема последнего изменения:** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="5f532-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="5f532-104">Портал администрирования Microsoft Lync Server 2013 Lync (ЛРС) — это веб-портал, с помощью которого организации могут сохранять Конференц-зал системы Lync.</span><span class="sxs-lookup"><span data-stu-id="5f532-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="5f532-105">Администраторы могут использовать веб-портал ЛРС администрирования для мониторинга работоспособности ЛРС, например за счет наблюдения за подключением аудио-и видеоустройств.</span><span class="sxs-lookup"><span data-stu-id="5f532-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="5f532-106">С помощью этого портала, администраторы могут удаленно собирать диагностические сведения, чтобы отслеживать работоспособность конференц-зала.</span><span class="sxs-lookup"><span data-stu-id="5f532-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="5f532-107">Веб-портал ЛРС администрирования разворачивается на каждом сервере клиентского доступа Lync.</span><span class="sxs-lookup"><span data-stu-id="5f532-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="5f532-108">Это руководство содержит инструкции для администраторов о том, как установить и настроить веб-портал ЛРС администрирования.</span><span class="sxs-lookup"><span data-stu-id="5f532-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="5f532-109">Она предназначена для администраторов, которые имеют опыт администрирования Lync Server и имеют права администратора на изменение топологии сервера Lync.</span><span class="sxs-lookup"><span data-stu-id="5f532-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="5f532-110">После развертывания веб-портала ЛРС на сервере администраторы могут проверить состояние всех комнат ЛРС, войдя на сайт со своих компьютеров или ноутбуков.</span><span class="sxs-lookup"><span data-stu-id="5f532-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5f532-111">Когда вы устанавливаете веб-портал ЛРС на сайте Microsoft Lync Server 2013, вы должны использовать <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">веб-портал для Microsoft Lync на комнатной подсистеме для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5f532-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="5f532-112">Для Skype для бизнеса Server 2015 доступна новая версия веб-портала ЛРС, но ее не следует устанавливать, если вы не развернули версию Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5f532-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="5f532-113">Скачайте <A href="http://go.microsoft.com/fwlink/?linkid=544807">веб-портал для Microsoft Lync комнатной подсистемы для Skype для бизнеса Server 2015</A>.</span><span class="sxs-lookup"><span data-stu-id="5f532-113">Download the <A href="http://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5f532-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="5f532-114">In This Section</span></span>

[<span data-ttu-id="5f532-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span><span class="sxs-lookup"><span data-stu-id="5f532-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="5f532-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f532-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="5f532-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f532-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5f532-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5f532-118">See Also</span></span>


[<span data-ttu-id="5f532-119">Развертывание конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f532-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

