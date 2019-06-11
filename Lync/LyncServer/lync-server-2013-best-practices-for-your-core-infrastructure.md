---
title: 'Lync Server 2013: советы и рекомендации для вашей базовой инфраструктуры'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb6e12f6f2c6d66a0d4f5fed17bc01dc250db5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="8061d-102">Рекомендации для базовой инфраструктуры в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8061d-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8061d-103">_**Тема последнего изменения:** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="8061d-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="8061d-104">Возможно, вы уже выполнили действия по проектированию отказоустойчивости вашей системы, применяя такие меры, как аппаратное резервирование, защита от потери напряжения питания, регулярная установка обновлений системы безопасности и использование средств защиты от вирусов, а также запуск сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="8061d-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="8061d-105">Эти рекомендации повышают эффективность не только вашей инфраструктуры Microsoft Lync Server 2013, но и всей сети.</span><span class="sxs-lookup"><span data-stu-id="8061d-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="8061d-106">Если вы не реализовали эти рекомендации, рекомендуем сделать это перед развертыванием Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8061d-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="8061d-107">Чтобы защитить серверы в среде Lync Server 2013 от случайного или целенаправленнаяового ущерба, которое может привести к простою, примите следующие меры предосторожности.</span><span class="sxs-lookup"><span data-stu-id="8061d-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="8061d-108">Обновляйте свои серверы с помощью обновлений для системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="8061d-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="8061d-109">Подписка на Microsoft Security Notification Service гарантирует получение немедленного уведомления о выпусках бюллетеней безопасности для любого продукта Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8061d-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="8061d-110">Чтобы подписаться на подписку, перейдите на веб- [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)сайт уведомлений Майкрософт по технической безопасности.</span><span class="sxs-lookup"><span data-stu-id="8061d-110">To subscribe, go to the Microsoft Technical Security Notifications website at [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="8061d-111">Убедитесь, что настройка прав доступа выполнена правильно.</span><span class="sxs-lookup"><span data-stu-id="8061d-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="8061d-p103">Ваши серверы должны быть установлены в помещениях, исключающих несанкционированный доступ. Установите надежное антивирусное программное обеспечение на всех ваших серверах. Регулярно обновляйте файлы сигнатур вирусов антивирусного программного обеспечения. Для обеспечения актуальности файлов сигнатур вирусов активируйте функцию автоматического обновления в вашем антивирусном программном обеспечении.</span><span class="sxs-lookup"><span data-stu-id="8061d-p103">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="8061d-116">Мы рекомендуем отключить службы операционной системы Windows Server, которые не требуются на компьютерах, на которых вы установили Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8061d-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="8061d-117">Зашифруйте операционные системы и дисковые устройства, на которых хранятся данные, с помощью полнодисковой системы шифрования, если вы не можете обеспечить постоянное и всестороннее управление серверами, их полную физическую изоляцию, а также надлежащий и безопасный вывод из эксплуатации замененных или отказавших дисковых устройств.</span><span class="sxs-lookup"><span data-stu-id="8061d-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="8061d-118">Отключите на серверах все внешние порты прямого доступа к памяти (DMA), если вы не можете гарантировать жесткий контроль за физическим доступом к серверам.</span><span class="sxs-lookup"><span data-stu-id="8061d-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="8061d-119">С помощью атак посредством прямого доступа к памяти, организовать которые достаточно просто, можно получить доступ к таким важным данным, как закрытые ключи шифрования.</span><span class="sxs-lookup"><span data-stu-id="8061d-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

