---
title: 'Lync Server 2013: рекомендации для основной инфраструктуры'
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
ms.openlocfilehash: cd53ac85ec544af58c1f94f7397a030f6b10fdb2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="7b65c-102">Рекомендации по основной инфраструктуре в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b65c-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b65c-103">_**Последнее изменение темы:** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="7b65c-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="7b65c-104">Вы, возможно, уже выполнили действия по проектированию отказоустойчивости в системе, используя такие рекомендации, как обеспечение избыточности оборудования, защита от потерь электроэнергии, регулярное установка обновлений безопасности и антивирусных мер и мониторинг активности сервера.</span><span class="sxs-lookup"><span data-stu-id="7b65c-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="7b65c-105">Эти рекомендации имеют не только инфраструктуру Microsoft Lync Server 2013, но и всю сеть.</span><span class="sxs-lookup"><span data-stu-id="7b65c-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="7b65c-106">Если вы не реализовали эти рекомендации, рекомендуем сделать это перед развертыванием Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b65c-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="7b65c-107">Чтобы защитить серверы в развертывании Lync Server 2013 от случайных или пурпосефулных причин, которые могут привести к простоям, примите следующие меры предосторожности:</span><span class="sxs-lookup"><span data-stu-id="7b65c-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="7b65c-108">Обновляйте свои серверы с помощью обновлений для системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="7b65c-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="7b65c-109">Подписка на службу уведомлений безопасности Майкрософт помогает убедиться в том, что вы получаете мгновенное уведомление о выпусках бюллетеней по безопасности для любого продукта Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7b65c-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="7b65c-110">Чтобы подписаться, перейдите на веб-сайт уведомлений о [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)технической безопасности Майкрософт по адресу.</span><span class="sxs-lookup"><span data-stu-id="7b65c-110">To subscribe, go to the Microsoft Technical Security Notifications website at [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="7b65c-111">Убедитесь, что права доступа настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="7b65c-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="7b65c-112">Храните серверы в физической среде, которая предотвращает несанкционированный доступ.</span><span class="sxs-lookup"><span data-stu-id="7b65c-112">Keep your servers in a physical environment that prevents unauthorized access.</span></span> <span data-ttu-id="7b65c-113">Убедитесь, что на всех серверах установлено достаточное антивирусное программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="7b65c-113">Ensure that adequate antivirus software is installed on all your servers.</span></span> <span data-ttu-id="7b65c-114">Поддерживайте актуальность этого программного обеспечения установкой самых последних файлов сигнатур вирусов.</span><span class="sxs-lookup"><span data-stu-id="7b65c-114">Keep the software up-to-date with the latest virus signature files.</span></span> <span data-ttu-id="7b65c-115">Используйте функцию автоматического обновления антивирусной программы для поддержания актуальности набора сигнатур вирусов.</span><span class="sxs-lookup"><span data-stu-id="7b65c-115">Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="7b65c-116">Мы рекомендуем отключить службы операционной системы Windows Server, которые не требуются на компьютерах, на которых устанавливается Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b65c-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="7b65c-117">Зашифруйте операционные системы и дисковые накопители, в которых данные хранятся с помощью полной системы шифрования, если вы не можете гарантировать постоянный и полный контроль над серверами, общую физическую изоляцию и правильную и безопасную списание замененного или неисправного диска устройства.</span><span class="sxs-lookup"><span data-stu-id="7b65c-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="7b65c-118">Отключите все внешние порты прямого доступа к памяти (DMA) сервера, если вы не можете обеспечить очень тщательный контроль над физическим доступом к серверам.</span><span class="sxs-lookup"><span data-stu-id="7b65c-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="7b65c-119">Атаки на основе прямого доступа к данным, которые могут быть запущены довольно просто, могут представлять собой очень конфиденциальную информацию, например закрытые ключи шифрования.</span><span class="sxs-lookup"><span data-stu-id="7b65c-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

