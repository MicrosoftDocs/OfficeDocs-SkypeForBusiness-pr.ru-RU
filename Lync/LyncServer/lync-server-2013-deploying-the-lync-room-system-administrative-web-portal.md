---
title: 'Lync Server 2013: развертывание веб-портала администрирования системы комнат Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b95e9b1ba6543add17ec27fec9e5f787ec7acd29
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="e8e8d-102">Развертывание веб-портала администрирования системы комнат Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8e8d-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8e8d-103">_**Последнее изменение темы:** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="e8e8d-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="e8e8d-104">Веб-портал администрирования Microsoft Lync Server 2013 Lync (LRS) — это веб-портал, который организации могут использовать для обслуживания комнат конференц-зала системы комнат Lync.</span><span class="sxs-lookup"><span data-stu-id="e8e8d-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="e8e8d-105">Администраторы могут использовать веб-портал администрирования LRS для наблюдения за работоспособностью LRS, например, мониторингом подключенных аудио-и видеоустройств.</span><span class="sxs-lookup"><span data-stu-id="e8e8d-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="e8e8d-106">С помощью этого портала администраторы могут удаленно собирать диагностические сведения для отслеживания работоспособности конференц-зала.</span><span class="sxs-lookup"><span data-stu-id="e8e8d-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="e8e8d-107">Веб-портал администрирования LRS развертывается на каждом сервере переднего плана Lync.</span><span class="sxs-lookup"><span data-stu-id="e8e8d-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="e8e8d-108">В этом руководстве представлены инструкции для администраторов об установке и настройке веб-портала администрирования LRS.</span><span class="sxs-lookup"><span data-stu-id="e8e8d-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="e8e8d-109">Он предназначен для администраторов, обладающих знаниями об администрировании Lync Server и имеющих права администратора на изменение топологии Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8e8d-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="e8e8d-110">После развертывания веб-портала администрирования LRS на сервере администраторы могут проверить состояние всех комнат LRS, войдя на сайт с собственных компьютеров или ноутбуков.</span><span class="sxs-lookup"><span data-stu-id="e8e8d-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e8e8d-111">При установке веб-портала администрирования LRS в развертывании Microsoft Lync Server 2013 следует использовать <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">веб-портал администрирования системы комнат Microsoft Lync для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e8e8d-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="e8e8d-112">Для Skype для бизнеса Server 2015 доступна новая версия веб-портала администрирования LRS, но не следует устанавливать эту версию, если вы не развернули Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e8e8d-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="e8e8d-113">Скачайте <A href="https://go.microsoft.com/fwlink/?linkid=544807">веб-портал администрирования системы комнат Microsoft Lync для Skype для бизнеса Server 2015</A>.</span><span class="sxs-lookup"><span data-stu-id="e8e8d-113">Download the <A href="https://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e8e8d-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="e8e8d-114">In This Section</span></span>

[<span data-ttu-id="e8e8d-115">Настройка среды Lync Server 2013 для веб-портала администрирования системы комнат Lync</span><span class="sxs-lookup"><span data-stu-id="e8e8d-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="e8e8d-116">Установка веб-портала администрирования системы комнат Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8e8d-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="e8e8d-117">Использование веб-портала администрирования системы комнат Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8e8d-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e8e8d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e8e8d-118">See Also</span></span>


[<span data-ttu-id="e8e8d-119">Развертывание конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8e8d-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

