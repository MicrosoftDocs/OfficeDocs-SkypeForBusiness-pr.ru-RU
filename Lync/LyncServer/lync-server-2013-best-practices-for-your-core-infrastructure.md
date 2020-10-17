---
title: 'Lync Server 2013: рекомендации для основной инфраструктуры'
description: 'Lync Server 2013: рекомендации для основной инфраструктуры.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0ea7cb9c7685a3b6f7c04146ec5631bbac10fe6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552195"
---
# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="eb79c-103">Рекомендации по основной инфраструктуре в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb79c-103">Best practices for your core infrastructure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb79c-104">_**Последнее изменение темы:** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="eb79c-104">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="eb79c-105">Вы, возможно, уже выполнили действия по проектированию отказоустойчивости в системе, используя такие рекомендации, как обеспечение избыточности оборудования, защита от потерь электроэнергии, регулярное установка обновлений безопасности и антивирусных мер и мониторинг активности сервера.</span><span class="sxs-lookup"><span data-stu-id="eb79c-105">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="eb79c-106">Эти рекомендации имеют не только инфраструктуру Microsoft Lync Server 2013, но и всю сеть.</span><span class="sxs-lookup"><span data-stu-id="eb79c-106">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="eb79c-107">Если вы не реализовали эти рекомендации, рекомендуем сделать это перед развертыванием Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb79c-107">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="eb79c-108">Чтобы защитить серверы в развертывании Lync Server 2013 от случайных или пурпосефулных причин, которые могут привести к простоям, примите следующие меры предосторожности:</span><span class="sxs-lookup"><span data-stu-id="eb79c-108">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="eb79c-109">Обновляйте свои серверы с помощью обновлений для системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="eb79c-109">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="eb79c-110">Подписка на службу уведомлений безопасности Майкрософт помогает убедиться в том, что вы получаете мгновенное уведомление о выпусках бюллетеней по безопасности для любого продукта Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="eb79c-110">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="eb79c-111">Чтобы подписаться, перейдите на веб-сайт уведомлений о технической безопасности Майкрософт по адресу [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202) .</span><span class="sxs-lookup"><span data-stu-id="eb79c-111">To subscribe, go to the Microsoft Technical Security Notifications website at [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="eb79c-112">Убедитесь, что права доступа настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="eb79c-112">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="eb79c-113">Храните серверы в физической среде, которая предотвращает несанкционированный доступ.</span><span class="sxs-lookup"><span data-stu-id="eb79c-113">Keep your servers in a physical environment that prevents unauthorized access.</span></span> <span data-ttu-id="eb79c-114">Убедитесь, что на всех серверах установлено достаточное антивирусное программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="eb79c-114">Ensure that adequate antivirus software is installed on all your servers.</span></span> <span data-ttu-id="eb79c-115">Поддерживайте актуальность этого программного обеспечения установкой самых последних файлов сигнатур вирусов.</span><span class="sxs-lookup"><span data-stu-id="eb79c-115">Keep the software up-to-date with the latest virus signature files.</span></span> <span data-ttu-id="eb79c-116">Используйте функцию автоматического обновления антивирусной программы для поддержания актуальности набора сигнатур вирусов.</span><span class="sxs-lookup"><span data-stu-id="eb79c-116">Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="eb79c-117">Мы рекомендуем отключить службы операционной системы Windows Server, которые не требуются на компьютерах, на которых устанавливается Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb79c-117">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="eb79c-118">Зашифруйте операционные системы и дисковые накопители, в которых данные хранятся с помощью системы шифрования с полным объемом данных, если вы не можете гарантировать постоянный и полный контроль над серверами, общую физическую изоляцию и надлежащую и безопасную списание замененных или неудачных дисков.</span><span class="sxs-lookup"><span data-stu-id="eb79c-118">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="eb79c-119">Отключите все внешние порты прямого доступа к памяти (DMA) сервера, если вы не можете обеспечить очень тщательный контроль над физическим доступом к серверам.</span><span class="sxs-lookup"><span data-stu-id="eb79c-119">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="eb79c-120">Атаки на основе прямого доступа к данным, которые могут быть запущены довольно просто, могут представлять собой очень конфиденциальную информацию, например закрытые ключи шифрования.</span><span class="sxs-lookup"><span data-stu-id="eb79c-120">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

